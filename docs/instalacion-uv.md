# Instalación de `uv` para entornos virtuales en Python

[`uv`](https://github.com/astral-sh/uv) es una herramienta rápida y moderna para gestionar entornos virtuales y dependencias en proyectos Python. Puede reemplazar a `venv` y `pip` con mejor rendimiento y características adicionales.

---

## 🔧 Requisitos previos

- Tener Python 3.8 o superior instalado
- Acceso a terminal (Linux/macOS) o PowerShell (Windows)

---

## 💻 Linux

```bash
curl -Ls https://astral.sh/uv/install.sh | bash
```

Esto instalará `uv` en tu sistema y lo ubicará en `~/.cargo/bin` o `/usr/local/bin`.

Verifica la instalación:

```bash
uv --version
```

---

## 🍎 macOS

### Opción 1: Con Homebrew

```bash
brew install astral-sh/uv/uv
```

### Opción 2: Script oficial

```bash
curl -Ls https://astral.sh/uv/install.sh | bash
```

Verifica la instalación:

```bash
uv --version
```

---

## 🪟 Windows

1. Abre PowerShell como administrador.
2. Ejecuta:

```powershell
irm https://astral.sh/uv/install.ps1 | iex
```

3. Cierra y vuelve a abrir la terminal para que se reconozca el comando `uv`.

Verifica:

```powershell
uv --version
```

---

## 🧪 Crear un entorno virtual con `uv`

```bash
uv venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate   # Windows
```

---

## 📦 Instalar dependencias

```bash
uv pip install requests fastapi
```

Para congelar dependencias:

```bash
uv pip freeze > requirements.txt
```

---

## 🔁 Actualizar `uv`

```bash
uv self-update
```

---

## ❌ Desinstalar `uv`

Borra el ejecutable desde el directorio donde fue instalado (por defecto en `~/.cargo/bin` o `%USERPROFILE%\.cargo\bin`).

---

¿Quieres más ejemplos con FastAPI, Flask u otro framework?
