# Step 8 — Genera el handoff final

## Objetivo
Dejar suficiente contexto para que otra persona pueda continuar el proyecto sin reconstruir el historial.

## Prompt exacto
~~~text
Actúa como Orchestrator.
Usa docs/project-plan.md, docs/design-handoff.md, docs/coding-handoff.md, docs/validation-report.md y docs/orchestration-review.md.
No modifiques código.
Genera un handoff final con objetivo, resultado, responsabilidades, evidencia, iteraciones, riesgos, pendientes y decisiones humanas.
~~~

## 1. Crea docs/final-handoff.md
~~~markdown
# Final Handoff

## Objetivo
Construir y validar Project Pulse.

## Resultado
El dashboard se implementó con HTML, CSS y JSON, sin backend.

## Responsabilidades
- Orchestrator: coordinación.
- Planner: planificación.
- Designer: diseño.
- Coder: implementación.
- Validator: validación.

## Evidencia
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md
- docs/orchestration-review.md

## Iteraciones
Registrar las iteraciones realmente ejecutadas y su evidencia.

## Riesgos
Registrar únicamente riesgos observados o relevantes al alcance.

## Pendientes
Registrar cualquier pendiente real antes de cerrar.

## Decisiones humanas
La aceptación del resultado y de los riesgos permanece bajo control humano.
~~~

## 2. Verificación
~~~bash
test -f docs/final-handoff.md
grep -Eiq 'Orchestrator|Planner|Designer|Coder|Validator' docs/final-handoff.md
~~~

## 3. Commit
~~~bash
git add docs/final-handoff.md
git commit -m "docs: create final agent handoff"
git push
~~