# Requisitos y herramientas

## Objetivo

Definir los elementos necesarios para llevar a cabo la adaptación de dArkOSRE en una consola H50 Pro.

Este documento describe el hardware, software y herramientas utilizadas durante el desarrollo del proyecto, indicando el sistema operativo desde el cual se ejecuta cada una de ellas.

---

# Hardware utilizado

## Consola objetivo

| Elemento                | Descripción            |
| ----------------------- | ---------------------- |
| Modelo                  | H50 Pro                |
| Arquitectura            | RK3326                 |
| Tipo de dispositivo     | Consola portátil retro |
| Medio de almacenamiento | Tarjeta microSD        |

## Equipo de trabajo

Para el desarrollo del proyecto se utilizó un equipo de cómputo con capacidad para trabajar con imágenes de sistemas operativos, edición de archivos de configuración y control de versiones.

---

# Sistemas operativos utilizados

Durante el proyecto se utilizaron dos sistemas operativos debido a que cada uno cumple una función específica dentro del proceso.

## Windows

Utilizado principalmente para:

* Preparación de la tarjeta microSD.
* Formateo del medio de almacenamiento.
* Grabación de la imagen de dArkOSRE.
* Selección inicial del modelo mediante las herramientas incluidas en la partición BOOT.

## Kali GNU/Linux

Utilizado para:

* Análisis del sistema.
* Modificación de archivos de configuración.
* Trabajo con archivos DTB.
* Gestión del repositorio mediante Git.
* Documentación técnica del proyecto.

Versión utilizada:

```
Kali GNU/Linux Rolling 2026.1
```

---

# Software utilizado

| Software          | Versión   | Sistema    | Uso                                          |
| ----------------- | --------- | ---------- | -------------------------------------------- |
| SD Card Formatter | 5.0.3     | Windows    | Preparación inicial de la tarjeta microSD    |
| Rufus             | 4.14.2377 | Windows    | Escritura de la imagen del sistema operativo |
| Git               | 2.53.0    | Kali Linux | Control de versiones                         |
| GitHub            | —         | Web        | Almacenamiento y seguimiento del proyecto    |

---

# Imagen base utilizada

| Parámetro | Valor                          |
| --------- | ------------------------------ |
| Sistema   | dArkOSRE                       |
| Variante  | R36 (Debian Trixie)            |
| Versión   | 03/08/2026                     |
| Archivo   | `dArkOSRE_R36_trixie_03082026` |

---

# Consideraciones

Este proyecto utiliza diferentes sistemas operativos debido a las características del hardware y las herramientas disponibles.

Aunque dArkOSRE incorpora herramientas para facilitar la selección del dispositivo, la adaptación específica de la H50 Pro requiere procesos adicionales de análisis y modificación, los cuales serán documentados en las siguientes etapas del proyecto.
