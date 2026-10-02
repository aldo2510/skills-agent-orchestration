## Step 4: Revisa la calidad de la orquestación

### Teoría: evaluar la calidad del sistema

Un sistema de agentes puede producir un resultado correcto y aun así estar mal orquestado.

La revisión debe mirar el **proceso**, no solamente el producto:

- ¿llegó el contexto correcto?
- ¿cada agente hizo lo que correspondía?
- ¿los handoffs fueron claros?
- ¿hubo evidencia?
- ¿se repitió la validación después de corregir?

Esto es similar a revisar una arquitectura de software: buscamos puntos débiles antes de convertir el flujo en una práctica repetible.

### 1. Revisión automática con Orchestrator

Copia y pega:

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

Identifica:
1. contexto perdido;
2. responsabilidades solapadas;
3. handoffs ambiguos;
4. decisiones sin evidencia;
5. validaciones insuficientes.

Para cada hallazgo indica documento, evidencia y mejora concreta.
```

### 2. Crea docs/orchestration-review.md

```markdown
# Orchestration Review

## 1. Handoff que funcionó bien
- Evidencia:
- Motivo:

## 2. Handoff que podría mejorar
- Evidencia:
- Información faltante:
- Mejora:

## 3. Responsabilidades solapadas
- ...

## 4. Evidencia insuficiente
- ...

## 5. Decisión que debe permanecer bajo control humano
- ...

## 6. Mejora propuesta para Orchestrator
- ...

## 7. Flujo V2
1. ...
2. ...
3. ...
```

### 3. Verificación

Copia y pega:

```text
Revisa docs/orchestration-review.md.

Comprueba que contiene al menos:
- un handoff positivo;
- un handoff mejorable;
- una decisión humana;
- una mejora del Orchestrator;
- un flujo V2.

No modifiques el archivo. Devuelve los elementos faltantes.
```

Completa lo que falte.

Haz commit y push.

**Tiempo: 10-12 min.**
