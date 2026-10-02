## Step 1: Conoce el equipo de agentes

### Teoría: qué es la orquestación de agentes

Un agente especializado no debería recibir todas las responsabilidades.

La orquestación consiste en dividir el trabajo y controlar el flujo:

```
Objetivo
   ↓
Orchestrator
   ↓
Agentes especializados
   ↓
Handoffs
   ↓
Validación
   ↓
Humano
```

Cada agente debe tener:
- una responsabilidad clara;
- contexto suficiente;
- límites;
- una salida definida;
- un consumidor para su resultado.

El Orchestrator no reemplaza a los especialistas: **coordina el trabajo y mantiene el contexto**.

### 1. Inspecciona los agentes

Abre:
- .github/agents/orchestrator.agent.md
- .github/agents/planner.agent.md
- .github/agents/designer.agent.md
- .github/agents/coder.agent.md
- .github/agents/validator.agent.md

### 2. Copia y pega este prompt

```text
Analiza los cinco agentes del directorio .github/agents.

No modifiques ningún archivo.

Para cada agente indica:
- responsabilidad;
- entrada que necesita;
- salida que debe producir;
- qué tareas NO debería realizar;
- qué agente debería consumir su salida.

Después describe el flujo recomendado entre Orchestrator, Planner, Designer, Coder y Validator.

Finalmente explica qué decisiones deberían permanecer bajo control humano.
```

### 3. Crea docs/agent-map.md

**Copia esta plantilla:**

```markdown
# Agent Map

## 1. Objetivo del equipo
...

## 2. Agentes
| Agente | Responsabilidad | Entrada | Salida | Consumidor |
|---|---|---|---|---|
| Orchestrator | ... | ... | ... | ... |
| Planner | ... | ... | ... | ... |
| Designer | ... | ... | ... | ... |
| Coder | ... | ... | ... | ... |
| Validator | ... | ... | ... | ... |

## 3. Flujo de handoffs
1. ...
2. ...
3. ...

## 4. Información que no debe perderse
- ...
- ...

## 5. Decisiones humanas
- ...

## 6. Escenario de accesibilidad
Si Validator detecta un problema:
- quién interpreta;
- quién decide;
- quién implementa;
- quién valida nuevamente.
```

### 4. Verifica

Copia y pega:

```text
Revisa docs/agent-map.md contra los cinco archivos .github/agents/*.agent.md.

No modifiques el documento.

Devuelve una tabla indicando para cada agente si la responsabilidad, entrada y salida están correctamente documentadas.
```

Corrige el documento según los hallazgos.

Haz commit y push.

**Tiempo: 12-14 min.**
