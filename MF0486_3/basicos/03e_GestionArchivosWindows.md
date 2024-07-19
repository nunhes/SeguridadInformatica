# Gestión de archivos en Windows

La gestión de archivos en Windows usando la consola se puede realizar tanto con el **Command Prompt (CMD)** como con **PowerShell**. A continuación, se presentan comandos y técnicas para manejar archivos y directorios en Windows, junto con ejemplos prácticos y enlaces de interés.

### Command Prompt (CMD)

1. **`dir`**: Lista archivos y directorios en el directorio actual.
   ```cmd
   dir                  # Lista básica
   dir /A               # Lista incluyendo archivos ocultos
   dir /S               # Lista archivos en el directorio actual y subdirectorios
   ```

2. **`cd`**: Cambia el directorio actual.
   ```cmd
   cd C:\ruta\al\directorio  # Cambia al directorio especificado
   cd ..                     # Sube un nivel
   cd \                      # Cambia al directorio raíz
   ```

3. **`mkdir`**: Crea un nuevo directorio.
   ```cmd
   mkdir nuevo_directorio
   ```

4. **`rmdir`**: Elimina un directorio vacío.
   ```cmd
   rmdir directorio_vacio
   ```

5. **`del`**: Elimina archivos.
   ```cmd
   del archivo.txt        # Elimina un archivo
   del /S /Q directorio   # Elimina todos los archivos en un directorio y subdirectorios sin preguntar
   ```

6. **`copy`**: Copia archivos de un lugar a otro.
   ```cmd
   copy archivo.txt destino\  # Copia un archivo
   copy *.txt destino\        # Copia todos los archivos .txt
   ```

7. **`move`**: Mueve o renombra archivos y directorios.
   ```cmd
   move archivo.txt destino\   # Mueve un archivo
   move directorio nuevo_nombre  # Renombra un directorio
   ```

8. **`type`**: Muestra el contenido de un archivo de texto.
   ```cmd
   type archivo.txt
   ```

### PowerShell

1. **`Get-ChildItem`**: Lista archivos y directorios (equivalente a `dir` en CMD).
   ```powershell
   Get-ChildItem              # Lista básica
   Get-ChildItem -Recurse     # Lista recursivamente
   Get-ChildItem -Hidden      # Incluye archivos ocultos
   ```

2. **`Set-Location`**: Cambia el directorio actual (equivalente a `cd` en CMD).
   ```powershell
   Set-Location C:\ruta\al\directorio
   ```

3. **`New-Item`**: Crea nuevos archivos o directorios.
   ```powershell
   New-Item -ItemType Directory -Path . -Name "nuevo_directorio"
   New-Item -ItemType File -Path . -Name "nuevo_archivo.txt"
   ```

4. **`Remove-Item`**: Elimina archivos o directorios.
   ```powershell
   Remove-Item archivo.txt
   Remove-Item -Recurse -Force directorio  # Elimina recursivamente sin confirmación
   ```

5. **`Copy-Item`**: Copia archivos o directorios.
   ```powershell
   Copy-Item archivo.txt -Destination .\destino\
   Copy-Item -Recurse .\directorio\ -Destination .\destino\
   ```

6. **`Move-Item`**: Mueve o renombra archivos y directorios.
   ```powershell
   Move-Item archivo.txt -Destination .\destino\
   Move-Item directorio -Destination nuevo_nombre
   ```

7. **`Get-Content`**: Muestra el contenido de un archivo de texto.
   ```powershell
   Get-Content archivo.txt
   ```

### Ejemplos Prácticos

#### Copia de Seguridad y Restauración

1. **Copia de seguridad de un directorio en CMD:**
   ```cmd
   xcopy C:\ruta\original D:\ruta\backup /E /H /C /I
   ```

2. **Copia de seguridad de un directorio en PowerShell:**
   ```powershell
   Copy-Item -Path "C:\ruta\original\*" -Destination "D:\ruta\backup" -Recurse -Force
   ```

#### Busqueda de Archivos por Fecha y Tamaño

1. **Buscar archivos mayores a 100 MB en CMD:**
   ```cmd
   forfiles /P C:\ruta /S /M *.* /C "cmd /c if @fsize gtr 104857600 echo @path"
   ```

2. **Buscar archivos mayores a 100 MB en PowerShell:**
   ```powershell
   Get-ChildItem -Path C:\ruta -Recurse | Where-Object { $_.Length -gt 100MB }
   ```

### Enlaces de Interés

1. **Documentación Oficial:**
   - [Command Prompt Commands](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
   - [PowerShell Documentation](https://docs.microsoft.com/en-us/powershell/)

2. **Tutoriales y Guías:**
   - [Learn Windows PowerShell](https://www.microsoft.com/en-us/learning/windows-powershell-training.aspx)
   - [Command Line Reference](https://ss64.com/nt/)

3. **Cursos en Línea:**
   - [Pluralsight: PowerShell Courses](https://www.pluralsight.com/browse/it-ops/systems-administration/powershell)
   - [Udemy: PowerShell for Beginners](https://www.udemy.com/course/learn-windows-powershell/)

4. **Comunidades y Foros:**
   - [Stack Overflow](https://stackoverflow.com/questions/tagged/windows)
   - [PowerShell.org](https://powershell.org/)

### Ejemplo Práctico Completo

Supongamos que quieres buscar y eliminar archivos mayores a 100MB en tu directorio personal que no han sido modificados en el último año. Aquí está cómo podrías hacerlo usando PowerShell:

```powershell
# Buscar archivos mayores a 100MB no modificados en el último año
Get-ChildItem -Path "C:\Users\TuUsuario" -Recurse | Where-Object { $_.Length -gt 100MB -and $_.LastWriteTime -lt (Get-Date).AddYears(-1) }

# Eliminar esos archivos (confirmando antes de eliminar)
Get-ChildItem -Path "C:\Users\TuUsuario" -Recurse | Where-Object { $_.Length -gt 100MB -and $_.LastWriteTime -lt (Get-Date).AddYears(-1) } | Remove-Item -Force -Confirm
```

Estos comandos y técnicas te permitirán gestionar archivos de manera eficiente en Windows usando la consola.