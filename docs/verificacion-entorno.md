# Verificación del entorno

Antes de comenzar a desarrollar y desplegar APIs Serverless, es importante verificar que todas las herramientas estén correctamente instaladas y configuradas.

## 1. Verificación de herramientas instaladas

### Python

```bash
python --version
```

### pip o uv

```bash
pip --version
# o
uv --version
```

### AWS CLI
```bash
aws --version
```

### Chalice
```bash
chalice --version
```

## 2. Verificación de credenciales AWS

Verifica que tus credenciales están configuradas correctamente:

```bash
aws sts get-caller-identity
```

## 3. Verificación de permisos y región por defecto

```bash
aws configure list
```

---

### Pruebas automáticas (opcional)

- Introduce pytest u otra herramienta para probar funciones Lambda de forma aislada.

###  Monitoreo desde AWS (opcional)

- CloudWatch Logs

- Revisar logs de ejecución

- Métricas de invocación

```bash
aws logs describe-log-groups
aws logs get-log-events --log-group-name ...
```

