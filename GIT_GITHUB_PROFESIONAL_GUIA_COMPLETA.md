# 📚 GIT Y GITHUB PROFESIONAL — GUÍA COMPLETA EN ESPAÑOL

**Nivel:** Principiante a Avanzado  
**Actualizado:** 2026  
**Objetivo:** Dominar Git como un developer profesional

---

## TABLA DE CONTENIDOS

1. [Conceptos Fundamentales](#conceptos-fundamentales)
2. [Instalación y Configuración Inicial](#instalación-y-configuración-inicial)
3. [Comandos Básicos Explicados](#comandos-básicos-explicados)
4. [Flujos de Trabajo Profesionales](#flujos-de-trabajo-profesionales)
5. [Ramas (Branches) y Merges](#ramas-y-merges)
6. [Commits de Calidad](#commits-de-calidad)
7. [GitHub: Configuración y Colaboración](#github-configuración-y-colaboración)
8. [Problemas Comunes y Soluciones](#problemas-comunes-y-soluciones)
9. [Buenas Prácticas Profesionales](#buenas-prácticas-profesionales)
10. [Checklist Diario](#checklist-diario)

---

## CONCEPTOS FUNDAMENTALES

### ¿Qué es Git?

Git es un **sistema de control de versiones descentralizado**. Significa:
- **Descentralizado:** Cada desarrollador tiene una copia completa del proyecto
- **Versionado:** Puedes guardar "snapshots" del código en momentos específicos
- **Rastreable:** Puedes ver quién cambió qué, cuándo y por qué

### ¿Qué es GitHub?

GitHub es una **plataforma en internet** que hospeda repositorios Git. Permite:
- Compartir código con otros developers
- Colaborar en proyectos
- Mostrar tu trabajo (portfolio)
- Contribuir a proyectos open source

### Conceptos Clave

| Término | Significado | Ejemplo |
|---------|-------------|---------|
| **Repository (Repo)** | Carpeta del proyecto con historial de cambios | `js-journey` |
| **Commit** | Una foto del código en un momento específico | `git commit -m "sem1: tipos de datos"` |
| **Branch** | Una rama del código para trabajar sin afectar main | `feature/login`, `bugfix/error-panel` |
| **Remote** | El servidor donde está el repo (GitHub) | `origin` (default) |
| **Clone** | Descargar un repo completo a tu computadora | `git clone <URL>` |
| **Pull** | Descargar cambios del servidor | `git pull origin main` |
| **Push** | Subir cambios a servidor | `git push origin main` |
| **Merge** | Combinar dos branches en uno solo | `git merge feature/login` |
| **Conflict** | Cuando dos cambios se contradicen | Se resuelven manualmente |
| **Pull Request** | Propuesta de cambios para revisar antes de mergear | En GitHub.com |

---

## INSTALACIÓN Y CONFIGURACIÓN INICIAL

### Paso 1: Instalar Git

**Windows:**
```bash
# Descargar de: git-scm.com
# O con Chocolatey:
choco install git
```

**macOS:**
```bash
# Con Homebrew:
brew install git
```

**Linux (Debian/Ubuntu):**
```bash
sudo apt update
sudo apt install git
```

**Verificar instalación:**
```bash
git --version
# Debe mostrar: git version 2.x.x
```

---

### Paso 2: Configuración Global de Git

Configura tu identidad (necesario para todos los commits):

```bash
# Tu nombre (visible en todos tus commits)
git config --global user.name "Tu Nombre Real"

# Tu email (debe ser el mismo de GitHub)
git config --global user.email "tu@email.com"

# Verificar configuración
git config --global --list

# Ver solo usuario y email
git config --global user.name
git config --global user.email
```

---

### Paso 3: Configurar Editor de Texto por Defecto

Cuando Git necesita que escribas mensajes largos:

**Para VSCode:**
```bash
git config --global core.editor "code --wait"
```

**Para Nano (más simple):**
```bash
git config --global core.editor "nano"
```

---

### Paso 4: Configuración Recomendada Adicional

```bash
# Mostrar colores en la terminal (más legible)
git config --global color.ui true

# Configurar git pull por defecto (traer cambios)
git config --global pull.rebase false

# Alias útiles (comandos cortos)
git config --global alias.st status          # git st en lugar de git status
git config --global alias.co checkout        # git co main en lugar de git checkout main
git config --global alias.br branch          # git br para ver branches
git config --global alias.cm "commit -m"     # git cm "mensaje" para commits rápidos
git config --global alias.unstage "reset HEAD --"  # git unstage archivo.js
git config --global alias.last "log -1 HEAD"       # git last para ver último commit

# Ver todos tus alias
git config --global --get-regexp alias
```

---

### Paso 5: Conectar GitHub con SSH (Opcional pero Recomendado)

SSH es más seguro que HTTPS (no necesitas escribir contraseña cada vez).

**Generar clave SSH:**
```bash
ssh-keygen -t ed25519 -C "tu@email.com"
# Presiona Enter para guardar en ubicación por defecto
# Presiona Enter para dejar sin contraseña (o pon una si lo prefieres)
```

**Copiar la clave pública:**
```bash
# En Windows (PowerShell):
type $env:USERPROFILE\.ssh\id_ed25519.pub | clip

# En macOS/Linux:
cat ~/.ssh/id_ed25519.pub | pbcopy
```

**Añadir a GitHub:**
1. Ve a github.com → Settings → SSH and GPG keys
2. New SSH key
3. Pega la clave
4. Click Add SSH key

**Verificar que funciona:**
```bash
ssh -T git@github.com
# Debe mostrar: Hi TU_USUARIO! You've successfully authenticated...
```

---

## COMANDOS BÁSICOS EXPLICADOS

### 1. Inicializar un Repositorio Local

```bash
# Crear carpeta del proyecto
mkdir mi-proyecto
cd mi-proyecto

# Inicializar git (crea carpeta .git oculta)
git init

# Verificar que fue creado
ls -la
# Debe mostrarse: drwxr-xr-x ... .git
```

---

### 2. Estado del Repositorio (VER QUÉ CAMBIÓ)

```bash
# Ver estado actual
git status

# Salida típica:
# On branch main
# 
# No commits yet
# 
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#         index.js
#         README.md

# Versión más corta (menos verbosa)
git status -s
# Salida: ?? index.js
#        ?? README.md
```

**Códigos de estado:**
- `??` = archivo sin seguimiento (untracked)
- `A` = agregado a staging
- `M` = modificado
- `D` = eliminado
- `R` = renombrado

---

### 3. Agregar Cambios (Staging Area)

```bash
# Agregar UN archivo específico
git add index.js

# Agregar TODOS los archivos
git add .

# Agregar archivos específicos (patrón)
git add src/          # Todos en carpeta src/
git add "*.js"        # Todos los .js

# Agregar todo EXCEPTO archivos específicos
git add . --update    # Solo archivos ya tracked

# Ver qué está staged (listo para commit)
git status
# Debe mostrar archivos en verde
```

**Archivo .gitignore** (qué NO agregar nunca):

```bash
# Crear archivo .gitignore en la raíz del proyecto
cat > .gitignore << 'EOF'
# Node.js
node_modules/
package-lock.json
npm-debug.log

# VSCode
.vscode/
*.code-workspace

# Archivos de sistema
.DS_Store
.env
.env.local

# Logs
*.log
logs/

# Carpetas temporales
dist/
build/
temp/
EOF

# Luego: git add .gitignore && git commit -m "add .gitignore"
```

---

### 4. Crear Commits (Guardar Cambios)

```bash
# Commit simple (la forma MENOS profesional)
git commit -m "cambios"
# ❌ NO HAGAS ESTO — es demasiado vago

# Commit PROFESIONAL (lo que debes hacer)
git commit -m "sem1: tipos de datos y conversiones"
# ✅ BIEN — describe QUÉ cambió y POR QUÉ

# Commit con descripción larga (para cambios complejos)
git commit -m "refactor: reorganizar estructura de carpetas" -m "Movidas:
- src/utils/ ahora contiene todas las funciones utilitarias
- src/lib/ para librerías externas
- src/components/ para componentes React

Motivo: mejorar mantenibilidad del proyecto"

# Abrir editor para escribir mensaje
git commit
# Se abre tu editor de texto — escribe el mensaje

# Ver el último commit que hiciste
git log -1
git show HEAD
```

---

### 5. Ver el Historial (Log)

```bash
# Ver últimos commits (salir con 'q')
git log

# Ver en línea (más compacto)
git log --oneline

# Ver últimos N commits
git log -5              # Últimos 5
git log -10 --oneline   # Últimos 10 en línea

# Ver con autor y fecha
git log --pretty=format:"%h %an %ad %s" --date=short

# Ver los cambios en cada commit
git log -p              # Muestra diferencias (diffs)
git log -p -2           # Últimos 2 commits con cambios

# Ver commits de un autor específico
git log --author="Tu Nombre"

# Ver commits con mensaje específico
git log --grep="tipos"  # Busca "tipos" en mensajes

# Ver en gráfico (ramas)
git log --graph --oneline --all

# Ver resumen de cambios por archivo
git log --stat
```

---

### 6. Ver Cambios (Diff)

```bash
# Ver cambios en archivos NO staged (sin agregar)
git diff

# Ver cambios en archivos staged (ya agregados)
git diff --staged
# O también:
git diff --cached

# Ver cambios en UN archivo específico
git diff archivo.js

# Ver cambios entre dos commits
git diff abc123 def456

# Ver cambios entre ramas
git diff main feature/login

# Ver solo los nombres de archivos cambiados (no el contenido)
git diff --name-only
git diff --name-only --staged
```

---

### 7. Deshacer Cambios

#### Deshacer cambios en archivos NO staged:

```bash
# Deshacer cambios en UN archivo
git checkout archivo.js
# O en Git moderno:
git restore archivo.js

# Deshacer TODOS los cambios no staged
git checkout .
# O:
git restore .

# Ver qué se va a deshacer
git diff archivo.js  # Primero mira qué vas a perder
```

#### Deshacer cambios en archivos staged (sacar de staging):

```bash
# Sacar UN archivo del staging
git reset archivo.js
# O:
git restore --staged archivo.js

# Sacar TODOS los archivos del staging
git reset
# O:
git restore --staged .

# Ver qué está staged antes
git status
```

#### Deshacer commits (los más peligrosos):

```bash
# Deshacer el último commit (pero mantener los cambios en staging)
git reset --soft HEAD~1

# Deshacer el último commit (cambios quedan en working directory)
git reset --mixed HEAD~1
# O simplemente:
git reset HEAD~1

# Deshacer el último commit COMPLETAMENTE (🔥 CUIDADO)
git reset --hard HEAD~1

# Deshacer N commits
git reset HEAD~3      # Deshace los últimos 3

# Crear un nuevo commit que DESHACE otro commit (más seguro)
git revert abc123     # Crea un nuevo commit opuesto
```

---

### 8. Renombrar y Eliminar Archivos

```bash
# Renombrar archivo (mantener el historial)
git mv archivo_viejo.js archivo_nuevo.js

# Luego commitea:
git commit -m "refactor: renombrar archivo_viejo a archivo_nuevo"

# Eliminar archivo (mantener el historial)
git rm archivo.js

# Luego commitea:
git commit -m "feat: eliminar archivo obsoleto"

# Eliminar archivo PERO mantener versión local (sin agregar a git)
git rm --cached archivo.js
git commit -m "chore: dejar de rastrear archivo.js"
```

---

## FLUJOS DE TRABAJO PROFESIONALES

### Flujo Básico Diario (El Que Usarás 80% del Tiempo)

```bash
# 1. En la mañana: traer cambios del equipo
git pull origin main

# 2. A lo largo del día: trabajar normalmente
# ... editas archivos ...

# 3. Antes de terminar la sesión: ver qué cambió
git status

# 4. Agregar cambios
git add .

# 5. Crear commit PROFESIONAL
git commit -m "sem1: tipos de datos y conversiones — implementé 15 ejercicios"

# 6. Subir a GitHub
git push origin main

# 7. Verificar que subió correctamente
git log -1  # Ver el último commit
git status  # Debe decir "working tree clean"
```

---

### Flujo con Ramas (Para Proyectos Mayores)

```bash
# 1. Ver en qué rama estás
git branch -v

# 2. Crear rama NUEVA para una característica
git checkout -b feature/nueva-funcionalidad
# O en Git moderno:
git switch -c feature/nueva-funcionalidad

# 3. Trabajar en la rama
# ... editas archivos ...

# 4. Commitear en esta rama
git add .
git commit -m "feat: implementar nueva funcionalidad"
git push origin feature/nueva-funcionalidad

# 5. EN GITHUB: abrir Pull Request (revisión)
# ... otros devs revisan tu código ...

# 6. Mergear a main (después de aprobación)
git checkout main
git pull origin main
git merge feature/nueva-funcionalidad
git push origin main

# 7. Eliminar rama ya mergeada
git branch -d feature/nueva-funcionalidad
git push origin --delete feature/nueva-funcionalidad
```

---

### Flujo de Equipos (Colaboración Profesional)

```bash
# 1. Descargar último código del equipo
git fetch origin
git rebase origin/main
# O simplemente:
git pull --rebase origin main

# 2. Ver ramas del equipo
git branch -a
git branch -r  # Solo remotas

# 3. Trabajar en tu rama local
git checkout -b feature/tu-tarea

# 4. Hacer varios commits PEQUEÑOS Y ATÓMICOS
git add src/archivo1.js
git commit -m "feat: parte 1 de la funcionalidad"

git add src/archivo2.js
git commit -m "feat: parte 2 de la funcionalidad"

# 5. Antes de push, sincronizar con main
git fetch origin
git rebase origin/main

# Si hay conflictos:
# ... resuelve los conflictos en VSCode ...
git add .
git rebase --continue

# 6. Push a tu rama
git push origin feature/tu-tarea -f  # -f porque hicimos rebase

# 7. En GitHub: crear Pull Request
# - Escribe descripción clara
# - Solicita revisión a compañeros
# - Espera aprobación

# 8. Mergear desde GitHub (más seguro)
# O desde línea de comandos:
git checkout main
git pull origin main
git merge feature/tu-tarea
git push origin main
```

---

## RAMAS Y MERGES

### Crear y Cambiar Ramas

```bash
# Ver ramas locales
git branch

# Ver TODAS las ramas (locales + remotas)
git branch -a

# Ver ramas con más información
git branch -v

# Crear rama NUEVA
git branch feature/login

# Crear rama Y cambiar a ella
git checkout -b feature/login
# O en Git moderno:
git switch -c feature/login

# Cambiar a una rama existente
git checkout main
# O:
git switch main

# Cambiar a rama remota (crea local si no existe)
git checkout feature/login-remota
git checkout --track origin/feature/login-remota

# Ver en qué rama estás
git branch --show-current
git rev-parse --abbrev-ref HEAD

# Renombrar rama (local)
git branch -m feature/login-viejo feature/login-nuevo

# Renombrar rama en GitHub
git branch -m feature/login-viejo feature/login-nuevo
git push origin --delete feature/login-viejo
git push origin feature/login-nuevo

# Eliminar rama LOCAL
git branch -d feature/login          # Si está mergeada
git branch -D feature/login          # Forzar eliminación

# Eliminar rama en GITHUB
git push origin --delete feature/login
```

---

### Mergear Ramas

```bash
# 1. Cambiar a rama DESTINO (normalmente main)
git checkout main

# 2. Traer cambios más recientes
git pull origin main

# 3. Mergear la otra rama
git merge feature/login
# Salida exitosa: Merge made by the 'ort' strategy

# 4. Si hay conflictos (incompatibilidades)
# Git mostrará:
# CONFLICT (content): Merge conflict in archivo.js
# Automatic merge failed; fix conflicts and then commit

# 5. Ver conflictos
git status
git diff

# 6. RESOLVER conflictos manualmente en VSCode
# Los conflictos se ven así en el archivo:
# <<<<<<< HEAD
# tu código
# =======
# código de la otra rama
# >>>>>>> feature/login

# Elimina los marcadores y deja el código correcto

# 7. Agregar cambios resueltos
git add archivo.js
git add .

# 8. Crear commit de merge
git commit -m "merge: incorporar feature/login a main"
# No escribas -m — Git abre editor automáticamente

# 9. Push a GitHub
git push origin main

# 10. Ver el merge en el historial
git log --graph --oneline --all
```

---

### Merge vs Rebase (¿Cuál usar?)

```bash
# MERGE (crea un commit de merge visible)
git merge feature/login
# Historial más legible: puedes ver dónde se juntó todo
# Usa esto en: ramas principales, trabajo en equipo

# REBASE (reescribe historial — más limpio pero peligroso)
git rebase main
# Historial más lineal: parece que se hizo todo en secuencia
# Usa esto en: ramas personales, antes de mergear
# NUNCA en ramas compartidas

# Ejemplo de rebase seguro:
git fetch origin
git rebase origin/main
git push origin feature/login -f  # -f porque rebaseamos

# Si rebase falla:
git rebase --abort              # Cancelar rebase
git rebase --continue           # Continuar después de resolver conflictos
git rebase --skip               # Saltar este commit
```

---

## COMMITS DE CALIDAD

### Formato Profesional de Mensajes

```bash
# MALO (evitar):
git commit -m "cambios"
git commit -m "arreglé cosas"
git commit -m "bug fix"

# BIEN (profesional):
git commit -m "feat: implementar login con JWT"
git commit -m "fix: corregir error en cálculo de totales"
git commit -m "docs: actualizar README con instrucciones"

# EXCELENTE (con descripción):
git commit -m "feat: implementar autenticación con JWT" -m "
Cambios:
- Agregué ruta POST /auth/login
- Implementé generación de tokens JWT
- Tokens expiran en 24 horas
- Guardados en httpOnly cookies

Razón:
- Requerimiento de seguridad del proyecto
- JWT es estándar en APIs REST modernas"
```

### Tipos de Commits (Convención Profesional)

Usa estos prefijos para claridad:

```bash
# feat: Nueva característica
git commit -m "feat: agregar formulario de login"

# fix: Corrección de bug
git commit -m "fix: corregir validación de email inválido"

# docs: Cambios en documentación
git commit -m "docs: actualizar guía de instalación"

# style: Cambios de formato (no afectan funcionalidad)
git commit -m "style: aplicar Prettier a todo el código"

# refactor: Reorganizar código (sin cambiar funcionalidad)
git commit -m "refactor: extraer componente de formulario"

# perf: Mejora de rendimiento
git commit -m "perf: optimizar búsqueda con índices de BD"

# test: Agregar o modificar tests
git commit -m "test: agregar tests para validación de email"

# chore: Cambios en herramientas, dependencias
git commit -m "chore: actualizar versión de React a 18.2"

# ci: Cambios en CI/CD
git commit -m "ci: agregar linter a GitHub Actions"
```

---

### Buenas Prácticas de Commits

```bash
# ✅ BIEN: Commits PEQUEÑOS y ATÓMICOS
git add src/components/Login.jsx
git commit -m "feat: crear componente Login"

git add src/services/auth.js
git commit -m "feat: implementar servicio de autenticación"

git add src/pages/LoginPage.jsx
git commit -m "feat: integrar Login en página principal"

# ❌ MALO: Un solo commit gigante con 50 cambios
# (imposible de revertir una sola parte si algo falla)

# ✅ BIEN: Commits frecuentes (al menos 1 por día)
# Esto deja un "heatmap" verde en GitHub que muestra consistencia

# ❌ MALO: Hacer 10 horas de cambios en UN commit
# Si falla algo, tienes que revertir todo

# ✅ BIEN: Escribir mensaje en imperativo
git commit -m "add validación de formulario"  # correcto
# No:
git commit -m "agregué validación"           # evitar
git commit -m "validación agregada"           # evitar

# Ver cambios del último commit
git show

# Ver cambios específicos de un commit
git show abc123def

# Ver cambios en un archivo específico en un commit
git show abc123def -- src/archivo.js

# Editar mensaje del último commit (antes de push)
git commit --amend -m "nuevo mensaje"

# Agregar archivo olvidado al último commit (antes de push)
git add archivo-olvidado.js
git commit --amend --no-edit
```

---

## GITHUB: CONFIGURACIÓN Y COLABORACIÓN

### Configurar GitHub Inicial

```bash
# 1. Crear repositorio en GitHub.com
# Ir a github.com/new
# - Nombre: js-journey
# - Descripción: Mi aprendizaje de JavaScript
# - Public (para portafolio)
# - Crear

# 2. En tu terminal local:
git remote add origin https://github.com/TU_USUARIO/js-journey.git
# O con SSH (si lo configuraste):
git remote add origin git@github.com:TU_USUARIO/js-journey.git

# 3. Renombrar rama main (si es necesario)
git branch -M main

# 4. Primer push
git push -u origin main
# -u significa "set upstream" (conectar rama local con remota)

# 5. Verificar
git remote -v
# origin    https://github.com/TU_USUARIO/js-journey.git (fetch)
# origin    https://github.com/TU_USUARIO/js-journey.git (push)
```

---

### Trabajar con Remotes

```bash
# Ver todos los remotes
git remote -v

# Ver información de un remote
git remote show origin

# Agregar un nuevo remote (para contribuir a otros proyectos)
git remote add upstream https://github.com/OTRO_USUARIO/otro-repo.git

# Cambiar URL del remote
git remote set-url origin https://github.com/TU_USUARIO/nuevo-nombre.git

# Cambiar a SSH
git remote set-url origin git@github.com:TU_USUARIO/js-journey.git

# Eliminar un remote
git remote remove upstream
```

---

### Push y Pull

```bash
# Subir cambios a GitHub (push)
git push origin main

# Subir rama específica
git push origin feature/login

# Subir TODAS las ramas
git push origin --all

# Subir y crear rama remota si no existe
git push -u origin feature/login
# -u conecta la rama local con la remota automáticamente

# Descargar cambios de GitHub (pull = fetch + merge)
git pull origin main

# Descargar sin mergear todavía (fetch)
git fetch origin

# Mergear manualmente después de fetch
git merge origin/main

# Descargar usando rebase (más limpio)
git pull --rebase origin main
# O:
git pull -r origin main

# Ver cambios remotos antes de pullear
git fetch origin
git log --oneline -5 origin/main

# Forzar push (cuidado — puede sobrescribir trabajo de otros)
git push origin main -f

# Push seguro (rechaza si hay cambios remotos)
git push --force-with-lease origin main
```

---

### Pull Requests (Revisión de Código)

```bash
# 1. Crear rama para tu característica
git checkout -b feature/nuevo-boton

# 2. Hacer cambios y commits
git add .
git commit -m "feat: agregar nuevo botón"

# 3. Subir rama
git push -u origin feature/nuevo-boton

# 4. EN GITHUB.COM:
# - Verás un botón "Compare & pull request"
# - Haz click
# - Escribe descripción clara
# - Selecciona reviewers
# - Crea Pull Request

# 5. Después de aprobación:
# - En GitHub: botón "Merge pull request"
# - O desde terminal:

git checkout main
git pull origin main
git merge feature/nuevo-boton
git push origin main

# 6. Eliminar rama después de mergear
git branch -d feature/nuevo-boton
git push origin --delete feature/nuevo-boton
```

---

### Sincronizar con Proyecto Original (Fork)

Si forkeaste un proyecto y quieres actualizar tu fork:

```bash
# 1. Agregar remote al proyecto original
git remote add upstream https://github.com/AUTOR_ORIGINAL/proyecto.git

# 2. Traer cambios del original
git fetch upstream

# 3. Ver rama main del original
git log upstream/main

# 4. Actualizar tu rama main local
git checkout main
git merge upstream/main

# 5. Subir a tu fork en GitHub
git push origin main

# Crear alias para esto:
git config --global alias.sync-fork "!git fetch upstream && git merge upstream/main && git push origin main"

# Luego:
git sync-fork
```

---

## PROBLEMAS COMUNES Y SOLUCIONES

### Problema: "Permission denied (publickey)"

**Causa:** Git no puede conectar a GitHub (problema SSH)

```bash
# Solución 1: Verificar SSH
ssh -T git@github.com

# Si falla, regenerar clave:
ssh-keygen -t ed25519 -C "tu@email.com"

# Solución 2: Cambiar a HTTPS
git remote set-url origin https://github.com/TU_USUARIO/repo.git

# Luego será necesario usar token personal:
# 1. Ir a github.com/settings/tokens
# 2. Generate new token (classic)
# 3. Copiar token
# 4. Cuando pida password, pegar el token (no tu contraseña)
```

---

### Problema: "fatal: refusing to merge unrelated histories"

**Causa:** Intentas mergear dos repos con historias diferentes

```bash
# Solución:
git pull origin main --allow-unrelated-histories
# O:
git merge origin/main --allow-unrelated-histories
```

---

### Problema: "Conflict (content): Merge conflict in archivo.js"

**Causa:** Dos cambios incompatibles en el mismo archivo

```bash
# 1. Ver archivos con conflicto
git status

# 2. Abrir el archivo y buscar:
# <<<<<<< HEAD
# tu código
# =======
# código remoto
# >>>>>>> rama

# 3. Elegir cuál código mantener o combinar ambos

# 4. Agregar cambios
git add archivo.js

# 5. Completar merge
git commit -m "merge: resolver conflictos en archivo.js"
git push

# Si no puedes resolver:
git merge --abort       # Cancelar merge
```

---

### Problema: "Please commit your changes or stash them before switching branches"

**Causa:** Tienes cambios sin commitear

```bash
# Solución 1: Commitear cambios
git add .
git commit -m "feat: cambios"
git checkout otra-rama

# Solución 2: Guardar cambios temporalmente (stash)
git stash
git checkout otra-rama
# Luego traer cambios:
git stash pop

# Ver stashes guardados
git stash list

# Eliminar un stash
git stash drop 0
```

---

### Problema: "How do I undo my last push?"

**Causa:** Subiste un commit que no querías

```bash
# CUIDADO: Solo si nadie más ha descargado

# Opción 1: Revertir commit (crear nuevo commit que lo deshace)
git revert HEAD
git push origin main
# Más seguro — visible en el historial

# Opción 2: Reset remoto (peligroso)
git reset HEAD~1
git push origin main --force-with-lease
# Solo si estás 100% seguro

# Opción 3: Si nadie ha visto:
git push origin HEAD --force-with-lease
```

---

### Problema: "I committed with the wrong email"

**Causa:** Usaste email incorrecto en un commit

```bash
# Si es el último commit:
git commit --amend --author="Nombre <email@correcto.com>"
git push origin main --force-with-lease

# Si es commits antiguos (cambiar historial completo):
# ⚠️ SOLO si trabajas solo en la rama
git filter-branch --env-filter '
if [ "$GIT_COMMITTER_EMAIL" = "email@viejo.com" ]
then
    export GIT_COMMITTER_EMAIL="email@correcto.com"
    export GIT_AUTHOR_EMAIL="email@correcto.com"
fi' -- --all

git push origin --force-with-lease --all
```

---

### Problema: "Large files" error en GitHub

**Causa:** Intentaste subir archivo > 100 MB

```bash
# Git LFS (Large File Storage)
# 1. Instalar:
git lfs install

# 2. Rastrear archivos grandes:
git lfs track "*.psd"
git add .gitattributes

# 3. Agregar archivo:
git add archivo-grande.psd
git commit -m "feat: agregar archivo grande"
git push

# O eliminar archivo del historial:
git rm archivo-grande.psd
git commit -m "remove: eliminar archivo grande"
git push
```

---

## BUENAS PRÁCTICAS PROFESIONALES

### El Heatmap de GitHub (Evidencia Visible)

```bash
# Ver tu contribución:
# github.com/TU_USUARIO

# Cómo mantener el heatmap VERDE:
# ✅ 1 commit por día mínimo
# ✅ Commits distribuidos durante el mes
# ✅ Commits en proyectos públicos (visible para recruiters)

# Ejemplo (tu rutina diaria):
git status
git add .
git commit -m "sem1: tipos de datos"
git push origin main

# NUNCA hagas todos los commits de una semana de una vez
# Parece sospechoso y no muestra consistencia real
```

---

### .gitignore Profesional

```bash
# En la raíz del proyecto, crear .gitignore completo:

# Node.js / npm
node_modules/
package-lock.json
npm-debug.log*
yarn-error.log*
.npm

# Ambiente
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# IDEs
.vscode/
.idea/
*.swp
*.swo
*~
.DS_Store

# Build
dist/
build/
*.tgz
out/

# Testing
coverage/
.nyc_output/

# Logs
logs/
*.log

# Temporal
temp/
tmp/
cache/

# Compilados
*.pyc
__pycache__/

# Específico del proyecto
config.local.js
secrets.json
```

---

### Ramas Profesionales (Estrategia)

```bash
# main: código en PRODUCCIÓN (siempre estable)
# develop: rama de integración (base para features)
# feature/*: características nuevas
# bugfix/*: correcciones
# hotfix/*: urgencias en producción
# release/*: preparación de versión

# Ejemplo flujo completo:
git checkout develop
git pull origin develop

git checkout -b feature/nueva-caracteristica
# ... trabajo ...
git add .
git commit -m "feat: implementar X"
git push -u origin feature/nueva-caracteristica

# En GitHub: Pull Request
# Esperar revisión y aprobación
# Mergear a develop

git checkout develop
git pull origin develop
git merge feature/nueva-caracteristica
git push origin develop

# Cuando es hora de release:
git checkout -b release/v1.0.0 develop
# ... cambios finales ...
git checkout main
git merge release/v1.0.0
git tag v1.0.0
git push origin main --tags
```

---

### Tags y Versiones

```bash
# Crear tag (versión importante)
git tag v1.0.0

# Crear tag anotado (más información)
git tag -a v1.0.0 -m "Version 1.0.0 - Initial release"

# Subir tags a GitHub
git push origin v1.0.0
# O todos:
git push origin --tags

# Ver tags
git tag -l
git tag -l "v1.*"

# Ver info de tag
git show v1.0.0

# Eliminar tag local
git tag -d v1.0.0

# Eliminar tag remoto
git push origin --delete v1.0.0
```

---

### Archivo README.md Profesional

```markdown
# Mi Proyecto JavaScript

Breve descripción de qué hace el proyecto.

## Features
- Característica 1
- Característica 2

## Stack
- JavaScript
- Node.js
- Express

## Instalación

```bash
git clone https://github.com/tu-usuario/proyecto.git
cd proyecto
npm install
```

## Uso

```bash
npm start
```

## Contribuir

1. Fork el proyecto
2. Crea rama (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'feat: Add AmazingFeature'`)
4. Push rama (`git push origin feature/AmazingFeature`)
5. Abre Pull Request

## Licencia

Distribuido bajo licencia MIT. Ver `LICENSE` para más detalles.
```

---

### Colaboración en Equipo

```bash
# 1. Establecer estándares del equipo en .git/config o README:

# Normas de commits:
# - Siempre en inglés
# - Usa prefijo: feat:, fix:, docs:, etc.
# - Mensaje imperativo: "add feature" no "added feature"

# Normas de ramas:
# - main: siempre estable
# - develop: rama de integración
# - feature/nombre-descriptivo: nuevas características
# - bugfix/nombre-descriptivo: correcciones

# Pull Request:
# - Mínimo 1 revisor
# - Checks automatizados deben pasar
# - No mergear tu propio code

# 2. Configurar protecciones en GitHub:
# Ir a Settings → Branches → Add rule
# - Branch name pattern: main
# - Require pull request reviews before merging
# - Require status checks to pass before merging

# 3. Sincronizar frecuentemente:
git fetch origin
git pull origin develop

# 4. Resolver conflictos regularmente (no dejar acumular)
```

---

## CHECKLIST DIARIO

### Mañana (Antes de Empezar)

```bash
# 1. Actualizar código del equipo
git fetch origin
git pull origin develop

# 2. Ver qué pasó (cambios del equipo)
git log --oneline origin/develop ^HEAD -5

# 3. Crear rama para tu tarea
git checkout -b feature/mi-tarea

# Ver estado
git status
```

---

### Durante el Día

```bash
# Cada vez que terminas una pequeña tarea:
git status               # Qué cambió
git diff                 # Ver cambios exactos
git add .
git commit -m "feat: descripción clara de qué hiciste"

# Múltiples commits pequeños es BUENO
# Un megacommit es MALO
```

---

### Final del Día

```bash
# 1. Ver historial de hoy
git log --oneline HEAD~5..HEAD

# 2. Subir código
git push origin feature/mi-tarea

# 3. Verificar que subió
git log -1
git status
# Debe decir: "working tree clean"

# 4. Documentar progreso (opcional)
# echo "- Implementé X, falta Y" >> PROGRESS.md
# git add PROGRESS.md && git commit -m "log: progreso del día"
```

---

### Fin de Semana (Antes de Terminar Sprint)

```bash
# 1. Sincronizar con main/develop
git fetch origin
git rebase origin/develop

# 2. Resolver cualquier conflicto
git status
# ... resolver conflictos ...
git add .
git rebase --continue

# 3. Push final
git push origin feature/mi-tarea -f

# 4. En GitHub: crear o actualizar Pull Request
# Solicitar revisión
# Responder comentarios

# 5. Después de aprobación: mergear
git checkout develop
git pull origin develop
git merge feature/mi-tarea
git push origin develop

# 6. Eliminar rama
git branch -d feature/mi-tarea
git push origin --delete feature/mi-tarea
```

---

## RESUMEN: COMANDOS MÁS USADOS

```bash
# CONFIGURACIÓN
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"

# INICIALIZAR
git init
git clone <URL>

# ESTADO Y CAMBIOS
git status
git diff
git add .
git commit -m "mensaje"

# HISTORIAL
git log
git log --oneline
git log -5

# RAMAS
git branch
git checkout -b rama
git merge rama
git branch -d rama

# REMOTES
git remote -v
git push origin main
git pull origin main
git fetch origin

# DESHACER
git restore archivo.js
git reset HEAD~1
git revert abc123

# TAGS
git tag v1.0.0
git push origin --tags
```

---

## REFERENCIAS ÚTILES

- **Git Official Docs:** https://git-scm.com/doc
- **GitHub Docs:** https://docs.github.com
- **Conventional Commits:** https://www.conventionalcommits.org/
- **Git Flow:** https://nvie.com/posts/a-successful-git-branching-model/
- **GitHub Skills:** https://skills.github.com

---

**Última actualización:** 2026  
**Autor:** Tu Developer Senior  
**Licencia:** MIT — Usa libremente

---

## NOTAS FINALES

- Git es como un superpoder: aprenderlo te cambia la carrera
- Los commits son tu curriculum silencioso (recruiters miran tu GitHub)
- Un mensaje de commit claro = código que otros (y tú en 6 meses) pueden entender
- Commitea frecuentemente: evita desastres y muestra consistencia
- El heatmap verde de GitHub es tu evidencia de disciplina

**Próximo paso:** Practica estos comandos CADA DÍA durante 2 semanas hasta que sean reflejos automáticos.

¡Adelante! 🚀
