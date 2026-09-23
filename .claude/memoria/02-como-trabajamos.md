# Cómo trabajamos — Análisis Matemático II

## Estilo por defecto

Mixto: por defecto, resolver y explicar el ejercicio paso a paso (como un resuelto de la guía, justificando cada paso). Pasar a modo socrático — pistas en vez de la respuesta — solo cuando se pida explícitamente ("no me lo resuelvas", "dame una pista", "quiero llegar solo").

## Prioridad de fuentes

1. La guía oficial (`Guia - v digital.pdf`) y las presentaciones de la cátedra: fuente de verdad de notación, enunciados, orden de temas y método esperado.
2. Los archivos `.claude/memoria/1x-*.md`: resumen propio por tema, construido sesión a sesión — no reemplazan al PDF, lo complementan.

Ante una discrepancia, gana el PDF de la cátedra por sobre cualquier resumen propio.

**No hay resueltos ni respuestas oficiales en el repo** (se sacaron deliberadamente, solo queda la guía de enunciados). Esto cambia cómo se verifica una resolución:

- El desarrollo y el resultado de cada ejercicio los produce el asistente junto con el usuario, sin poder contrastarlos contra una respuesta oficial guardada en el repo.
- Prestar más atención a la consistencia interna de la resolución (verificar resultados por un camino alternativo, casos límite, dimensiones/unidades cuando aplique) ya que no hay una respuesta de la cátedra para comparar directo.
- Si el usuario tiene la respuesta oficial a mano (por ejemplo, la vio en el aula virtual) y no coincide con la resolución propia, revisar el desarrollo propio paso a paso en vez de asumir que el resultado propio es el correcto.

## Convenciones

- Usar la notación y el método que usa la cátedra en sus propios resueltos, no una alternativa de otro libro, salvo que se pida explícitamente comparar métodos.
- Al resolver un ejercicio de la guía, citar de qué TP y número es (ej. "TP6, ejercicio 4b") para poder ubicarlo después.
- Al explicar teoría, dejar explícito qué parte es definición/enunciado formal y qué parte es interpretación o ejemplo — en los parciales los ítems teóricos evalúan justamente esa distinción (ver `CLAUDE.md`, sección de régimen de evaluación).

### Formato de un ejercicio resuelto en `Resueltos propios/`

- Encabezado `## Ejercicio N` con el **enunciado completo** tal como figura en la guía (incluyendo, si los tiene, los incisos a), b), c)... dentro del mismo enunciado).
- Si el ejercicio tiene incisos, la resolución de cada uno va bajo un encabezado de nivel inferior (`### a) ...`) que **repite textualmente el subenunciado** de ese inciso (no una paráfrasis ni un título descriptivo propio) — así el heading sirve para ubicar de qué parte del enunciado original se trata.
- Si el ejercicio no tiene incisos, la resolución va directamente bajo `### Resolución`.
- Las fórmulas en `$...$` / `$$...$$` para que rendericen en GitHub.

## Actualización de la memoria

Al cerrar un tema o detectar un error recurrente propio, actualizar el archivo `1x-*.md` de ese TP y, si corresponde, mover el tema de "en curso" a "cerrado" en `01-estado-actual.md`.
