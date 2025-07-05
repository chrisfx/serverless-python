## ¿Qué es Chalice?

AWS Chalice es un microframework de Python desarrollado por Amazon para crear y desplegar rápidamente APIs RESTful, funciones Lambda, y event-driven apps sobre AWS Serverless.

  - Similar a Flask, pero diseñado para trabajar directamente con AWS Lambda y API Gateway.


### Ventajas

- 🎯 Simplicidad	Sintaxis muy parecida a Flask, ideal para Pythonistas
- ⚡ Despliegue rápido	Una sola línea despliega todo (chalice deploy)
- 🔗 Integración directa con AWS	Crea automáticamente Lambda + API Gateway
- 🧪 Soporte local	Prueba funciones localmente (chalice local)
- 📂 Estructura mínima	No necesitas definir manualmente archivos de infraestructura (yaml)


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

