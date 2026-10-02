## Step 5: Valida el producto

### Teoría
Validar no significa decir "parece correcto". El Validator debe producir evidencia reproducible y separar PASS, FAIL y hallazgos.

### Copia y pega
```text
Usa el requerimiento, docs/project-plan.md y docs/design-handoff.md.
Delega al Validator una revisión completa.
Valida HTML, CSS, JSON, datos, estados, progreso, responsive, accesibilidad y ausencia de backend.
No corrijas código.
Registra evidencia y severidad en docs/validation-report.md.
```

Plantilla:

```markdown
# Validation Report
## Resumen
- Estado:
- Alcance:

## Checks
| Check | Resultado | Evidencia |
|---|---|---|
| HTML | ... | ... |
| CSS | ... | ... |
| JSON | ... | ... |
| Estados | ... | ... |
| Progreso | ... | ... |
| Responsive | ... | ... |
| Accesibilidad | ... | ... |
| Sin backend | ... | ... |

## Hallazgos
| Hallazgo | Severidad | Evidencia | Recomendación |
|---|---|---|---|
| ... | ... | ... | ... |
```

Haz commit y push.

**Tiempo: 10-12 min.**