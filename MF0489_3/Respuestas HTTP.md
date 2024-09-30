# Respuestas HTTP

Las **respuestas HTTP** (también conocidas como **códigos de estado HTTP**) son números que indican el resultado de una solicitud realizada por un cliente (normalmente un navegador) a un servidor web. Estos códigos de estado se dividen en cinco categorías, que corresponden a la primera cifra del código:

### 1xx: Respuestas informativas
Son respuestas que indican que la solicitud fue recibida y el proceso continúa.

- **100 Continue**: El servidor recibió la primera parte de la solicitud y el cliente puede continuar con el resto.
- **101 Switching Protocols**: El servidor acepta cambiar el protocolo a pedido del cliente (por ejemplo, de HTTP a WebSocket).

### 2xx: Respuestas exitosas
Indican que la solicitud fue recibida, entendida y aceptada correctamente.

- **200 OK**: La solicitud fue exitosa y el servidor devuelve el recurso solicitado.
- **201 Created**: La solicitud fue exitosa y un nuevo recurso fue creado (usado para POST/PUT).
- **202 Accepted**: La solicitud fue aceptada, pero el proceso aún no ha sido completado.
- **204 No Content**: La solicitud fue exitosa, pero no hay contenido que devolver.

### 3xx: Redirecciones
Indican que el cliente necesita tomar alguna acción adicional para completar la solicitud, como seguir una redirección.

- **301 Moved Permanently**: El recurso solicitado ha sido movido permanentemente a una nueva URL.
- **302 Found**: El recurso solicitado ha sido temporalmente movido a otra ubicación (redirección temporal).
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud (útil para la cache del navegador).

### 4xx: Errores del cliente
Indican que hubo un error por parte del cliente en la solicitud.

- **400 Bad Request**: La solicitud está mal formada o tiene un error sintáctico.
- **401 Unauthorized**: No se ha proporcionado autenticación válida (se requiere autenticación).
- **403 Forbidden**: El servidor entiende la solicitud, pero se niega a completarla (acceso prohibido).
- **404 Not Found**: El recurso solicitado no pudo ser encontrado en el servidor.
- **405 Method Not Allowed**: El método HTTP utilizado no está permitido para el recurso solicitado.

### 5xx: Errores del servidor
Indican que hubo un error por parte del servidor al procesar la solicitud.

- **500 Internal Server Error**: El servidor encontró un error inesperado que le impidió completar la solicitud.
- **501 Not Implemented**: El servidor no tiene la capacidad de cumplir con el método solicitado.
- **502 Bad Gateway**: Un servidor actuando como gateway o proxy recibió una respuesta inválida del servidor upstream.
- **503 Service Unavailable**: El servidor no está disponible temporalmente (por sobrecarga o mantenimiento).
- **504 Gateway Timeout**: Un servidor actuando como gateway o proxy no recibió una respuesta a tiempo del servidor upstream.

### Ejemplos de uso común:
- **200 OK**: Indica que la página o recurso se ha cargado correctamente.
- **403 Forbidden**: Indica que intentaste acceder a un recurso al que no tienes permisos.
- **404 Not Found**: Se refiere a una página o recurso que no existe en el servidor.
- **500 Internal Server Error**: Generalmente señala un problema en el lado del servidor, como un fallo en el código.

