# 🔐 SSH + Git Setup (macOS)

Guía de referencia rápida para configurar **llaves SSH y Git** en un Mac nuevo
(GitHub personal + GitLab corporativo)

---

## 🎯 ¿Cuándo usar esta guía?

* Mac nuevo
* Mac formateado
* Cambio de equipo
* “No me acuerdo cómo era lo de las llaves SSH”

---

## 1️⃣ Verificar Git y Homebrew

```bash
git --version
which git
```

Si Git apunta a `/usr/bin/git`, instalar versión actual con Homebrew:

```bash
brew install git
```

Verificar nuevamente:

```bash
which git
# debería mostrar: /opt/homebrew/bin/git
```

---

## 2️⃣ Verificar si ya existen llaves SSH

```bash
ls -la ~/.ssh
```

Si **NO existen** archivos tipo `id_ed25519_*`, crear llaves nuevas.

---

## 3️⃣ Crear llaves SSH (una por proveedor)

### GitHub – cuenta personal

```bash
ssh-keygen -t ed25519 -C "correo@gmail.com" -f ~/.ssh/id_ed25519_github
```

Presionar **Enter** para passphrase (o definir una si se desea).

---

### GitLab – cuenta corporativa

```bash
ssh-keygen -t ed25519 -C "correo@empresa.com" -f ~/.ssh/id_ed25519_gitlab
```

---

## 4️⃣ Agregar llaves al SSH Agent

Iniciar el agente:

```bash
eval "$(ssh-agent -s)"
```

Agregar llaves:

```bash
ssh-add ~/.ssh/id_ed25519_github
ssh-add ~/.ssh/id_ed25519_gitlab
```

Ver llaves cargadas:

```bash
ssh-add -l
```

---

## 5️⃣ Configurar archivo SSH (`~/.ssh/config`)

Crear o editar el archivo:

```bash
nano ~/.ssh/config
```

Contenido recomendado:

```ssh
# GitHub - Personal
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_github
  IdentitiesOnly yes

# GitLab - Corporativo
Host gitlab.com
  HostName gitlab.com
  User git
  IdentityFile ~/.ssh/id_ed25519_gitlab
  IdentitiesOnly yes
```

Guardar:

* `Ctrl + O`
* `Enter`
* `Ctrl + X`

---

## 6️⃣ Copiar las llaves públicas

### GitHub

```bash
cat ~/.ssh/id_ed25519_github.pub
```

Copiar todo el contenido.

En GitHub:

* Settings → SSH and GPG keys → New SSH key
* Title: `MacBook - Personal`
* Key type: Authentication

---

### GitLab

```bash
cat ~/.ssh/id_ed25519_gitlab.pub
```

En GitLab:

* Preferences → SSH Keys
* Title: `MacBook - Corporativo`

---

## 7️⃣ Probar conexión SSH

```bash
ssh -T git@github.com
ssh -T git@gitlab.com
```

Resultado esperado:

* GitHub: mensaje de bienvenida
* GitLab: mensaje indicando usuario autenticado

---

## 8️⃣ Configurar identidad Git (global)

```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "correo@gmail.com"
```

> Para repos corporativos, la identidad se ajusta **por repositorio**.

Ejemplo dentro del repo:

```bash
git config user.email "correo@empresa.com"
```

---

## 9️⃣ Verificación final

```bash
git config --list
git remote -v
```

---

## 🧠 Notas rápidas

* GitHub y GitLab usan **la misma URL SSH**, la selección de llave la hace `~/.ssh/config`
* No es necesario regenerar llaves si las copias desde otro Mac
* Cada Mac puede tener títulos distintos en GitHub/GitLab

---

## 🆘 Comandos de emergencia

Eliminar llaves del agent:

```bash
ssh-add -D
```

Recargar llaves:

```bash
ssh-add ~/.ssh/id_ed25519_github
ssh-add ~/.ssh/id_ed25519_gitlab
```

---

🛡️ *Documento de recuperación rápida – configuración SSH y Git en macOS.*
