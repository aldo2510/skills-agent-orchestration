# Step 4 — Audita la orquestación

## Objetivo
Detectar handoffs débiles, responsabilidades duplicadas y evidencia insuficiente.

## 1. Prompt exacto
~~~text
Audita:
- docs/agent-map.md
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md

No modifiques archivos.

Indica:
1. un handoff claro;
2. un handoff mejorable;
3. responsabilidades que se solapan;
4. evidencia insuficiente;
5. una decisión que debe permanecer humana;
6. una mejora para una versión 2.
~~~

## 2. Crea docs/orchestration-review.md
~~~markdown
# Orchestration Review

## Handoff claro
Planner → Designer porque existe una entrada y una salida explícitas.

## Handoff mejorable
Validator → Orchestrator debe transportar evidencia por criterio.

## Solapamientos
Orchestrator coordina; no debe reemplazar a los especialistas.

## Evidencia insuficiente
El comportamiento responsive requiere revisión visual, no solo lectura de HTML.

## Control humano
La aceptación del resultado corresponde al participante.

## Versión 2
Objetivo → Planner → Designer → Coder → Validator → corrección → Validator → humano.
~~~

## 3. Verificación
~~~bash
test -f docs/orchestration-review.md
grep -Eiq 'handoff|humano|Orchestrator' docs/orchestration-review.md
grep -Eiq 'mejora|versión 2|v2' docs/orchestration-review.md
~~~

## 4. Commit
~~~bash
git add docs/orchestration-review.md
git commit -m "docs: audit orchestration"
git push
~~~

**Tiempo sugerido: 10–12 min.**