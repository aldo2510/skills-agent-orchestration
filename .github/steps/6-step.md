# Step 6 — Ejecuta un handoff de corrección

## Objetivo
Demostrar un ciclo real: hallazgo → agente responsable → corrección → evidencia.

## Prompt exacto para Orchestrator
~~~text
Actúa como Orchestrator.
Queremos demostrar una iteración controlada.
Introduce deliberadamente un defecto pequeño y reversible en Project Pulse cambiando en app/index.html la referencia de styles.css por style.css.
Después delega al Validator para detectar el problema.
Cuando el Validator lo reporte, delega al Coder para corregirlo.
No cierres el hallazgo hasta que exista evidencia de la corrección.
Actualiza docs/coding-handoff.md con el handoff completo.
~~~

## 1. Prompt exacto para Validator
~~~text
Actúa como Validator.
No modifiques archivos.
Revisa las referencias de app/index.html y comprueba que CSS y JSON puedan cargarse.
Reporta el archivo afectado, el problema, la evidencia y el agente responsable de corregirlo.
~~~

## 2. Prompt exacto para Coder
~~~text
Actúa como Coder.
Corrige únicamente el defecto reportado por Validator.
No cambies el diseño ni agregues funcionalidades.
Verifica que app/index.html vuelva a referenciar correctamente app/styles.css.
Entrega evidencia del cambio.
~~~

## 3. Actualiza docs/coding-handoff.md

Copia esta sección al final:

~~~markdown
## Iteración de corrección

| Hallazgo | Agente | Acción | Evidencia | Estado |
|---|---|---|---|---|
| Referencia CSS incorrecta | Coder | Restaurar styles.css en index.html | grep de la referencia + revisión del navegador | Resuelto |

## Regla
El hallazgo solo pasa a Resuelto después de comprobar nuevamente el archivo corregido.
~~~

## 4. Verificación
~~~bash
grep -E 'styles.css|style.css' app/index.html
test -f docs/coding-handoff.md
grep -Eiq 'Iteración|hallazgo|Coder|Resuelto' docs/coding-handoff.md
~~~

## 5. Commit
~~~bash
git add docs/coding-handoff.md app/index.html
git commit -m "docs: record correction handoff"
git push
~~