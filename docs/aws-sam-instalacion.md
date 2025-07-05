# Instalación de AWS SAM (Serverless Application Model)

**AWS SAM** es un framework de infraestructura como código (IaC) que permite desarrollar, probar y desplegar aplicaciones **serverless** en AWS de manera estructurada y sencilla.

## Requisitos previos

Antes de instalar AWS SAM CLI, asegúrate de tener lo siguiente:

- ✅ Cuenta de AWS y credenciales configuradas (`aws configure`)
- ✅ AWS CLI instalado  
- ✅ Docker instalado (requerido para pruebas locales)
- ✅ Git (opcional pero recomendado)

## 1. Instalar la CLI de AWS SAM

### En Linux

```bash
# Descargar la última versión
wget https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip

# Descomprimir
unzip aws-sam-cli-linux-x86_64.zip -d sam-installation

# Instalar
sudo ./sam-installation/install
```

### En macOS

Si usas Homebrew:

```bash
brew tap aws/tap
brew install aws-sam-cli
```

### En Windows

1. Descarga el instalador desde:
   [https://github.com/aws/aws-sam-cli/releases/latest](https://github.com/aws/aws-sam-cli/releases/latest)

2. Ejecuta el instalador `.exe` y sigue los pasos.

## 2. Verificar instalación

```bash
sam --version
```

Ejemplo de salida:

```
SAM CLI, version 1.108.0
```

## 3. Crear un nuevo proyecto

```bash
sam init
```

Luego sigue el asistente para:

- Elegir el runtime (por ejemplo: Python 3.12)
- Plantilla de ejemplo
- Nombre del proyecto

Estructura generada:

```
mi-app/
├── README.md
├── template.yaml
├── events/
├── hello_world/
│   ├── app.py
│   └── requirements.txt
└── tests/
```

## 4. Ejecutar localmente (requiere Docker)

```bash
sam local start-api
```

La API estará disponible en: `http://127.0.0.1:3000/hello`

## 5. Desplegar la aplicación

Primero empaqueta el proyecto:

```bash
sam build
```

Luego despliega:

```bash
sam deploy --guided
```

Esto creará un archivo `samconfig.toml` con tus configuraciones.

## 6. Eliminar los recursos de AWS

Para eliminar lo desplegado:

```bash
aws cloudformation delete-stack --stack-name nombre-del-stack
```
