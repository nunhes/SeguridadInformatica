# Criptografía basada en códigos

> Definición: La criptografía basada en códigos comprende todos los criptosistemas simétricos o asimétricos cuya seguridad depende, en parte o totalmente, de la dificultad de descifrar un código lineal de corrección de errores (por ejemplo, el código cuasicíclico o los códigos Goppa).

La criptografía basada en códigos es el área de investigación que se centra en el estudio de criptosistemas basados en códigos de corrección de errores. **En las comunicaciones digitales, la alteración de un solo bit puede provocar un desastre si no hay forma de identificar y solucionar los problemas**. Las sumas de comprobación son una ilustración básica de un código de detección de errores. El objetivo es **maximizar la probabilidad de exactitud en la transmisión de datos al tiempo que se reduce el volumen de información adicional añadida**.

La idea del código de corrección de errores se le ocurrió a Robert McEliece en 1978. Empezó con un código específico de corrección de errores, el código binario Goppa, y utilizó una transformación lineal invertible para desordenarlo. En un nivel muy fundamental, el enfoque de McEliece equivale a una factorización secreta, que es algo similar al criptosistema de clave pública de Rivest Shamir y Adleman, conocido como RSA. Sólo el propietario conoce la factorización de la clave pública, que es el resultado del código Goppa y la transformación lineal.

La [clave](https://utimaco.com/es/servicio/base-de-conocimientos/infraestructura-de-clave-publica/que-es-la-criptografia-de-clave) pública es una matriz generadora aleatoria de una versión arbitrariamente permutada de la clave privada, que es un código Goppa binario irreducible aleatorio. Sólo el propietario de la clave privada (el código Goppa) puede corregir los fallos que se hayan introducido en el texto cifrado, que es una palabra-código.

En la criptografía basada en códigos, el emisor del mensaje introduce intencionadamente fallos en el código para dificultar la descodificación y, por tanto, el descifrado. El receptor del mensaje puede descifrarlo utilizando algún conocimiento secreto (a menudo relativo a la estructura del código), pero un atacante sin acceso al conocimiento secreto no puede.

La criptografía basada en códigos tiene el potencial de ser reconocida como un criptosistema completo dada la disponibilidad de algoritmos de cifrado, intercambio de claves y [firma digital](https://utimaco.com/es/servicio/base-de-conocimientos/firma-digital/que-es-una-firma-digital).

A diferencia de RSA y otros sistemas de clave pública bien conocidos, el método de McEliece parece ser resistente al quantum, lo que ha reavivado el interés por él.

La técnica de McEliece quedó relegada a un segundo plano para los diseñadores. Debido al hecho de que el método de McEliece requería claves públicas significativamente mayores que otros métodos, como el RSA, no generó mucho interés en su momento. Sin embargo, a medida que se acerca la era de los ordenadores cuánticos, se le vuelve a prestar atención porque parece ser inmune a los ataques que utilizan el [método de Shor](https://utimaco.com/es/servicio/base-de-conocimientos/criptografia-postcuantica/que-es-el-algoritmo-de-shor).

Por ello, el algoritmo subyacente "Classic McEliece" para la encapsulación de claves se encuentra actualmente en la ronda 4 del [proceso de normalización del NIST](https://utimaco.com/es/servicio/base-de-conocimientos/criptografia-postcuantica/en-que-consiste-el-proceso-de) para la [Criptografía Postcuántica (PQC)](https://utimaco.com/es/servicio/base-de-conocimientos/criptografia-postcuantica/que-es-la-criptografia-postcuantica-pqc).

---

ref:

- https://www.inesdi.com/blog/breve-introduccion-a-la-criptografia/

- https://es.wikipedia.org/wiki/Criptograf%C3%ADa

---

Los **métodos criptográficos actuales** y las **tendencias futuras** en el ámbito de la criptografía están definidos por la necesidad de mantener la confidencialidad, integridad y autenticidad de la información en un mundo cada vez más interconectado. A continuación, una breve introducción a los principales métodos criptográficos actuales y las tendencias que están surgiendo:

### Métodos Criptográficos Actuales

1. **Cifrado simétrico:**
   - **AES (Advanced Encryption Standard):** Uno de los algoritmos de cifrado más utilizados y eficientes, estándar para aplicaciones de alta seguridad.
   - **DES/Triple DES:** Aunque DES está obsoleto por su vulnerabilidad, el Triple DES sigue siendo usado en algunas aplicaciones, aunque también se considera menos seguro.
   
2. **Cifrado asimétrico:**
   - **RSA (Rivest-Shamir-Adleman):** Un estándar en el cifrado de clave pública que se basa en la factorización de números grandes. Utilizado en muchos sistemas de seguridad, aunque con clave de al menos 2048 bits para ser seguro hoy en día.
   - **ECDSA (Elliptic Curve Digital Signature Algorithm):** Un algoritmo de firmas digitales basado en curvas elípticas, ofreciendo la misma seguridad que RSA con claves mucho más pequeñas, lo que lo hace más eficiente.
   - **Diffie-Hellman:** Protocolo para el intercambio seguro de claves. Aunque la versión clásica está siendo reemplazada por variantes basadas en curvas elípticas debido a su mayor seguridad.

3. **Funciones hash:**
   - **SHA-2 (Secure Hash Algorithm 2):** Ampliamente usado para garantizar la integridad de los datos, SHA-256 y SHA-512 son versiones comunes.
   - **SHA-3:** Un algoritmo más reciente con diseño diferente a SHA-2, considerado más robusto frente a posibles ataques futuros.

4. **Criptografía basada en curvas elípticas (ECC):**
   - **ECC (Elliptic Curve Cryptography):** La criptografía de curvas elípticas es altamente eficiente y ofrece seguridad equivalente a RSA pero con claves más pequeñas, lo que reduce los requisitos de procesamiento y almacenamiento.

5. **Criptografía de clave pública basada en emparejamiento de bilineal (Pairing-Based Cryptography):**
   - Utilizada en esquemas avanzados como la criptografía basada en identidad y la criptografía basada en atributos, especialmente para escenarios de control de acceso.

### Tendencias Futuras en Criptografía

1. **Criptografía Post-Cuántica:**
   - **Impacto de la computación cuántica:** Los ordenadores cuánticos, una vez desarrollados completamente, podrían romper los algoritmos actuales como RSA y ECC al resolver problemas de factorización y logaritmos discretos con mayor rapidez (usando algoritmos cuánticos como Shor). Por ello, se están investigando nuevas técnicas criptográficas resistentes a ataques cuánticos.
   - **Algoritmos resistentes a cuántica:** Algunas de las propuestas actuales incluyen:
     - **Lattice-Based Cryptography:** Criptografía basada en redes algebraicas.
     - **Hash-Based Cryptography:** Algoritmos de firma digital como XMSS y LMS.
     - **Multivariate Polynomial Cryptography.**
   
2. **Homomorphic Encryption (Cifrado Homomórfico):**
   - Permite realizar operaciones sobre datos cifrados sin necesidad de desencriptarlos primero. Esto podría revolucionar la privacidad en aplicaciones como la computación en la nube, permitiendo procesar datos sensibles sin comprometer su seguridad.

3. **Zero-Knowledge Proofs (Pruebas de Conocimiento Cero):**
   - Técnicas que permiten a una parte probar que conoce un valor (como una contraseña) sin revelar dicho valor. Estas pruebas son muy útiles en sistemas de autenticación y en aplicaciones de privacidad (por ejemplo, en blockchain).

4. **Criptografía multipartita:**
   - Permite que varias partes realicen cálculos conjuntos sin revelar sus propios datos privados. Esto es especialmente útil en ámbitos financieros y de salud, donde diferentes entidades deben colaborar sin comprometer la confidencialidad de la información.

5. **Blockchain y criptografía descentralizada:**
   - Las cadenas de bloques han impulsado la investigación en criptografía aplicada, especialmente en términos de protección de datos distribuidos y la creación de criptomonedas seguras.
   - **Contratos inteligentes** y **sistemas de votación electrónicos** son áreas de crecimiento donde la criptografía se está adaptando para mejorar la confianza y transparencia.

6. **Criptografía ligera (Lightweight Cryptography):**
   - Con el auge de dispositivos IoT (Internet de las Cosas), surge la necesidad de algoritmos criptográficos eficientes que puedan operar en dispositivos con recursos limitados en términos de procesamiento y energía.

### Desafíos Futuros
- **Computación cuántica:** Aunque los ordenadores cuánticos aún están en desarrollo, la comunidad criptográfica está tomando medidas para migrar a algoritmos resistentes a cuántica.
- **Privacidad en la era de los datos masivos:** Con la creciente cantidad de datos personales que se recopilan y analizan, la criptografía deberá evolucionar para equilibrar el análisis de grandes volúmenes de información sin comprometer la privacidad.

En resumen, la criptografía está en constante evolución, con una transición hacia algoritmos resistentes a la computación cuántica y técnicas que permiten mantener la privacidad y seguridad en entornos de computación cada vez más complejos.