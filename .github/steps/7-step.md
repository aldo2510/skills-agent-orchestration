# Step 7 — Ejecuta una segunda validación

## Objetivo
Una corrección sin nueva evidencia es una hipótesis. Validator debe comprobar nuevamente el resultado.

## 1. Prompt exacto
~~~text
Actúa como Validator.

Revisa nuevamente el dashboard después de las correcciones.

No modifiques archivos.

Compara cada hallazgo de la primera validación con el estado actual.
Para cada uno indica:
- hallazgo original;
- evidencia actual;
- resultado;
- si quedó resuelto;
- si requiere otra iteración.

Incluye también JSON, HTML, CSS, responsive y accesibilidad.
~~~

## 2. Actualiza docs/validation-report.md
Agrega esta sección:

~~~markdown
## Segunda ronda

| Hallazgo original | Evidencia nueva | Resultado |
|---|---|---|
| Referencia de archivo | HTML y navegador revisados | Resuelto |
| JSON inválido | python -m json.tool | Resuelto |
| Problema visual | Revisión responsive | Resuelto |

## Segunda validación

La segunda validación confirma si las correcciones resolvieron los hallazgos. Si alguno continúa abierto, debe regresar al Orchestrator.
~~~

## 3. Ejecuta verificaciones
~~~bash
python -m json.tool app/project-data.json
grep -E 'styles.css|project-data.json' app/index.html
~~~

## 4. Commit
~~~bash
git add docs/validation-report.md app
git commit -m "docs: record second validation"
git push
~~~

**Tiempo sugerido: 7–9 min.**