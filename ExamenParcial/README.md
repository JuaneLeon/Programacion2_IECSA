# Registro de Aviones con Archivos Binarios (C++)

Este repositorio contiene un proyecto en C++, probablemente de un examen parcial, que demuestra la **gestión de archivos binarios (`fstream`)** en C++. El programa implementa un sistema simple de altas (Create) y consultas (Read) para un registro de aviones, guardando los datos de forma persistente.

## 🎯 Propósito del Proyecto

El objetivo principal es crear una aplicación de consola que permita al usuario:
1.  **Añadir** múltiples registros de aviones a un archivo binario (`aviones.dat`).
2.  **Validar** los datos de entrada, incluyendo la comprobación de números de serie duplicados.
3.  **Leer** y mostrar todos los registros del archivo en una tabla formateada.
4.  **Buscar** un registro específico por su número de serie.

## ✈️ Características Principales

* **Persistencia de Datos:** Toda la información se almacena en el archivo binario `aviones.dat`, permitiendo que los datos sobrevivan después de que el programa se cierra.
* **Validación de N° de Serie:** El programa incluye un método `existeNumeroSerie()` que lee el archivo `aviones.dat` para asegurar que cada nuevo avión tenga un número de serie único.
* **Validación de Datos Lógica:** Se valida que las posiciones y el tiempo sean valores lógicos (ej. `posFinal > posInicial`, `tiempo > 0`).
* **Interfaz de Menú:** Una vez que se termina la captura inicial de datos, el programa muestra un menú para consultar la información.
* **Salida Formateada:** Utiliza `<iomanip>` (`setw`, `left`) para mostrar los registros en una tabla limpia y ordenada.

## 💡 Conceptos Técnicos Demostrados

Este proyecto pone a prueba varios conceptos fundamentales de C++:

* **Programación Orientada a Objetos (POO):** Toda la lógica (manipulación de datos, validación y operaciones de archivo) está encapsulada dentro de la clase `RegVelAvion`.
* **Manejo de Archivos Binarios (`fstream`):**
    * `ofstream(..., ios::binary | ios::app)`: Se utiliza para abrir el archivo en modo binario y de "añadir" (append), lo que permite agregar nuevos registros sin borrar los existentes.
    * `ifstream(..., ios::binary)`: Se usa para leer el archivo en modo binario.
    * `arch.write(reinterpret_cast<char*>(&...))`: Escritura de los bytes crudos de las variables (`int`, `float`) en el archivo.
    * `arch.read(reinterpret_cast<char*>(&...))`: Lectura de los bytes crudos del archivo de vuelta a las variables.
* **Manejo de C-Strings (`cstring`):** El programa utiliza arreglos de `char` (ej. `char MatAvion[7]`) y `strncpy` para manejar los datos de texto, un requisito común en el manejo de registros binarios de tamaño fijo.
* **Acceso Secuencial:** La lectura (`archAccAleatleer`) y la búsqueda (`buscarPorNumeroSerie`) se implementan mediante un **acceso secuencial**, leyendo el archivo registro por registro desde el principio hasta encontrar el dato deseado o llegar al final.

## 🚀 Cómo Funciona

1.  **Compilar y Ejecutar** el programa.
2.  **Fase de Captura:** El programa entra inmediatamente en un bucle `do-while`, pidiendo los datos para el primer avión (N° de Serie, Matrícula, Modelo, etc.).
3.  Continuará pidiendo registros de aviones hasta que el usuario responda 'n' a la pregunta "¿Desea capturar otro avion?".
4.  **Menú Principal:** Una vez que se sale del bucle de captura, aparece el menú de opciones:
    * **1. Ver todos los registros:** Lee `aviones.dat` y muestra la tabla completa.
    * **2. Buscar avion por numero de serie:** Pide un N° de serie y muestra solo ese registro si lo encuentra.
    * **3. Salir:** Termina el programa.

## 📦 Ejecutable

La carpeta `output/` contiene el archivo ejecutable ya compilado:

* `RegAvion`: Ejecutable de `ClaseRegAvion.cpp`