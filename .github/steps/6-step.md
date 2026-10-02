# Step 6 — Ejecuta un handoff de corrección

## Objetivo
Demostrar que un hallazgo del Validator viaja hasta el agente responsable y vuelve con evidencia.

## 1. Prompt exacto
~~~text
Actúa como Orchestrator.

Lee docs/validation-report.md.

Para cada hallazgo:
1. identifica al agente responsable;
2. crea un handoff concreto;
3. pide la corrección mínima;
4. exige evidencia del cambio;
5. actualiza docs/coding-handoff.md.

No cierres un hallazgo sin evidencia.
~~~

## 2. Actualiza docs/coding-handoff.md
~~~markdown
# Coding Handoff

## Iteración de corrección

| Hallazgo | Agente | Acción | Evidencia | Estado |
|---|---|---|---|---|
| Referencia incorrecta | Coder | Revisar referencia | HTML revisado | Resuelto |
| Dato inválido | Coder | Corregir JSON | python -m json.tool | Resuelto |
| Problema visual | Designer/Coder | Ajustar layout | Revisión del navegador | Resuelto |

## Regla
Un hallazgo pasa a Resuelto solo cuando existe evidencia verificable.
~~~

## 3. Verificación
~~~bash
test -f docs/coding-handoff.md
grep -Eiq 'Iteración|hallazgo|Agente' docs/coding-handoff.md
~~~

## 4. Commit
~~~bash
git add docs/coding-handoff.md app
git commit -m "docs: record correction handoff"
git push
~~~

**Tiempo sugerido: 8–10 min.**