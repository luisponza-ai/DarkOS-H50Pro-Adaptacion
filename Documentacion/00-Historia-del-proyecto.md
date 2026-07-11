# Adaptacion de DarkOS para consola H50 Pro

## Introduccion

Este proyeto tiene como objetivo la adaptacion y documentacion del proceso llevado a cabo para la configuracion de DarkOS en una consola H50 Pro la cual se basa en la arquitectura con la que se contadaba RK3326.

La finalidad es obtener un sistema el cual sea funcional, estable y reproducible, dejando registros de todas las modificaciones realizadas para facilitar futuras instalaciones y servir como una referencia para otros usuarios con el mismo hardware o similares.

## Inicio del proyecto

En un principio la consola H50 Pro dejo de dar imagen, lo cual llevo a realizar diagnosticos. Se determino que la memoria SD original presento daños, asi como la estructura de la tarjeta quedo afectada y no fue posible su reconstruccion. Antes de volverse inutilizable se realizo una copia de seguridad de las dos particiones que es factible observar en Windows. 

Con el paso del tiempo este dejo de ser un problema de recuperacion en uno de reinstacion completa. Se buscaron imagenes que pudiesen ser compatibles, sin tener una solucion real. Gracias a la investigacion se llego a ArkOS el cual es el sistema operativo utilizado en este tipo de consolas. Sin embargo, en dicha investigacion se encuntra el sistema DarkOS siendo la continuacion de ArkOs, el cual presenta mejoras de compatibilidad con consolas estilo Retro.

Los porblemas de adaptacion comensaron por la compatibilidad, iferentes interfaces probadas, el modelo de la consola, llevando a modificaciones en los archivos DTB. Se realizarn pruebas hasta conseguir una configuracion estable. 

