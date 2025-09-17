## AWS Configuración de credenciales

```bash
aws configure
# enter AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, region
```

### Ingresar los datos requeridos

```bash
AWS Access Key ID [None]: TU_ACCESS_KEY
AWS Secret Access Key [None]: TU_SECRET_KEY
Default region name [None]: us-east-1
Default output format [None]: json
```

Esto crea el archivo de configuración en:

Linux/macOS/WSL2: ~/.aws/credentials y ~/.aws/config

### Estructura de los archivos generados

~/.aws/credentials

```ini
[default]
aws_access_key_id = TU_ACCESS_KEY
aws_secret_access_key = TU_SECRET_KEY
```

~/.aws/config

```ini
[default]
region = us-east-1
output = json
```

Verificar conexión a AWS

Ejecuta un comando básico como prueba:

```bash
aws sts get-caller-identity
```

Salida esperada:

```json
{
    "UserId": "AIDXXXXXXXXXXXXXXX",
    "Account": "123456789012",
    "Arn": "arn:aws:iam::123456789012:user/tu-usuario"
}
```

### Perfiles adicionales (opcional)

Puedes agregar múltiples perfiles editando los archivos manualmente:

~/.aws/credentials

```ini
[default]
aws_access_key_id = TU_ACCESS_KEY
aws_secret_access_key = TU_SECRET_KEY

[perfil-dev]
aws_access_key_id = TU_DEV_ACCESS_KEY
aws_secret_access_key = TU_DEV_SECRET_KEY
```

```ini
[default]
region = us-east-1
output = json

[profile perfil-dev]
region = us-west-2
output = yaml
```

### Notas adicionales

* Para usar el entorno WSL2, asegúrate de que el subsistema tenga acceso a internet.

* Si usas zsh o fish, asegúrate de que $HOME/.aws esté correctamente accesible.

* Puedes usar variables de entorno en lugar de archivos de configuración:

```bash
export AWS_ACCESS_KEY_ID=TU_ACCESS_KEY
export AWS_SECRET_ACCESS_KEY=TU_SECRET_KEY
export AWS_DEFAULT_REGION=us-east-1
```


