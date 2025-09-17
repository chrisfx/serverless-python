# Recomendaciones para exponer APIs Serverless

Estas son buenas prácticas y herramientas recomendadas para desarrollar y exponer APIs de manera profesional, segura y eficiente.

---

## 🐧 Usa un entorno Linux (o similar)

- Se recomienda trabajar en **Linux**, **macOS** o **WSL2 en Windows** para facilitar la compatibilidad con herramientas de desarrollo modernas.
- Linux/WSL2 mejora el soporte de Docker, Python, Git, y herramientas de red.

---

## 🐍 Usa entornos virtuales con `uv` o `venv`

- Aísla las dependencias del proyecto usando entornos virtuales.
- Recomendado: [`uv`](https://github.com/astral-sh/uv) por su velocidad y compatibilidad.

```bash
# Crear entorno virtual con uv
uv venv
source .venv/bin/activate
```

- Alternativa tradicional:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

## ⚙️ Configuración de AWS

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
