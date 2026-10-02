## Step 3: Orquesta diseño, desarrollo y validación

### Objetivo
Ejecutar un flujo real de agentes con handoffs y una segunda ronda de validación.

### Fase A — Designer

Copia y pega al Orchestrator:

```text
Usa docs/project-plan.md como contexto.

Delega al Designer el diseño de Project Pulse.
El Designer no debe implementar código.

Debe entregar:
- layout;
- componentes;
- jerarquía visual;
- estados;
- progreso;
- responsive behavior;
- accesibilidad;
- reglas claras para Coder.

Guarda el resultado como docs/design-handoff.md.
```

Crea `docs/design-handoff.md`:

```markdown
# Design Handoff

## Contexto recibido
- ...

## Layout
...

## Componentes
...

## Estados
...

## Progreso
...

## Responsive
- Desktop:
- Tablet:
- Mobile:

## Accesibilidad
...

## Reglas para Coder
- ...

## Trade-offs
...

## Preguntas abiertas
...
```

### Fase B — Coder

Copia y pega:

```text
Usa docs/project-plan.md y docs/design-handoff.md.

Delega al Coder la implementación.

Debe modificar:
- app/index.html
- app/styles.css
- app/project-data.json

Debe conservar la separación entre estructura, estilos y datos.
Al terminar debe mostrar los cambios y la evidencia de validación.

Guarda docs/coding-handoff.md.
```

Estructura:

```markdown
# Coding Handoff

## Contexto recibido
...

## Cambios
| Archivo | Cambio | Motivo |
|---|---|---|
| ... | ... | ... |

## Decisiones
...

## Evidencia
...

## Incertidumbres
...
```

### Fase C — Validator

Copia y pega:

```text
Usa el requerimiento original, docs/project-plan.md y docs/design-handoff.md.

Delega al Validator una revisión completa.

No corrijas código.

Debe validar:
- HTML;
- CSS;
- JSON;
- datos;
- estados;
- progreso;
- responsive;
- accesibilidad;
- ausencia de backend;
- coherencia con el diseño.

Debe registrar evidencia, severidad y recomendación en docs/validation-report.md.
```

Usa:

```markdown
# Validation Report

## Resumen
- Estado:
- Alcance:

## Checks
| Check | Resultado | Evidencia |
|---|---|---|
| CSS | PASS/FAIL | ... |
| JSON | PASS/FAIL | ... |
| Datos | PASS/FAIL | ... |
| Estados | PASS/FAIL | ... |
| Progreso | PASS/FAIL | ... |
| Responsive | PASS/FAIL | ... |
| Accesibilidad | PASS/FAIL | ... |
| Sin backend | PASS/FAIL | ... |

## Hallazgos
| Hallazgo | Severidad | Evidencia | Recomendación |
|---|---|---|---|
| ... | ... | ... | ... |
```

### Fase D — Corrección

Copia y pega:

```text
Procesa docs/validation-report.md.

Para cada hallazgo:
1. indica el agente responsable;
2. crea un handoff específico;
3. explica qué debe cambiar;
4. define cómo se comprobará la corrección.

No implementes directamente cambios que correspondan a Coder o Designer.
```

Actualiza `docs/coding-handoff.md` con:

```markdown
## Iteración de corrección
| Hallazgo | Agente | Cambio | Evidencia |
|---|---|---|---|
| ... | ... | ... | ... |
```

### Fase E — Segunda validación

Copia y pega:

```text
Vuelve a ejecutar el Validator después de las correcciones.

Compara con el primer validation-report.

Indica:
- hallazgos resueltos;
- hallazgos pendientes;
- evidencia.

No corrijas código.
```

Añade:

```markdown
## Segunda ronda
- Hallazgos resueltos:
- Hallazgos pendientes:
- Evidencia:
```

### Fase F — Handoff final

Copia y pega:

```text
Genera docs/final-handoff.md para un engineering lead que no participó en el ejercicio.

Incluye:
- objetivo;
- resultado;
- responsabilidades de cada agente;
- decisiones;
- validaciones;
- iteraciones;
- riesgos;
- pendientes;
- decisiones humanas.

No inventes evidencia.
```

### Fase G — Revisión

Abre `app/index.html` en el navegador y comprueba visualmente el resultado.

Haz commit y push.

**Tiempo: 35-38 min.**
