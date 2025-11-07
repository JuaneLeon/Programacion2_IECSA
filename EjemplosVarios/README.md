# 🗂️ Colección de Ejemplos de POO en C++

Este directorio contiene una colección de archivos C++ independientes, cada uno diseñado para demostrar un concepto específico de la Programación Orientada a Objetos (POO).

---

## 📄 Archivos de Ejemplo

A continuación se describe cada programa individualmente.

### 1. EjemploConstructoryDestructor.cpp

* **Concepto Clave:** Constructor y Destructor (Ciclo de Vida del Objeto).
* **Descripción:** Este programa es un ejemplo claro de cómo funcionan los **constructores** y **destructores**. La clase `pareja` tiene un constructor parametrizado (`pareja(int a2, int b2)`) que se llama al crear un objeto, y un destructor (`~pareja()`) que se llama automáticamente cuando el objeto sale del ámbito (al final de `main`).
* **Observa:** Las impresiones en consola (`cout`) permiten ver exactamente cuándo se crea y se destruye cada objeto.

---

### 2. Polimorfismo01.cpp

* **Concepto Clave:** Polimorfismo Básico y Clases Abstractas.
* **Descripción:** Este es un ejemplo fundamental de polimorfismo.
    * **Clase Abstracta:** `Figura` actúa como una "plantilla" y no puede ser instanciada por sí misma, ya que contiene *funciones virtuales puras* (ej. `virtual float area()=0;`).
    * **Clases Derivadas:** `Rectangulo` y `Triangulo` *heredan* de `Figura` y están obligadas a implementar sus propias versiones de `area()` y `perimetro()`.
    * **La Magia Polimórfica:** En `main()`, un puntero de la clase base (`Figura *fig`) puede apuntar a objetos de las clases derivadas. Cuando `fig->captura()` llama internamente a `area()`, C++ sabe automáticamente si debe ejecutar la versión del rectángulo o la del triángulo.

---

### 3. Polimorfismo02.cpp

* **Concepto Clave:** Polimorfismo Aplicado con Menú Interactivo.
* **Descripción:** Este archivo expande el concepto de `Polimorfismo01.cpp` y lo hace más robusto.
    * **Expansión:** Se añade una nueva clase, `Circulo`, que también hereda de la clase base abstracta `Poligono`.
    * **Interactivo:** El `main()` es un menú de usuario (`do-while`) que permite al usuario elegir qué figura desea calcular.
    * **Puntero Único:** Un solo puntero (`Poligono *fig`) se reutiliza. Dependiendo de la elección (1, 2, o 3), el puntero se asigna a un rectángulo, un triángulo o un círculo. La llamada `fig->captura()` funciona para los tres, demostrando el poder del polimorfismo para escribir código genérico.

---

## 📦 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para cada ejemplo:

* `constructor`: Ejecutable de `EjemploConstructoryDestructor.cpp`
* `polimorfismo01`: Ejecutable de `Polimorfismo01.cpp`
* `polimorfismo02`: Ejecutable de `Polimorfismo02.cpp`