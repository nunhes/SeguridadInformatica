# Acceso a servicios remotos vía SSH

La terminal de Linux es una herramienta potente y versátil. Aunque a primera vista puede parecer menos intuitiva que las interfaces gráficas, en muchos casos resulta ser el recurso más óptimo para solucionar problemas y realizar tareas avanzadas en un equipo. A pesar de la gran variedad de entornos gráficos disponibles, el uso de la línea de comandos garantiza la correcta ejecución de tareas de forma independiente al entorno de escritorio que estemos utilizando.

SSH (Secure Shell) es un protocolo de red que permite acceder de forma segura a dispositivos remotos mediante una conexión encriptada. Es utilizado habitualmente para la administración remota de servidores y la transferencia segura de archivos, proporcionando una autenticación robusta y comunicación cifrada. Aunque el cifrado de SSH **protege los datos en tránsito**, es importante señalar que, aunque reduce significativamente los riesgos de intercepción o manipulación, no garantiza una seguridad absoluta.

**Con SSH podemos acceder a la terminal de cualquier equipo remoto del que conozcamos su dirección IP, usuario y contraseña**, sin importar si está en otra parte de nuestra empresa o en un lugar remoto del mundo. De hecho, cuando contratamos un VPS (Servidor Privado Virtual) para alojar páginas web u otros servicios (correo, nube, etc.), SSH suele ser la única forma de conexión que se nos proporciona. SSH también permite [acceder a carpetas remotas fácilmente](https://forums.linuxmint.com/viewtopic.php?p=2292172#p2292172) y el [montaje local de carpetas remotas](https://forums.linuxmint.com/viewtopic.php?t=402352) en nuestro equipo mediante SFTP de forma sencilla.

Una vez conectados, podemos controlar completamente el equipo remoto como si estuviéramos trabajando directamente en él. Esto incluye la posibilidad de actualizar, instalar y desinstalar aplicaciones, reiniciar servicios, y ejecutar programas. Si estas aplicaciones disponen de una interfaz gráfica (GUI), podemos lanzarlas en nuestra máquina local e interactuar con ellas, tal como si estuvieran corriendo en nuestro equipo.

### Autenticación mediante contraseña

Linux **Mint incluye preinstalado el cliente SSH**, por lo que solo es necesario **instalar el servidor SSH en los equipos remotos a los que queramos acceder**. Para ello, ejecutamos:

```
sudo apt install openssh-server
```

Además, abrimos el puerto 22 en el cortafuegos con:

```
sudo ufw allow ssh
```

Para conectarnos al equipo remoto, utilizamos:

```
ssh USUARIO-REMOTO@IP-REMOTA
```

Esto establecerá una sesión SSH estándar, permitiendo ejecutar comandos de forma remota. Por ejemplo:

```
ssh user@192.168.1.100
```

Este comando abre una sesión SSH en la máquina con IP `192.168.1.100`, permitiendo que el usuario `user` ejecute comandos en el sistema remoto.

### Reenvío de aplicaciones gráficas (X11 Forwarding)

Si la aplicación remota tiene GUI y deseas ejecutarla en tu entorno local, necesitas habilitar el reenvío de X11. Primero, verifica que el archivo de configuración en el equipo remoto (`/etc/ssh/sshd_config`) tenga activada la opción:

```
X11Forwarding yes
```

Luego, reinicia el servicio SSH en el equipo remoto:

```
sudo systemctl restart sshd
```

Una vez hecho esto, conecta usando la opción `-X`:

```
ssh -X USUARIO-REMOTO@IP-REMOTA
```

Esto te permitirá ejecutar aplicaciones gráficas en tu equipo local. Si no puedes ver la GUI, revisa el archivo de configuración y asegúrate de que `X11Forwarding` esté correctamente configurado.

### Autenticación mediante clave SSH

Es recomendable usar claves SSH en lugar de contraseñas para mayor seguridad y conveniencia. Para generar un par de claves (pública y privada), ejecuta:

```
ssh-keygen
```

Este comando te guiará en la generación de las claves. Si decides establecer una **contraseña (passphrase)** para tu clave privada, esta solo se pedirá la primera vez que uses la clave tras iniciar sesión en tu equipo local.

Una vez generada la clave pública, cópiala al equipo remoto con:

```
ssh-copy-id -i ~/.ssh/id_rsa.pub USUARIO-REMOTO@IP-REMOTA
```

Esto añadirá tu clave pública al equipo remoto, permitiendo que te reconozca sin necesidad de ingresar una contraseña en futuras conexiones.

### Transferencia de archivos

SSH también incluye dos herramientas útiles para transferir archivos entre equipos:

1. **`scp`**: Permite copiar archivos de manera puntual. Ejemplos:

   - Copiar un archivo local a un equipo remoto:

     ```
     scp Documentos/archivo.txt USUARIO-REMOTO@IP-REMOTA:Descargas/
     ```

   - Copiar un archivo del equipo remoto al equipo local:

     ```
     scp USUARIO-REMOTO@IP-REMOTA:Documentos/archivo.txt Descargas/
     ```

2. **`sftp`**: Proporciona una sesión interactiva para transferir archivos. Conecta usando:

   ```
   sftp USUARIO-REMOTO@IP-REMOTA
   ```

   Una vez conectado, puedes listar archivos, cambiar de directorio, subir y descargar archivos.

### Conclusión

SSH es una herramienta esencial para la administración remota de sistemas, ofreciendo no solo acceso seguro a la terminal, sino también opciones avanzadas como la transferencia de archivos y el uso de aplicaciones gráficas. Además, el uso de claves públicas/privadas mejora la seguridad y facilita el acceso a múltiples servidores.