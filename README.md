# 🐳 Informe Técnico — Docker

## Autor: Andrés Felipe Padilla  
## Proyecto: **Tarea - Introducción a Docker**

---

### 📚 1. Resumen de los conceptos aprendidos

Durante la serie de videos sobre **Docker**, se abordaron los siguientes temas clave:

#### **Video 1: Introducción a Docker**
- Docker es una plataforma que permite **crear, ejecutar y administrar contenedores** que aíslan aplicaciones y sus dependencias.
- Los contenedores son más **ligeros y eficientes** que las máquinas virtuales porque comparten el mismo kernel del sistema operativo.
- Se introdujeron los conceptos de **imagen**, **contenedor** y **registro (Docker Hub)**.

#### **Video 2: Imágenes y Contenedores**
- Una **imagen** es una plantilla inmutable que contiene el sistema base, librerías y configuraciones.
- Un **contenedor** es una instancia en ejecución de una imagen.
- Comandos básicos aprendidos:
  ```bash
  docker pull ubuntu
  docker run -it ubuntu bash
  docker ps -a
  docker stop <id>
  docker rm <id>
  ```

#### **Video 3: Dockerfile y automatización**
- El **Dockerfile** define los pasos para construir una imagen personalizada.
- Se exploraron instrucciones como `FROM`, `RUN`, `COPY`, `WORKDIR` y `CMD`.
- Ejemplo básico:
  ```dockerfile
  FROM python:3.11
  WORKDIR /app
  COPY . .
  RUN pip install -r requirements.txt
  CMD ["python", "main.py"]
  ```

#### **Video 4: Docker Compose**
- **Docker Compose** permite definir y ejecutar múltiples contenedores con un solo archivo `docker-compose.yml`.
- Es útil para proyectos con varios servicios (por ejemplo, una app + base de datos).
- Comandos comunes:
  ```bash
  docker-compose up -d
  docker-compose down
  ```

---

### 💭 2. Reflexiones personales

- **Ventajas:**
  - Facilita la configuración de entornos de desarrollo.
  - Mejora la portabilidad de las aplicaciones entre distintos sistemas.
  - Evita conflictos de dependencias (“funciona en mi máquina” deja de ser un problema).

- **Desafíos:**
  - Puede ser confuso al principio por la cantidad de comandos y conceptos.
  - Es necesario entender temas de redes y volúmenes.
  - El tamaño de las imágenes puede crecer rápidamente si no se optimizan.

- **Uso práctico:**
  - Ideal para pruebas rápidas, microservicios y despliegue continuo.
  - Personalmente, me pareció una herramienta muy útil para organizar mis proyectos y evitar instalar librerías directamente en mi sistema.

---

### ⚙️ 3. Ejemplo práctico: Mini Proyecto con Docker

#### Objetivo:
Contenerizar una aplicación Python simple que imprime un mensaje desde un contenedor.

**Estructura del proyecto:**
```
docker-example/
│
├── app/
│   └── main.py
│
├── Dockerfile
└── docker-compose.yml
```

**`app/main.py`**
```python
print("Hola desde Docker 🐳")
```

**`Dockerfile`**
```dockerfile
FROM python:3.11
WORKDIR /app
COPY ./app /app
CMD ["python", "main.py"]
```

**`docker-compose.yml`**
```yaml
version: "3.8"
services:
  app:
    build: .
    container_name: ejemplo_docker
    command: python main.py
```

**Ejecución:**
```bash
docker-compose up --build
```

**Salida esperada:**
```
Hola desde Docker 🐳
```

---

### 🔗 4. Recursos adicionales consultados

- [Documentación oficial de Docker](https://docs.docker.com/)
- [Referencia de Dockerfile](https://docs.docker.com/engine/reference/builder/)
- [Documentación de Docker Compose](https://docs.docker.com/compose/)
- [Tutorial en YouTube: Aprende Docker en 1 hora](https://www.youtube.com/watch?v=pTFZFxd4hOI)
- [Artículo: Diferencias entre imágenes y contenedores](https://www.redhat.com/es/topics/containers/what-is-docker)

---

### 📦 5. Enlace al repositorio

🔗 **Repositorio en GitHub:** [https://github.com/SmartLee1229/tarea](https://github.com/SmartLee1229/tarea)

---
