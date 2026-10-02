# Step 2 — Planifica con Planner

## Objetivo
Convertir un objetivo en un plan que otro agente pueda ejecutar sin inventar requisitos.

## 1. Prompt exacto
~~~text
Actúa como Orchestrator.

Delegá al agente Planner la planificación de Project Pulse.

Debe entregar:
- objetivo;
- alcance;
- requisitos;
- estructura de datos;
- componentes;
- entregables;
- criterios de aceptación;
- riesgos;
- handoff para Designer;
- handoff para Coder;
- criterios para Validator.

No implementes código.
~~~

## 2. Crea docs/project-plan.md
~~~markdown
# Project Plan

## Objetivo
Construir Project Pulse, un dashboard estático que muestre proyectos, estado, responsable, actualización y progreso.

## Alcance
- HTML.
- CSS separado.
- JSON separado.
- Sin backend.
- Responsive.
- Accesibilidad básica.

## Entregables
- app/index.html
- app/styles.css
- app/project-data.json
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md
- docs/final-handoff.md

## Criterios de aceptación
- HTML carga CSS y JSON.
- Todos los proyectos aparecen.
- Cada tarjeta muestra nombre, estado, owner, fecha y progreso.
- El layout se adapta a pantallas pequeñas.
- No requiere backend.

## Riesgos
- JSON inválido.
- Referencias rotas.
- Problemas responsive.
- Datos inconsistentes.

## Handoffs
Planner → Designer: requisitos visuales.
Designer → Coder: diseño y restricciones.
Coder → Validator: archivos y evidencia.
Validator → Orchestrator: hallazgos.
~~~

## 3. Verificación
~~~bash
test -f docs/project-plan.md
grep -Eiq 'objetivo|alcance' docs/project-plan.md
grep -Eiq 'entregables|riesgos|criterios' docs/project-plan.md
grep -Eiq 'handoff|Designer|Coder|Validator' docs/project-plan.md
~~~

## 4. Commit
~~~bash
git add docs/project-plan.md
git commit -m "docs: create project plan"
git push
~~~

**Tiempo sugerido: 12–14 min.**