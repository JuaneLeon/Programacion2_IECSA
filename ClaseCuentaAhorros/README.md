# Calculadora de Interés de Cuenta de Ahorros (C++)

Este repositorio demuestra la implementación de una clase `CuentaAhorros` en C++ para calcular el interés mensual de un ahorrador, siguiendo buenas prácticas de Programación Orientada a Objetos (POO).

## 🎯 Propósito del Proyecto

El objetivo es modelar una cuenta de ahorros que almacena un saldo y una tasa de interés anual. La clase debe ser capaz de calcular el interés mensual, actualizar el saldo con ese interés y devolver el monto del interés ganado.

## 📂 Archivos en este Repositorio

* `CuentaAhorrosVpublic.cpp`
* `CuentaAhorrosVPrivate.cpp`

### Nota Importante sobre los Archivos

Ambos archivos (`Vpublic` y `VPrivate`) contienen **exactamente el mismo código**.

A pesar de la diferencia en los nombres, las dos versiones implementan correctamente la **encapsulación**, usando atributos `private` (`saldoAhorro` y `tasaInteresAnual`). No existe una versión que exponga los datos como `public`.

## 💡 Análisis del Código

El código en ambos archivos utiliza un diseño de clase encapsulado y robusto.

* **Clase:** `CuentaAhorros`
* **Encapsulación:** Los atributos clave (`saldoAhorro` y `tasaInteresAnual`) se declaran como `private`. Esto protege los datos y evita que se modifiquen accidentalmente desde fuera de la clase.
* **Constructor (`CuentaAhorros()`):**
    * Se utiliza el constructor por defecto para gestionar la inicialización del objeto.
    * El propio constructor se encarga de **solicitar y validar** los datos del usuario (saldo y tasa).
    * Incluye un bucle `do-while` para asegurar que la tasa de interés introducida sea válida (entre 0 y 100) antes de continuar.
* **Método `calcularInteresMensual()`:**
    * Este método calcula el interés mensual basado en el saldo y la tasa anual (Fórmula: `(saldo * tasa) / 1200`).
    * **Modifica el estado (Mutator):** Es importante notar que este método no solo *calcula* el interés, sino que también *actualiza* el `saldoAhorro` interno, sumándole el interés ganado.
* **Función `main()`:**
    * Demuestra cómo crear múltiples instancias independientes de la clase (`ahorrador1`, `ahorrador2`).
    * Al crear cada objeto, el constructor se ejecuta automáticamente, pidiendo los datos para cada ahorrador por separado.

## 🚀 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para ambas versiones (que, en este caso, son idénticas en funcionalidad):

* `cuentaPublic`: Ejecutable de `CuentaAhorrosVpublic.cpp`
* `cuentaPrivate`: Ejecutable de `CuentaAhorrosVPrivate.cpp`