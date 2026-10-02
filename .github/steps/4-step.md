# Step 4 — Audita la orquestación

## Objetivo

Analizar si los agentes están colaborando correctamente y si los handoffs contienen información suficiente para que el siguiente agente pueda continuar el trabajo.

El documento de evidencia ya está preparado. No necesitas pedirle a Copilot que genere el Markdown.

## 1. Revisión opcional con Copilot

Copia y pega este prompt:

~~~text
Audita la orquestación del proyecto revisando:
- docs/agent-map.md
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md

No modifiques ningún archivo.

Indica:
1. Un handoff que sea claro.
2. Un handoff que pueda mejorarse.
3. Si existen responsabilidades solapadas.
4. Qué evidencia es insuficiente.
5. Una decisión que deba permanecer bajo control humano.
6. Una mejora concreta para una versión 2 del flujo.

No escribas código.
~~~

La respuesta de Copilot sirve como apoyo. Debes contrastarla con los documentos reales.

## 2. Crea docs/orchestration-review.md

Crea exactamente:

`docs/orchestration-review.md`

Copia y pega:

~~~markdown
# Orchestration Review

## Handoff claro

Planner → Designer tiene una entrada y una salida explícitas.

El Planner entrega requisitos, dependencias y restricciones. El Designer utiliza esa información para definir la estructura visual.

## Handoff mejorable

Validator → Orchestrator debe transportar evidencia por criterio y no solamente un resumen general.

Un buen handoff debe indicar:
- qué se validó;
- qué evidencia se encontró;
- qué falló;
- qué agente debe actuar;
- qué resultado se espera después de la corrección.

## Responsabilidades

| Agente | Responsabilidad |
|---|---|
| Orchestrator | Coordinar el flujo y mantener el contexto |
| Planner | Convertir requisitos en un plan |
| Designer | Definir la experiencia visual |
| Coder | Implementar el dashboard |
| Validator | Validar y reportar evidencias |

El Orchestrator coordina y no debe reemplazar el trabajo especializado de los demás agentes.

## Evidencia insuficiente

El comportamiento responsive requiere revisión visual además de la inspección del HTML y CSS.

La existencia de una regla CSS no demuestra por sí sola que el resultado visual sea correcto.

## Decisión humana

La aceptación final del resultado corresponde al participante.

Los agentes pueden proponer cambios, pero la decisión de aceptar el resultado permanece bajo control humano.

## Versión 2 del flujo

Objetivo → Planner → Designer → Coder → Validator → corrección → Validator → revisión humana.

## Conclusión

La orquestación debe evaluarse por la calidad de los handoffs y por la evidencia que acompaña cada resultado, no únicamente por la cantidad de agentes utilizados.
~~~

## 3. Verificación

Ejecuta:

~~~bash
test -f docs/orchestration-review.md
grep -Eiq 'handoff|humano|Orchestrator' docs/orchestration-review.md
grep -Eiq 'mejora|versión 2|V2' docs/orchestration-review.md
~~~

Todos deben finalizar correctamente.

## Criterio de salida

No continúes mientras:

- no exista `docs/orchestration-review.md`;
- el documento no incluya un handoff claro;
- no exista un handoff mejorable;
- no se haya documentado la decisión humana;
- no se haya definido una mejora para una versión 2.

## 4. Commit y push

~~~bash
git add docs/orchestration-review.md
git commit -m "docs: audit orchestration"
git push
~~~
