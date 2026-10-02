## Step 2: Pide al Orchestrator un plan

> **Idea clave:** el Orchestrator no debería convertirse en un "agente que hace todo". Su valor está en decidir **quién hace qué, con qué contexto y con qué criterio de salida**.

### Requerimiento

Construir un dashboard **Project Pulse** que muestre:

- nombre del proyecto;
- estado;
- progreso;
- responsable;
- fecha de actualización.

Debe ser simple, responsive y funcionar sin backend.

### 1. Analiza antes de delegar

Primero pregunta al Orchestrator:

> Antes de delegar, analiza el requerimiento. ¿Qué partes del trabajo deberían pasar por Planner, Designer, Coder y Validator? ¿Qué contexto debe recibir cada uno? No implementes.

Observa si identifica correctamente las dependencias.

### 2. Delegación al Planner

Pide:

> Coordina al Planner para convertir este requerimiento en un plan ejecutable. El Planner no debe implementar código. El plan debe incluir objetivo, alcance, entregables, dependencias, riesgos, criterios de aceptación y estrategia de validación.

Guarda el resultado en `docs/project-plan.md`.

### 3. Evalúa el plan

No aceptes automáticamente el primer resultado.

Comprueba si el plan responde:

- ¿qué se va a construir?
- ¿qué archivos deberían cambiar?
- ¿qué queda fuera del alcance?
- ¿cómo se comprobará que funciona?
- ¿qué riesgos existen?
- ¿qué necesita saber el Designer?
- ¿qué necesita saber el Coder?
- ¿qué debe validar el Validator?

### 4. Prueba un handoff defectuoso

Pregunta al Orchestrator:

> Imagina que entregas al Designer un plan sin criterios de aceptación. ¿Qué decisiones podría tomar de forma arbitraria? Propón cómo mejorarías el handoff.

Añade una sección **Handoff quality** en `docs/project-plan.md` explicando qué información consideras imprescindible.

### 5. Decisiones humanas

Agrega:

- una decisión que tomaste tú;
- una recomendación del Planner que aceptaste;
- una recomendación que modificaste o rechazaste;
- un criterio que usarás para saber cuándo el plan está listo para implementación.

Haz commit y push.

**Tiempo sugerido: 15-18 min.**
