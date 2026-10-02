# Step 3 — Diseña e implementa mediante handoffs

## Objetivo
Ejecutar el flujo Planner → Designer → Coder → Validator, conservando evidencia en cada transición.

## Prompt al Orchestrator
~~~text
Actúa como Orchestrator.
Usa docs/project-plan.md.
Delega primero al Designer y guarda docs/design-handoff.md.
Después delega al Coder para implementar app/index.html, app/styles.css y app/project-data.json.
Finalmente delega al Validator para revisar el resultado y guardar docs/validation-report.md.
Cada handoff debe incluir contexto, objetivo, restricciones, resultado y evidencia.
No mezcles responsabilidades.
~~~

## Prompt para Designer
~~~text
Actúa como Designer.
Usa docs/project-plan.md.
No implementes código.
Define layout, jerarquía visual, tarjetas, estados, progreso, responsive y accesibilidad.
Entrega un handoff claro para Coder.
~~~

## 1. Crea docs/design-handoff.md
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

## Restricciones
No backend. HTML, CSS y JSON separados.

## Handoff a Coder
Implementar únicamente el alcance definido y conservar la separación entre estructura, estilos y datos.
~~~

## Prompt para Coder
~~~text
Actúa como Coder.
Usa docs/project-plan.md y docs/design-handoff.md.
Implementa app/index.html, app/styles.css y app/project-data.json.
Mantén separación de responsabilidades.
No agregues backend.
Verifica referencias y JSON.
~~~

## Prompt para Validator
~~~text
Actúa como Validator.
No modifiques archivos.
Valida HTML, CSS, JSON, datos visibles, estados, progreso, responsive, accesibilidad y ausencia de backend.
Para cada criterio entrega resultado y evidencia concreta.
~~~

## 2. Crea docs/validation-report.md
~~~markdown
# Validation Report

| Criterio | Resultado | Evidencia |
|---|---|---|
| HTML | Cumple | app/index.html |
| CSS | Cumple | app/styles.css |
| JSON | Cumple | python -m json.tool app/project-data.json |
| Datos | Cumple | app/project-data.json |
| Estados | Verificar | navegador |
| Progreso | Verificar | navegador |
| Responsive | Verificar | navegador en varios tamaños |
| Accesibilidad | Verificar | HTML semántico |
| Sin backend | Cumple | estructura del repositorio |

## Hallazgos
Registrar cada hallazgo con agente responsable y evidencia.

## Regla de cierre
Un hallazgo solo se cierra cuando existe nueva evidencia.
~~~

## 3. Crea docs/coding-handoff.md
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

## 4. Verificación
~~~bash
test -f docs/design-handoff.md
test -f docs/coding-handoff.md
test -f docs/validation-report.md
python -m json.tool app/project-data.json
grep -Eiq 'Orchestrator|Planner|Designer|Coder|Validator' docs/coding-handoff.md
~~~

## 5. Commit
~~~bash
git add app docs
git commit -m "feat: orchestrate dashboard workflow"
git push
~~