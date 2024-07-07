# Gestión de archivos en Linux

La gestión de archivos en Linux desde la consola es una habilidad esencial para cualquier usuario o administrador de sistemas. A continuación, se presentan algunos comandos básicos y avanzados para manejar archivos y directorios en Linux, junto con ejemplos y enlaces de interés.

### Comandos Básicos

1. **`ls`**: Lista el contenido de un directorio.
   ```bash
   ls                # Lista archivos y carpetas en el directorio actual
   ls -l             # Lista con detalles (permisos, propietario, tamaño, etc.)
   ls -a             # Incluye archivos ocultos (que comienzan con .)
   ls -lh            # Lista con detalles y tamaños legibles
   ```

2. **`cd`**: Cambia el directorio actual.
   ```bash
   cd /ruta/al/directorio      # Cambia al directorio especificado
   cd ..                       # Sube un nivel en la jerarquía de directorios
   cd                          # Cambia al directorio home del usuario
   ```

3. **`pwd`**: Muestra la ruta del directorio actual.
   ```bash
   pwd
   ```

4. **`mkdir`**: Crea un nuevo directorio.
   ```bash
   mkdir nuevo_directorio
   mkdir -p ruta/al/nuevo_directorio  # Crea directorios anidados
   ```

5. **`rmdir`**: Elimina un directorio vacío.
   ```bash
   rmdir directorio_vacio
   ```

6. **`rm`**: Elimina archivos o directorios.
   ```bash
   rm archivo                # Elimina un archivo
   rm -r directorio          # Elimina un directorio y su contenido recursivamente
   rm -f archivo             # Fuerza la eliminación sin pedir confirmación
   rm -rf directorio         # Combina recursivo y forzado
   ```

7. **`cp`**: Copia archivos o directorios.
   ```bash
   cp archivo destino               # Copia un archivo a destino
   cp -r directorio destino         # Copia un directorio y su contenido a destino
   cp archivo1 archivo2 /ruta/al/destino  # Copia múltiples archivos a destino
   ```

8. **`mv`**: Mueve o renombra archivos o directorios.
   ```bash
   mv archivo nuevo_nombre             # Renombra un archivo
   mv archivo /ruta/al/destino         # Mueve un archivo a destino
   mv directorio /ruta/al/destino      # Mueve un directorio a destino
   ```

9. **`touch`**: Crea archivos vacíos o actualiza la fecha de modificación.
   ```bash
   touch nuevo_archivo
   ```

10. **`cat`**: Muestra el contenido de un archivo.
    ```bash
    cat archivo.txt
    ```

11. **`more` y `less`**: Muestra el contenido de un archivo paginado.
    ```bash
    more archivo.txt
    less archivo.txt
    ```

12. **`head` y `tail`**: Muestra las primeras o últimas líneas de un archivo.
    ```bash
    head archivo.txt      # Muestra las primeras 10 líneas
    head -n 20 archivo.txt # Muestra las primeras 20 líneas
    tail archivo.txt      # Muestra las últimas 10 líneas
    tail -n 20 archivo.txt # Muestra las últimas 20 líneas
    tail -f archivo.log   # Muestra y sigue actualizando el final del archivo (útil para logs)
    ```

### Comandos Avanzados

1. **`find`**: Busca archivos y directorios.
   ```bash
   find /ruta -name "archivo*"
   find /ruta -type d -name "directorio*"
   find /ruta -mtime -1   # Archivos modificados en las últimas 24 horas
   find /ruta -size +100M # Archivos mayores a 100MB
   ```

2. **`grep`**: Busca texto dentro de archivos.
   ```bash
   grep "cadena" archivo.txt
   grep -r "cadena" /ruta  # Busca recursivamente en directorios
   grep -i "cadena" archivo.txt  # Búsqueda sin distinguir mayúsculas y minúsculas
   ```

3. **`tar`**: Crea y extrae archivos tar (archivos comprimidos).
   ```bash
   tar -cvf archivo.tar directorio/     # Crear un archivo tar
   tar -xvf archivo.tar                 # Extraer un archivo tar
   tar -czvf archivo.tar.gz directorio/ # Crear un archivo tar comprimido con gzip
   tar -xzvf archivo.tar.gz             # Extraer un archivo tar comprimido con gzip
   ```

4. **`chmod`**: Cambia los permisos de archivos y directorios.
   ```bash
   chmod 755 archivo
   chmod -R 755 directorio  # Cambia permisos recursivamente
   ```

5. **`chown`**: Cambia el propietario de archivos y directorios.
   ```bash
   chown usuario:grupo archivo
   chown -R usuario:grupo directorio  # Cambia propietario recursivamente
   ```

### Enlaces de Interés

1. **Documentación Oficial y Man Pages**:
   - [Linux Man Pages](https://linux.die.net/man/)
   - [GNU Coreutils Documentation](https://www.gnu.org/software/coreutils/manual/)

2. **Tutoriales y Guías**:
   - [Linux Command Line Basics - Coursera](https://www.coursera.org/learn/linux-command-line)
   - [The Linux Command Line - A Book by William Shotts](http://linuxcommand.org/tlcl.php)
   - [Linux Handbook](https://linuxhandbook.com/linux-commands/)

3. **Comunidad y Soporte**:
   - [Stack Overflow](https://stackoverflow.com/questions/tagged/linux)
   - [LinuxQuestions.org](https://www.linuxquestions.org/)
   - [Reddit: r/linux](https://www.reddit.com/r/linux/)

### Ejemplo Práctico

Supongamos que quieres buscar y eliminar archivos de más de 100MB en tu directorio personal que no han sido modificados en el último año. Aquí está cómo podrías hacerlo usando varios de los comandos mencionados:

```bash
# Buscar archivos de más de 100MB no modificados en el último año
find ~/ -size +100M -mtime +365

# Eliminar esos archivos (usando xargs para pasar los resultados a rm)
find ~/ -size +100M -mtime +365 | xargs rm
```

Esta combinación de comandos y técnicas te permitirá gestionar archivos de manera eficiente en Linux usando la consola.