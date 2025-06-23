## Tabla comparativa (Chalice vs Framework vs SAM)

### 📊 Comparativa: Chalice vs SAM vs Serverless Framework

| Característica                  | AWS Chalice 🐍             | AWS SAM 📦                    | Serverless Framework ⚙️      |
|--------------------------------|----------------------------|-------------------------------|-------------------------------|
| Lenguaje principal             | Python                     | Multilenguaje (YAML + Python) | Multilenguaje                |
| Complejidad                    | Baja                       | Media                         | Media-Alta                   |
| IaC (infraestructura como código) | Parcial (automática)     | Completa (YAML + CFN)         | Completa (`serverless.yml`)  |
| Despliegue simple              | ✅ `chalice deploy`         | ✅ `sam deploy --guided`      | ✅ `sls deploy`               |
| Pruebas locales                | ✅ `chalice local`          | ✅ `sam local` (con Docker)   | Requiere plugins             |
| Multi-cloud                    | ❌ Solo AWS                | ❌ Solo AWS                   | ✅ AWS, Azure, GCP           |
| Comunidad y soporte            | Media                      | Alta (AWS oficial)            | Muy alta (activa)            |
| Ideal para...                  | Prototipos, MVPs           | Flujo CI/CD en AWS            | Apps grandes, complejas      |


## ¿Cuándo usar cada uno?

### 🚀 [Chalice](https://github.com/aws/chalice)
- Ideal si trabajas **solo con Python**.
- Perfecto para **prototipos rápidos** o **APIs pequeñas**.
- Muy fácil de aprender y usar.
- Opinado y limitado: menos flexible que otros frameworks.

> ✅ Úsalo si quieres rapidez y simplicidad para construir y probar funciones Lambda en minutos.

---

### 🧰 [AWS SAM (Serverless Application Model)](https://docs.aws.amazon.com/serverless-application-model/)
- Herramienta oficial de AWS.
- Ofrece **control total sobre el despliegue** y configuración.
- Se integra bien con **CloudFormation**, IAM, CI/CD y CodePipeline.
- Más detallado y robusto, pero también más complejo.

> ✅ Úsalo si trabajas exclusivamente en AWS y necesitas una herramienta poderosa para proyectos profesionales y complejos.

---

### 🌐 [Serverless Framework](https://www.serverless.com/)
- Framework multi-nube (AWS, Azure, GCP).
- Soporta **plugins, extensiones** y **infraestructura como código**.
- Excelente para equipos que buscan escalabilidad, organización modular y despliegues integrados.
- Amplia comunidad y documentación.

> ✅ Úsalo si necesitas **flexibilidad, plugins personalizados** o si tu equipo trabaja con distintas nubes o entornos complejos.

---

### 📌 Conclusión rápida

| Herramienta           | Nivel de complejidad | Ideal para                                 |
|------------------------|----------------------|---------------------------------------------|
| Chalice               | 🟢 Bajo               | Prototipos rápidos con solo Python          |
| AWS SAM               | 🟡 Medio              | Control total en proyectos AWS avanzados    |
| Serverless Framework  | 🔵 Medio-Alto         | Flexibilidad multi-nube y arquitecturas serias |



## Pros y contras en puntos clave