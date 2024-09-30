---
title: Aplicación de una infraestructura de clave pública (PKI)
---

### 1. Identificación de los componentes de una PKI y su modelo de relaciones  
Una PKI consta de varios componentes clave que interactúan para garantizar la seguridad en la comunicación:
- **Autoridad de certificación (CA)**: Responsable de emitir y gestionar los certificados digitales.
- **Autoridad de registro (RA)**: Verifica la identidad de los usuarios antes de la emisión de certificados.
- **Usuarios finales**: Individuos u organizaciones que utilizan certificados.
- **Directorio de certificados**: Almacena y distribuye los certificados públicos.
- **Lista de certificados revocados (CRL)**: Identifica certificados que ya no son válidos.
- **Gestión de claves**: Encargada de la generación, distribución y almacenamiento seguro de las claves criptográficas.

### 2. Autoridad de certificación y sus elementos  
La **CA** tiene un rol central en una PKI:
- **Emisión de certificados**: Asocia claves públicas con identidades verificadas.
- **Renovación y revocación**: Mantiene actualizados los certificados según las políticas definidas.
- **Mantenimiento de registros**: Guarda la historia y el estado de cada certificado.

### 3. Política de certificado y declaración de prácticas de certificación (CPS)  
La **Política de Certificado** define las reglas y las prácticas bajo las cuales se emiten y utilizan los certificados. La **Declaración de Prácticas de Certificación (CPS)** describe cómo la CA implementa esta política, detallando los procedimientos técnicos y operativos.

### 4. Lista de certificados revocados (CRL)  
La **CRL** es un documento que enumera los certificados digitales que han sido revocados antes de su fecha de caducidad. Esto asegura que los certificados comprometidos o caducados no se utilicen para actividades malintencionadas.

### 5. Funcionamiento de las solicitudes de firma de certificados (CSR)  
Un **CSR** es un mensaje enviado a la CA que incluye la clave pública del solicitante y otra información que será utilizada para generar el certificado. La CA verifica la solicitud y luego firma el certificado con su propia clave privada.

### 6. Infraestructura de gestión de privilegios (PMI)  
La **PMI** administra los privilegios y permisos de los usuarios dentro de una red. Mientras que la PKI gestiona la autenticación, la PMI gestiona qué recursos o acciones puede realizar un usuario.

### 7. Campos de certificados de atributos, incluyen la descripción de sus usos habituales y la relación con los certificados digitales  
Los certificados de atributos incluyen información adicional sobre el usuario, como su rol, derechos o permisos dentro de un sistema. Estos son complementarios a los certificados digitales estándar que solo verifican identidad.

### 8. Aplicaciones que se apoyan en la existencia de una PKI  
Algunas aplicaciones que dependen de una PKI para garantizar la seguridad incluyen:
- **Cifrado de correos electrónicos (S/MIME, PGP)**.
- **VPNs y redes privadas seguras**.
- **Autenticación en servicios web y aplicaciones (TLS/SSL)**.
- **Firmas digitales para documentos legales**.
