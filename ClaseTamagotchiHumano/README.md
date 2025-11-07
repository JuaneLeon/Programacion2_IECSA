# 👤 Práctica 02 - Clase Persona (C++)
**Universidad Aeronáutica de Querétaro**

Este proyecto demuestra los fundamentos de la Programación Orientada a Objetos (POO) en C++. El reto consiste en construir una clase `Persona` que no solo almacena su nombre, sino que también tiene un comportamiento *aleatorio* y simulado.

---

## 📂 Estructura de Archivos

El proyecto está dividido correctamente en archivos de cabecera e implementación:

* **`Persona.h`**: El archivo de cabecera. Define la **interfaz** de la clase, declarando sus atributos (`private`) y métodos (`public`).
* **`Persona.cpp`**: El archivo de implementación. Contiene el **código** (la lógica) de todos los métodos declarados en `Persona.h`.
* **`main.cpp`**: El punto de entrada del programa. Se encarga de crear el objeto, pedir datos al usuario e iniciar la simulación.

---

## 💡 Conceptos Técnicos Clave

* **Programación Orientada a Objetos (POO):**
    * **Clase:** `Persona` encapsula datos (estado) y comportamiento.
    * **Encapsulación:** El atributo `nombre` es `private` y se accede de forma segura mediante `setNombre()`.
    * **Separación de Archivos:** La interfaz (`.h`) está separada de la implementación (`.cpp`), una práctica esencial para proyectos organizados.
* **Generación Aleatoria:** El programa usa `std::rand()` para tomar decisiones, haciendo que el comportamiento del objeto sea impredecible.
* **Simulación de Tiempo (Hilos):**
    * Se utiliza `std::this_thread::sleep_for` y `std::chrono` para pausar la ejecución.
    * Esto simula acciones que toman tiempo, como `dormir()`, `hablar()` y `contar()`.

---

## 🚀 Flujo de Ejecución

1.  El programa se inicia y crea un objeto `Persona`.
2.  Solicita al usuario que "Ingrese un nombre:".
3.  El nombre se almacena de forma segura en el objeto (`setNombre`).
4.  Se llama al método principal: `persona.decirNombre()`.
5.  El objeto dice "Mi nombre es: [Nombre]".
6.  Se genera un número aleatorio (20-120).
7.  ¡Aquí ocurre la magia! El objeto realiza una acción basada en el número:
    * **Si es 20-59:** Llama a `dormir()` 😴 (Pausa de 2 seg).
    * **Si es 60-99:** Llama a `hablar()` 🗣️ (Pausa de 1 seg).
    * **Si es 100-120:** Llama a `contar()` 🔢 (Pausa de 1 seg).
8.  Al finalizar la acción, el programa se despide con "Adios!".

---

## 📦 Ejecutable

La carpeta `output/` contiene el archivo ejecutable ya compilado:

* `PersonaApp`: Ejecutable del proyecto.