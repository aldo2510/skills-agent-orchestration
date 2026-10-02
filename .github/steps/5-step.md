# Step 5 — Realiza la primera revisión humana

## Objetivo
Separar la validación de los agentes de la aceptación final de la persona.

## Prompt exacto
~~~text
Revisa el estado completo de Project Pulse y sus handoffs.
No modifiques archivos.
Resume objetivo, responsabilidades, hallazgos, evidencia, riesgos y decisiones que requieren intervención humana.
No escribas código.
~~~

## 1. Crea x-review.md
~~~markdown
# Human Review

## Checklist
- [ ] Dashboard visible.
- [ ] Proyectos correctos.
- [ ] Estados correctos.
- [ ] Progreso correcto.
- [ ] JSON válido.
- [ ] Referencias CSS y JSON correctas.
- [ ] Responsive revisado.
- [ ] Handoffs coherentes.
- [ ] Hallazgos revisados.

## Evidencia
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md
- docs/orchestration-review.md

## Decisión humana
**Resultado:** Acepto / Acepto con observaciones / Requiere corrección

**Motivo:** Escribe aquí la razón basada en la evidencia.
~~~

## 2. Verificación
~~~bash
test -f x-review.md
test -f docs/validation-report.md
grep -Eiq 'hallazgos|criterio' docs/validation-report.md
~~~

## 3. Commit
~~~bash
git add x-review.md
git commit -m "docs: record human review"
git push
~~