# Tu primer Pull Request en 7 pasos

Todo desde la terminal, sin SSH. Necesitás una cuenta en [github.com](https://github.com).

> **Terminal:** en Windows usá *PowerShell*; en macOS, *Terminal*; en Linux, tu terminal habitual.

## 1. Instalar Git y GitHub CLI

**Windows**
```powershell
winget install Git.Git GitHub.cli
```

**macOS** (requiere [Homebrew](https://brew.sh))
```bash
brew install git gh
```

**Linux (Debian/Ubuntu)**
```bash
sudo apt update && sudo apt install -y git gh
```

**Cerrá y volvé a abrir la terminal**, y verificá:
```bash
git --version
gh --version
```

Presentate ante Git (una sola vez, usá el email de tu cuenta de GitHub):
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

## 2. Loguearte en GitHub

```bash
gh auth login
```

Elegí estas opciones con las flechas y `Enter`:

1. `GitHub.com`
2. `HTTPS`
3. `Y` (autenticar Git con tus credenciales de GitHub)
4. `Login with a web browser`

Copiá el código de 8 caracteres, apretá `Enter`, pegalo en el navegador y autorizá. Verificá:
```bash
gh auth status
```

## 3. Hacer un fork y clonarlo

Un *fork* es tu copia personal del repo, en tu cuenta.

```bash
gh repo fork leoturzi/github-demo --clone
cd github-demo
```

## 4. Crear una branch y hacer un cambio mínimo

Creá tu rama (no trabajes directo en `main`):
```bash
git switch -c mi-primer-cambio
```

Creá un archivo con tu usuario (reemplazá `TU_USUARIO`; así tu PR no choca con el de nadie):
```bash
echo "Hola, soy TU_USUARIO" > hola-TU_USUARIO.txt
```

## 5. Stage de los cambios

```bash
git add .
git status
```

`git status` debe mostrar tu archivo en verde: ya está en el *staging*.

## 6. Commit y push

```bash
git commit -m "Agrego mi saludo"
git push -u origin mi-primer-cambio
```

## 7. Abrir el Pull Request

```bash
gh pr create --title "Agrego mi saludo" --body "Mi primer PR"
```

Si pregunta a qué repo enviarlo, elegí `leoturzi/github-demo`. Al terminar te imprime el link de tu PR. ¡Listo! 🎉

---

### Si algo falla

| Problema | Solución |
|----------|----------|
| `git` o `gh` no se reconoce | Cerrá y reabrí la terminal |
| `Author identity unknown` al hacer commit | Repetí los dos `git config` del paso 1 |
| `gh` pide login de nuevo | Ejecutá `gh auth login` otra vez |
