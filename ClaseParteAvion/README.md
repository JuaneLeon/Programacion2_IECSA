# Gestión de Partes de Avión (C++)

Este repositorio demuestra uno de los pilares fundamentales de la Programación Orientada a Objetos (POO): la **Encapsulación**. Compara dos versiones de una clase `Parte` para ilustrar la diferencia crítica entre usar miembros de datos `public` y `private`.

## 🎯 Propósito del Proyecto

El objetivo del programa es capturar información sobre una parte de un avión (clave, nombre, vida útil y tiempo de uso) y calcular el tiempo de vida restante.

El programa incluye validaciones robustas para asegurar que:
* La vida útil no exceda los 10 años.
* El tiempo de uso sea menor que la vida útil.

## 📂 Archivos en este Repositorio

La diferencia clave entre los dos archivos es el modificador de acceso usado para los atributos de la clase.

### 📄 `ClaseParteAvionV1.cpp` (Enfoque `public` - Mala Práctica)

Esta versión declara todos sus miembros de datos (atributos) como `public`.

* **Atributos:** `clave`, `nomParte`, `vidaUtil`, etc., son `public`.
* **Encapsulación:** **Nula.** No existe protección de datos.
* **Riesgo:** Cualquier parte del programa (como la función `main()`) puede modificar directamente los atributos del objeto. Por ejemplo, se podría escribir `partavion.TiempoRest = -100;` después de calcularlo, corrompiendo el estado del objeto y rompiendo la lógica del programa.

### 📄 `ClaseParteAvionV2.cpp` (Enfoque `private` - Buena Práctica)

Esta versión declara todos sus miembros de datos como `private`, lo cual es la forma correcta y estándar de implementar una clase en POO.

* **Atributos:** `clave`, `nomParte`, `vidaUtil`, etc., son `private`.
* **Encapsulación:** **Alta.** Los datos están protegidos y ocultos del exterior.
* **Acceso:** La única forma de interactuar con los datos es a través de los métodos `public` que la clase proporciona (como `CargarInformacion()`, `tiempoRestante()`, y los métodos `get`/`set`).
* **Integridad de Datos:** La función `main()` **no puede** modificar directamente `partavion.TiempoRest`. El valor solo puede ser asignado por el propio método de la clase `tiempoRestante()`, asegurando que el cálculo sea siempre el correcto.

## 💡 Comparativa de Enfoques: `public` vs. `private`

| Característica | `ClaseParteAvionV1.cpp` | `ClaseParteAvionV2.cpp` |
| :--- | :--- | :--- |
| **Acceso a Datos** | `public` | `private` |
| **Encapsulación** | **Nula (Mala Práctica)** | **Alta (Buena Práctica)** |
| **Protección de Datos** | Ninguna. `main()` puede corromper los datos. | Total. Los datos están protegidos. |
| **Integridad** | Baja (Insegura) | **Alta (Segura)** |
| **Métodos `get`/`set`** | No son necesarios (pero es mala idea) | **Incluidos** (Interfaz de acceso controlado) |

Es importante notar que la función `main()` es **idéntica en ambos archivos** y funciona en los dos casos. Sin embargo, la versión `V2` (privada) es **infinitamente más segura y robusta**, ya que garantiza que el objeto no puede ser puesto en un estado inválido desde el exterior.

## 🚀 Ejecutables

La carpeta `output/` contiene los archivos ejecutables ya compilados para ambas versiones:

* `parteAvionV1`: Ejecutable de `ClaseParteAvionV1.cpp`
* `parteAvionV2`: Ejecutable de `ClaseParteAvionV2.cpp`