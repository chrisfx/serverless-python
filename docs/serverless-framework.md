## Introducción al framework

Serverless Framework es una herramienta de infraestructura como código (IaC) que permite crear, configurar y desplegar aplicaciones serverless (sin servidor) sobre múltiples proveedores en la nube — principalmente AWS, pero también Azure, Google Cloud, entre otros.

- Es uno de los frameworks más maduros y usados para Lambda + API Gateway.


## Instalación de Serverless Framework
Serverless Framework es una herramienta de código abierto que facilita el desarrollo, despliegue y operación de aplicaciones serverless (sin servidor), especialmente con AWS Lambda.

Requisitos previos
Antes de instalar Serverless Framework, necesitas:

- ✅ Tener instalado Node.js (v14 o superior recomendado)

- ✅ Tener instalado npm (v6 o superior)

- ✅ Tener una cuenta de AWS con credenciales configuradas (aws configure)

Puedes verificar si tienes Node.js y npm con:
```bash
node -v
npm -v
```

### Requisitos previos
Antes de instalar Chalice, asegúrate de tener instalado lo siguiente:

- ✅ Python 3.7 o superior

- ✅ pip (el gestor de paquetes de Python)

- ✅ Una cuenta de AWS (capa libre) con credenciales configuradas (aws configure)

- ✅ Git (opcional, pero recomendado)

### Crear un entorno virtual (opcional, pero recomendado)

```bash
python3 -m venv .venv
uv venv #si deseas usar uv
source .venv/bin/activate  # En Linux o macOS
.venv\Scripts\activate     # En Windows
```
```bash
npm install -g serverless
```
Verifica la instalación:

```bash
serverless --version
Salida esperada:
```
```yaml
Framework Core: 3.x.x
Plugin: 6.x.x
SDK: 4.x.x
```
También puedes usar el comando abreviado:

```bash
sls --version
```

### Crear un nuevo proyecto Serverless

```bash
serverless create --template aws-python --path mi-api-serverless
cd mi-api-python
```



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

### Instala dependencias si es necesario:
```bash
pip install -r requirements.txt
```
### Desplegar AWS
```bash
sls deploy
```
### Salida

```bash
endpoints:
  GET - https://xxxxx.execute-api.us-east-1.amazonaws.com/dev/hello
functions:
  hello: mi-api-serverless-dev-hello
```

### Invocar la función desde la línea de comandos
```bash
sls invoke -f hello
```
### Eliminar los recursos de AWS
```bash
sls remove
```
Esto borra todos los recursos creados (Lambda, API Gateway, roles, etc.).