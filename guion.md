# Guion — Git & GitHub

Cada tema dura **~2 minutos** (≈ 250 palabras habladas). Entre corchetes va lo que hay que **hacer en pantalla**. Al final de cada tema hay una **frase puente** para pasarle la palabra a la persona siguiente.

> Consejo: no lean el guion de corrido. Usen cada bloque como una lista de ideas y hablen mirando a la clase, usando la interacción como apoyo.

---

## 1. ¿Qué es Git? (0:00 – 2:00)

**Apertura:** "Buenas, somos el grupo X y hoy vamos a hablar de Git y GitHub. Arranco con una pregunta: ¿a quién le pasó tener un archivo que se llama `tp_final_v3_FINAL_ahora_si.zip`?"

[Pantalla: lista de archivos zip desordenados.]

- Este es el problema real: sin control de versiones, la "historia" de un proyecto son copias de archivos con nombres cada vez más absurdos. No se sabe qué cambió, quién lo cambió, ni cómo volver atrás.
- **Git** es un sistema de control de versiones: guarda la historia de cada cambio de tu proyecto. Lo creó Linus Torvalds en 2005 para desarrollar el kernel de Linux.

[Clic en **✨ Usar Git**. Aparece el historial y el recuadro de repositorio.]

- Ahora tenemos una sola carpeta y toda la historia ordenada. A esto lo llamamos **repositorio**, o **repo**: la carpeta del proyecto más su historia, que Git guarda en una carpeta oculta llamada `.git`.
- Cada punto de esta lista es un **commit**.

[Pasar el mouse sobre el commit subrayado "primera versión".]

- Un commit es una "foto" del proyecto en un momento dado, con un mensaje que explica qué cambió.
- Dos ideas clave: Git es **distribuido** (la historia completa vive en tu computadora) y funciona **sin internet**.

**Puente:** "Ya vimos qué es Git. Ahora le paso a [nombre] para ver cómo se guarda un commit paso a paso."

---

## 2. Commits: las 3 áreas (2:00 – 4:00)

**Apertura:** "Un commit no se hace de un salto. Los cambios pasan por tres lugares."

[Pantalla: las tres cajas.]

- **Working directory**: donde editás tus archivos. Es lo que ves en tu editor.
- **Staging area**: la "sala de espera". Acá elegís qué cambios van a entrar en el próximo commit.
- **Repositorio**: la historia guardada.

[Clic en **✏️ Editar un archivo**. Aparece en Working directory, en naranja.]

- Edité un archivo. Git lo detecta, pero todavía no lo guardó.

[Clic en **git add .**]

- Con `git add` lo muevo a staging: le digo "este cambio quiero guardarlo".

[Clic en **git commit**.]

- Con `git commit` lo guardo en el repositorio, con un mensaje. Miren la terminal: se creó un commit con su código único.

[Repetir una vez más para mostrar que se acumulan.]

- ¿Por qué existe staging? Porque me permite armar commits **chicos y ordenados**: puedo haber tocado diez archivos y commitear solo los tres que tienen que ver con una misma idea.
- Regla de oro: commits chicos, con mensajes claros. En seis meses vas a agradecerlo.

**Puente:** "Hasta acá guardamos la historia en una sola línea. Pero ¿qué pasa si dos personas quieren trabajar a la vez? De eso habla [nombre]."

---

## 3. Branches y merge (4:00 – 6:00)

**Apertura:** "Hasta ahora trabajábamos en una sola línea. Pero imaginen que están solos y tienen **dos tareas**: cambiar el botón y armar el login. Si las mezclan, un cambio a medio hacer rompe el proyecto. ¿Cómo se ordenan? Con **ramas**."

[Pantalla: grafo con `main`.]

- Una **branch** es una línea paralela de trabajo. `main` es la rama principal, la que tiene que estar siempre estable.

[Clic en **git branch boton** y **git branch login**.]

- Creé una rama por tarea: `boton` y `login`. Cada una tiene su propia línea.

[Clic en **+ commit en boton**, **+ commit en login**, y **+ commit en main**, alternando.]

- Puedo saltar de una tarea a la otra y los cambios **no se mezclan**: lo del botón no afecta al login ni a `main`. Trabajo ordenado y puedo experimentar tranquilo.

[Clic en **merge boton → main**.]

- Cuando el botón está listo, hago **merge**: junto los cambios dentro de `main`. El punto verde es el commit que une las líneas.

[Clic en **merge login → main**. Después **↺ Reiniciar**, repetir hasta los commits y hacer **⚡ Provocar conflicto**, luego los dos merge.]

- ¿Y si las dos tareas tocaron **la misma línea**? Acá una puso el botón azul y la otra violeta. El primer merge entra sin problemas, pero el segundo genera un **conflicto**: Git no sabe cuál elegir.

[Clic en **Combinar ambas**.]

- Lo resolvemos a mano. Un conflicto no es un error: es Git pidiéndonos una decisión. Y ojo: con más personas en el equipo pasa seguido, por eso lo que sigue importa.

**Puente:** "Todo esto pasó en nuestra computadora, trabajando solos. Ahora [nombre] nos cuenta cómo llevarlo a la nube para trabajar en equipo."

---

## 4. ¿Qué es GitHub? (6:00 – 8:00)

**Apertura:** "Hasta ahora todo es local: si se rompe mi compu o quiero compartir el proyecto, estoy en problemas. Ahí entra GitHub."

[Pantalla: repo local y repo remoto.]

- Aclaración importante, que se confunde mucho: **Git** es la herramienta, un programa que corre en tu compu. **GitHub** es una plataforma web, en la nube, donde se guardan repos de Git. Hay alternativas, como GitLab o Bitbucket.
- En GitHub tenemos un **repo remoto**: una copia del repo, accesible desde cualquier lugar.

[Clic en **git commit** dos veces.]

- Hice dos commits nuevos en mi compu. El remoto todavía no los tiene.

[Clic en **git push**.]

- Con `git push` **subo** mis commits a GitHub. Ahora están sincronizados.

[Clic en **git commit** y luego **git push**; después mostrar **git pull**.]

- Con `git pull` hago lo contrario: **traigo** los cambios que otros subieron. Y con `git clone` me bajo un repo completo por primera vez.

[Señalar el cuadro Git vs GitHub.]

- Además de guardar código, GitHub suma el perfil público, los README, y las herramientas para colaborar que vamos a ver ahora.

**Puente:** "Con el repo en la nube, cualquiera puede colaborar. ¿Cómo? Se lo paso a [nombre]."

---

## 5. Fork y Pull Requests (8:00 – 10:00)

**Apertura:** "Supongamos que quiero arreglar algo en un proyecto open source que no es mío. No puedo editarlo directamente. ¿Entonces?"

[Pantalla: flujo de 5 pasos.]

[Clic en **🍴 Hacer fork**.]

- Primero hago un **fork**: una copia del repo, en mi cuenta. Ahí sí puedo hacer lo que quiera.

[Clic en **✏️ Hacer un cambio**.]

- Hago mi cambio. Miren el diff: en rojo lo que se borra, en verde lo que se agrega.

[Clic en **🔀 Abrir Pull Request**.]

- Ahora abro un **Pull Request** (PR): le pido al dueño del proyecto que integre mi cambio.

[Clic en **💬 Pedir cambios**.]

- Alguien lo **revisa**. Esto es el **code review**. Puede pedir cambios, comentar, discutir. Es una de las mejores prácticas: ningún cambio llega a `main` sin que otra persona lo vea.

[Repetir el flujo y esta vez clic en **✅ Aprobar**, luego **🟣 Merge**.]

- Cuando se aprueba, se hace merge y el cambio entra en `main`.
- Los PR sirven también dentro de un equipo: protegen `main` y mejoran la calidad del código.

**Puente:** "Pero ¿cómo sabe el equipo qué hay que hacer? Eso lo organizan los issues. [Nombre], dale."

---

## 6. Issues y Projects (10:00 – 12:00)

**Apertura:** "Un equipo no solo escribe código: también tiene que decidir qué hacer, en qué orden y quién lo hace."

[Pantalla: tablero con tres columnas.]

- Un **issue** es una tarea, un bug o una idea. Cada uno tiene un número, un título y **etiquetas**: `bug` en rojo, `feature` en verde, `docs` en azul, `good first issue` para quien recién arranca.
- Se les puede asignar una persona, una fecha o un hito (milestone).

[Arrastrar "Agregar botón de login" de To do a En progreso.]

- Un **Project** ordena esos issues en un **tablero kanban**: pendiente, en progreso y hecho. Con solo mirarlo, todo el equipo sabe cómo viene el trabajo.

[Arrastrar "El menú no abre en celular" hasta Hecho.]

- Lo lindo es que todo se conecta: si en un Pull Request escribo "Closes #3", cuando se hace merge, el issue número 3 se cierra solo.
- Para nosotros, usar issues y tablero es lo mismo que en una empresa: nadie pregunta "¿quién hace qué?", está a la vista.

**Puente:** "Ya tenemos código, colaboración y organización. Para cerrar, [nombre] nos cuenta cómo cuidarlo todo."

---

## 7. Seguridad, ecosistema y cierre (12:00 – 14:00)

**Apertura:** "Subir código a la nube también trae responsabilidades. Veamos buenas prácticas."

[Pantalla: checklist. Tildar cada punto mientras se explica.]

- **2FA**: autenticación en dos pasos, para que una contraseña robada no alcance.
- **Nunca subir contraseñas ni tokens**. Para eso existe `.gitignore`: le decimos a Git qué archivos ignorar. Si algo sensible se sube, hay que considerarlo comprometido.
- **Dependabot**: avisa cuando una librería que usamos tiene una vulnerabilidad, y propone la actualización.
- Commits chicos, mensajes claros y **proteger `main`** con Pull Requests.

[Señalar la línea de ecosistema.]

- GitHub es también un ecosistema: el hogar del **open source** (millones de proyectos que podemos leer, usar y mejorar), **Copilot**, el asistente de IA, y **GitHub Pages**, para publicar sitios gratis. De hecho, esta presentación podría estar publicada ahí.

**Cierre:** "Resumiendo: Git guarda la historia, GitHub la lleva a la nube, los PR ordenan la colaboración, los issues organizan el trabajo y la seguridad lo protege. Para terminar, un mini quiz."

[Responder el quiz entre todos, 3 preguntas.]

**Final:** "Eso fue todo. Gracias, ¿preguntas?"

---

## Plan de tiempos

| Tema | Persona | Duración | Acumulado |
|------|---------|----------|-----------|
| 1. Qué es Git | | 2:00 | 2:00 |
| 2. Commits | | 2:00 | 4:00 |
| 3. Branches y merge | | 2:00 | 6:00 |
| 4. GitHub | | 2:00 | 8:00 |
| 5. Fork y PR | | 2:00 | 10:00 |
| 6. Issues y Projects | | 2:00 | 12:00 |
| 7. Seguridad y cierre | | 2:00 | 14:00 |

Quedan 1-6 minutos de margen para demoras, cambios de persona y preguntas.
