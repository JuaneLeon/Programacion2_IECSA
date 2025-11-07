# 📅 Calculadora de Día de la Semana (C++)

Este proyecto es una implementación en C++ del **Algoritmo de Congruencia de Zeller**, utilizado para determinar el día de la semana (lunes, martes, etc.) de cualquier fecha específica.

---

## 📂 Estructura de Archivos

El proyecto está organizado en tres archivos, siguiendo las buenas prácticas de la Programación Orientada a Objetos (POO):

* **`Fecha.h`**: El archivo de cabecera. Define la **interfaz** de la clase `Fecha`, declarando sus atributos privados (`dia`, `mes`, `ssaa`) y sus métodos públicos.
* **`Fecha.cpp`**: El archivo de implementación. Contiene la **lógica** de los métodos de la clase, incluyendo el constructor y, lo más importante, el algoritmo `diaSemana()`.
* **`main.cpp`**: El programa principal (driver). Se encarga de pedir la fecha al usuario, crear el objeto `Fecha` y mostrar el resultado en un formato legible (ej. "Lunes").

---

## 💡 Concepto Técnico: Congruencia de Zeller

El corazón de este programa es el método `diaSemana()`, que implementa una variación del **Algoritmo de Congruencia de Zeller**.

Este es un algoritmo matemático diseñado para tomar un día (`dia`), mes (`mes`) y año (`ssaa`) y, a través de una serie de cálculos aritméticos y operaciones módulo, devolver un número entero (en este caso, 0 para Domingo, 1 para Lunes, ..., 6 para Sábado).

La implementación en `Fecha.cpp` maneja la lógica del algoritmo, incluyendo el ajuste necesario para los meses de enero y febrero (que se tratan como los meses 13 y 14 del año anterior).

---

## 🚀 Flujo de Ejecución

1.  El `main.cpp` solicita al usuario que ingrese el día, mes y año.
2.  Estos valores se pasan al **constructor** de la clase `Fecha` para crear un nuevo objeto `f`.
3.  Se llama al método `f.diaSemana()`, el cual ejecuta el Algoritmo de Zeller.
4.  El método devuelve un número entero entre 0 y 6.
5.  El `main.cpp` utiliza una estructura `switch` para "traducir" este número al nombre del día correspondiente y lo imprime en la consola.

---

## 📦 Ejecutable

La carpeta `output/` contiene el archivo ejecutable ya compilado:

* `DiaSemana`: Ejecutable del proyecto.