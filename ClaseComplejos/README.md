# Magnitud de Números Complejos (C++)

Este repositorio demuestra un concepto fundamental de la Programación Orientada a Objetos (POO), la **Encapsulación**, comparando el uso de miembros de datos `public` contra `private`.

## 🎯 Propósito del Proyecto

El objetivo es calcular la magnitud (o módulo) de un número complejo $Z = x + yi$ usando la fórmula:

$$|Z| = \sqrt{x^2 + y^2}$$

Ambos archivos implementan una clase `complejo`, pero difieren drásticamente en cómo acceden y modifican sus datos, ilustrando por qué la encapsulación es una buena práctica.

## 📂 Archivos en este Repositorio

A continuación se detalla el enfoque de cada versión.

### 📄 `ClaseComplejoPublic.cpp`

Esta versión utiliza miembros de datos `public`, lo cual **rompe la encapsulación**.

* **Atributos:** `real` e `imag` se declaran explícitamente como `public`.
* **Acceso a Datos:** La función `main()` puede acceder y modificar los atributos del objeto **directamente** (ej. `z1.real = 2;`).
* **Riesgo:** No hay control. Cualquier parte del programa puede modificar los datos, lo que puede llevar a estados inconsistentes o errores difíciles de rastrear.

### 📄 `ClaseComplejoPrivate.cpp`

Esta versión utiliza miembros de datos `private`, lo cual es la **práctica recomendada en POO** para una correcta encapsulación.

* **Atributos:** `real` e `imag` son `private` por defecto (al estar declarados antes de cualquier modificador `public:`).
* **Acceso a Datos:** La función `main()` **no puede** acceder directamente a `z1.real` o `z1.imag`. Si lo intentara, el código no compilaría.
* **Solución:** Se provee un método `public` llamado `davalores()` (conocido como "setter" o "mutator") que actúa como una interfaz controlada para asignar valores a los atributos privados.

## 💡 Comparativa de Enfoques: `public` vs. `private`

| Característica | `ClaseComplejoPublic.cpp` | `ClaseComplejoPrivate.cpp` |
| :--- | :--- | :--- |
| **Modificador de Acceso** | `public` | `private` (por defecto) |
| **Acceso a Atributos** | **Directo** desde `main()` (`z1.real = ...`) | **Indirecto**, vía método "setter" (`z1.davalores(...)`) |
| **Encapsulación** | **Baja**. No hay protección de datos. | **Alta**. Los datos están protegidos del exterior. |
| **Control de Datos** | Nulo. | Controlado (la clase decide cómo se asignan). |
| **Buena Práctica OOP** | ❌ No recomendado. | ✅ **Recomendado**. |

La versión `ClaseComplejoPrivate.cpp` demuestra el pilar de la **Encapsulación**: ocultar el estado interno de un objeto y exponer solo los métodos públicos necesarios para interactuar con él.

## 🚀 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para ambas versiones:

* `complejoPublic`: Ejecutable de `ClaseComplejoPublic.cpp`
* `complejoPrivate`: Ejecutable de `ClaseComplejoPrivate.cpp`