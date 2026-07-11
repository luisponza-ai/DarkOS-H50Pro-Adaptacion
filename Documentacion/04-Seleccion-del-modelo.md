# Selección del modelo

## Objetivo

Seleccionar la configuración de hardware que será utilizada por dArkOSRE durante el primer arranque de la consola H50 Pro.

En la versión utilizada para este proyecto, la selección del dispositivo no se realiza desde la consola, sino desde Windows mediante la herramienta incluida en la partición **BOOT** de la tarjeta microSD.

## Sistema operativo utilizado

**Windows**

## Herramienta utilizada

La imagen de dArkOSRE incluye un script que permite seleccionar el modelo de consola antes de insertar la tarjeta microSD en el dispositivo.

Esta herramienta modifica los archivos de configuración necesarios para que el sistema operativo inicie con los parámetros correspondientes al hardware seleccionado.

## Procedimiento

1. Insertar la tarjeta microSD en el equipo con Windows.
2. Abrir la partición **BOOT**.
3. Ejecutar el script de selección de dispositivo incluido por dArkOSRE.
4. Elegir la configuración correspondiente a la consola.
5. Esperar a que el script finalice la actualización de los archivos de arranque.
6. Extraer la tarjeta de forma segura.
7. Insertar la microSD en la H50 Pro para realizar el primer encendido.

## Configuración utilizada

Durante las pruebas realizadas en este proyecto se utilizó la siguiente configuración:

| Parámetro | Valor                |
| --------- | -------------------- |
| Board     | R36-V12 (2023-08-18) |
| Variant   | 3                    |
| Panel     | 3                    |

Esta configuración fue utilizada como punto de partida para las pruebas de compatibilidad con la consola H50 Pro.

## Observaciones

Aunque dArkOSRE incorpora esta herramienta para facilitar la selección del hardware, la configuración elegida no resolvió completamente la compatibilidad con la pantalla de la H50 Pro.

Por este motivo fue necesario continuar con un proceso de adaptación del sistema, el cual se documenta en los capítulos siguientes.
