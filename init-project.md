# 🧰 Crear y subir un repositorio Git desde consola (macOS)

Guía paso a paso para **iniciar un proyecto desde cero** y publicarlo en **GitHub**, usando únicamente **terminal**.

---

## 1️⃣ Crear carpeta del proyecto

```bash
mkdir nombre-del-repo
cd nombre-del-repo
```

---

## 2️⃣ Inicializar Git

```bash
git init
git branch -M main
```

---

## 3️⃣ Crear archivos iniciales

```bash
touch README.md
```

(Opcional) Crear `.gitignore`:

```bash
touch .gitignore
```

---

## 4️⃣ Primer commit

```bash
git status
git add .
git commit -m "Primer commit"
```

---

## 5️⃣ Crear repositorio en GitHub (web)

En GitHub:

* New repository
* Nombre igual al de la carpeta
* Público o privado
* No agregar README, .gitignore ni licencia

Copiar la URL SSH del repo recién creado:

```text
git@github.com:usuario/nombre-del-repo.git
```

---

## 6️⃣ Conectar repositorio local con GitHub

```bash
git remote add origin git@github.com:usuario/nombre-del-repo.git
git push -u origin main
```

---

## 7️⃣ Flujo de trabajo normal

```bash
git status
git add .
git commit -m "Descripción del cambio"
git push
```

---

## 8️⃣ Verificación rápida

```bash
git remote -v
git branch
git log --oneline
```

---

## 9️⃣ Clonar repositorio existente

```bash
git clone git@github.com:usuario/nombre-del-repo.git
cd nombre-del-repo
```

---

## 🧠 Comandos útiles

```bash
git status
git diff
git log
git show
```

---

🛠️ *Cheatsheet – Git por consola en macOS*
