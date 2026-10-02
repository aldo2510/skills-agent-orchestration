## Step 9: Audita la orquestación

### Teoría
Un sistema multiagente puede producir un buen dashboard y aun así tener un proceso deficiente. La auditoría revisa contexto, responsabilidades, handoffs y evidencia.

### Copia y pega
```text
Revisa:
- docs/agent-map.md
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md
- docs/final-handoff.md

Actúa como engineering lead.
No modifiques archivos.
Identifica contexto perdido, responsabilidades solapadas, handoffs ambiguos, decisiones sin evidencia y validaciones insuficientes.
```

Crea `docs/orchestration-review.md`:

```markdown
# Orchestration Review
## Handoff que funcionó bien
- Evidencia:
- Motivo:

## Handoff mejorable
- Evidencia:
- Mejora:

## Responsabilidades solapadas
...

## Evidencia insuficiente
...

## Decisión humana
...

## Mejora del Orchestrator
...

## Flujo V2
1. ...
2. ...
3. ...
```

Haz commit y push.

**Tiempo: 8-10 min.**