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
    return {'message': 'Hello from Chalice'}
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

