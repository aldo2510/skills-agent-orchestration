# Step 4 — Audita la orquestación

## Objetivo
Detectar handoffs débiles, responsabilidades duplicadas y evidencia insuficiente.

## Prompt exacto
~~~text
Audita docs/agent-map.md, docs/project-plan.md, docs/design-handoff.md, docs/coding-handoff.md y docs/validation-report.md.
No modifiques archivos.
Indica un handoff claro, uno mejorable, responsabilidades solapadas, evidencia insuficiente, una decisión humana y una mejora para V2.
~~~

## 1. Crea docs/orchestration-review.md
~~~markdown
# Orchestration Review

## Handoff claro
Planner → Designer tiene una entrada y una salida explícitas.

## Handoff mejorable
Validator → Orchestrator debe transportar evidencia por criterio y no solo un resumen.

## Solapamientos
Orchestrator coordina; no debe reemplazar a los especialistas.

## Evidencia insuficiente
El comportamiento responsive requiere revisión visual, no solo lectura del HTML.

## Control humano
La aceptación del resultado corresponde al participante.

## Versión 2
Objetivo → Planner → Designer → Coder → Validator → corrección → Validator → humano.
~~~

## 2. Verificación
~~~bash
test -f docs/orchestration-review.md
grep -Eiq 'handoff|humano|Orchestrator' docs/orchestration-review.md
grep -Eiq 'mejora|versión 2|V2' docs/orchestration-review.md
~~~

## 3. Commit
~~~bash
git add docs/orchestration-review.md
git commit -m "docs: audit orchestration"
git push
~~