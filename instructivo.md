# Tu primer Pull Request en 7 pasos

Terminal para Git y el login (sin SSH), y la web de GitHub para abrir el Pull Request. Necesitás una cuenta en [github.com](https://github.com).

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

Sumate al muro de participantes creando **a mano** un archivo de texto:

1. Abrí la carpeta `github-demo` en el explorador de archivos (Windows: `explorer .` · macOS: `open .` · Linux: `xdg-open .`) y entrá en `participantes`.
2. Creá ahí un archivo de texto llamado **`TU_USUARIO.txt`**, con **tu usuario de GitHub** tal cual está en tu perfil (ej.: `octocat.txt`). Solo letras, números y guiones, sin espacios.
3. Escribí `Hola` adentro y guardalo.

Cada persona crea un archivo distinto, así los PRs no chocan entre sí.

> **Ojo con la extensión:** que termine en `.txt` una sola vez, no `.txt.txt`. En Windows activá *Ver → Mostrar → Extensiones de nombre de archivo*. En macOS, si usás TextEdit, elegí *Formato → Convertir en texto plano* antes de guardar.

## 5. Stage de los cambios

```bash
git add .
git status
```

`git status` debe mostrar `participantes/TU_USUARIO.txt` en verde (con tu usuario, sin `.txt.txt`): ya está en el *staging*. Si el nombre está mal, renombrá el archivo y repetí `git add .`.

## 6. Commit y push

```bash
git commit -m "Sumo mi usuario al muro"
git push -u origin mi-primer-cambio
```

## 7. Abrir el Pull Request

Abrí tu fork en el navegador:
```bash
gh repo view --web
```

1. Hacé clic en el botón verde **Compare & pull request** (aparece arriba, en el aviso amarillo).
2. Verificá que diga: base `leoturzi/github-demo` · `main` ← compare `TU_USUARIO/github-demo` · `mi-primer-cambio`.
3. Poné el título "Sumo mi usuario al muro" y hacé clic en **Create pull request**.

¡Listo! 🎉

**¿Y ahora?** Cuando tu PR sea mergeado, abrí la [presentación](https://leoturzi.github.io/github-demo/), andá a la pestaña **Tu turno** y buscá tu avatar en el muro.

---

### Si algo falla

| Problema | Solución |
|----------|----------|
| `git` o `gh` no se reconoce | Cerrá y reabrí la terminal |
| `Author identity unknown` al hacer commit | Repetí los dos `git config` del paso 1 |
| `gh` pide login de nuevo | Ejecutá `gh auth login` otra vez |
