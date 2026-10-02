## Step 3: Orquesta diseño, desarrollo y validación

Esta es la parte principal del laboratorio.

> **Idea clave:** la orquestación se vuelve útil cuando existe un flujo de trabajo con dependencias y feedback. No se trata de lanzar cinco agentes y esperar que todo funcione.

---

### Fase A — Diseño

Pide al Orchestrator que delegue al Designer.

Puedes usar:

> Usa docs/project-plan.md como contexto. Delega al Designer la definición de la experiencia del dashboard. El Designer debe entregar un handoff accionable para el Coder y no debe implementar código.

El Designer debe definir:

- layout;
- jerarquía visual;
- tarjetas de proyecto;
- estados;
- progreso;
- responsive behavior;
- criterios básicos de accesibilidad;
- relación entre estructura, estilos y datos.

Guarda el handoff en `docs/design-handoff.md`.

**Antes de continuar**, revisa si el Coder podría implementar el dashboard únicamente leyendo ese documento.

Si no puede, mejora el handoff.

### Fase B — Implementación

Pide al Orchestrator:

> Delega al Coder la implementación usando docs/project-plan.md y docs/design-handoff.md como contexto. El Coder debe mantener separados HTML, CSS y JSON. Al terminar, entrega un resumen de cambios y evidencia de validación básica.

El Coder debe implementar:

- `app/index.html`;
- `app/styles.css`;
- `app/project-data.json`.

Debe conservar la separación entre estructura, estilos y datos.

Guarda en `docs/coding-handoff.md`:

- entrada recibida;
- cambios realizados;
- archivos afectados;
- decisiones tomadas;
- evidencia;
- preguntas o incertidumbres.

### Fase C — Validación

Ahora delega al Validator.

> Revisa la implementación completa usando el requerimiento original y los handoffs como referencia. No corrijas el código. Reporta únicamente hallazgos, evidencia, severidad y recomendación.

El Validator debe comprobar:

- referencias HTML → CSS → JSON;
- estructura HTML;
- datos válidos;
- estados visibles;
- progreso;
- responsive behavior;
- ausencia de dependencias de backend;
- problemas obvios de accesibilidad;
- coherencia con el diseño.

Guarda `docs/validation-report.md`.

### Fase D — No aceptes el primer resultado

Esta fase es deliberadamente iterativa.

Pide al Orchestrator:

> Procesa el reporte de Validator. Clasifica los hallazgos, decide qué agente debe intervenir y genera un handoff específico para corregir cada problema. No corrijas directamente si el trabajo corresponde a otro agente.

Después delega la corrección al agente correspondiente.

Actualiza `docs/coding-handoff.md` con:

- hallazgo;
- agente responsable;
- cambio realizado;
- razón;
- evidencia antes/después.

Vuelve a ejecutar la validación.

### Fase E — Introduce una segunda ronda

Pide al Validator una segunda revisión:

> Revisa nuevamente el dashboard después de las correcciones. Compara el resultado con el requerimiento original y con el primer validation-report. Indica qué hallazgos fueron resueltos y cuáles permanecen.

Esto obliga al equipo a demostrar que el feedback realmente produjo una mejora.

### Fase F — Handoff final

Pide al Orchestrator que produzca `docs/final-handoff.md`.

Debe incluir:

- responsabilidades de cada agente;
- decisiones relevantes;
- secuencia de trabajo;
- validaciones ejecutadas;
- iteraciones realizadas;
- riesgos;
- pendientes;
- decisiones bajo control humano.

### Fase G — Revisión humana

Abre el HTML en el navegador.

Revisa manualmente:

1. el dashboard;
2. los datos;
3. los handoffs;
4. el reporte de validación;
5. la segunda ronda de validación;
6. la coherencia con el requerimiento original.

Corrige cualquier problema que los agentes no hayan detectado.

Haz commit y push.

### Preguntas para discusión

Antes de terminar esta fase, responde:

1. ¿Qué agente aportó más valor?
2. ¿Qué información tuvo que pasar entre agentes?
3. ¿Qué información se perdió o quedó ambigua?
4. ¿Qué ocurrió cuando el Validator devolvió feedback?
5. ¿Qué tarea no debería hacer nunca el Orchestrator?
6. ¿Qué decisión necesitó intervención humana?

**Tiempo sugerido: 45-55 min.**
