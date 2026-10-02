## Step 3: Orquesta diseño, desarrollo y validación

Esta es la parte principal del laboratorio.

### Fase A — Diseño

Pide al Orchestrator que delegue al Designer.

El Designer debe definir:
- layout;
- jerarquía visual;
- tarjetas de proyecto;
- estados;
- progreso;
- responsive behavior;
- criterios básicos de accesibilidad.

Guarda el handoff en docs/design-handoff.md.

### Fase B — Implementación

Pide al Orchestrator que delegue al Coder.

El Coder debe implementar:
- app/index.html;
- app/styles.css;
- app/project-data.json.

Debe conservar la separación entre estructura, estilos y datos.

### Fase C — Validación

Pide al Orchestrator que delegue al Validator.

El Validator debe comprobar:
- referencias HTML -> CSS -> JSON;
- estructura HTML;
- datos válidos;
- estados visibles;
- progreso;
- responsive behavior;
- ausencia de dependencias de backend.

Guarda docs/validation-report.md.

### Fase D — Iteración

No aceptes automáticamente el primer resultado.

Pide al Orchestrator que procese los hallazgos del Validator y delegue una corrección al agente correspondiente.

Documenta en docs/coding-handoff.md:
- qué cambió;
- qué agente lo cambió;
- por qué;
- qué evidencia entregó.

### Fase E — Handoff final

Pide al Orchestrator que produzca docs/final-handoff.md con:
- responsabilidades de cada agente;
- decisiones relevantes;
- validaciones ejecutadas;
- riesgos;
- pendientes;
- decisiones bajo control humano.

### Fase F — Revisión humana

Abre el HTML en el navegador, revisa el resultado y contrasta la salida con el requerimiento original.

Corrige cualquier problema que los agentes no hayan detectado.

Haz commit y push.

**Tiempo sugerido: 45-55 min.**
