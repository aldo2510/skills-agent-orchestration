# Step 6 — Ejecuta un handoff de corrección

## Objetivo
Demostrar que un hallazgo del Validator viaja hasta el agente responsable y vuelve con evidencia.

## Prompt exacto
~~~text
Actúa como Orchestrator.
Lee docs/validation-report.md.
Para cada hallazgo identifica al agente responsable, crea un handoff concreto, pide la corrección mínima, exige evidencia y actualiza docs/coding-handoff.md.
No cierres un hallazgo sin evidencia.
~~~

## 1. Actualiza docs/coding-handoff.md

Copia esta sección al final:

~~~markdown
## Iteración de corrección

| Hallazgo | Agente | Acción | Evidencia | Estado |
|---|---|---|---|---|
| Referencia incorrecta | Coder | Revisar referencia | HTML revisado | Resuelto |
| Dato inválido | Coder | Corregir JSON | python -m json.tool | Resuelto |
| Problema visual | Designer/Coder | Ajustar layout | Revisión del navegador | Resuelto |

## Regla
Un hallazgo pasa a Resuelto solo cuando existe evidencia verificable.
~~~

Si el Validator no encontró esos hallazgos, reemplaza las filas por los hallazgos reales. No inventes resultados.

## 2. Verificación
~~~bash
test -f docs/coding-handoff.md
grep -Eiq 'Iteración|hallazgo|Agente' docs/coding-handoff.md
~~~

## 3. Commit
~~~bash
git add docs/coding-handoff.md app
git commit -m "docs: record correction handoff"
git push
~~