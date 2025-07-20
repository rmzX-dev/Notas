Los códigos de respuesta HTTP son códigos de estado enviados por el servidor en respuesta a la solicitud del navegador o cliente. Aquí tienes una lista de los códigos de respuesta HTTP más comunes, agrupados por categorías:

### 1: Informativos
- **100 Continue**: El servidor ha recibido los encabezados de la solicitud y el cliente debe proceder a enviar el cuerpo de la solicitud.
- **101 Switching Protocols**: El servidor acepta cambiar el protocolo según lo solicitado por el cliente.

### 2: Éxito
- **200 OK**: La solicitud ha tenido éxito.
- **201 Created**: La solicitud ha sido cumplida y ha resultado en la creación de un nuevo recurso.
- **202 Accepted**: La solicitud ha sido aceptada para procesamiento, pero no se ha completado.
- **204 No Content**: La solicitud se ha procesado con éxito, pero no devuelve ningún contenido.

### 3: Redirección
- **300 Multiple Choices**: Hay varias opciones para el recurso que el cliente puede seguir.
- **301 Moved Permanently**: El recurso solicitado ha sido movido de forma permanente a una nueva URL.
- **302 Found**: El recurso solicitado ha sido movido temporalmente a una nueva URL.
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud.

### 4: Error del cliente
- **400 Bad Request**: La solicitud no puede ser procesada debido a un error de sintaxis del cliente.
- **401 Unauthorized**: La solicitud requiere autenticación.
- **403 Forbidden**: El servidor entiende la solicitud, pero se niega a autorizarla.
- **404 Not Found**: El recurso solicitado no ha sido encontrado en el servidor.
- **405 Method Not Allowed**: El método especificado en la solicitud no está permitido para el recurso.

### 5: Error del servidor
- **500 Internal Server Error**: El servidor ha encontrado una situación que no sabe cómo manejar.
- **501 Not Implemented**: El servidor no reconoce el método de solicitud o no tiene la capacidad para cumplirlo.
- **502 Bad Gateway**: El servidor, actuando como una puerta de enlace o proxy, recibió una respuesta inválida del servidor ascendente.
- **503 Service Unavailable**: El servidor no está disponible actualmente, generalmente debido a mantenimiento o sobrecarga.
- **504 Gateway Timeout**: El servidor, actuando como una puerta de enlace o proxy, no recibió una respuesta a tiempo del servidor ascendente.