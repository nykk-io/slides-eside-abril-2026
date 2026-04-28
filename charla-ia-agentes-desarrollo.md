# 🤖 IA, Agentes y el Arte (casi perdido) de Hacer Software

> Charla para universitarios · ~45 minutos
> *"Una sesión de veteranos hablando con los que vienen detrás"*

---

## 📋 Estructura general (timing orientativo)

| Bloque | Tiempo | Tono |
|---|---|---|
| 1. Arranque y definiciones | 5 min | Desenfadado, picante |
| 2. De dónde venimos (batallitas) | 7 min | Nostálgico, divertido |
| 3. Qué es un agente de verdad | 8 min | Técnico, con chispa |
| 4. Cómo ha cambiado el curro | 8 min | Realista |
| 5. El elefante en la habitación: los juniors | 8 min | Crudo, sin filtros |
| 6. El futuro: ¿dónde están los arquitectos? | 5 min | Provocador |
| 7. Consejos accionables + Q&A | 4 min | Pragmático |

---

## 🎬 BLOQUE 1 — Arranque: "Hola, somos dinosaurios" (5 min)

### Slide: Portada
**Título sugerido:** *"Sobrevivir al apocalipsis de la IA (sin haberla escrito nosotros)"*

### Gancho inicial
> Empezar fuerte: *"Levantad la mano los que habéis usado Copilot, Cursor o Claude esta semana. Ahora bajadla los que entendéis de verdad el código que os ha escrito. Vale, esta charla va para los que habéis bajado la mano."*

### Definiciones rápidas, al grano

No hace falta academia. Tres conceptos, tres frases:

- **IA generativa** → *Predice el siguiente token. Eso es todo. El resto es marketing.*
- **LLM** → *Un autocompletado con esteroides que ha leído medio internet.*
- **Agente** → *Un LLM al que le has dado tijeras y permiso para correr por el pasillo.* (Loop + herramientas + objetivo.)

### Chiste necesario
> *"En 2021 discutíamos tabs vs espacios. En 2026 discutimos qué modelo elegir para discutir si usar tabs o espacios."*

---

## 🦖 BLOQUE 2 — De dónde venimos (7 min)

### La línea temporal del dev veterano

Aquí tocan batallitas. Elegid las vuestras, pero sugiero:

- **Años 2000s** → Stack Overflow no existía. Buscabas en foros de phpBB y rezabas.
- **2008** → GitHub. "¿Código abierto? ¿Gratis? ¿Dónde está la trampa?"
- **2015** → Stack Overflow ES DIOS. Tu trabajo es googlear bien.
- **2021** → Aparece Copilot. "Bah, un juguete, no sabe ni cerrar una llave."
- **2023** → ChatGPT. El primer *"ostras, esto escribe mejor que mi compañero"*.
- **2024-2025** → Agentes. El IDE ejecuta cosas solo mientras vas al baño.
- **2026 (hoy)** → Estamos aquí. Y nadie sabe dónde estaremos en 18 meses.

### Anécdota de guerra (elegir una)

**Opción A — El pull request fantasma:**
> *"Hace dos años me pasé tres días debuggeando un bug que resultó ser un copia-pega de Stack Overflow de 2012. Hoy me paso tres días debuggeando un bug que la IA generó con total seguridad citando código que no existe. Hemos cambiado de enfermedad."*

**Opción B — La documentación prehistórica:**
> *"Antes leías un libro de 800 páginas de O'Reilly para aprender un framework. Ahora le preguntas al chat y te miente en 12 segundos. Progreso."*

**Opción C — El deploy de los viernes:**
> *"Antes desplegábamos el viernes a las 18:00 y pasábamos el weekend rezando. Ahora desplegamos a las 18:00 y el agente se pelea él solo con el rollback. Algunos llaman a esto 'progreso'. Yo lo llamo 'delegar el pánico'."*

### Dato para enganchar
> **El 90% de los equipos de ingeniería usa IA en sus flujos de trabajo**, frente al 61% hace solo un año. En menos de la mitad de las empresas, **más del 50% del código es generado por IA**. En 18 meses. Esto nunca había pasado.

*Fuente: State of Engineering Management Report / Jellyfish 2025.*

---

## 🧠 BLOQUE 3 — ¿Qué es un agente de verdad? (8 min)

### El disclaimer importante

> *"Todo el mundo llama 'agente' a cualquier cosa. Vamos a desambiguar."*

### La jerarquía de autonomía (escribir en pizarra o slide)

1. **Chatbot** → Tú preguntas, él responde. Fin.
2. **Copiloto** → Autocompleta mientras tecleas. Tú decides.
3. **Asistente con herramientas** → Puede buscar en web, leer ficheros, hacer llamadas a APIs. Pero tú guías.
4. **Agente** → Tiene un **objetivo**, un **loop** y **herramientas**. Decide qué hacer, lo hace, mira el resultado, y vuelve a decidir. *Sin tu mano.*
5. **Sistema multiagente** → Varios agentes que se coordinan. Aquí empieza el Far West.

### Anatomía mínima de un agente

```
LOOP {
  1. Observa el estado (qué hay, qué pasó)
  2. Piensa (¿qué paso acerca al objetivo?)
  3. Actúa (llama a una tool: bash, browser, editor, API)
  4. Observa el resultado
  5. ¿Terminé? → salir. Si no → volver al 1.
}
```

Eso es todo. El resto es ingeniería de prompts, gestión de contexto, y rezar.

### El giro de tono (ponernos técnicos-pero-cachondos)

> *"Un agente no es magia. Es un while-true con un LLM dentro y permisos demasiado generosos."*

### Ejemplos reales que ya están en producción

- **Claude Code / Cursor Agent / Copilot Agent** → Leen tu repo, entienden el stack, hacen cambios, corren tests, abren PRs.
- **Agentes de QA** → Ejecutan tu app, prueban flows, reportan bugs con reproducibilidad.
- **Agentes de ops** → Monitorizan logs, detectan anomalías, hacen rollback.
- **Agentes de research** → Leen 40 papers, sintetizan, citan.

### Dato bomba
> El **22% del código fusionado en repos es ya autored por IA**, según el Q4 2025 Impact Report de DX (analizando 135.000+ developers). No asistido. **Autored.** Es decir, la IA lo escribió y un humano dijo "vale".

---

## 💼 BLOQUE 4 — Cómo ha cambiado el curro de verdad (8 min)

### La foto real del mercado (datos 2025-2026)

- **84%** de developers usan o planean usar IA en su flujo de trabajo *(Stack Overflow Survey 2025, n=49.000+)*
- **51%** de profesionales la usan **a diario**
- **~3,6 horas/semana** ahorradas de media por dev
- GitHub Copilot: **20 millones de usuarios** (más habitantes que Rumanía)
- Claude Code y Cursor pisándole los talones

### Pero aquí viene el plot twist

> **Solo el 29% de los developers confía en la precisión de la IA.** Y la cosa va a peor: el sentimiento positivo hacia las herramientas de IA bajó del 70% en 2023-24 al **60% en 2025**.

*"Usamos más una herramienta en la que confiamos menos. Muy sano todo."*

### La paradoja de productividad (ESTO HAY QUE CONTARLO)

Estudio del METR (Model Evaluation & Threat Research, randomised controlled trial):

- Devs **creían** que eran un **20% más rápidos** con IA.
- En realidad eran un **19% más lentos**.
- **Gap de percepción: 39 puntos.**

> *"Nos sentimos productivos porque generamos más líneas. Pero alguien tiene que revisarlas. Y resulta que ese alguien somos también nosotros. Genial."*

### Datos de Faros Engineering

- +21% tareas completadas por dev individual
- **+91% tiempo de revisión** (los PRs se duplicaron: +98%)
- La productividad "se evapora" en colas de review

### La parte buena (para que no se suiciden)

- Para tareas **bien acotadas** (boilerplate, refactors mecánicos, tests, docs): ganancia real y brutal.
- Para **explorar tecnologías nuevas**: acelera el aprendizaje x10 si lo usas bien.
- Para **debugging de síntomas conocidos**: espectacular.

### La clave que nadie dice

> *"La IA magnifica lo que ya eres. Si eres bueno, te hace mejor. Si eres malo, te hace malo más rápido y con más confianza."*

*(Esto literalmente lo dice el DORA Report 2025: la IA no es bala de plata, amplifica las fortalezas y debilidades existentes.)*

---

## 😬 BLOQUE 5 — El elefante en la habitación: los juniors (8 min)

> **AVISO DE TONO:** aquí bajamos el humor y subimos la honestidad. Es la parte que tus alumnos necesitan oír aunque duela.

### El dato que abre el bloque

> Un estudio de Harvard con **285.000 empresas y 62 millones de trabajadores (2015-2025)** encontró que cuando las empresas empiezan a usar IA generativa, **el empleo junior cae entre un 9% y un 10% en seis trimestres**. El senior apenas se mueve.

### Más sal en la herida

- **67%** de caída en ofertas de puestos entry-level entre 2022 y 2026.
- Empleo de developers de 22-25 años: **-20%** desde su pico de finales de 2022 (Stanford Digital Economy Study).
- Desempleo en grads de CS: **6,1%**. En ingeniería informática: **7,5%**. De los más altos por carrera.
- **54%** de líderes de ingeniería planean contratar menos juniors gracias a los copilotos IA *(LeadDev Survey 2025)*.

### Por qué pasa esto (la parte incómoda)

El "trato" histórico funcionaba así:
- El junior hacía las tareas pequeñas, rutinarias, aburridas.
- A cambio, **aprendía cómo funciona un sistema real**.
- El senior liberaba tiempo para problemas difíciles.

**La IA ha roto ese trato.** El senior ahora le pide al chatbot, no al junior. Y el junior... no entra.

### Batallita veterana (contadla en primera persona)

> *"Yo aprendí a programar arreglando bugs de mierda que nadie quería tocar. Memory leaks, race conditions, configs de Apache en producción un domingo. Eso fue mi carrera. Hoy, el junior que debería estar haciendo eso está aplicando a 500 ofertas y la IA está arreglando el bug en 3 minutos. El problema no es que el bug se arregle. Es que ese junior nunca va a entender POR QUÉ se rompió."*

### El concepto clave: "Hollow Senior"

> **Hollow Senior (senior hueco):** developer que depende tanto de la IA que nunca desarrolla la intuición profunda. Puede mover piezas, pero cuando se cae producción a las 3 AM y el modelo no tiene contexto... no sabe qué hacer.

Datos que respaldan esto:
- **+50% de código copia-pegado** (del 8,3% al 12,3% de líneas cambiadas)
- **Refactoring real bajó del 25% a menos del 10%**

*"Estamos criando una generación que sabe pedir código pero no sabe leerlo."*

### Guiño a los alumnos (importante)

> *"Y antes de que os suicidéis en el descanso: esto es un problema del SECTOR, no vuestro. Vosotros no elegisteis graduaros en el peor momento de entrada laboral de los últimos 20 años. Pero sí podéis elegir cómo prepararos."*

---

## 🏛️ BLOQUE 6 — ¿Dónde estarán los arquitectos en 2035? (5 min)

### La pregunta provocadora

> *"Si en 2026 no contratas juniors, ¿de dónde saldrán los seniors en 2031? ¿Y los arquitectos en 2035?"*

### La matemática inquietante

| Año | Lo que pasa |
|---|---|
| 2025-2027 | Extinción del junior. Ahorro a corto plazo celebrado en earnings calls. |
| 2027-2030 | Escasez de mid-level (3-5 años de experiencia). Guerra de ofertas. |
| 2030-2035 | Crisis de seniors y arquitectos. Los que quedan se retiran. |
| 2035+ | *"Tenemos arquitectos que nunca pusieron un ladrillo."* |

### La cita que debéis usar

> *"La industria está comiéndose su propia semilla."*
> — frase recurrente en el análisis de ByteIota sobre el colapso del pipeline junior

### El otro ángulo: el senior exhausto

Hoy los seniors **revisan código IA a escala**, no mentorean.
- **+19% de tiempo en code review** que antes.
- El "válvula de escape" de delegar en juniors ya no existe.
- Code review fatigue = top de burnout según estudios recientes.

### El escenario que algunos predicen

> 70% de probabilidad de una **crisis de talento senior entre 2029 y 2031**. Jubilaciones masivas + ausencia de pipeline = guerra de salarios + dependencia total de sistemas IA que nadie entiende del todo.

### La pregunta al aire (dejar en silencio 5 segundos)

> *"¿Y si el mejor momento para ser arquitecto de software sea justo dentro de 10 años, precisamente porque no habrá casi ninguno?"*

---

## 🎯 BLOQUE 7 — Consejos accionables (4 min)

> *"Os habéis ganado el derecho a una lista de consejos sin humor. Aquí va."*

### Para el alumno de universidad AHORA

1. **Aprende los fundamentos como si la IA no existiera.**
   Sistemas operativos, redes, estructuras de datos, bases de datos, concurrencia. *Eso no lo va a cubrir Copilot por ti cuando el modelo alucine.*

2. **Usa la IA como tutor, no como autor.**
   Pídele que te **explique** el código, no que te lo escriba. Si no lo entiendes, no avances. Eres tú contra el "Hollow Senior".

3. **Especialízate en lo que la IA hace mal (todavía).**
   - Debugging profundo de producción
   - Arquitectura de sistemas distribuidos
   - Seguridad y edge cases adversariales
   - Dominios muy específicos (embedded, kernel, compiladores, etc.)

4. **Aprende a evaluar código, no solo a escribirlo.**
   La skill del futuro es **code review con ojo crítico**. Ver el bug que la IA no vio.

5. **Contribuye a open source.**
   Es LITERALMENTE la única forma realista de aparecer con experiencia sin que te contraten primero. Y aprendes revisando código real.

6. **No te cases con una herramienta.**
   Copilot, Cursor, Claude Code, lo que venga. Aprende el **paradigma**, no el producto. En 2 años la mitad no existirán y la otra mitad serán otra cosa.

7. **Construye algo tuyo de principio a fin.**
   Un side project real, desplegado, con usuarios (aunque sean 3). **Haz cosas que un agente no puede hacer solo:** decidir qué construir y por qué.

### Para todos (veteranos incluidos)

> *"La pregunta ya no es '¿te va a quitar el trabajo la IA?'. Es '¿vas a ser el que sabe domarla, o el que la usa sin entenderla?'"*

---

## 🎤 Cierre (30 segundos)

> *"Llevo [X] años desarrollando software. He visto caer frameworks, lenguajes, paradigmas, y tres burbujas. Esta es la primera vez que siento que el oficio está cambiando de verdad, no solo las herramientas.*
>
> *La buena noticia es que los que entendéis los fundamentos y sabéis pensar en sistemas vais a ser carísimos en 10 años.*
>
> *La mala es que los que no... no vais a ser nada.*
>
> *Gracias."*

### Q&A: 5 min de preguntas sueltas

---

## 📚 Fuentes y datos citados (para el slides, al final)

- Stack Overflow Developer Survey 2025 (n=49.000+)
- Jellyfish — *2025 AI Metrics in Review*
- JetBrains — *State of Developer Ecosystem 2025* (n=24.534)
- DX — *Q4 2025 Impact Report* (135.000+ devs)
- Harvard Study on Seniority-Biased Change (2025) — 62M trabajadores
- Stanford Digital Economy Study — empleo devs 22-25 años
- METR — RCT sobre productividad con AI coding tools
- Faros Engineering — métricas de PRs y reviews
- LeadDev Survey 2025 — 54% líderes reducirán contratación junior
- DORA Report 2025 — AI como amplificador, no solución
- ByteIota — análisis del colapso del pipeline junior

---

## 💡 Notas de entrega (para ti, no para la slide)

- **Interacción:** pide levantar manos al menos 3 veces (inicio, bloque 3, bloque 7).
- **Pausa dramática:** obligatoria al final del bloque 6. Los silencios venden.
- **Batallitas:** cuenta las tuyas reales. Los datos los olvidan, las historias las recuerdan.
- **Tono mutante:** arranque divertido → realismo crudo → consejos secos. Ese arco funciona.
- **Si hay tiempo:** demo en vivo de un agente real (Claude Code, Cursor) resolviendo algo pequeño. 2 minutos máximo. Impacta más que 20 slides.
