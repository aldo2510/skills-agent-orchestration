# Step 1 — Conoce el equipo de agentes

## Objetivo
Identifica las responsabilidades reales antes de delegar trabajo.

## 1. Inspecciona los agentes
~~~bash
find .github/agents -maxdepth 1 -type f -print
for f in .github/agents/*.agent.md; do echo "===== $f ====="; cat "$f"; done
~~~

## 2. Prompt exacto para Copilot
~~~text
Analiza todos los agentes de .github/agents.

No modifiques archivos.

Para cada agente explica:
- responsabilidad;
- entrada;
- salida;
- límites;
- siguiente agente recomendado.

Explica cómo Orchestrator debe conservar contexto y exigir evidencia.
~~~

## 3. Crea docs/agent-map.md
~~~markdown
# Agent Map

| Agente | Responsabilidad | Entrada | Salida |
|---|---|---|---|
| Orchestrator | Coordinar agentes y contexto | Objetivo y resultados | Handoffs y decisiones |
| Planner | Planificar | Requerimiento | Plan |
| Designer | Diseñar UI | Plan | Diseño |
| Coder | Implementar | Diseño y plan | Código |
| Validator | Validar | Código y criterios | Evidencia y hallazgos |

## Reglas
1. Cada agente tiene un límite claro.
2. Orchestrator coordina y no reemplaza especialistas.
3. Cada handoff contiene contexto, tarea, restricciones y evidencia.
4. Ningún resultado se acepta sin validación.
~~~

## 4. Verificación
~~~bash
test -f docs/agent-map.md
grep -Eiq 'Orchestrator|Planner|Designer|Coder|Validator' docs/agent-map.md
grep -Eiq 'handoff|entrada|salida' docs/agent-map.md
~~~

## 5. Commit
~~~bash
git add docs/agent-map.md
git commit -m "docs: map agent responsibilities"
git push
~~~

**Tiempo sugerido: 12–14 min.**