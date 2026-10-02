## Step 2: Pide al Orchestrator un plan

> **Idea clave:** el Orchestrator no debería convertirse en un "agente que hace todo". Su valor está en decidir quién hace qué, con qué contexto y con qué criterio de salida.

### Requerimiento

Construir un dashboard **Project Pulse** que muestre:
- nombre del proyecto;
- estado;
- progreso;
- responsable;
- fecha de actualización.

Debe ser simple, responsive y funcionar sin backend.

### 1. Analiza antes de delegar

Pregunta al Orchestrator:

> Antes de delegar, analiza el requerimiento. ¿Qué partes del trabajo deberían pasar por Planner, Designer, Coder y Validator? ¿Qué contexto debe recibir cada uno? No implementes.

### 2. Delega al Planner

Pide:

> Coordina al Planner para convertir este requerimiento en un plan ejecutable. El Planner no debe implementar código. El plan debe incluir objetivo, alcance, entregables, dependencias, riesgos, criterios de aceptación y estrategia de validación.

### 3. Crea docs/project-plan.md

**El archivo no existe inicialmente.**

Usa esta estructura:

    # Project Pulse - Plan de proyecto

    ## 1. Objetivo
    ...

    ## 2. Alcance
    ### Incluido
    - ...
    ### Fuera de alcance
    - ...

    ## 3. Entregables
    - app/index.html
    - app/styles.css
    - app/project-data.json
    - documentación de handoffs

    ## 4. Responsabilidades
    | Agente | Responsabilidad |
    |---|---|
    | Planner | ... |
    | Designer | ... |
    | Coder | ... |
    | Validator | ... |

    ## 5. Dependencias
    - ...

    ## 6. Criterios de aceptación
    - El dashboard muestra ...
    - ...
    
    ## 7. Estrategia de validación
    - ...

    ## 8. Riesgos
    | Riesgo | Impacto | Mitigación |
    |---|---|---|
    | ... | ... | ... |

    ## 9. Handoff quality
    ¿Qué información es imprescindible para que Designer y Coder puedan continuar sin reinterpretar el requerimiento?

    ## 10. Decisiones humanas
    - Decisión tomada:
    - Recomendación aceptada:
    - Recomendación modificada/rechazada:
    - Criterio para considerar el plan listo:

### 4. Evalúa el plan

No aceptes automáticamente el primer resultado.

Comprueba:
- ¿qué se va a construir?
- ¿qué queda fuera?
- ¿cómo se comprobará?
- ¿qué riesgos existen?
- ¿qué necesita saber Designer?
- ¿qué necesita saber Coder?
- ¿qué debe validar Validator?

### 5. Prueba un handoff defectuoso

Pregunta:

> Imagina que entregas al Designer un plan sin criterios de aceptación. ¿Qué decisiones podría tomar de forma arbitraria? Propón cómo mejorarías el handoff.

Incorpora tus conclusiones en la sección Handoff quality.

Haz commit y push.

**Tiempo sugerido: 15-18 min.**
