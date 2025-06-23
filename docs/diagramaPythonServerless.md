## Diagrama: Flujo Python + AWS Serverless

```mermaid
graph TD
  A[Inicio] --> B[API Gateway]
  B --> C[Lambda]
  C --> D[DynamoDB]
  C --> E[Respuesta]
```
