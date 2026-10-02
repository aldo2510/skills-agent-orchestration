# Step 2 — Planifica con Planner

## Objetivo
Convertir el objetivo de Project Pulse en un plan que otro agente pueda ejecutar sin inventar requisitos.

## Prompt exacto
~~~text
Actúa como Orchestrator.
Delega al Planner la planificación de Project Pulse.
Debe producir objetivo, alcance, requisitos, estructura de datos, componentes, entregables, criterios de aceptación, riesgos y handoffs para Designer, Coder y Validator.
No implementes código.
~~~

## 1. Crea docs/project-plan.md
~~~markdown
# Project Plan

## Objetivo
Construir Project Pulse, un dashboard estático que muestre proyectos, estado, responsable, fecha de actualización y progreso.

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

## 2. Verificación
~~~bash
test -f docs/project-plan.md
grep -Eiq 'objetivo|alcance|entregables|riesgos|criterios' docs/project-plan.md
grep -Eiq 'handoff|Designer|Coder|Validator' docs/project-plan.md
~~~

## 3. Commit
~~~bash
git add docs/project-plan.md
git commit -m "docs: create project plan"
git push
~~