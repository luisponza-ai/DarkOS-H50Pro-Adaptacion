# Investigación y adaptación del DTB

## Objetivo

Documentar el proceso de investigación que permitió identificar la causa del problema de visualización presentado en la consola H50 Pro al utilizar dArkOSRE y desarrollar una solución mediante la adaptación del archivo Device Tree Blob (DTB).

A diferencia de una instalación convencional, donde únicamente se utiliza una imagen preparada para un modelo específico, en este caso fue necesario realizar un proceso de análisis, comparación y modificación del hardware descrito dentro del DTB para lograr la compatibilidad entre el sistema operativo y la pantalla integrada de la consola.

Este capítulo describe el razonamiento técnico seguido durante la investigación, las pruebas realizadas, las herramientas utilizadas, los archivos analizados y los cambios efectuados hasta obtener una configuración funcional.

---

# El inicio de la investigación

Después del primer arranque fue posible comprobar que dArkOSRE iniciaba correctamente en la consola H50 Pro. El sistema operativo completaba el proceso de carga; sin embargo, la imagen aparecía dividida horizontalmente, haciendo imposible utilizar la consola con normalidad.

Inicialmente se consideró que el problema podía estar relacionado con la selección del modelo, una incompatibilidad general del sistema o diferencias entre variantes de hardware. No obstante, el hecho de que el sistema arrancara correctamente indicaba que la mayor parte del hardware estaba siendo reconocida.

Esto permitió dirigir la investigación hacia la configuración de la pantalla definida dentro del Device Tree Blob (DTB).

---

# Comprendiendo el funcionamiento del DTB

Antes de modificar cualquier archivo fue necesario comprender qué era un DTB y cuál era su función.

El Device Tree Blob es un archivo binario utilizado por Linux para describir el hardware del dispositivo. En él se define la configuración del procesador, memoria, pantalla, audio, botones, buses de comunicación y otros componentes necesarios para que el kernel inicialice correctamente el sistema.

Debido a la escasa documentación disponible sobre la H50 Pro, se consultó documentación del proyecto Device Tree, del kernel de Linux, repositorios relacionados con ArkOS y dArkOS, además de experiencias compartidas por la comunidad para dispositivos basados en RK3326.

El objetivo no era copiar una solución existente, sino comprender la estructura del DTB para localizar la sección responsable del problema de la pantalla.

---

# Identificación del panel

Durante la investigación se identificó que el panel utilizado por la consola estaba definido mediante:

```dts
compatible = "sitronix,st7703", "simple-panel-dsi";
```

Esta referencia permitió identificar que el controlador de pantalla correspondía a un panel Sitronix ST7703 conectado mediante interfaz MIPI-DSI.

---

# Primeras pruebas

Antes de modificar el DTB se realizaron diversas pruebas:

- Instalación de diferentes imágenes compatibles con RK3326.
- Selección de distintos modelos disponibles en dArkOSRE.
- Sustitución de archivos DTB completos.
- Pruebas con distintas configuraciones de panel.

Ninguna de estas pruebas resolvió completamente la pantalla dividida, por lo que fue necesario analizar el contenido interno del DTB.

---

# Descompilación del DTB

Los archivos DTB fueron convertidos a formato DTS mediante:

```bash
dtc -I dtb -O dts archivo.dtb -o archivo.dts
```

Esto permitió inspeccionar y modificar la estructura interna del Device Tree.

Archivos utilizados:

- [rf3536k4ka.dtb](../DTB/Original/rf3536k4ka.dtb)
- [rk3326-r36s-linuxa.dtb](../DTB/darkOS/rk3326-r36s-linuxa.dtb)
- [original.dts](../DTB/dts/original.dts)
- [darkos.dts](../DTB/dts/darkos.dts)
- [darkos_pruebas.dts](../DTB/dts/darkos_pruebas.dts)

---

# Comparación de archivos

Las comparaciones se realizaron principalmente con:

```bash
diff -u archivo1.dts archivo2.dts
```

y para filtrar únicamente información relacionada con la pantalla:

```bash
diff -u original.dts darkos.dts | grep -i -E "display|panel|timing|resolution|hactive|vactive|clock|lane|dsi"
```

También se conservaron los archivos de comparación generados durante la investigación:

- [cambios.patch](../Comparaciones/cambios.patch)
- [comparacion_h50_darkos.patch](../Comparaciones/comparacion_h50_darkos.patch)
- [h50-vs-darkos.patch](../Comparaciones/h50-vs-darkos.patch)

El análisis mostró diferencias en numerosas secciones del Device Tree, por lo que se decidió modificar únicamente un grupo de parámetros en cada prueba para poder identificar exactamente cuál producía cambios en el comportamiento de la consola.

---

# Descubrimiento de la sección display-timings

Después de numerosas pruebas se determinó que el problema estaba relacionado con la configuración de sincronización de la pantalla.

La sección clave fue:

```text
display-timings
```

Dentro de ella se encuentran parámetros como:

- clock-frequency
- hactive
- vactive
- hfront-porch
- hback-porch
- vfront-porch
- vback-porch
- hsync-len
- vsync-len

En lugar de modificar todo el DTB, las pruebas comenzaron a concentrarse únicamente en esta sección.

La modificación más importante consistió en adaptar los parámetros de sincronización utilizados por el panel, pasando de la configuración original de 320×240 a la utilizada por la pantalla de la H50 Pro.

Además de modificar `hactive` y `vactive`, también fue necesario ajustar los parámetros de sincronización horizontal y vertical, así como la frecuencia del reloj de píxeles.

---

# Compilación del DTB

Una vez realizadas las modificaciones, el archivo DTS fue compilado nuevamente mediante:

```bash
dtc -I dts -O dtb darkos_pruebas.dts -o nuevo.dtb
```

El archivo generado fue:

- [nuevo.dtb](../DTB/Compilados/nuevo.dtb)

Posteriormente fue copiado a la tarjeta SD para validar su funcionamiento directamente en la consola.

---

# Resultado obtenido

Las pruebas demostraron que la incompatibilidad no se encontraba en todo el DTB, sino únicamente en la configuración utilizada para inicializar el panel.

La modificación de la sección `display-timings`, junto con los ajustes realizados durante la investigación, permitió obtener un arranque funcional conservando intacta la configuración del resto del hardware.

---

# Conclusiones

La adaptación del DTB permitió comprender el funcionamiento del Device Tree en dispositivos basados en Rockchip y desarrollar una metodología de trabajo para futuras adaptaciones.

El proceso seguido fue:

1. Obtener los DTB originales.
2. Descompilar a DTS.
3. Comparar configuraciones.
4. Identificar diferencias relevantes.
5. Modificar únicamente una sección por prueba.
6. Compilar nuevamente el DTB.
7. Validar el resultado en hardware real.

La solución final fue el resultado de un proceso iterativo de investigación, comparación y pruebas controladas, más que de la sustitución directa de archivos provenientes de otros dispositivos.
