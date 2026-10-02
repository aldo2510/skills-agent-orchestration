## Step 6: Corrige mediante handoffs

### Teoría
La orquestación se demuestra cuando un hallazgo viaja desde Validator hasta el agente que puede resolverlo y vuelve a validación.

### Copia y pega
```text
Procesa docs/validation-report.md.
Para cada hallazgo, identifica el agente responsable, crea un handoff específico, define el cambio y cómo se comprobará.
No implementes directamente cambios que correspondan a Designer o Coder.
```

Actualiza `docs/coding-handoff.md`:

```markdown
## Iteración de corrección
| Hallazgo | Agente | Cambio | Evidencia |
|---|---|---|---|
| ... | ... | ... | ... |
```

Haz que el agente correspondiente implemente las correcciones.

**Tiempo: 8-10 min.**