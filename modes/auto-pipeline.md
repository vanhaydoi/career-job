# Modo: auto-pipeline — Pipeline Completo Automático

Cuando el usuario pega un JD (texto o URL) sin sub-comando explícito, ejecutar TODO el pipeline en secuencia:

## Paso 0 — Extraer JD

Si el input es una **URL** (no texto de JD pegado), seguir esta estrategia para extraer el contenido:

**Orden de prioridad:**

1. **Playwright (preferido):** La mayoría de portales de empleo (Lever, Ashby, Greenhouse, Workday) son SPAs. Usar `browser_navigate` + `browser_snapshot` para renderizar y leer el JD.
2. **WebFetch (fallback):** Para páginas estáticas (ZipRecruiter, WeLoveProduct, company career pages).
3. **WebSearch (último recurso):** Buscar título del rol + empresa en portales secundarios que indexan el JD en HTML estático.

**Si ningún método funciona:** Pedir al candidato que pegue el JD manualmente o comparta un screenshot.

**Si el input es texto de JD** (no URL): usar directamente, sin necesidad de fetch.

## Paso 1 — Evaluación A-G
Ejecutar exactamente igual que el modo `oferta` (leer `modes/oferta.md` para todos los bloques A-F + Block G Posting Legitimacy).

## Paso 2 — Gap Gate (NUEVO)

Después de la evaluación A-G, verificar si el CV necesita mejoras:

1. Leer `config/profile.yml → project_generation`
2. Si `enabled: false`, saltar este paso
3. Si el score de match global está por debajo de `add_threshold` (default 70%), ofrecer gap-fill:
   > "El match de tu CV con este JD es del {X}%. Tienes gaps en: {lista de skills missing/weak}.
   > ¿Quieres que ejecute gap-fill mode para analizar gaps y generar proyectos synthetic que llenen estos huecos en tu CV?"
4. Si user dice "yes" → ejecutar `modes/gap-fill.md` (Step 2-7 completos)
5. Si user dice "no" → continuar con CV actual

**NOTA:** Gap-fill modifica `cv.md`. El PDF se generará después con el CV actualizado.

## Paso 3 — Guardar Report .md
Guardar la evaluación completa en `reports/{###}-{company-slug}-{YYYY-MM-DD}.md` (ver formato en `modes/oferta.md`).
Include Block G in the saved report. Add `**Legitimacy:** {tier}` to the report header.

## Paso 4 — Generar PDF
Ejecutar el pipeline completo de `pdf` (leer `modes/pdf.md`). Usar el `cv.md` actual (puede haber sido modificado por gap-fill en Paso 2).

## Paso 5 — Draft Application Answers (solo si score >= 4.5)

Si el score final es >= 4.5, generar borrador de respuestas para el formulario de aplicación:

1. **Extraer preguntas del formulario**: Usar Playwright para navegar al formulario y hacer snapshot. Si no se pueden extraer, usar las preguntas genéricas.
2. **Generar respuestas** siguiendo el tono (ver abajo).
3. **Guardar en el report** como sección `## H) Draft Application Answers`.

### Preguntas genéricas (usar si no se pueden extraer del formulario)

- Why are you interested in this role?
- Why do you want to work at [Company]?
- Tell us about a relevant project or achievement
- What makes you a good fit for this position?
- How did you hear about this role?

### Tono para Form Answers

**Posición: "I'm choosing you."** el candidato tiene opciones y está eligiendo esta empresa por razones concretas.

**Reglas de tono:**
- **Confiado sin arrogancia**: "I've spent the past year building production AI agent systems — your role is where I want to apply that experience next"
- **Selectivo sin soberbia**: "I've been intentional about finding a team where I can contribute meaningfully from day one"
- **Específico y concreto**: Siempre referenciar algo REAL del JD o de la empresa, y algo REAL de la experiencia del candidato
- **Directo, sin fluff**: 2-4 frases por respuesta. Sin "I'm passionate about..." ni "I would love the opportunity to..."
- **El hook es la prueba, no la afirmación**: En vez de "I'm great at X", decir "I built X that does Y"

**Framework por pregunta:**
- **Why this role?** → "Your [specific thing] maps directly to [specific thing I built]."
- **Why this company?** → Mencionar algo concreto sobre la empresa. "I've been using [product] for [time/purpose]."
- **Relevant experience?** → Un proof point cuantificado. "Built [X] that [metric]. Sold the company in 2025."
- **Good fit?** → "I sit at the intersection of [A] and [B], which is exactly where this role lives."
- **How did you hear?** → Honesto: "Found through [portal/scan], evaluated against my criteria, and it scored highest."

**Idioma**: Siempre en el idioma del JD (EN default). Aplicar `/tech-translate`.

## Paso 6 — Actualizar Tracker
Registrar en `data/applications.md` con todas las columnas incluyendo Report y PDF en ✅.

## Paso 7 — Ofrecer Interview Prep (NUEVO)

Después de todo el pipeline, ofrecer preparación de entrevista:

> "¿Quieres que prepare preguntas de entrevista para este rol? Puedo generar:
> - **tech-qa**: Preguntas técnicas con respuestas personalizadas basadas en tu CV
> - **full**: Tech Q&A + Company research + STAR stories
> - **no**: Omitir"

- Si user dice "tech" → ejecutar `modes/tech-qa.md`
- Si user dice "full" → ejecutar `modes/tech-qa.md` + `modes/interview-prep.md`
- Si user dice "no" → finalizar

**Si algún paso falla**, continuar con los siguientes y marcar el paso fallido como pendiente en el tracker.
