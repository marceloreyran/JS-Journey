# 🚀 GUÍA DEFINITIVA: DOMINAR JAVASCRIPT EN 6 MESES

## es.javascript.info + freeCodeCamp + Herramientas Profesionales + Sistema de Motivación Real

**Autor:** MontDev  
**Tiempo:** 360 horas (2h/día × 180 días)  
**Resultado:** 6+ proyectos en producción + oferta de empleo  
**Última actualización:** 2026

---

## 📑 TABLA DE CONTENIDOS

## Lista de Contenido

1. [La Verdad Cruda](#la-verdad-cruda)
2. [Los 5 Momentos Críticos (y cómo pasarlos)](#los-5-momentos-críticos)
3. [Setup Día 1 — Empieza Hoy](#setup-día-1)
4. [Plan Completo 6 Meses](#plan-6-meses)
5. [Cómo Integrar es.javascript.info + freeCodeCamp](#integración-de-recursos)
6. [Las 4 Herramientas Juntas](#las-4-herramientas)
7. [Todos los Prompts de Gemini](#prompts-gemini)
8. [Sistema de Motivación para Cuando Abandones](#sistema-motivación)
9. [Checklist de Seguimiento](#checklist-seguimiento)

---

## LA VERDAD CRUDA

Hay personas que llevan 6 meses "aprendiendo" JavaScript viendo videos y copiando código.

Siguen sin poder resolver un problema solos.

Luego están los que estudian 6 meses de verdad:

- Leen artículos complejos y resuelven ejercicios antes de ver soluciones
- Escriben código en VSCode, lo rompen, entienden por qué se rompió
- Usan git CADA DÍA, creando un heatmap que es evidencia física
- Publican proyectos en internet con URLs que funcionan
- Aprueban entrevistas técnicas porque entienden por qué funcionan las cosas

**La diferencia NO es talento.**

Es la decisión de aparecer cada día aunque cueste. Ese es literalmente el único factor que importa.

---

## LOS 5 MOMENTOS CRÍTICOS

Si sabes que van a llegar, puedes preparte para pasarlos sin abandonar.

### 🔴 MOMENTO 1: SEMANA 2 — CLOSURES NO TIENEN SENTIDO

**Lo que sientes:** Leíste el artículo dos veces y tu cerebro dice "no entiendo nada".

**La verdad:** Todos sienten eso. Incluso developers con años de experiencia.

**Cómo pasarlo:**

- ❌ NO releas el artículo completo de principio a fin
- ✅ SÍ vuelve SOLO al párrafo que no entendiste
- ✅ Dibuja el entorno léxico en PAPEL (en serio, papel)
- ✅ Usa el debugger de VSCode (F5) para ver el closure en tiempo real
- ✅ Pide a Gemini que lo explique con una analogía que NO sea de código

**Checkpoint antes de avanzar:**

- [ ] Puedo explicar un closure en voz alta a alguien sin ver código
- [ ] Implementé makeCounter() y once() sin mirar el tutorial
- [ ] Usé el debugger para ver las variables del closure

Si no marcaste los 3 checkpoints → vuelve a estudiar closures. Tómately el tiempo.

---

### 🔴 MOMENTO 2: SEMANA 7 — EL EVENT LOOP PARECE IMPOSIBLE

**Lo que sientes:** Lees sobre Promise, setTimeout, async/await y tu cerebro explota.

**La verdad:** El event loop confunde a developers con 10 años de experiencia. Es genuinamente difícil. Por eso es lo más valuado en entrevistas técnicas.

**Cómo pasarlo:**

- ❌ NO tomes 2+ artículos de §11 en una sesión
- ✅ MÁXIMO 2 artículos por sesión
- ✅ Usa latentflip.com/loupe mientras ejecutas tu código
- ✅ Ve el call stack, task queue, microtask queue EN TIEMPO REAL
- ✅ Acepta que puede tomar 2-3 semanas

**Checkpoint antes de avanzar:**
- [ ] Puedo predecir el orden de ejecución de snippets con Promise, setTimeout, queueMicrotask
- [ ] Entiendo POR QUÉ Promise.resolve().then() imprime antes que setTimeout(..., 0)
- [ ] Implementé un módulo HTTP con timeout, reintentos y error handling

---

### 🔴 MOMENTO 3: SEMANA 9 — EL BACKEND SE SIENTE ABSTRACTO

**Lo que sientes:** No hay interfaz visual bonita. Solo JSON. Solo logs en Warp. No ves nada "hacerse".

**La verdad:** Eso es EXACTAMENTE lo que corren en producción las empresas más grandes del mundo. Cada API que consumiste vino de un servidor como el que estás construyendo ahora.

**Cómo pasarlo:**
- Cuando veas JSON en Warp → piensa: "hay un usuario real del otro lado esperando esta respuesta"
- Cuando hagas deploy en Railway (semana 12) → verás tu API en una URL pública
- Ese momento cambia todo

**Checkpoint:**
- [ ] Entiendo fs, streams y EventEmitter de Node.js
- [ ] Mi API está desplegada en Railway con URL pública
- [ ] He probado endpoints desde Warp con curl y REST Client

---

### 🔴 MOMENTO 4: SEMANA 13 — TYPESCRIPT PARECE EXAGERACIÓN

**Lo que sientes:** El compilador señala "errores" que no se ven como errores. Siento que me ataca.

**La verdad:** TypeScript NO está siendo difícil. Está encontrando bugs reales que en JavaScript solo aparecerían en producción, frente a usuarios reales, en el peor momento.

**Cómo pasarlo:**
- Cambia el marco: "El compilador es mi aliado más honesto"
- Cada error de TypeScript que resuelves = un bug que no llegará a producción
- Activa "strict": true desde el inicio — sin excepciones
- Instala Pretty TypeScript Errors para mensajes legibles

**Checkpoint:**
- [ ] Migré código a TypeScript estricto
- [ ] Entiendo generics y cuándo usarlos
- [ ] Publiqué paquete npm en TypeScript estricto

---

### 🔴 MOMENTO 5: MES 3-4 — "NO ESTOY AVANZANDO LO SUFICIENTE"

**Lo que sientes:** Llevas semanas estudiando y sientes que sigues siendo un principiante.

**La verdad:** La comparación es el robo de la alegría. La sensación de "no avanzar" aparece EXACTAMENTE cuando más estás aprendiendo cosas complejas.

**Cómo pasarlo:**
- Abre tu PRIMER COMMIT de la semana 1
- Léelo completo
- Ahora lee lo que escribiste hace 4 semanas
- Esa diferencia es tu progreso REAL

**Checkpoint:**
- [ ] Reconozco la diferencia abismal entre mi código de semana 1 y semana 4
- [ ] Dejé de compararme con developers en internet
- [ ] Me comparo SOLO conmigo mismo hace un mes

---

## SETUP DÍA 1 — EMPIEZA HOY

No mañana. Hoy. El primer commit es lo que convierte intención en acción.

### PASO 1: Instala las herramientas base

```bash
# Descarga e instala (toma 10 minutos):
# VSCode: code.visualstudio.com
# Warp terminal: warp.dev (GRATUITA)
# Node.js v18+: nodejs.org

# Verifica en terminal:
node --version      # debe ser v18+
npm --version       # debe existir
code --version      # debe existir
```

### PASO 2: Instala extensiones de VSCode

Abre VSCode → Ctrl+Shift+X → Busca cada una:

**Instala HOY (Mes 1):**
- ESLint
- Prettier
- Error Lens
- GitLens
- JavaScript ES6 Snippets
- Quokka.js

**Instalarás después (no hoy):**
- Mes 2: Live Server, HTML CSS Support, Path Intellisense
- Mes 3: REST Client, Node.js Extension Pack, DotENV, SQLite Viewer
- Mes 4: Pretty TypeScript Errors, TypeScript Hero, Vitest
- Mes 5-6: ES7+ React Snippets, Tailwind IntelliSense, Markdown Preview Enhanced, Code Snap

### PASO 3: Configura Prettier

En VSCode: Ctrl+Shift+P → "Open User Settings (JSON)"

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.tabSize": 2,
  "editor.wordWrap": "on"
}
```

### PASO 4: Crea tu estructura de proyecto

En Warp (terminal):

```bash
# Crea carpeta raíz
mkdir js-journey
cd js-journey

# Inicializa git DESDE EL PRIMER DÍA
git init
git config user.name "Tu Nombre"
git config user.email "tu@email.com"

# Crea estructura de 6 meses
mkdir -p mes-01/semana-{01,02,03,04}
mkdir -p mes-02/semana-{05,06,07,08}
mkdir -p mes-03/semana-{09,10,11,12}
mkdir -p mes-04/semana-{13,14,15,16}
mkdir -p mes-05/semana-{17,18,19,20}
mkdir -p mes-06/semana-{21,22,23,24}
mkdir -p src/utils src/lib src/components

# Abre en VSCode
code .
```

### PASO 5: Tu primer commit (el más importante)

```bash
# En VSCode, crea archivo README.md:
cat > README.md << 'CONTENT'
# Mi Journey de JavaScript — 6 Meses

Aprendiendo a dominar JavaScript desde cero.

## Herramientas
- es.javascript.info (lectura de base)
- freeCodeCamp (ejercicios interactivos)
- VSCode (escritura)
- Warp (ejecución + git)
- Gemini (revisión y tutor)

## Meta
360 horas en 6 meses = 2 horas cada día

## Progreso
Empezado: $(date)
CONTENT

# Tu primer commit
git add .
git commit -m "inicio: día 1 de mi journey de JavaScript en serio"
```

### PASO 6: Sube a GitHub

1. Ve a github.com → New repository
2. Nombre: "js-journey"
3. Descripción: "Mi aprendizaje de JavaScript — 6 meses, 360 horas, 6+ proyectos"
4. Public (importante: sea público)
5. Create

Luego en Warp:

```bash
git remote add origin https://github.com/TU_USUARIO/js-journey.git
git branch -M main
git push -u origin main

# Verifica
git remote -v
```

### PASO 7: Tu rutina diaria (NO NEGOCIABLE)

Tu estructura de 2 horas será siempre:

| Tiempo | Actividad |
|--------|-----------|
| 0:00 – 0:50 | Lee UN artículo completo de es.javascript.info O freeCodeCamp |
| 0:50 – 1:30 | VSCode: escribe código desde cero, sin copiar |
| 1:30 – 2:00 | Warp: ejecuta y commitea. Luego Gemini: revisa |

**REGLA:** Primero tú solo 90 minutos. LUEGO Gemini. Nunca al revés.

---

## PLAN 6 MESES — COMPLETO Y DETALLADO

### 📘 MES 1: EL MOTOR DE JAVASCRIPT (Semanas 1-4)

**Objetivo:** Entender cómo funciona el lenguaje, no memorizar sintaxis.

**Proporción:**
- es.javascript.info: 70%
- freeCodeCamp: 30%

#### SEMANA 1: Variables, tipos, operadores

**es.javascript.info §2 (lectura base):**
- Hola mundo
- Variables (var, let, const)
- Tipos de datos
- typeof
- Conversiones de tipo
- Operadores básicos y comparaciones
- Operadores lógicos
- Nullish coalescing ??
- if/else y switch
- Bucles while, do…while, for

**freeCodeCamp (ejercicios interactivos):**
- Sección "Aprender a programar"
- Variables y tipos → 5+ ejercicios interactivos
- Haz los ejercicios DESPUÉS de es.javascript.info

**Herramientas esta semana:**
- VSCode: crea `tipos.js` y `operadores.js`
- Quokka.js: muestra resultados inline
- Warp: ejecuta con `node tipos.js`

**Proyecto de la semana:**
```javascript
// mes-01/semana-01/quiz-tipos.js
// 15 expresiones donde PREDICES el resultado ANTES de ejecutar
// Ejemplo:
console.log(1 + "1");           // ¿Qué es esto?
console.log(1 == "1");          // ¿true o false?
console.log(null == undefined); // ¿true o false?
// ... 12 más

// Necesitas 12+ correctas para avanzar
```

**Prompt de Gemini (DESPUÉS de 90 min solo):**
```
Acabo de estudiar tipos de datos en es.javascript.info. 
Dame 7 expresiones JavaScript donde la coerción produzca 
un resultado sorprendente. No me des las respuestas — 
yo predigo cada resultado como comentario, ejecuto en Warp, 
y al final me explicas solo los que fallé.
```

**Commit:**
```bash
git add .
git commit -m "sem1: tipos, operadores y conversiones"
git push
```

---

#### SEMANA 2: Funciones, scope léxico, closures

**es.javascript.info §6 (LECTURA MÁS IMPORTANTE DEL MES):**
- Funciones (introducción y flecha)
- Recursión y pila de llamadas
- Scope de variables, TDZ
- **CLOSURES** ← Leer 2 veces, dibuja en papel, usa debugger
- var vs let vs const
- var (función scope, hoisting)
- call, apply, bind
- Decoradores de función
- setTimeout y setInterval

**freeCodeCamp:**
- "Funciones avanzadas"
- "Closures y scope" → 8+ ejercicios interactivos

**Herramientas críticas:**
- VSCode debugger (F5): pausa adentro de un closure
- Panel Variables: observa el entorno léxico
- Papel: dibuja cómo funciona makeCounter()

**Proyecto de la semana:**
```javascript
// mes-01/semana-02/utils.js
// Implementa SIN mirar el tutorial:
function memoize(fn) { /* closure que cachea resultados */ }
function debounce(fn, ms) { /* closure que espera */ }
function throttle(fn, ms) { /* closure que limita frecuencia */ }
function once(fn) { /* closure que ejecuta una sola vez */ }

// Cada función con comentario que explique el closure internamente
```

**Checkpoint (marcar antes de avanzar):**
- [ ] Expliqué un closure en voz alta sin ver código
- [ ] Implementé makeCounter() desde cero
- [ ] Usé el debugger para ver closure en tiempo real
- [ ] Entiendo por qué los closures "recuerdan" variables

**Prompt de Gemini:**
```
Aquí está mi implementación de makeCounter() y once() [pasa código].
¿Son correctas? ¿Forma más idiomática? ¿Edge cases que faltan?
No me reescribas — señala qué mejorar y por qué.
```

---

#### SEMANA 3: Objetos, prototipos, clases, this

**es.javascript.info §4 + §8 + §9:**
- Objetos (introducción)
- Métodos de objeto y this
- new y constructores
- Optional chaining ?.
- **PROTOTYPES** ← leer ANTES que Clases
- Cadena de prototipos
- Herencia prototípica
- Clases (es azúcar sintáctica)
- extends y super

**freeCodeCamp:**
- "Programación orientada a objetos"
- Prototypes y clases → 10+ ejercicios

**Herramientas:**
- VSCode debugger: observa [[Prototype]] en panel Variables
- Dibuja cadena de prototipos en papel

**Proyecto:**
```javascript
// mes-01/semana-03/herencia.js
// Crea Animal → Mamífero → Perro

// PRIMERO: usando prototipos puros (sin class)
function Animal(nombre) { this.nombre = nombre; }
Animal.prototype.hacer = function() { ... };

// LUEGO: reimplementa con class
class Animal { ... }

// Al final: tests que verifican comportamiento idéntico
```

**Prompt de Gemini:**
```
Dame 7 snippets donde el valor de this sea sorprendente.
No me des respuestas — yo predigo cada uno en VSCode,
ejecuto en Warp, verifico. Al final me explicas los que fallé.
```

---

#### SEMANA 4: Arrays, Map/Set, módulos ES

**es.javascript.info §5 + §13:**
- Arrays y métodos: map, filter, reduce, find, some, every
- Map y Set
- Desestructuración
- Spread operator ...
- Iterables y for…of
- JSON
- Módulos ES (import/export)

**freeCodeCamp:**
- "Estructuras de datos"
- "Arrays avanzados" → 12+ ejercicios

**Proyecto final del mes (TU PRIMER PROYECTO DE PORTFOLIO):**

```
En VSCode crea:
├── src/
│   └── utils/
│       ├── closures.js      (memoize, debounce, throttle, once)
│       ├── arrays.js        (funciones reutilizables con arrays)
│       └── objects.js       (utilidades de objetos)
├── README.md                (explica cada función)
└── package.json             (metadata)
```

**Commit y push:**
```bash
git add .
git commit -m "mes1: librería de utilidades JS completa"
git push
```

**Checklist mes 1:**
- [ ] 4 commits, uno por semana
- [ ] Entiendo closures de verdad
- [ ] Entiendo prototipos y cadena de herencia
- [ ] Entiendo cuándo usar map/filter/reduce
- [ ] Proyecto en GitHub con código real

---

### 🌐 MES 2: DOM Y ASINCRONÍA (Semanas 5-8)

**Objetivo:** Manejar DOM como senior + event loop sin magia.

#### SEMANA 5: DOM — selección, manipulación, delegación

**es.javascript.info Navegador §1-2:**
- Árbol DOM
- Navegar el DOM (parentNode, childNodes, etc)
- Búsqueda: getElementById, querySelector, querySelectorAll
- Modificar: createElement, appendChild, removeChild
- Estilos y clases
- **Burbujeado (bubbling) y captura (capturing)**
- **Delegación de eventos** ← IMPORTANTE para web real

**freeCodeCamp:**
- "DOM y eventos"
- "Selectores CSS en JavaScript" → 8+ ejercicios

**Herramientas:**
- VSCode: instala Live Server
- Browser: F12 → Elements tab

**Proyecto:**
```html
<!-- mes-02/semana-05/index.html -->
<!-- Lista dinámica con delegación de eventos -->
<!-- Agregar, editar inline, eliminar ítems -->
<!-- UN SOLO event listener en el contenedor padre -->
```

---

#### SEMANA 6: Formularios, eventos UI, localStorage

**es.javascript.info §3-4:**
- Propiedades de formularios
- Validación
- Eventos de foco (focus, blur)
- Eventos de teclado
- localStorage y sessionStorage

**freeCodeCamp:**
- "Formularios interactivos"
- localStorage exercises

**Proyecto:**
```
Formulario multi-step sin librerías:
- 3 pasos (datos personales, preferencias, confirmación)
- Validación en tiempo real
- Barra de progreso visual
- Estado persistente en localStorage
- Accesible con Tab y Enter
```

---

#### SEMANA 7: EVENT LOOP, PROMISES, ASYNC/AWAIT ⚠️ CRÍTICA

**⚠️ ESTA ES LA SEMANA MÁS DIFÍCIL — TÓMATE TU TIEMPO**

**es.javascript.info §11 (TODOS los artículos, SIN SALTARME NINGUNO):**
- Introducción a callbacks
- Promesas (introducción)
- Cadena de promesas
- Manejo de errores
- Promise API: all, race, allSettled, any
- **Microtareas y macrotareas (event loop)** ← La explicación del event loop real
- async/await

**NO COMPRIMAS ESTA SEMANA:**
- Máximo 2 artículos por sesión
- 7 días = 3-4 artículos por día

**freeCodeCamp:**
- "Promises y async/await"
- 15+ ejercicios interactivos

**Herramientas CRÍTICAS:**
- latentflip.com/loupe: visualiza call stack, task queue, microtask queue EN TIEMPO REAL mientras tu código ejecuta
- VSCode: ejecuta ejemplos pequeños
- Papel: dibuja el flujo de ejecución

**Proyecto:**
```javascript
// src/lib/http.js
// Wrapper sobre fetch con:
// - Timeout via AbortController
// - Reintentos con backoff exponencial (1s, 2s, 4s)
// - Clasificación de errores (4xx vs 5xx vs red)
// - Cancelación

// Este módulo lo reutilizarás en meses 3, 4, 5
```

**CHECKPOINT CRÍTICO (marca todos antes de avanzar):**
- [ ] Puedo predecir orden de ejecución de snippets con Promise/setTimeout/queueMicrotask
- [ ] Entiendo POR QUÉ Promise.resolve().then() imprime antes que setTimeout(..., 0)
- [ ] Implementé módulo HTTP con timeout y reintentos

**Prompt de Gemini (USAR ESTE SÍ O SÍ):**
```
Dame 6 snippets que mezclen Promise, setTimeout y queueMicrotask
en orden no obvio. No me des respuestas. Yo predigo el orden
de ejecución de cada uno como comentario, ejecuto en Warp,
verifico. Al final me explicas el razonamiento de los que fallé
— incluyendo por qué mi intuición estaba equivocada.
```

---

#### SEMANA 8: PROYECTO DEL MES — SPA SIN FRAMEWORKS

**Proyecto final del mes:**

Una Single Page Application que funcione en internet:
- Routing con History API (sin recargas de página)
- Estado global sin librerías (patrón pub/sub)
- Componentes reutilizables
- Usa tu módulo HTTP de semana 7
- Loading states, error handling en UI
- Deploy en Vercel (URL pública)

**Stack:**
- Vite vanilla JavaScript
- Tus librerías del mes 1
- Tu módulo HTTP
- ES Modules

**Ejemplo de proyectos válidos:**
- HackerNews reader
- News aggregator
- Weather app
- Todo app avanzado
- Pomodoro timer

**Comandos:**
```bash
npm create vite@latest spa-proyecto -- --template vanilla
cd spa-proyecto
npm run dev          # desarrollo local
npm run build        # para production
npx vercel --prod    # deploy en Vercel
```

**Entregable:** URL pública que funciona

---

### 🖥️ MES 3: NODE.JS Y APIs REST (Semanas 9-12)

**Objetivo:** Construir y desplegar API con base de datos y autenticación.

#### SEMANA 9: Node.js core

**nodejs.org/docs:**
- CommonJS vs ESM
- fs/promises
- Streams (readable, writable, transform)
- EventEmitter
- process.env

**freeCodeCamp:**
- "Node.js básico"
- File system exercises

**Proyecto:**
```javascript
// Script Node que lee CSV grande con streams
// Sin cargar TODO en memoria
// Filtra, transforma, escribe resultado
// Mide memoria con process.memoryUsage()
```

---

#### SEMANA 10: Express — arquitectura por capas

**expressjs.com:**
- Middleware pipeline
- Router modular
- Validación Zod
- Error handling centralizado

**Estructura (crea desde HOY):**
```
src/
├── routes/       # Definición de rutas
├── controllers/  # Lógica de las rutas
├── services/     # Lógica de negocio
├── middlewares/  # Validación, auth
├── schemas/      # Schemas Zod
└── types/        # TypeScript types (mes 4)
```

---

#### SEMANA 11: SQLite, JWT, autenticación

**better-sqlite3 + bcrypt + jwt:**
- SQL: CREATE TABLE, SELECT, JOIN, INDEX
- bcrypt (hashing passwords)
- JWT (JSON Web Tokens)
- httpOnly cookies
- Refresh tokens

**Proyecto:**
```javascript
// API con autenticación completa:
// - Registro con validación Zod
// - Login con JWT en httpOnly cookie
// - Logout
// - Middleware de auth
// - Ruta protegida (/perfil)
// - Passwords hasheados con bcrypt
```

---

#### SEMANA 12: Deploy en Railway

**railway.app:**
- Configurar .env
- Deploy desde GitHub
- Variables de entorno en producción
- Logs de producción

**Proyecto final del mes:**
```
API REST de blog DESPLEGADA:
- Usuarios, posts, comentarios
- Auth con JWT
- SQLite
- Arquitectura por capas
- Validación Zod
- Deploy en Railway (URL pública)
- README con curl de ejemplo para cada endpoint
```

**Deploy:**
```bash
npm install -g @railway/cli
railway login
railway up
railway logs --tail
```

---

### 📘 MES 4: TYPESCRIPT Y TESTING (Semanas 13-16)

**Objetivo:** Código de calidad profesional con tipos y tests.

#### SEMANAS 13-14: TypeScript — tipos avanzados

**typescriptlang.org/handbook:**
- Everyday Types
- Narrowing y type guards
- Functions con tipos
- Generics
- Utility types (Partial, Pick, Omit, Record)
- Conditional types
- Discriminated unions

**Herramientas:**
- VSCode: Pretty TypeScript Errors
- Activar "strict": true
- `npx tsc --noEmit` para verificar tipos

**Proyecto:**
```
Migra librería del mes 1 a TypeScript estricto:
- memoize, debounce, throttle, deepClone, groupBy
- Sin ningún 'any'
- Con generics reales
- Publicado en npm
```

---

#### SEMANAS 15-16: Vitest — testing profesional

**vitest.dev:**
- describe, it, expect
- Matchers principales
- Mocking de módulos
- Mock de fetch
- Tests asíncronos
- TDD: rojo → verde → refactor
- Cobertura con --coverage
- CI con GitHub Actions

**Herramientas:**
- VSCode: extensión oficial Vitest
- Warp: `npx vitest --watch`

**Proyecto:**
```
Tests para API del mes 3:
- Tests unitarios de servicios
- Tests de integración con supertest
- Cobertura mínima 80%
- CI con GitHub Actions
- Badge de estado en README
```

---

### ⚛️ MES 5: REACT (Semanas 17-20)

**Objetivo:** Dominar React entendiendo por qué existe cada hook.

#### SEMANAS 17-18: React core

**es.react.dev/learn:**
- Describir la UI
- Añadir interactividad (useState)
- Escape hatches (useEffect, useRef, useContext)
- Custom hooks
- memo, useMemo, useCallback

**freeCodeCamp:**
- "React para principiantes"
- 20+ ejercicios interactivos

**Herramientas:**
- VSCode: ES7+ React Snippets
- React DevTools en navegador
- Crear proyecto: `npm create vite@latest mi-app -- --template react-ts`

**Proyecto:**
```
App fullstack: React + API del mes 3
- Auth completa
- CRUD de posts
- UI con errores
- Loading states
- Deploy en Vercel
```

---

#### SEMANAS 19-20: React Router, React Query, proyecto principal

**tanstack.com/query + reactrouter.com:**
- React Router v6
- useQuery y useMutation
- React Hook Form + Zod
- Tailwind CSS

**Proyecto final del mes — TU PIEZA DE PORTFOLIO MÁS IMPORTANTE:**

```
Proyecto FULLSTACK COMPLETO:

Frontend (React + TypeScript + Vercel):
- React Router v6
- React Query
- React Hook Form + Zod
- Tailwind CSS
- Tests

Backend (Node + Express + Railway):
- Tu API del mes 3

Deploy:
- Frontend: Vercel
- Backend: Railway

Características:
- CRUD completo
- Auth segura
- Error handling
- Loading states
- Tests
- README profesional
```

**Ejemplos válidos:**
- Twitter clon
- Trello clon
- Blog avanzado
- Task manager
- Social network

---

### 💼 MES 6: PORTFOLIO Y EMPLEO (Semanas 21-24)

#### SEMANA 21: Portfolio profesional

**Tareas:**
- [ ] Pulir todos los READMEs
- [ ] Agregar screenshots de cada proyecto
- [ ] Crear portfolio web en React
- [ ] Deploy en Vercel
- [ ] Actualizar LinkedIn

#### SEMANA 22: Entrevistas técnicas

**Tareas:**
- [ ] Estudiar preguntas frecuentes de JS
- [ ] Implementar desde cero: Promise.all, debounce, flatten, deepClone, EventEmitter
- [ ] Practicar algoritmos en LeetCode
- [ ] Simular entrevista con Gemini

#### SEMANAS 23-24: Aplicaciones y seguimiento

**Tareas:**
- [ ] 15+ aplicaciones de empleo (2 por día mínimo)
- [ ] Tabla de seguimiento en `aplicaciones.md`
- [ ] Follow-up a cada aplicación
- [ ] 3 simulaciones de entrevista

**Checklist final:**
- [ ] 6 proyectos reales en GitHub con URLs públicas
- [ ] Heatmap verde de 24 semanas
- [ ] Portfolio web personal
- [ ] Paquete npm publicado
- [ ] Tests en proyectos
- [ ] CI/CD con GitHub Actions
- [ ] 15+ aplicaciones
- [ ] LinkedIn actualizado

---

## INTEGRACIÓN DE RECURSOS: es.javascript.info + freeCodeCamp

**¿Cuál usar en cada semana?**

| Semana | Tema | es.javascript.info % | freeCodeCamp % |
|--------|------|-----|-----|
| 1 | Tipos | 70 | 30 |
| 2 | Closures | 80 | 20 |
| 3 | Prototipos | 75 | 25 |
| 4 | Arrays | 70 | 30 |
| 5 | DOM | 60 | 40 |
| 6 | Formularios | 60 | 40 |
| 7 | Event loop | 90 | 10 |
| 8 | Proyecto | 0 | 0 |
| 9 | Node.js | 50 | 50 |
| 10 | Express | 40 | 60 |
| 11 | SQL/Auth | 30 | 70 |
| 12 | Proyecto | 0 | 0 |

**Flujo en cada semana:**

1. **es.javascript.info primero** — es más profundo, te da el "por qué"
2. **freeCodeCamp después** — ejercicios interactivos, refuerza lo aprendido
3. **Tu código en VSCode** — aplica ambos recursos
4. **Warp y git** — ejecuta y commitea
5. **Gemini** — revisa después de 90 min solo

---

## LAS 4 HERRAMIENTAS JUNTAS

El orden es SAGRADO. Si lo cambias, dejas de aprender.

### 1️⃣ LEES (es.javascript.info + freeCodeCamp)

```
Lee artículo completo de es.javascript.info
    ↓
Cuando llegues a "Ejercicios" → DETÉN
    ↓
Resuelve ejercicios sin ver solución
    ↓
Luego: haz ejercicios de freeCodeCamp del mismo tema
```

### 2️⃣ ESCRIBES (VSCode)

```
Abre archivo nuevo
    ↓
Reescribe el concepto desde cero (sin copiar)
    ↓
Ejecuta. Se rompe. Arréglalo.
    ↓
Usa debugger (F5) para ver línea por línea
    ↓
Entiende POR QUÉ pasó lo que pasó
```

### 3️⃣ EJECUTAS (Warp)

```
node archivo.js
    ↓
Si error: selecciona → Warp AI explica en contexto
    ↓
git add .
git commit -m "tema: descripción"
git push
```

### 4️⃣ REVISAS (Gemini)

```
SOLO después de 90 minutos de trabajo solo
    ↓
"Revisa mi código"
    ↓
"Genera ejercicios adicionales"
    ↓
"Explícalo desde otro ángulo"
```

**REGLA DE ORO:** Primero tú solo. LUEGO Gemini. Nunca al revés.

---

## TODOS LOS PROMPTS DE GEMINI

### MES 1 — Fundamentos

**Semana 1 - Coerción de tipos:**
```
Acabo de estudiar tipos de datos y conversiones en es.javascript.info.
Dame 7 expresiones JavaScript donde la coerción produzca 
un resultado sorprendente.
No me des las respuestas — yo predigo cada resultado 
como comentario en VSCode, ejecuto en Warp, 
y al final me explicas solo los que fallé y el razonamiento.
```

**Semana 2 - Closures:**
```
Aquí está mi implementación de makeCounter() y once() [pasa código].
¿Son correctas conceptualmente?
¿Hay una forma más idiomática?
¿Qué edge cases no estoy cubriendo?
No me reescribas el código — señala solo qué mejorar y por qué.
```

**Semana 3 - this y prototipos:**
```
Dame 7 snippets de JavaScript donde el valor de this sea sorprendente,
ordenados del más simple al más complejo.
No me des las respuestas.
Yo predigo cada uno como comentario en VSCode,
ejecuto en Warp, verifico.
Al final me explicas el razonamiento de los que fallé
y por qué mi intuición estaba incorrecta.
```

**Semana 4 - Datasets:**
```
Dame un array de 20 objetos de productos con:
nombre, categoría, precio (número), stock, disponible (boolean),
calificación 1–5 (decimal).
Voy a practicar map, filter, reduce, find, some, every, sort
en VSCode con Quokka.js.
Solo los datos — sin código de ejemplo.
Los datos deben parecer reales.
```

### MES 2 — DOM y Asincronía

**Semana 5 - Code review DOM:**
```
Tengo este código DOM que funciona correctamente [pasa código].
Actúa como senior developer.
¿Hay anti-patrones, algo ineficiente, algo que no escale,
o algo que cause problemas en el futuro?
No reescribas el código — señala problemas específicos
con su impacto real.
```

**Semana 6 - Formularios:**
```
Voy a construir un formulario multi-step en JS puro.
3 pasos: datos personales, preferencias, confirmación.
Antes de codear: ¿qué validaciones, qué estados,
qué edge cases de UX?
Solo análisis — el código lo escribo yo.
```

**Semana 7 - EVENT LOOP (CRÍTICO):**
```
Dame 6 snippets que mezclen Promise, setTimeout y queueMicrotask
en orden no obvio.
No me des respuestas.
Yo predigo el orden de ejecución de cada uno como comentario
en VSCode, ejecuto en Warp, verifico.
Al final me explicas el razonamiento de los que fallé
— incluyendo por qué mi intuición estaba equivocada.
```

**Semana 8 - SPA arquitectura:**
```
Voy a construir una SPA en JS vanilla sin frameworks.
Necesito routing con History API, estado global compartido,
componentes reutilizables.
Dame solo el diseño: estructura de carpetas y flujo de datos.
El código lo escribo yo.
```

### MES 3 — Node.js y APIs

**Semana 9 - Streams:**
```
¿Cuándo tiene sentido usar streams en Node.js vs fs.readFile?
Dame 2 escenarios concretos donde la diferencia impacte
en memoria o velocidad de forma real,
con el código mínimo para demostrarlo en VSCode con Node.
```

**Semana 10 - Arquitectura Express:**
```
Voy a estructurar una API Express con arquitectura por capas.
Dame la estructura de carpetas de producción
con routes, controllers, services, middlewares, Zod.
El rol de cada capa en máximo 2 líneas.
Solo el diseño — el código lo escribo yo.
```

**Semana 11 - Diseño BD:**
```
Voy a crear API de blog (usuarios, posts, comentarios) en SQLite.
Dame el SQL completo de CREATE TABLE para cada tabla
con foreign keys correctos y los índices que crearías.
Para cada índice, una línea que explique por qué.
```

**Semana 12 - Debug producción:**
```
Mi API funciona en local pero en Railway aparece este error:
[pega error exacto].
Dame las 3 causas más probables en orden de probabilidad,
con la solución específica para cada una.
```

### MES 4 — TypeScript y Testing

**Semanas 13-14 - Tipado:**
```
Tengo esta función JavaScript [pasa código].
Quiero migrarla a TypeScript strict.
Para cada decisión de tipo — incluyendo generics —
explica por qué la elegiste.
No me des el código final — guíame sobre las decisiones.
```

**Semanas 15-16 - Tests:**
```
Tengo esta función TypeScript [pasa código].
Dame tests con Vitest que cubran:
- caso principal feliz
- 3 edge cases olvidados
- 1 caso que debe lanzar error
Solo los tests — la implementación ya la tengo.
```

### MES 5 — React

**Semanas 17-18 - Components:**
```
Tengo este componente React TypeScript [pasa código].
Actúa como senior revisando mi PR.
¿Re-renders innecesarios, estado mal ubicado,
useEffect con dependencias incorrectas?
Sé específico: señala el problema, por qué es un problema,
cómo lo resolverías.
Sin reescribir el componente.
```

**Semanas 19-20 - Stack:**
```
Voy a construir [describe idea] con React TypeScript.
¿Qué stack: React Router o Next.js, React Query o SWR,
Zustand o Context?
Dame trade-offs reales en 2 líneas por opción.
Sin exagerar ventajas de ninguno.
```

### MES 6 — Portfolio y Empleo

**Semana 21 - README:**
```
Aquí está el README de mi proyecto principal [pasa README].
Imagina que eres tech lead con 30 segundos para decidir
si me llamas.
¿Qué te convence?
¿Qué falta, qué sobra?
¿Cuál es el cambio más importante para que diga
'este developer sabe lo que hace' en 30 segundos?
```

**Semana 22 - Entrevista:**
```
Hazme una entrevista técnica de 20 minutos para posición junior-mid.
Preguntas sobre: closures, event loop, prototipos, async/await.
Una pregunta a la vez.
Cuando responda, dime qué faltó sin darme la respuesta.
Al final: evaluación honesta con 3 fortalezas y 3 áreas de mejora.
```

**Semanas 23-24 - Personalizar vacante:**
```
Esta es la JD [pega].
Mis proyectos son: [lista 4 con URL, stack, descripción].
¿Cuál es el más relevante y por qué?
¿Cómo lo presentaría en los primeros 5 minutos
para conectarlo con el problema que buscan resolver?
```

---

## SISTEMA DE MOTIVACIÓN — CUANDO QUIERAS ABANDONAR

Guarda esta sección. Vuelve aquí cuando la montaña se sienta demasiado empinada.

### "No soy suficientemente inteligente"

JavaScript tiene conceptos genuinamente difíciles.
- Los closures confunden a developers experimentados
- El event loop requiere tiempo para "hacer clic"
- TypeScript parece excesivo hasta que no lo es

**No eres tú. Es el tema.**

La inteligencia NO es lo que separa a quien aprende de quien no.

**Es la persistencia.**

Y tú estás aquí leyendo esto, así que tienes la persistencia.

**Checkpoint:** ¿Conoces a alguien que esté en la semana 2 estudiando closures? Probablemente se sienta igual que tú ahora.

---

### "Voy demasiado lento"

Abre tu PRIMER COMMIT de la semana 1.
Léelo completo.
Ahora lee lo que escribiste hace 4 semanas.

Esa diferencia es tu progreso REAL. Y es enorme, aunque no se sienta así desde adentro.

**Un mes sólido vale más que tres meses apresurados que hay que repetir.**

---

### "Un concepto no entra"

Estrategias en orden:

**1. Usa el debugger de VSCode (F5)**
Lo invisible se vuelve visible cuando puedes pausar y observar.

**2. Rompe el ejemplo intencionalmente**
Cambia una variable, añade un console.log.
Ver QUÉ se rompe enseña más que la explicación.

**3. Pide a Gemini una analogía diferente**
No con código. Con una historia de la vida real.

**4. Lee al día siguiente con mente fresca**
El cerebro procesa mientras duermes.
Lo que no entró hoy puede entrar mañana.

---

### "Perdí días o semanas de estudio"

Pasa. La vida interrumpe. Lo importante no es cuántos días perdiste.

**Es qué haces cuando vuelves.**

**REGLA:** No te castigues. No intentes "recuperar" 8 horas.
Continúa desde donde dejaste con tus 2 horas habituales.

Si perdiste más de 2 semanas:
- Primera sesión de vuelta: releed los últimos 3 artículos
- No avances
- Reconstruye el contexto
- Continúa normal desde el día siguiente

**La consistencia retomada vale más que la intensidad compensatoria.**

---

### "No vale la pena"

¿Vale la pena saber hacer las cosas que quiero hacer?

Si la respuesta es SÍ, el camino vale la pena aunque cueste.

No existe atajar la comprensión real.
Puedes aprender sintaxis en una semana.
Dominar el lenguaje toma 6 meses.

**Ambas son decisiones válidas, pero tienen resultados completamente diferentes.**

---

## CHECKLIST DE SEGUIMIENTO

### Cada DÍA:
- [ ] 2 horas de estudio (no negociable)
- [ ] Commitea a git al terminar

### Cada SEMANA:
- [ ] 4 sesiones de 2 horas (= 8 horas)
- [ ] 1 commit por sesión (= 4 commits)
- [ ] README semanal: qué aprendí, qué me costó

### Cada MES:
- [ ] 4 commits, uno por semana
- [ ] 1 proyecto completado
- [ ] GitHub muestra progreso (heatmap)
- [ ] Actualicé mi portfolio con el nuevo proyecto

### FINAL DE 6 MESES:
- [ ] 6 proyectos reales en GitHub
- [ ] Heatmap verde de 24 semanas
- [ ] Portfolio web personal
- [ ] Paquete npm publicado
- [ ] Tests en proyectos
- [ ] CI/CD con GitHub Actions
- [ ] 15+ aplicaciones de empleo
- [ ] LinkedIn actualizado
- [ ] 3 simulaciones de entrevista
- [ ] Oferta de empleo (objetivo final)

---

## RESUMEN FINAL

### Los 3 puntos más importantes:

**1. La única diferencia es aparecer cada día**
No es talento. No es inteligencia. Es consistencia.

Meta: 2 horas cada día. Punto.

**2. El sistema de herramientas funciona en orden**
es.javascript.info → VSCode → Warp → Gemini

Si cambias el orden, dejas de aprender.

**3. Commitea a git cada día**
El heatmap de 180 días es evidencia que nadie puede falsificar.

---

## ANTES DE EMPEZAR

Abre VSCode ahora.
Crea tu carpeta `js-journey`.
Haz tu primer commit.

El primero es siempre el más difícil porque es la frontera entre intención y acción.

**Cruza esa frontera hoy.**

```javascript
// Tu primer archivo (mes-01/semana-01/index.js):
console.log("Empezó mi journey de JavaScript.");
console.log("Hoy es el primer día de los próximos 180 días.");
console.log("Voy a dominar esto.");

// Ejecuta en Warp:
// node mes-01/semana-01/index.js
// 
// Luego commitea:
// git add .
// git commit -m "inicio: día 1 de mi journey"
// git push
```

---

**Total: 360 horas en 180 días**
**Resultado: Developer con fundamentos reales, no tutorials copiados**

**Start strong. Appear every day. Build real things.**

Nos vemos en el mes 6.

