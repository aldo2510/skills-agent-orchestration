## Step 2: Planifica con Planner

### Teoría: planificación y handoffs

En un equipo de agentes, un plan no sirve solamente para saber "qué hacer". Sirve para **transportar contexto** entre especialistas.

Un handoff de calidad responde:

```
¿Qué recibí?
¿Qué debo hacer?
¿Qué restricciones tengo?
¿Qué debo entregar?
¿Cómo sabrá el siguiente agente que terminé correctamente?
```

Si falta alguno de estos elementos, el siguiente agente puede interpretar el trabajo de otra manera.

### Requerimiento

Construir un dashboard Project Pulse que muestre:
- nombre del proyecto;
- estado;
- progreso;
- responsable;
- fecha de actualización.

Debe ser responsive y funcionar sin backend.

### 1. Copia y pega en Orchestrator

```text
Usa el requerimiento de Project Pulse.

No implementes código.

Divide el trabajo entre Planner, Designer, Coder y Validator.
Indica exactamente qué contexto debe recibir cada agente y qué salida debe entregar para el siguiente agente.
```

### 2. Delega al Planner

```text
Convierte el requerimiento de Project Pulse en un plan ejecutable.

Incluye:
- objetivo;
- alcance;
- fuera de alcance;
- entregables;
- dependencias;
- riesgos;
- criterios de aceptación;
- estrategia de validación;
- información necesaria para Designer;
- información necesaria para Coder;
- información necesaria para Validator.

No implementes código.
```

### 3. Crea docs/project-plan.md

**Copia esta plantilla:**

```markdown
# Project Pulse - Plan

## 1. Objetivo
...

## 2. Alcance
### Incluido
- ...
### Fuera de alcance
- ...

## 3. Entregables
- app/index.html
- app/styles.css
- app/project-data.json
- documentación de handoffs

## 4. Responsabilidades
| Agente | Responsabilidad |
|---|---|
| Planner | ... |
| Designer | ... |
| Coder | ... |
| Validator | ... |

## 5. Dependencias
- ...

## 6. Criterios de aceptación
- ...
- ...
- ...

## 7. Estrategia de validación
- ...

## 8. Riesgos
| Riesgo | Impacto | Mitigación |
|---|---|---|
| ... | ... | ... |

## 9. Calidad del handoff
- Información imprescindible para Designer:
- Información imprescindible para Coder:
- Información imprescindible para Validator:

## 10. Decisiones humanas
- ...
```

### 4. Revisa el plan

Copia y pega:

```text
Revisa docs/project-plan.md contra el requerimiento.

No modifiques archivos.

Devuelve:
- requisito;
- dónde está cubierto;
- evidencia;
- información faltante.

Después revisa si existe algún cambio innecesario.
```

Aplica las correcciones.

### 5. Handoff defectuoso

Ahora observa un caso típico de orquestación: entregar contexto incompleto.

Copia y pega:

```text
Explica qué problemas tendría Designer si recibe un plan sin criterios de aceptación.

Después muestra cómo debería modificarse docs/project-plan.md para evitar esa ambigüedad.
No modifiques archivos.
```

Aplica la mejora indicada.

Haz commit y push.

**Tiempo: 12-14 min.**
