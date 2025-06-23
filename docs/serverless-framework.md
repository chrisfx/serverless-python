## Introducción al framework

Serverless Framework es una herramienta de infraestructura como código (IaC) que permite crear, configurar y desplegar aplicaciones serverless (sin servidor) sobre múltiples proveedores en la nube — principalmente AWS, pero también Azure, Google Cloud, entre otros.

- Es uno de los frameworks más maduros y usados para Lambda + API Gateway.

## serverless.yml explicado
El archivo serverless.yml define toda la aplicación:
```yaml
service: my-api-python

provider:
  name: aws
  runtime: python3.11
  region: us-east-1

functions:
  hello:
    handler: handler.hello
    events:
      - http:
          path: hello
          method: get
```
Explicación rápida:

- service: nombre del proyecto

- provider: nube objetivo (AWS), runtime, región

- functions: lista de funciones Lambda

  - handler: ruta al archivo y función (handler.py → def hello)

  - events: cómo se activa (en este caso, con HTTP vía API Gateway)


## Comandos clave: sls create, sls deploy
```bash
# Crear un nuevo proyecto con template
sls create --template aws-python --path my-api
cd my-api

# Instalar dependencias necesarias
pip install -r requirements.txt

# Desplegar la aplicación
sls deploy

# Invocar una función manualmente
sls invoke -f hello

# Ver logs en vivo
sls logs -f hello -t

# Eliminar la aplicación del entorno AWS
sls remove
```
## Estructura típica del proyecto
```bash
my-api/
├── handler.py            # Funciones Lambda
├── serverless.yml        # Infraestructura y eventos
├── requirements.txt      # Dependencias Python
└── .serverless/          # Archivos empaquetados para despliegue (auto)
```
Ejemplo de handler.py:
```python
def hello(event, context):
    return {
        "statusCode": 200,
        "body": "Hello from Serverless!"
    }
```

