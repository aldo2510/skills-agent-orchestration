# Step 1 — Conoce el equipo de agentes

## Objetivo
Entender qué responsabilidad tiene cada agente y qué información debe pasar entre ellos.

## Prompt exacto
~~~text
Actúa como Orchestrator.
Analiza los agentes disponibles en .github/agents.
No modifiques archivos.
Para cada agente indica responsabilidad, entrada, salida, qué no debe hacer y siguiente handoff.
~~~

## 1. Crea docs/agent-map.md
~~~markdown
# Agent Map

| Agente | Responsabilidad | Entrada | Salida | No debe hacer |
|---|---|---|---|---|
| Orchestrator | Coordinar el flujo y conservar contexto | Objetivo y resultados | Delegaciones y decisiones | Sustituir a especialistas |
| Planner | Convertir objetivo en plan | Requerimiento | Plan ejecutable | Implementar código |
| Designer | Diseñar experiencia visual | Plan | Diseño/handoff | Implementar |
| Coder | Implementar | Plan + diseño | Archivos ejecutables | Cambiar requisitos |
| Validator | Comprobar resultado | Código + criterios | Evidencia y hallazgos | Ocultar fallos |

## Regla de handoff
Cada handoff debe contener contexto, objetivo, restricciones, resultado, evidencia y siguiente acción.
~~~

## 2. Verificación
~~~bash
test -f docs/agent-map.md
grep -Eiq 'Orchestrator|Planner|Designer|Coder|Validator' docs/agent-map.md
grep -Eiq 'handoff|entrada|salida' docs/agent-map.md
~~~

## 3. Commit
~~~bash
git add docs/agent-map.md
git commit -m "docs: map agent responsibilities"
git push
~~