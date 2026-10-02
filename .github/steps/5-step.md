## Step 5: Handoff final y revisión humana

### Teoría: human-in-the-loop

En una arquitectura de agentes, automatizar una tarea no significa automatizar completamente la decisión.

El patrón que practicarás es:

```
Humano define objetivo
        ↓
Orchestrator coordina
        ↓
Agentes ejecutan
        ↓
Validator genera evidencia
        ↓
Humano acepta, corrige o rechaza
```

La revisión final debe comprobar dos cosas:

1. **Producto:** el dashboard funciona y cumple el requerimiento.
2. **Proceso:** los agentes recibieron contexto correcto y dejaron evidencia suficiente.

### 1. Genera el handoff final

Copia y pega:

```text
Actualiza docs/final-handoff.md para un engineering lead que no participó en el ejercicio.

Incluye:
- objetivo y resultado;
- flujo de los cinco agentes;
- trabajo realizado por cada agente;
- decisiones relevantes;
- evidencia de validación;
- segunda ronda de validación;
- iteraciones;
- riesgos;
- pendientes;
- decisiones humanas.

Usa únicamente evidencia existente en el repositorio.
No inventes información.
```

### 2. Revisión manual

Abre en el navegador:
- app/index.html.

Revisa:
- dashboard;
- datos;
- responsive;
- textos;
- estados;
- progreso.

Después revisa:
- todos los handoffs;
- validation-report.md;
- orchestration-review.md;
- final-handoff.md.

### 3. Crea x-review.md

**Copia esta plantilla:**

```markdown
# Human Review

## 1. Contexto entre agentes
¿Qué información viajó entre agentes?
...

## 2. Información perdida o ambigua
...

## 3. Mejor delegación
...

## 4. Peor delegación
...

## 5. Intervención humana
...

## 6. Recomendación modificada o rechazada
...

## 7. Problema descubierto manualmente
...

## 8. Cambio que haría a la arquitectura
...

## 9. Generar vs. orquestar
¿Qué diferencia observaste?
...
```

### 4. Revisión final con Orchestrator

Copia y pega:

```text
Haz una revisión final del ejercicio.

No modifiques archivos.

Comprueba que existan:
- docs/agent-map.md
- docs/project-plan.md
- docs/design-handoff.md
- docs/coding-handoff.md
- docs/validation-report.md
- docs/orchestration-review.md
- docs/final-handoff.md
- x-review.md

Comprueba también que validation-report.md tenga una segunda ronda.

Devuelve una checklist PASS/FAIL.
```

Haz commit y push.

**Tiempo: 10-12 min.**
