# Step 5 — Revisión humana inicial

## Objetivo
Separar validación automática de aceptación humana.

## 1. Prompt exacto
~~~text
Revisa el estado completo de Project Pulse y sus handoffs.

No modifiques archivos.

Resume:
- objetivo;
- responsabilidades de cada agente;
- hallazgos;
- evidencia;
- riesgos;
- decisiones que requieren intervención humana.

No escribas código.
~~~

## 2. Crea x-review.md
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
La persona participante decide si el resultado cumple el objetivo y si los hallazgos fueron resueltos correctamente.
~~~

## 3. Verificación
~~~bash
test -f x-review.md
test -f docs/validation-report.md
grep -Eiq 'hallazgos|criterio' docs/validation-report.md
~~~

## 4. Commit
~~~bash
git add x-review.md
git commit -m "docs: record human review"
git push
~~~

**Tiempo sugerido: 10–12 min.**