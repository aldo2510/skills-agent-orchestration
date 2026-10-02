## Step 3: Orquesta diseño, desarrollo y validación

Esta es la parte principal del laboratorio.

> **Idea clave:** la orquestación se vuelve útil cuando existe un flujo con dependencias, handoffs, validación y feedback. No se trata de lanzar cinco agentes y esperar que todo funcione.

### Fase A — Diseño

Pide al Orchestrator:

> Usa docs/project-plan.md como contexto. Delega al Designer la definición de la experiencia del dashboard. El Designer debe entregar un handoff accionable para el Coder y no debe implementar código.

El Designer debe definir:
- layout;
- jerarquía visual;
- tarjetas;
- estados;
- progreso;
- responsive behavior;
- accesibilidad básica;
- relación entre HTML, CSS y datos.

Crea docs/design-handoff.md.

Usa:

    # Design Handoff

    ## Contexto recibido
    - Requerimiento:
    - Criterios de aceptación relevantes:

    ## Propuesta visual
    ### Layout
    ...
    ### Componentes
    ...
    ### Estados
    ...
    ### Progreso
    ...

    ## Responsive behavior
    - Desktop:
    - Tablet:
    - Mobile:

    ## Accesibilidad
    - ...

    ## Reglas para el Coder
    - ...
    - ...

    ## Decisiones y trade-offs
    - ...

    ## Preguntas abiertas
    - ...

Antes de continuar, pregúntate: ¿un Coder podría implementar el dashboard leyendo solamente este handoff y el plan?

### Fase B — Implementación

Pide al Orchestrator:

> Delega al Coder la implementación usando docs/project-plan.md y docs/design-handoff.md como contexto. Mantén separados HTML, CSS y JSON. Al terminar, entrega evidencia de lo realizado.

El Coder debe implementar:
- app/index.html;
- app/styles.css;
- app/project-data.json.

Crea o actualiza docs/coding-handoff.md:

    # Coding Handoff

    ## Contexto recibido
    - Plan:
    - Design handoff:

    ## Cambios realizados
    | Archivo | Cambio | Motivo |
    |---|---|---|
    | ... | ... | ... |

    ## Decisiones tomadas
    - ...

    ## Evidencia
    - Cómo comprobé que funciona:
    - Qué revisé manualmente:

    ## Incertidumbres
    - ...

### Fase C — Validación

Delega al Validator:

> Revisa la implementación completa usando el requerimiento original, el plan y los handoffs. No corrijas el código. Reporta hallazgos, evidencia, severidad y recomendación.

Debe comprobar:
- HTML → CSS → JSON;
- estructura HTML;
- datos válidos;
- estados visibles;
- progreso;
- responsive behavior;
- ausencia de backend;
- accesibilidad básica;
- coherencia con el diseño.

Crea docs/validation-report.md:

    # Validation Report

    ## Resumen
    - Estado:
    - Fecha:
    - Alcance:

    ## Checks
    | Check | Resultado | Evidencia |
    |---|---|---|
    | Referencia CSS | PASS/FAIL | ... |
    | Referencia JSON | PASS/FAIL | ... |
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

    ## Revalidación
    - Qué debería comprobarse después de una corrección:

### Fase D — Iteración

No aceptes automáticamente el primer resultado.

Pide al Orchestrator:

> Procesa el reporte de Validator. Clasifica los hallazgos, decide qué agente debe intervenir y genera un handoff específico para corregir cada problema. No corrijas directamente si el trabajo corresponde a otro agente.

Actualiza docs/coding-handoff.md:

    ## Iteración de corrección
    | Hallazgo | Agente | Cambio | Evidencia |
    |---|---|---|---|
    | ... | ... | ... | ... |

Después vuelve a validar.

### Fase E — Segunda validación

Pide al Validator:

> Revisa nuevamente el dashboard después de las correcciones. Compara el resultado con el requerimiento original y con el primer validation-report. Indica qué hallazgos fueron resueltos y cuáles permanecen.

Añade al validation-report una sección:

    ## Segunda ronda
    - Hallazgos resueltos:
    - Hallazgos pendientes:
    - Evidencia:

### Fase F — Handoff final

Pide al Orchestrator que produzca docs/final-handoff.md.

Usa:

    # Final Handoff

    ## Objetivo y resultado
    ...

    ## Flujo de agentes
    ...

    ## Responsabilidades
    | Agente | Trabajo realizado | Evidencia |
    |---|---|---|
    | ... | ... | ... |

    ## Decisiones relevantes
    - ...

    ## Validaciones ejecutadas
    - ...

    ## Iteraciones
    - ...

    ## Riesgos y pendientes
    - ...

    ## Decisiones bajo control humano
    - ...

### Fase G — Revisión humana

Abre el HTML en el navegador y revisa:
1. dashboard;
2. datos;
3. handoffs;
4. validación inicial;
5. segunda validación;
6. requerimiento original.

Corrige cualquier problema que los agentes no hayan detectado.

Haz commit y push.

### Criterios de salida

- [ ] Existe design-handoff.md.
- [ ] Existe coding-handoff.md.
- [ ] Existe validation-report.md.
- [ ] Existe final-handoff.md.
- [ ] La implementación funciona.
- [ ] Existe evidencia de una segunda validación.
- [ ] Revisaste manualmente el resultado.

**Tiempo sugerido: 40-45 min.**
