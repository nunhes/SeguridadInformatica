# nmap

Nmap es una herramienta poderosa y versátil para el escaneo de redes. Los modificadores (o flags) de Nmap te permiten personalizar tus escaneos de acuerdo a tus necesidades específicas. A continuación, te explico algunos de los modificadores más comunes de Nmap y cómo utilizarlos con ejemplos prácticos.

### 1. Escaneo básico de puertos

**Comando:**

```bash
nmap <IP>
```

**Ejemplo:**

```bash
nmap 192.168.1.1
```

Esto realiza un escaneo básico de puertos en la IP 192.168.1.1.

### 2. Especificar rangos de puertos

**Modificador: `-p`**

**Comando:**

```bash
nmap -p <puerto/rango> <IP>
```

**Ejemplo:**

```bash
nmap -p 80,443 192.168.1.1
nmap -p 1-65535 192.168.1.1
```

El primer ejemplo escanea solo los puertos 80 y 443. El segundo ejemplo escanea todos los puertos del 1 al 65535.

### 3. Escaneo de puertos más comunes

**Modificador: `-F`**

**Comando:**

```bash
nmap -F <IP>
```

**Ejemplo:**

```bash
nmap -F 192.168.1.1
```

Esto realiza un escaneo rápido de los 100 puertos más comunes.

### 4. Detectar sistema operativo

**Modificador: `-O`**

**Comando:**

```bash
nmap -O <IP>
```

**Ejemplo:**

```bash
nmap -O 192.168.1.1
```

Esto intenta detectar el sistema operativo del dispositivo objetivo.

### 5. Escaneo con servicio y versión

**Modificador: `-sV`**

**Comando:**

```bash
nmap -sV <IP>
```

**Ejemplo:**

```bash
nmap -sV 192.168.1.1
```

Esto escanea los puertos y determina qué servicios están corriendo y sus versiones.

### 6. Escaneo de red completa

**Modificador: `-sn`**

**Comando:**

```bash
nmap -sn <rango de IP>
```

**Ejemplo:**

```bash
nmap -sn 192.168.1.0/24
```

Esto realiza un "ping scan" para descubrir dispositivos activos en la red 192.168.1.0/24 sin realizar un escaneo de puertos.

### 7. Escaneo sigiloso

**Modificador: `-sS`**

**Comando:**

```bash
nmap -sS <IP>
```

**Ejemplo:**

```bash
nmap -sS 192.168.1.1
```

Esto realiza un escaneo SYN, que es menos probable de ser detectado por firewalls y sistemas de detección de intrusos.

### 8. Guardar resultados en un archivo

**Modificador: `-oN` (formato normal), `-oX` (formato XML), `-oG` (formato Grepable)**

**Comando:**

```bash
nmap -oN <archivo> <IP>
nmap -oX <archivo> <IP>
nmap -oG <archivo> <IP>
```

**Ejemplo:**

```bash
nmap -oN scan_result.txt 192.168.1.1
nmap -oX scan_result.xml 192.168.1.1
nmap -oG scan_result.gnmap 192.168.1.1
```

Esto guarda los resultados del escaneo en un archivo en los formatos especificados.

### 9. Escaneo con script

**Modificador: `--script`**

**Comando:**

```bash
nmap --script <script> <IP>
```

**Ejemplo:**

```bash
nmap --script vuln 192.168.1.1
```

Esto ejecuta un script de Nmap para buscar vulnerabilidades conocidas en la IP 192.168.1.1.

### 10. Escaneo agresivo

**Modificador: `-A`**

**Comando:**

```bash
nmap -A <IP>
```

**Ejemplo:**

```bash
nmap -A 192.168.1.1
```

Esto realiza un escaneo agresivo, que incluye detección de sistema operativo, escaneo de servicios y versión, y scripts de detección de vulnerabilidades.

Estos son solo algunos ejemplos de cómo usar Nmap con diferentes modificadores. Nmap tiene muchos más flags y opciones que puedes explorar según tus necesidades específicas en hacking ético.