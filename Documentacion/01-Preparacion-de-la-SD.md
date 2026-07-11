## Preparacion de la tarjeta SD

# Objetivo
Esta etapa tiene como finalidad preparar un tarjeta microSD limpia para realizar una instacion nueva de DarkOS en una consolo H50 Pro.

Debido a que la tarjeta original presento daños que impidieron recuperar completamente el sistema anterior, se decidio realizar una instalacion desde cero utilizando una nueva preparacion del medio de almacenamiento. 

# Estado inicial de la tarjeta

Antes de inicial el proceo de preparacion, se realiza un respaldo de la informacion disponible en la tarjeta utilizada para pruebas. 

El respaldo debe incluir

-Copia de la particion BOOT
-Conservacion de archivos disponibles para futuras comparaciones.
-Verificacion del contenido antes de proceder con la limpieza de la tarjeta

La tarjeta utilizada en este proyecto corresponde a una micro SD: 

Capacidad: 125GB
Uso previsto: Instalacion de DarkOS para H50 PRO.

--------------------------------------------------------------------------

# Herramientas utilizadas

Para realizar la limpieza inicial de la tarjeta se utilizo:

SD Card Formatter

Esta herramienta fue seleccionada por que esta diseñada especificamente para trabajar con tarjetas SD y permite preparar correctamente el medio antrs  de realizar una nueva instalacion. 

(Esta herramienta se encuentra en Windows)

--------------------------------------------------------------------------

# Proceso realizado 

1.- Conectar la tarjeta microSD al equipo
2.- Verificar que la unidad corresponde a la tarjeta destinada par ala instalacion
3.- Ejecutar SD Card Formatter.
4.- Realizar el formateo de la tarjeta 
5.- Confirmar que la tarjeta quedara disponible para recibir una nueva imagen del sistema.

--------------------------------------------------------------------------

# Resultado

El proceso de formateo finaliza correctamente, dejando la tarjeta preparada para continuar con la instalacion de DarkOS

El siguiente paso del proyecto sera la escritura de la imagen del sistema operativo en la tarjeta microSD y las pruebas de arranque en la consola H50 Pro. 

