# Tecnologías Serverless de AWS

AWS ofrece una amplia gama de servicios serverless que permiten construir aplicaciones sin necesidad de gestionar servidores. A continuación, se describen algunas de las tecnologías clave que puedes utilizar para crear soluciones modernas, escalables y eficientes.

---

## Lambda: código sin servidores

**AWS Lambda** te permite ejecutar código sin aprovisionar ni administrar servidores. Solo cargas tu función, defines un desencadenador (como una solicitud HTTP, un evento de base de datos o un archivo nuevo en S3), y Lambda ejecuta el código bajo demanda.

- Soporta múltiples lenguajes: Python, Node.js, Go, Java, .NET, Ruby, etc.
- Escala automáticamente según la demanda.
- Se cobra solo por el tiempo de ejecución y la cantidad de invocaciones.

**Casos de uso comunes:**
- Backend para APIs
- Automatización de tareas
- Procesamiento de archivos
- Validación y transformación de datos

---

## API Gateway: crea tus endpoints

**Amazon API Gateway** permite crear, publicar, mantener y proteger APIs REST, HTTP y WebSocket. Es el punto de entrada ideal para tus aplicaciones serverless.

- Integra directamente con Lambda, DynamoDB, Step Functions, y otros servicios.
- Soporte para autenticación (IAM, Cognito, API Keys).
- Capacidad para limitar el tráfico (rate limiting), cacheo de respuestas, y transformación de payloads.

**Casos de uso comunes:**
- Crear APIs RESTful para frontend web o móvil
- WebSocket para comunicación en tiempo real
- Versionado y monitoreo de APIs

---

## DynamoDB: persistencia sin servidor

**Amazon DynamoDB** es una base de datos NoSQL completamente administrada, rápida y flexible. Está diseñada para cargas de trabajo de baja latencia y alto rendimiento.

- Modelo de datos basado en tablas, ítems y atributos.
- Soporte para claves primarias compuestas y acceso por índices secundarios.
- Integración perfecta con Lambda para arquitecturas serverless.

**Ventajas clave:**
- Escalado automático (On-Demand Mode)
- Alta disponibilidad y replicación multi-región
- TTL, Streams, y acceso condicional

**Casos de uso comunes:**
- Almacenamiento de usuarios, sesiones o catálogos
- Backend de aplicaciones móviles o juegos
- Registro de eventos (logs, métricas)





