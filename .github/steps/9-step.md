# Step 9 — Audita nuevamente la orquestación

## Objetivo
Comprobar que el flujo produjo trazabilidad, evidencia e iteración real.

## 1. Prompt exacto
~~~text
Audita toda la orquestación.

No modifiques archivos.

Revisa:
- responsabilidades;
- handoffs;
- iteraciones;
- evidencia;
- validación;
- decisiones humanas.

Identifica:
1. un handoff bien definido;
2. un handoff mejorable;
3. un solapamiento;
4. una evidencia insuficiente;
5. una mejora concreta para una versión 2.
~~~

## 2. Crea docs/orchestration-review.md
~~~markdown
# Orchestration Review

## Handoff bien definido
Planner → Designer tiene una entrada y una salida explícitas.

## Handoff mejorable
Validator → Orchestrator debe transportar evidencia por criterio y no solo un resumen.

## Solapamientos
Orchestrator coordina; no debe implementar ni sustituir al Validator.

## Evidencia insuficiente
El responsive behavior requiere revisión visual en más de un tamaño.

## Decisión humana
La persona participante decide si la evidencia es suficiente para aceptar el resultado.

## Mejora para V2
Usar un formato común de handoff:
- contexto;
- objetivo;
- restricciones;
- resultado;
- evidencia;
- riesgos;
- siguiente acción.

## Flujo V2
Objetivo → Planner → Designer → Coder → Validator → corrección → Validator → Orchestrator → humano.
~~~

## 3. Verificación
~~~bash
test -f docs/orchestration-review.md
grep -Eiq 'handoff|humano|Orchestrator' docs/orchestration-review.md
~~~

## 4. Commit
~~~bash
git add docs/orchestration-review.md
git commit -m "docs: complete orchestration audit"
git push
~~~

**Tiempo sugerido: 8–10 min.**