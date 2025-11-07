# Calculadora de Velocidad de Avión (C++)

Este repositorio contiene un proyecto simple en C++ que demuestra dos enfoques diferentes de Programación Orientada a Objetos (POO) para resolver el mismo problema: calcular la velocidad promedio de un avión.

## 🎯 Propósito del Proyecto

El objetivo principal es calcular la velocidad de un avión basándose en su posición inicial, posición final y el tiempo transcurrido, usando la fórmula:

$$v = (posFinal - posInicial) / tiempo$$

Ambos archivos implementan una clase `velAvion`, pero difieren significativamente en cómo manejan la **obtención de datos**, la **validación** y la **creación de objetos (instanciación)**.

## 📂 Archivos en este Repositorio

A continuación se detalla el enfoque de cada versión.

### 📄 `ClaseVelAvionV1.cpp`

Esta versión representa un enfoque donde la lógica de entrada de datos reside principalmente en la función `main()`.

* **Instanciación:** Utiliza un **constructor parametrizado**. Los datos se piden al usuario en `main()` y luego se pasan al constructor para crear el objeto.
* **Validación:** Incluye un método `valida()` simple que se llama *después* de que el objeto ha sido creado.
* **Desventaja:** Si los datos son inválidos, el programa simplemente informa del error pero no vuelve a solicitar la información. La validación es básica (no valida el tiempo).

### 📄 `ClaseVelAvionV2.cpp`

Esta versión implementa un enfoque con **mayor encapsulación**, donde la clase es responsable de gestionar su propio estado, incluyendo la obtención y validación de sus datos.

* **Instanciación:** Utiliza el **constructor por defecto**. Se crea un objeto "vacío" (`velAvion avion02;`).
* **Obtención de Datos:** Se llama a un método `obtenerDatos()` que se encarga de solicitar la información al usuario.
* **Validación:**
    * Utiliza un método `valida()` robusto que revisa todas las entradas (posiciones y tiempo).
    * La validación se implementa dentro de un bucle `do-while` en `obtenerDatos()`.
    * **Característica clave:** El programa no continúa hasta que el usuario introduce datos lógicamente correctos (ej. `posFinal > posInicial`, `tiempo > 0`).
    * Proporciona mensajes de error específicos para cada tipo de dato inválido.

## 💡 Comparativa de Enfoques

| Característica | `ClaseVelAvionV1.cpp` | `ClaseVelAvionV2.cpp` |
| :--- | :--- | :--- |
| **Instanciación** | Constructor parametrizado | Constructor por defecto |
| **Entrada de Datos** | En la función `main()` | Dentro del método `obtenerDatos()` de la clase |
| **Validación** | Básica, después de la creación. | Robusta, **durante** la entrada de datos. |
| **Bucle de Validación** | No tiene. | Sí, usa `do-while` para forzar datos correctos. |
| **Manejo de Errores** | Mensaje genérico ("Datos inválidos"). | Mensajes específicos por cada error. |
| **Encapsulación** | Menor (El `main` "conoce" los datos) | **Mayor** (La clase gestiona su propio estado) |

En general, **`ClaseVelAvionV2.cpp` representa una práctica de POO más sólida** al hacer que la clase sea autónoma y responsable de garantizar que su estado interno sea siempre válido.

## 🚀 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para ambas versiones:

* `avionV1`: Ejecutable de `ClaseVelAvionV1.cpp`
* `avionV2`: Ejecutable de `ClaseVelAvionV2.cpp`