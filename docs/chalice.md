## ¿Qué es Chalice?

AWS Chalice es un microframework de Python desarrollado por Amazon para crear y desplegar rápidamente APIs RESTful, funciones Lambda, y event-driven apps sobre AWS Serverless.

  - Similar a Flask, pero diseñado para trabajar directamente con AWS Lambda y API Gateway.


### Ventajas

- 🎯 Simplicidad	Sintaxis muy parecida a Flask, ideal para Pythonistas
- ⚡ Despliegue rápido	Una sola línea despliega todo (chalice deploy)
- 🔗 Integración directa con AWS	Crea automáticamente Lambda + API Gateway
- 🧪 Soporte local	Prueba funciones localmente (chalice local)
- 📂 Estructura mínima	No necesitas definir manualmente archivos de infraestructura (yaml)


- AWS Chalice es un framework de Python que permite crear y desplegar aplicaciones Serverless utilizando AWS Lambda y API Gateway de forma sencilla.

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

### Instalar Chalice
```bash
pip install chalice
```
- Verificar instalación
```bash
chalice --version
```

### Configurar tus credenciales de AWS

```bash
aws configure
```

Y proporciona:

- Access Key ID

- Secret Access Key

- Región predeterminada (por ejemplo: us-east-1)

- Formato de salida (puedes dejarlo en blanco o usar json)

### Comando para iniciar (chalice new-project)

```bash
chalice new-project myapi
cd myapi
```
Esto crea una estructura mínima:
```bash
myapi/
├── .chalice/          # Configuración AWS y stages
├── app.py             # Tu aplicación (punto de entrada)
└── requirements.txt   # Dependencias
```

### Ejemplo básico con 1 endpoint

```python
from chalice import Chalice

app = Chalice(app_name='myapi')

@app.route('/')
def index():
    return {'message': 'Hola Pycon Colombia 2025'}
```

### Instrucciones para probar local o desplegar
#### Ejecutar localmente (localhost:8000)
```bash
chalice local
```
Abre en tu navegador:
http://localhost:8000/

#### Puedes asignar puerto

```bash
chalice local --port 8080
```     

#### Desplegar en AWS

```bash
chalice deploy
```

### Interactuando vía payload

```bash
from chalice import Chalice

app = Chalice(app_name='hello-api')

@app.route('/greet', methods=['POST'], content_types=['application/json'])
def greet_user():
    request = app.current_request
    body = request.json_body
    name = body.get('name', 'Stranger')
    return {"message": f"Hello, how are you {name}?"}


# The view function above will return {"hello": "world"}
# whenever you make an HTTP GET request to '/'.
#
# Here are a few more examples:
#
# @app.route('/hello/{name}')
# def hello_name(name):
#    # '/hello/james' -> {"hello": "james"}
#    return {'hello': name}
#
# @app.route('/users', methods=['POST'])
# def create_user():
#     # This is the JSON body the user sent in their POST request.
#     user_as_json = app.current_request.json_body
#     # We'll echo the json body back to the user in a 'user' key.
#     return {'user': user_as_json}
#    
# curl curl -X POST https://b4xrfemfr2.execute-api.us-west-1.amazonaws.com/api/greet \
#   -H "Content-Type: application/json" \
#   -d '{"name": "ITPython"}'
#
# curl -X POST http://localhost:8000/greet \
#   -H "Content-Type: application/json" \
#   -d '{"name": "ITPy"}'
#
```