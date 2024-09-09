Claro, aquí tienes un conjunto de preguntas tipo test sobre las diferencias entre `sh` (Bourne shell) y `bash` (Bourne Again SHell):

### Preguntas sobre las diferencias entre `sh` y `bash`

1. **¿Cuál de las siguientes afirmaciones es verdadera respecto a `bash` en comparación con `sh`?**
   - A) `bash` es una versión más antigua que `sh`.
   - B) `bash` incluye características de scripting más avanzadas que `sh`.
   - C) `sh` no permite la ejecución de scripts, mientras que `bash` sí.
   - D) Ambas son idénticas en funcionalidad.

   **Respuesta correcta:** B

2. **¿Qué característica de `bash` no está presente en `sh`?**
   - A) Soporte para variables de entorno.
   - B) Edición de línea de comandos con atajos de teclado.
   - C) Capacidad de ejecutar scripts.
   - D) Soporte para comandos internos.

   **Respuesta correcta:** B

3. **¿Cuál es la principal diferencia en la manera de manejar arrays entre `sh` y `bash`?**
   - A) `sh` no soporta arrays.
   - B) `bash` usa corchetes cuadrados para definir arrays, mientras que `sh` usa paréntesis.
   - C) Ambos manejan arrays de la misma manera.
   - D) `sh` requiere la declaración de arrays en un archivo separado.

   **Respuesta correcta:** A

4. **¿Qué comando se usa en `bash` para obtener la última ejecución de un comando en el historial, que no es compatible con `sh`?**
   - A) `!!`
   - B) `!$`
   - C) `history`
   - D) `last`

   **Respuesta correcta:** A

5. **¿Cuál de las siguientes es una forma de declarar una variable en `bash`, que no es válida en `sh`?**
   - A) `var=valor`
   - B) `declare -i var=5`
   - C) `let var=5`
   - D) `set var=value`

   **Respuesta correcta:** B

6. **En `bash`, ¿cómo se puede hacer que un script sea más interactivo mediante la lectura de entrada del usuario?**
   - A) Usando el comando `echo`.
   - B) Usando el comando `read`.
   - C) Usando el comando `input`.
   - D) Usando el comando `input read`.

   **Respuesta correcta:** B

7. **¿Qué opción permite que `bash` ejecute un script en modo "estricto", lo que significa que se detendrá si se encuentra un error?**
   - A) `set -e`
   - B) `set -x`
   - C) `set -u`
   - D) `set -o`

   **Respuesta correcta:** A

8. **¿Cuál de las siguientes características permite a `bash` realizar la expansión de variables de manera más flexible que `sh`?**
   - A) Expansión de comandos.
   - B) Expansión de arrays.
   - C) Expansión de aritmética.
   - D) Todas las anteriores.

   **Respuesta correcta:** D

9. **¿Cuál es el propósito de la opción `set -u` en `bash`?**
   - A) Permitir la expansión de comandos.
   - B) Detener la ejecución si se intenta usar una variable no inicializada.
   - C) Permitir la ejecución de múltiples comandos en una línea.
   - D) Establecer el modo de depuración.

   **Respuesta correcta:** B

10. **¿Qué comando permite a `bash` realizar un bucle for sobre un rango de números, que no se puede hacer directamente en `sh`?**
    - A) `for i in {1..10}; do`
    - B) `for i in [1-10]; do`
    - C) `for i from 1 to 10; do`
    - D) `for i in (1 2 3 4 5 6 7 8 9 10); do`

    **Respuesta correcta:** A

### Resumen

Estas preguntas cubren varias de las diferencias clave entre `sh` y `bash`, incluyendo características de scripting, manejo de variables, y comandos específicos. Puedes utilizarlas en un cuestionario o como material de estudio.