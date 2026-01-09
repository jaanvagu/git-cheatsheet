# 🧠 Git Cheatsheet – Uso diario (Mac · GitHub · GitLab · VS Code)

Este documento resume los **comandos Git más usados**, el flujo recomendado y tips clave para trabajar con repositorios **personales y corporativos** desde macOS y VS Code.

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

Crear primer commit:

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

## 🔄 Cambiar remoto existente (muy común)

```bash
git remote rename origin old-origin
git remote add origin NUEVA_URL
```

Verificar:

```bash
git remote -v
```

---

## 🧑‍💻 Identidad por repositorio (personal vs corporativo)

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
git commit -m "Mensaje claro del cambio"
git push
```

---

## 🧩 Staging (stage) explicado

Agregar archivo específico:

```bash
git add archivo.py
```

Quitar del stage:

```bash
git restore --staged archivo.py
```

---

## 🧹 .gitignore (aplicar cambios correctamente)

Si Git ya estaba siguiendo archivos que ahora ignoras:

```bash
git rm -r --cached .
git add .
git commit -m "Aplicar .gitignore correctamente"
```

---

## 🌿 Ramas (básico)

```bash
git branch
git checkout -b nueva-rama
git checkout main
git merge nueva-rama
```

---

## 📜 Historial

```bash
git log
git log --oneline --graph --all
```

---

## 🧠 Comandos útiles de diagnóstico

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

## 🧰 Uso desde VS Code

* Control de versiones: `⌘ + Shift + G`
* Commit desde VS Code:

  * Escribe mensaje
  * ✔ Commit
* Push / Pull desde barra inferior
* Terminal integrada:

```bash
Ctrl + `
```

---

## ⚠️ Buenas prácticas

* No subir credenciales (`.env`, `.json`, `.key`)
* Usar `.gitignore` siempre
* Commits pequeños y claros
* Un repo = un propósito claro

---

## 🏁 Nota final

Este cheatsheet está pensado como **guía rápida de referencia**, no como documentación teórica.
Ideal para volver a Git sin fricción y evitar errores comunes.

---

🛡️ *Security & Compliance mindset applied to code.*
