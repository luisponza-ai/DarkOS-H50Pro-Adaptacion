# Primer arranque

## Objetivo

Verificar el comportamiento de la consola H50 Pro durante el primer inicio de dArkOSRE después de grabar la imagen y seleccionar el modelo correspondiente.

## Sistema utilizado

* Consola H50 Pro
* Imagen: `dArkOSRE_R36_trixie_03082026`

## Procedimiento

1. Retirar la tarjeta microSD del equipo con Windows de forma segura.
2. Insertar la microSD en la consola H50 Pro.
3. Encender la consola.
4. Esperar a que finalice el proceso de configuración inicial de dArkOSRE.

## Comportamiento observado

Durante el primer arranque se observó la siguiente secuencia:

1. Al presionar el botón de encendido se iluminó el LED rojo de la consola.
2. Aproximadamente un minuto después apareció la primera imagen del sistema.
3. La pantalla volvió a negro mientras continuaba el proceso de carga.
4. Se ejecutó el proceso **First Boot** de dArkOSRE.
5. Durante este proceso la imagen comenzó a mostrarse dividida horizontalmente.
6. La pantalla volvió a apagarse momentáneamente mientras el sistema continuaba con la configuración inicial.
7. Posteriormente apareció el mensaje **Welcome to dArkOS**.
8. Finalmente se inició la interfaz principal de EmulationStation.

## Resultado

El sistema operativo inició correctamente y completó el proceso de configuración inicial sin presentar errores durante el arranque.

Sin embargo, la imagen permaneció dividida horizontalmente, impidiendo una visualización correcta de la interfaz.

## Conclusión

El primer arranque permitió comprobar que la instalación de dArkOSRE fue exitosa y que el sistema era capaz de iniciar correctamente en la H50 Pro.

El problema observado no impedía el inicio del sistema, por lo que la investigación se orientó hacia la compatibilidad del hardware, particularmente la configuración del panel de la pantalla definida en el archivo Device Tree (DTB).

La investigación realizada para identificar y corregir este problema se documenta en el siguiente capítulo.
