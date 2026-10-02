# Step 3 — Orquesta diseño, código y validación

## Objetivo
Ejecutar un flujo multiagente completo con handoffs y evidencia.

## 1. Prompt al Orchestrator
~~~text
Actúa como Orchestrator.

Usa docs/project-plan.md.

Ejecuta por delegación:
1. Planner entrega el plan.
2. Designer produce el diseño.
3. Guarda el resultado en docs/design-handoff.md.
4. Coder implementa app/index.html, app/styles.css y app/project-data.json.
5. Validator revisa el resultado.
6. Guarda docs/validation-report.md.
7. Si hay hallazgos, identifica al agente responsable.
8. Documenta docs/coding-handoff.md.
9. Genera docs/final-handoff.md.

Cada handoff debe incluir contexto, tarea, restricciones, resultado y evidencia.
No mezcles responsabilidades.
~~~

## 2. Prompt para Designer
~~~text
Actúa como Designer.

Usa docs/project-plan.md.
No implementes código.

Define layout, jerarquía, tarjetas, estados, progreso, responsive y accesibilidad.
Entrega un handoff claro para Coder.
~~~

## 3. Crea docs/design-handoff.md
~~~markdown
# Design Handoff

## Layout
Header superior y grid responsive de tarjetas.

## Tarjeta
Nombre, estado, owner, fecha, progreso y porcentaje.

## Responsive
La grilla debe adaptarse al ancho sin scroll horizontal.

## Accesibilidad
HTML semántico, headings claros, textos legibles y progreso accesible.

## Handoff a Coder
Conservar HTML, CSS y JSON separados. No usar backend.
~~~

## 4. Prompt para Coder
~~~text
Actúa como Coder.

Usa docs/project-plan.md y docs/design-handoff.md.

Implementa app/index.html, app/styles.css y app/project-data.json.
Mantén separación de responsabilidades.
No agregues backend.
Verifica las referencias y el JSON.
~~~

## 5. Prompt para Validator
~~~text
Actúa como Validator.

No modifiques archivos.

Valida HTML, CSS, JSON, datos visibles, estados, progreso, responsive, accesibilidad y ausencia de backend.
Para cada criterio entrega evidencia concreta y resultado.
~~~

## 6. Crea docs/validation-report.md
~~~markdown
# Validation Report

| Criterio | Resultado | Evidencia |
|---|---|---|
| HTML | Revisar | app/index.html |
| CSS | Revisar | referencia styles.css |
| JSON | Revisar | python -m json.tool |
| Datos | Revisar | project-data.json |
| Estados | Revisar | navegador |
| Progreso | Revisar | navegador |
| Responsive | Revisar | tamaños de pantalla |
| Accesibilidad | Revisar | HTML semántico |
| Sin backend | Revisar | estructura del repo |

## Hallazgos
Todo hallazgo debe tener evidencia y agente responsable.

## Segunda ronda
Después de corregir cualquier hallazgo, Validator debe volver a ejecutar la validación.
~~~

## 7. Crea docs/coding-handoff.md
~~~markdown
# Coding Handoff

| Etapa | Agente | Entrada | Salida | Evidencia |
|---|---|---|---|---|
| Plan | Planner | Requerimiento | Plan | docs/project-plan.md |
| Diseño | Designer | Plan | Diseño | docs/design-handoff.md |
| Código | Coder | Diseño | Archivos | app/ |
| Validación | Validator | Código | Hallazgos | docs/validation-report.md |

## Regla de iteración
Un hallazgo vuelve al agente responsable y solo se cierra con nueva evidencia.
~~~

## 8. Crea docs/final-handoff.md
~~~markdown
# Final Handoff

## Objetivo
Project Pulse funcional y validado.

## Responsabilidades
Orchestrator coordina. Planner planifica. Designer diseña. Coder implementa. Validator valida.

## Evidencia
Plan, diseño, código, validación y handoffs.

## Riesgos
Cambios posteriores requieren nueva validación.

## Decisión humana
La aceptación final corresponde al participante.
~~~

## 9. Verificación
~~~bash
test -f docs/design-handoff.md
test -f docs/coding-handoff.md
test -f docs/validation-report.md
test -f docs/final-handoff.md
python -m json.tool app/project-data.json
grep -Eiq 'Orchestrator|Planner|Designer|Coder|Validator' docs/final-handoff.md
~~~

## 10. Commit
~~~bash
git add app docs
git commit -m "feat: orchestrate dashboard workflow"
git push
~~~

**Tiempo sugerido: 20–25 min.**