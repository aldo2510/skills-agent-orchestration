## Step 1: Conoce tu equipo de agentes

> **Idea clave:** un equipo de agentes no es una colección de prompts. Cada agente debe tener una responsabilidad, límites, entradas y una salida clara para que otro agente pueda continuar el trabajo.

### 1. Abre el entorno

Abre un Codespace y ejecuta Copilot CLI.

Inspecciona primero el repositorio y después los archivos bajo `.github/agents/`.

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

Lee cada archivo `.agent.md` y responde:

- ¿qué puede hacer el agente?
- ¿qué no debería hacer?
- ¿qué información necesita para trabajar?
- ¿qué debería entregar al siguiente agente?

### 3. Experimenta con el contexto

Pide al Orchestrator:

> Explica qué información necesitarías recibir antes de delegar una tarea al Planner. No modifiques ningún archivo.

Después pregunta:

> ¿Qué podría salir mal si el Coder recibe únicamente "construye el dashboard" sin recibir el requerimiento, restricciones ni criterios de aceptación?

Compara la respuesta con tus propios criterios.

### 4. Diseña el mapa de handoffs

Crea `docs/agent-map.md`.

Incluye:

- responsabilidad de cada agente;
- entradas esperadas;
- salida esperada;
- agente que consume esa salida;
- información que debe viajar en cada handoff;
- un ejemplo de información que **no** debería delegarse automáticamente;
- qué decisiones permanecen bajo control humano.

Puedes representar el flujo así:

```text
Human
  ↓
Orchestrator
  ↓
Planner
  ↓
Designer → Coder → Validator
                  ↓
              feedback
                  ↓
                Coder
                  ↓
                Human
```

### 5. Mini ejercicio de arquitectura

Imagina que el Validator encuentra un problema de accesibilidad.

Escribe quién debería:
1. interpretar el hallazgo;
2. decidir si debe corregirse;
3. implementar la corrección;
4. comprobar nuevamente el resultado.

Explica por qué.

Haz commit y push.

**Tiempo sugerido: 15-18 min.**
