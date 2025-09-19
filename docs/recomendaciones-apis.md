# Preparación del entorno de desarrollo

Herramientas recomendadas y buenas prácticas para desarrollar y exponer **APIs Serverless**.

---

## 🐧 Usa un entorno Linux (o similar)

- Se recomienda trabajar en **Linux**, **macOS** o **WSL2 en Windows** para facilitar la compatibilidad con herramientas de desarrollo modernas.
- Linux/WSL2 mejora el soporte de Docker, Python, Git, y herramientas de red.

---

## 🐍 Usa entornos virtuales con `uv` o `venv`

- Aísla las dependencias del proyecto usando entornos virtuales.
- Recomendado **Python** 3.10 o superior.
- Recomendado: [`uv`](https://github.com/astral-sh/uv) por su velocidad y compatibilidad.
- Instalación [`uv`](https://chrisfx.github.io/serverless-python/instalacion-uv/) 

```bash
# Crear entorno virtual con uv
uv venv
# Activar el entorno virtual dentro del folder contenedor del .venv
source .venv/bin/activate
# Desactivar
deactivate
```

- Alternativa tradicional virtual environment:
```bash
# Crear entorno virtual
python3 -m venv .venv
# Activar el entorno virtual dentro del folder contenedor del .venv
source .venv/bin/activate
# Desactivar
deactivate
```

---



## ⚙️ Configuración de AWS

- Configuración [`AWS`](https://chrisfx.github.io/serverless-python/aws-setup/)


```bash
aws configure
# enter AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, region
```

---

## 📈 Observabilidad

- Usa logs estructurados.
- Agrega monitoreo con herramientas como:
  - Prometheus + Grafana
  - Sentry, Datadog, AWS CloudWatch

---

## ✅ Buenas prácticas adicionales

- Usa `.env` y no subas claves sensibles al repositorio.
- Usa Git con ramas bien definidas (`main`, `dev`, `feature/*`).
- Automatiza despliegues con CI/CD (GitHub Actions, GitLab CI, etc.).
