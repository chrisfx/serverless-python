## Diagrama: Flujo Python + AWS Serverless

```mermaid
graph TD
    A[Usuario: Cliente HTTP] -->|Petición HTTP| B(API Gateway)
    B -->|Invoca| C[Lambda Function (Python)]
    C -->|Consulta/Almacena datos| D[DynamoDB]
    C -->|Procesa lógica| E[Lógica Python]
    D -->|Devuelve datos| C
    C -->|Respuesta| B
    B -->|Respuesta JSON| A
```
