## Step 1: Conoce tu equipo de agentes

> **Idea clave:** un equipo de agentes no es una colección de prompts. Cada agente debe tener una responsabilidad, límites, entradas y una salida clara para que otro agente pueda continuar el trabajo.

### 1. Abre el entorno

Abre un Codespace y ejecuta Copilot CLI.

Inspecciona:
- .github/agents/orchestrator.agent.md
- .github/agents/planner.agent.md
- .github/agents/designer.agent.md
- .github/agents/coder.agent.md
- .github/agents/validator.agent.md

No pidas todavía que implementen el dashboard.

### 2. Entiende las responsabilidades

Identifica:

| Agente | Responsabilidad |
|---|---|
| Orchestrator | Coordina el trabajo y conserva el contexto |
| Planner | Convierte el requerimiento en un plan |
| Designer | Define estructura y experiencia visual |
| Coder | Implementa |
| Validator | Busca problemas y entrega evidencia |

Para cada agente responde:
- ¿qué puede hacer?
- ¿qué no debería hacer?
- ¿qué información necesita?
- ¿qué debe entregar?
- ¿quién consume su salida?

### 3. Experimenta con el contexto

Pide al Orchestrator:

> Explica qué información necesitarías recibir antes de delegar una tarea al Planner. No modifiques ningún archivo.

Después:

> ¿Qué podría salir mal si el Coder recibe únicamente "construye el dashboard" sin recibir el requerimiento, restricciones ni criterios de aceptación?

Compara las respuestas con tus propios criterios.

### 4. Crea docs/agent-map.md

**El archivo no existe inicialmente. Debes crearlo.**

Usa esta plantilla:

    # Agent Map

    ## 1. Objetivo del equipo
    Explica qué problema resuelve el conjunto de agentes.

    ## 2. Agentes
    | Agente | Responsabilidad | Entrada | Salida | Consumidor |
    |---|---|---|---|---|
    | Orchestrator | ... | ... | ... | ... |
    | Planner | ... | ... | ... | ... |
    | Designer | ... | ... | ... | ... |
    | Coder | ... | ... | ... | ... |
    | Validator | ... | ... | ... | ... |

    ## 3. Flujo de handoffs
    Describe paso a paso cómo debería viajar la información.

    ## 4. Información que no debería perderse
    - ...
    - ...
    - ...

    ## 5. Decisiones bajo control humano
    - ...
    - ...

    ## 6. Escenario de accesibilidad
    Si Validator encuentra un problema de accesibilidad:
    - ¿quién interpreta el hallazgo?
    - ¿quién decide si se corrige?
    - ¿quién implementa?
    - ¿quién vuelve a validar?
    - ¿por qué?

### 5. Criterios de salida

- [ ] Identificaste los 5 agentes.
- [ ] Documentaste entrada y salida de cada uno.
- [ ] Definiste los handoffs.
- [ ] Identificaste decisiones humanas.
- [ ] Respondiste el escenario de accesibilidad.

Haz commit y push.

**Tiempo sugerido: 15-18 min.**
