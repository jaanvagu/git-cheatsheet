# 🧠 Git Cheatsheet – Uso diario (macOS · GitHub · GitLab · VS Code)

Cheatsheet de **comandos Git y atajos** para trabajar desde **macOS**, usando **GitHub (personal)** y **GitLab (corporativo)**, principalmente desde **VS Code y terminal**.

---

## 🔧 Verificación básica

```bash
git --version
which git
git status
```

---

## 📁 Inicializar un repositorio nuevo

```bash
git init
git branch -M main
```

Primer commit:

```bash
git add .
git commit -m "Primer commit"
```

---

## 🌐 Conectar con repositorio remoto

### GitHub (personal)

```bash
git remote add origin git@github.com:USUARIO/REPO.git
git push -u origin main
```

### GitLab (corporativo)

```bash
git remote add origin git@gitlab.com:GRUPO/SUBGRUPO/REPO.git
git push -u origin main
```

---

## 🔄 Cambiar remoto existente

```bash
git remote rename origin old-origin
git remote add origin NUEVA_URL
```

Ver remotos:

```bash
git remote -v
```

---

## 🧑‍💻 Identidad Git por repositorio

```bash
git config user.name "Jairo Valencia"
git config user.email "correo@dominio.com"
```

Ver configuración activa:

```bash
git config --list
```

---

## 🔑 Probar conexión SSH

```bash
ssh -T git@github.com
ssh -T git@gitlab.com
```

---

## 📌 Flujo diario básico

```bash
git status
git add .
git commit -m "Mensaje del commit"
git push
```

---

## 🧩 Stage (staging area)

Agregar archivo específico:

```bash
git add archivo.py
```

Quitar del stage:

```bash
git restore --staged archivo.py
```

---

## 🧹 Aplicar `.gitignore` cuando ya había archivos trackeados

```bash
git rm -r --cached .
git add .
git commit -m "Aplicar .gitignore"
```

---

## 🌿 Ramas

Listar ramas:

```bash
git branch
```

Crear y cambiar:

```bash
git checkout -b nueva-rama
```

Volver a main:

```bash
git checkout main
```

Merge:

```bash
git merge nueva-rama
```

---

## 📜 Historial

```bash
git log
git log --oneline --graph --all
```

---

## 🧠 Diagnóstico rápido

```bash
git diff
git diff --staged
git status -sb
```

---

## 🧪 Clonar repositorios

```bash
git clone git@github.com:USUARIO/REPO.git
git clone git@gitlab.com:GRUPO/REPO.git
```

---

## 🧰 VS Code (macOS)

* Control de versiones:

  ```text
  ⌘ + Shift + G
  ```

* Terminal integrada:

  ```text
  Ctrl + `
  ```

* Commit desde VS Code:

  * Escribir mensaje
  * ✔ Commit
  * Push desde la barra inferior

---

🛡️ *Cheatsheet operativo para trabajo diario en seguridad, compliance y desarrollo.*
