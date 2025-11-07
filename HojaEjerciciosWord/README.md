# 📝 Colección de Ejercicios de C++ (Prácticas de Word)

Este directorio contiene una variada colección de ejercicios prácticos de Programación Orientada a Objetos (POO) en C++. Cada archivo `.cpp` en el directorio raíz es un programa independiente, mientras que las subcarpetas contienen proyectos más complejos y vinculados.

---

## 📄 Ejercicios Individuales (Directorio Raíz)

Estos archivos son programas autocontenidos que demuestran un concepto específico.

### 1. ClaseRectanguloAnchoyAlto.cpp

* **🧩 Concepto Clave:** Encapsulación y Manejo de Excepciones (`try-catch`).
* **Descripción:** Define una clase `Rectangle` que usa `throw invalid_argument` para lanzar un error si las dimensiones no están en el rango válido. El `main` usa un bloque `try-catch` para capturar estos errores.

### 2. ClaseRectanguloCoordenadas.cpp

* **📐 Concepto Clave:** Validación Geométrica Compleja.
* **Descripción:** Una versión avanzada de `Rectangulo` que se construye a partir de cuatro coordenadas. Incluye lógica de validación detallada para asegurar que los puntos formen un rectángulo válido.

### 3. ClaseOperacionesComplejos.cpp

* **🧮 Concepto Clave:** Diseño de Clases y Métodos Estáticos.
* **Descripción:** Implementa una clase `Complejo` para sumar y restar dos números complejos. Utiliza un método `static` como "helper" para validar la entrada de datos.

### 4. ClaseRacional (Suma, Resta, Multiplicación y División)

* **🔢 Concepto Clave:** Aritmética de Clases y Métodos `private` (Helpers).
* **Descripción:** Dos archivos (`...SumayResta.cpp` y `...MultiplicacionyDivision.cpp`) que definen una clase `Racional`.
* **Destacado:** Utilizan un método `private void reducirFraccion()` para simplificar automáticamente el resultado de cada operación.

### 5. ClaseDesensoAvion.cpp

* **✈️ Concepto Clave:** Aplicación de Dominio Específico (Aeronáutica).
* **Descripción:** Un programa simple que encapsula cálculos aeronáuticos para un piloto, como la distancia de descenso (regla 3-a-1) y la tasa de descenso requerida.

### 6. ClaseSalarioAviacion.cpp

* ** polymorphic Concepto Clave:** Polimorfismo y Clases Abstractas.
* **Descripción:** Un ejemplo perfecto de Polimorfismo. `Empleado` es una clase base abstracta con un método virtual puro. Las clases derivadas (con/sin horas extras) implementan el cálculo de salario de forma diferente.

---

## 📁 Sub-proyecto: ClaseAnimales

Esta carpeta contiene un proyecto de POO completo y vinculado, compuesto por múltiples archivos, que demuestra la **Herencia** y el **Polimorfismo**.

### Conceptos Clave del Proyecto:

* **Herencia (Inheritance):** Las clases `Mamifero`, `Ave`, e `Insecto` heredan de una clase base común `Animal`.
* **Clase Base Abstracta (Abstract Base Class):** `Animal` es una clase abstracta porque define al menos una **función virtual pura** (`virtual std::string DefinirClaseAnimalEres() = 0;`). Esto obliga a todas las clases derivadas a implementar este método.
* **Polimorfismo (Polymorphism):** El `main.cpp` crea objetos de las clases derivadas pero los almacena en un puntero de la clase base (`Animal* animal = nullptr;`). Esto permite tratar a todos los animales de forma genérica.
* **RTTI (`dynamic_cast`):** La función `mostrarInformacionAnimal` usa `dynamic_cast` (Run-Time Type Information) para identificar el tipo real del objeto en tiempo de ejecución (ej. `dynamic_cast<Ave*>(animal)`) y así poder acceder a métodos específicos de esa clase (como `getColorPlumaje()`).
* **Memoria Dinámica:** El programa usa `new` para crear los objetos en el *heap* y `delete` para liberarlos.

### Desglose de Archivos del Proyecto:

* **`Animal.h`**: Define la interfaz de la clase base abstracta `Animal`.
* **`Mamifero.h`**: Define la clase derivada `Mamifero`.
* **`Ave.h`**: Define la clase derivada `Ave`, añadiendo atributos propios como `colorPlumaje`.
* **`Insecto.h`**: Define la clase derivada `Insecto`, añadiendo el atributo `vuela`.
* **`main.cpp`**: El programa principal (driver) que muestra el menú al usuario y crea los objetos de forma polimórfica.

---

## 📦 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para cada ejercicio.