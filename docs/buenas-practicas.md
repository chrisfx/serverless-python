
---

### 📁 `buenas-practicas.md`

# Buenas prácticas en desarrollo de APIs Serverless

Aplica estas recomendaciones para mejorar la calidad, mantenibilidad y seguridad de tus APIs.

---

## 1. Organización del código

- Sigue una estructura clara: `app/`, `handlers/`, `utils/`
- Usa `requirements.txt` o `pyproject.toml` bien definidos

---

## 2. Uso de entornos separados

- Desarrollo
- Pruebas
- Producción

Utiliza variables de entorno y perfiles de AWS para aislar entornos.

---

## 3. Manejo de errores

- Usa `try/except` con logging claro
- Retorna errores HTTP adecuados (400, 404, 500)

---

## 4. Seguridad

- Nunca subas tus claves de acceso a un repositorio
- Utiliza variables de entorno .env para desarrollo
- Usa AWS Secrets Manager o Parameter Store
- Restringe los permisos de los roles Lambda

---

## 5. Optimización

- Ajusta la memoria y tiempo de ejecución según el uso
- Evita dependencias innecesarias
- Utiliza versiones ligeras de librerías (por ejemplo, `boto3-lite`)

---

## 6. Versionado y despliegue

- Usa Git y CI/CD para automatizar despliegues
- Versiona tus funciones
