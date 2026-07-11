# Instalación de dArkOSRE

## Objetivo

Grabar la imagen del sistema operativo dArkOSRE sobre una tarjeta microSD previamente preparada, obteniendo una instalación base lista para su primer arranque en la consola H50 Pro.

## Sistema operativo utilizado

**Windows**

## Herramientas utilizadas

| Herramienta | Versión   | Función                                                             |
| ----------- | --------- | ------------------------------------------------------------------- |
| Rufus       | 4.14.2377 | Escritura de la imagen del sistema operativo en la tarjeta microSD. |

## Imagen utilizada

| Parámetro         | Valor                          |
| ----------------- | ------------------------------ |
| Sistema operativo | dArkOSRE                       |
| Variante          | R36 (Debian Trixie)            |
| Versión           | 03/08/2026                     |
| Archivo utilizado | `dArkOSRE_R36_trixie_03082026` |

## Procedimiento

1. Se ejecutó Rufus desde Windows.
2. Se seleccionó la tarjeta microSD previamente preparada.
3. Se eligió la imagen `dArkOSRE_R36_trixie_03082026`.
4. Se inició el proceso de escritura de la imagen.
5. Se esperó a que Rufus finalizara la copia y verificara correctamente la información escrita.

## Resultado

La imagen de dArkOSRE fue instalada correctamente en la tarjeta microSD, quedando lista para realizar el primer arranque en la consola H50 Pro.

Con esta etapa finaliza la preparación del medio de instalación. Las siguientes fases del proyecto se enfocan en el primer inicio del sistema, la selección del modelo de la consola y el proceso de adaptación necesario para lograr la compatibilidad completa con la H50 Pro.
