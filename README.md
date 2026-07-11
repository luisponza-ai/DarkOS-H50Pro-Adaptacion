# DarkOS-H50Pro-Adaptacion

## Descripción del proyecto

Este proyecto documenta el proceso de recuperación, instalación y adaptación de DarkOS en una consola portátil H50 Pro basada en arquitectura RK3326.

El objetivo principal es crear una guía completa y reproducible que permita a otros usuarios comprender el proceso necesario para solucionar problemas de compatibilidad entre el sistema operativo y el hardware de la consola.

---

## Objetivo

El propósito de este proyecto es documentar paso a paso:

- Diagnóstico inicial de la consola.
- Recuperación y análisis de la tarjeta microSD.
- Instalación limpia de DarkOS.
- Configuración del hardware.
- Adaptación de archivos del sistema.
- Modificación y prueba de configuraciones.
- Creación de una instalación estable.

La documentación busca servir como referencia para usuarios que presenten problemas similares con consolas basadas en arquitectura RK3326.

---

## Créditos y proyecto base

Este proyecto utiliza como base el sistema operativo dArkOS desarrollado por Christian Haitian (@christianhaitian).

dArkOS es un proyecto orientado a consolas portátiles retro basado en ArkOS, cuyo desarrollo incluye adaptaciones, configuraciones y mejoras enfocadas en diferentes plataformas de hardware.

El presente repositorio no pretende sustituir ni reclamar la autoría del sistema original. Su objetivo es documentar el proceso de adaptación realizado específicamente para la consola H50 Pro basada en arquitectura RK3326.

Los cambios, pruebas, configuraciones, documentación y archivos generados durante este proceso corresponden únicamente a la adaptación realizada en este proyecto.

Se recomienda consultar siempre el repositorio oficial del proyecto dArkOS para obtener la versión original y conocer sus condiciones de uso.

---

## Hardware utilizado

**Consola:**
- H50 Pro

**Arquitectura:**
- Rockchip RK3326

**Sistema operativo:**
- DarkOS

---

## Problema inicial

El proyecto comenzó después de que una consola H50 Pro dejó de mostrar imagen durante el arranque.

Después de realizar pruebas de diagnóstico se determinó que la tarjeta microSD original presentaba daños que impedían una recuperación completa del sistema.

Antes de perder completamente la tarjeta se realizaron respaldos mediante imagen completa y copia de archivos accesibles.

---

# Entorno de trabajo

Este proyecto utiliza dos sistemas operativos debido a que cada uno cumple con funciones especificas denro del proceso de adaptacion de DarkOS para la consola H50 Pro.

# Windows

Windows es utilizado principalmenta para las tareas relacionadas con herramientas graficas y gestion inicial de medios de almacenamiento. 

Entre las actividades realizadas desde este sistema se encuentran:

-Creacion de respaldos mediante herramientas como Win 32 Disk imager.
-Uso de herramientas especificas para tarjetas microSD
-Preparacion inicial de la tarjeta mediante SD Card Formatter.
-Gestion de archivos accesibles desde particiones compatibles con Windows (EasyROOM, donde se encuentran los emuladores y juegos)

Windows es utilizado en las primeras etapas del proceso debido a la disponibilidad de herramientas especificas para trabajar con tarjetas SD y respaldos de imahenes.

# Linux

Linux es utilizado para las tareas relacionadas con diagnosticos, analisis y modificaciones del sistema. 

Entre las actividades realizadas desde este sistema se encuentran:

- Analisis de partiiones y sisteas de archivos
- Revision de estructura interna de la tarjeta microSD.
- Montaje y exploracion de particiones Linux
- Trabajo con archivos del sistema.
- Modificaciones y compilaciones de archivos relacionados con DTB
- Herramientas de desarrollo y documentacion del proyecto.

Linux permite trabajar con mayor profundidad sobre las estructiras internas del sistema operatio utilizado por la consola.
 
---

# Flujo de trabajo 

Windows 
|
|- Preoaracion inicial de SD
|
|- Respaldos
|
|- Herramientas graficas
|
Terjeta microSD
|
Linux (en mi caso kali)
|
|- Diagnostico
|
|- Modificacion del sistema
|
|- Desarrollo y pruebas

---

## Estado del proyecto

Actualmente el proyecto se encuentra en fase de documentación y reconstrucción desde cero.

Los principales objetivos son:

- Reproducir el proceso completo de instalación.
- Documentar las configuraciones utilizadas.
- Registrar problemas encontrados y soluciones aplicadas.
- Crear una guía útil para otros usuarios.

---

---

## Apoyo al proyecto

La creación de esta documentación requiere tiempo de investigación, pruebas y organización del material.

Si este proyecto resulta útil y deseas apoyar su desarrollo, próximamente se agregarán opciones de colaboración.

---

## Licencias y derechos de autor

Los derechos correspondientes al sistema dArkOS, sus componentes originales y archivos desarrollados por terceros pertenecen a sus respectivos autores.

Este repositorio contiene documentación propia, procedimientos de adaptación, configuraciones de prueba y registros del proceso realizado para la consola H50 Pro.

Antes de redistribuir archivos originales del sistema, se recomienda verificar las condiciones de licencia establecidas por sus respectivos autores.
