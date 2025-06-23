# 📦 ¿Qué es AWS SAM?

**AWS SAM (Serverless Application Model)** es un framework de **infraestructura como código (IaC)** que te permite **definir, probar y desplegar** aplicaciones serverless en AWS de forma estructurada y automatizada, usando archivos YAML.

Piensa en SAM como una forma **declarativa** de describir:

- 🔁 Funciones Lambda
- 🌐 APIs (API Gateway)
- 🗄️ Bases de datos (DynamoDB)
- 🔐 Permisos (IAM Roles/Policies)

Todo desde un **solo archivo YAML**.

---

## ✨ Características clave

- 🧱 **Basado en AWS CloudFormation**  
  Usa su robustez, pero con **una sintaxis más simple** enfocada en recursos serverless.

- 🐳 **Pruebas locales con Docker**  
  Ejecuta y depura funciones Lambda localmente con `sam local`.

- 🔁 **Compatible con CI/CD**  
  Integra fácilmente con **GitHub Actions, AWS CodePipeline, GitLab CI, Jenkins**, entre otros.

- ⚙️ **Flujo típico CI/CD**  
  ```text
  build → test → deploy


## ¿SAM requiere Docker?
Sí, si quieres usar sam local para probar tus funciones, necesitas tener Docker instalado y en ejecución, ya que SAM simula el entorno real de Lambda dentro de un contenedor local.

```bash
sam local start-api
```
Levanta una versión local de tu API Gateway + Lambda en http://localhost:3000.

## 🔄 Flujo CI/CD típico con SAM

!!! note "Resumen del flujo"
    Este es el ciclo básico para desarrollar, probar y desplegar una aplicación serverless con SAM:

```mermaid
graph TD
    A[📝 Escribes código + YAML] --> B[🔧 sam build]
    B --> C[🧪 sam local invoke / start-api (opcional)]
    C --> D[🚀 sam deploy --guided]
    D --> E[✅ Aplicación desplegada en AWS]
```

En pipelines automatizados, puedes hacer:
```bash
sam build
sam deploy --no-confirm-changeset --no-fail-on-empty-changeset
```

Esto se puede integrar con:

- GitHub Actions
- AWS CodeBuild + CodePipeline
- GitLab CI/CD

## Ejemplo de plantilla template.yaml (SAM YAML)
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Transform: AWS::Serverless-2016-10-31
Description: API simple con SAM + Python

Resources:
  HelloFunction:
    Type: AWS::Serverless::Function
    Properties:
      CodeUri: hello/
      Handler: app.lambda_handler
      Runtime: python3.11
      Events:
        HelloApi:
          Type: Api
          Properties:
            Path: /hello
            Method: get
```
Este ejemplo crea una función Lambda en Python que se activa vía una llamada HTTP GET /hello.
### Despliegue rápido
```bash
sam build
sam deploy --guided
```
Esto empaqueta el código, te pide una configuración inicial (región, bucket de despliegue, etc.), y sube tu aplicación a AWS.