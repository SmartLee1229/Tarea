# 📁 Informe sobre Git y GitHub

**Autor:** Andrés Felipe Padilla  
**Entrega:** Tarea Git & GitHub

---

## 🧭 Objetivo
Este README explica con palabras propias los principales comandos de **Git**, el proceso paso a paso para enviar cambios a un repositorio en **GitHub**
---

## 1) Principales comandos de Git (explicación y ejemplos)

- `git init`  
  Crea un repositorio Git local en la carpeta actual. Sólo se usa una vez por proyecto.
  ```bash
  git init
  ```

- `git status`  
  Muestra el estado actual del repositorio: archivos modificados, archivos sin trackear y rama actual.
  ```bash
  git status
  ```

- `git add <archivo|.>`  
  Añade archivos al área de preparación (staging area) para que queden listos para el commit.
  ```bash
  git add README.md
  git add .    # añade todos los cambios
  ```

- `git commit -m "mensaje"`  
  Registra los cambios añadidos al staging area en el historial local con un mensaje descriptivo.
  ```bash
  git commit -m "Agrega README inicial con instrucciones"
  ```

- `git branch` / `git branch <nombre>`  
  Lista ramas o crea una nueva rama.
  ```bash
  git branch            # lista ramas
  git branch feature-x  # crea branch 'feature-x'
  ```

- `git checkout <rama>` / `git switch <rama>`  
  Cambia a otra rama existente.
  ```bash
  git checkout feature-x
  # o
  git switch feature-x
  ```

- `git merge <rama>`  
  Fusiona cambios de otra rama en la rama actual.
  ```bash
  git merge feature-x
  ```

- `git remote add origin <url>`  
  Añade un repositorio remoto (por ejemplo, GitHub) con un nombre (aquí `origin`).
  ```bash
  git remote add origin https://github.com/tuusuario/tarea.git
  ```

- `git push <remote> <rama>`  
  Envía los commits locales a un repositorio remoto.
  ```bash
  git push origin main
  ```

- `git pull`  
  Obtiene cambios desde el remoto e intenta fusionarlos con la rama actual.
  ```bash
  git pull origin main
  ```

- `git clone <url>`  
  Descarga (clona) un repositorio remoto a tu máquina local.
  ```bash
  git clone https://github.com/tuusuario/tarea.git
  ```

---

## 2) Proceso paso a paso para enviar cambios a GitHub (ejemplo práctico)

A continuación se muestra un flujo típico desde la creación del proyecto local hasta la publicación en GitHub. Ejecuta los comandos en la terminal dentro de la carpeta del proyecto.

### Paso 0 — Preparar el proyecto local
1. Crea la carpeta del proyecto y ve a ella:
   ```bash
   mkdir tarea-git
   cd tarea-git
   ```
2. (Opcional) Crea un archivo README y un `.gitignore`:
   ```bash
   echo "# Tarea Git" > README.md
   echo "__pycache__/" > .gitignore
   ```


### Paso 1 — Inicializar repositorio Git
```bash
git init
```
- Resultado: aparecerá la carpeta oculta `.git/` y `git status` mostrará que no hay commits aún.

### Paso 2 — Añadir archivos al staging
```bash
git add README.md .gitignore
git status
```
- `git status` debe mostrar los archivos listos para commit (staged).

### Paso 3 — Realizar el primer commit
```bash
git commit -m "Primer commit: agrega README y .gitignore"
```
- `git log --oneline` mostrará un commit.

### Paso 4 — Crear el repositorio remoto en GitHub
1. Entra a GitHub y crea un nuevo repositorio (por ejemplo `tarea`).  
2. No escojas inicializar con README (si ya tienes README local) para evitar conflictos.


Al crear el repositorio GitHub te dará instrucciones; copia la URL HTTPS, por ejemplo:
```
https://github.com/SmartLee1229/tarea.git
```

### Paso 5 — Conectar tu repo local con GitHub (remote)
```bash
git remote add origin https://github.com/SmartLee1229/tarea.git
git branch -M main
```

### Paso 6 — Enviar cambios al remoto (push)
```bash
git push -u origin main
```
- `-u` establece `origin/main` como rama por defecto para futuros `git push` y `git pull`.

### Paso 7 — Verificar en GitHub
- Abre el repositorio en GitHub y verifica que los archivos estén visibles y que el commit apareció.

---

## 3) Capturas de pantalla (instrucciones para generarlas)

Guarda las capturas en la carpeta `screenshots/` con los nombres sugeridos arriba. Aquí tienes métodos rápidos según tu sistema operativo:

- **Windows (Win + Shift + S)**: selecciona área -> guarda desde la app "Recortes y anotación" o pega en un editor y guarda.  
- **macOS (Cmd + Shift + 4)**: selecciona área -> se guarda en el escritorio.  
- **Linux (PrtSc / gnome-screenshot)**: usa `PrtSc` o la herramienta de captura de tu distro.

**Recomendación:** 1) Abre la terminal en la carpeta del proyecto, 2) ejecuta el comando, 3) toma la captura inmediatamente mostrando la salida del comando, 4) guarda en `screenshots/`.

---

## 4) Ejemplo de estructura final del repositorio

```
tarea/                    # repositorio
├── README.md             # este archivo (informe)
├── .gitignore
├── archivo_ejemplo.py
└── screenshots/
    ├── 0_estructura_inicial.png
    ├── 1_git_init.png
    ├── 2_git_add.png
    ├── 3_git_commit.png
    ├── 4_github_new_repo.png
    ├── 5_git_remote_add.png
    ├── 6_git_push.png
    └── 7_github_verificar.png
```

---

## 5) Entrega / Compartir enlace

Sigue estos pasos finales para entregar y compartir el enlace:

1. Asegúrate de que todas las capturas están en `screenshots/` y que `README.md` está actualizado.  
2. Añade y comete los cambios:
   ```bash
   git add README.md screenshots/ .gitignore
   git commit -m "Entrega: informe Git con capturas"
   ```
3. Haz push a GitHub:
   ```bash
   git push origin main
   ```
4. Copia la URL del repositorio (por ejemplo `https://github.com/SmartLee1229/tarea`) y pégala como entrega.


---

## 6) Observaciones finales / Buenas prácticas
- Escribe mensajes de commit claros y concisos.  
- Crea ramas para nuevas funcionalidades y usa `merge` o `pull request` para integrarlas.  
- Añade un `.gitignore` para no subir archivos temporales ni credenciales.  
- Revisa `git status` con frecuencia para evitar sorpresas.

---


