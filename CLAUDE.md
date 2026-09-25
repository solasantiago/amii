# CLAUDE.md

## Memoria persistente del proyecto

La memoria del asistente vive en `.claude/memoria/` (dentro del repo, para que viaje entre computadoras). Los tres archivos base se cargan acá en cada sesión; el resto se lee bajo demanda según indica el índice.

@.claude/memoria/00-indice.md
@.claude/memoria/01-estado-actual.md
@.claude/memoria/02-como-trabajamos.md

Regla: ante cualquier detalle fino de un tema (definición exacta, hipótesis de un teorema, método de resolución de un tipo de ejercicio), leer el archivo `1x-*` correspondiente en `.claude/memoria/` antes de responder. Lo que sigue en este archivo es un resumen orientativo; si contradice a `.claude/memoria/1x-*.md`, gana ese archivo, y sobre todos, la guía y las presentaciones oficiales en PDF.

## Proyecto: Análisis Matemático II

Repositorio de estudio **individual** para la cátedra de Análisis Matemático II (95-0703, UTN FRBA). No es un proyecto de desarrollo de software: es material de cursada (guía de ejercicios, resueltos, respuestas y presentaciones teóricas) más la memoria de estudio que se va armando sesión a sesión con el asistente.

- **Objetivo del repo:** preparar los dos parciales (P1 y P2) de la aprobación directa y, si hiciera falta, el examen final.
- **Modalidad:** individual.
- **Contenido:** 12 TPs, desde funciones de varias variables hasta ecuaciones diferenciales ordinarias.

## Régimen de evaluación

Resumen de `Estructura evaluaciones.pdf` (ciclo lectivo 2021 — la metodología de calificación se mantiene; las fechas de esta cursada están abajo).

- Se toman dos parciales, **P1** y **P2**. Cada uno se compone de 2 ítems teóricos (T1, T2) y 4 ítems prácticos (E1-E4).
  - **P1:** viernes 25/09/2026, 19 hs. Temas hasta extremos inclusive → TP0 a TP6.
  - **P2:** fecha aún no definida. Resto del programa → TP7 a TP11.
- **Aprobación directa:** ambos parciales aprobados con mínimo **8D**, respondiendo bien 4 de los 6 ítems con al menos 1 teórico.
- **Regularidad (sin aprobación directa):** ambos parciales con mínimo 6 puntos, resolviendo bien 2 de los 4 ítems prácticos (no cuenta lo teórico).
- Cada parcial tiene dos instancias de recuperación; solo **uno** de los dos parciales puede recuperarse.
- Criterio de nota según ítems bien resueltos (base = 1 teórico + 2 prácticos):
  | Ítems bien | Nota |
  |---|---|
  | Base | 6D (debe complementar práctica) |
  | Base + 1 | 8D |
  | Base + 2 | 9D |
  | Base + 3 | 10D |
  | Solo 3 prácticos | 6D (debe complementar teoría) |
  | Solo 4 prácticos | 7D (debe complementar teoría) |
  | Solo 2 prácticos | 6 (debe complementar teoría y práctica) |
  | Cualquier otro caso | 1 a 5 (parcial insuficiente) |
- Los ítems teóricos salen del listado de "requerimientos teóricos para el examen final" de la guía de TP — clave para armar el temario de teoría.
- **Final (aprobación no directa):** modalidad virtual, 2 horas, 10 preguntas, mínimo 6 correctas para aprobar.

## Los 12 temas (TPs)

| TP | Tema | Parcial | Presentación |
|---|---|---|---|
| TP0 | Preliminares / repaso | P1 | — |
| TP1 | Funciones de varias variables | P1 | `TP1 - Funciones etc.pdf` |
| TP2 | Límite y continuidad | P1 | `TP2 - Limite.pdf` |
| TP3 | Derivadas parciales y direccionales | P1 | `TP3 - Derivadas.pdf` |
| TP4 | Diferenciabilidad | P1 | `TP4 - Diff.pdf` / `TP4 - Diff - demos.pdf` |
| TP5 | Funciones compuestas (regla de la cadena) | P1 | `TP5 - Compuestas.pdf` |
| TP6 | Taylor y extremos | P1 | `TP6 - Taylor a.pdf` / `b.pdf` |
| TP7 | Integrales curvilíneas | P2 | `TP7 - Int Curvas.pdf` |
| TP8 | Integrales múltiples | P2 | `TP8 - Multiples a.pdf` / `b.pdf` |
| TP9 | Integrales de superficie / Flujo | P2 | `TP9 - Flujo.pdf` |
| TP10 | Teoremas integrales (Green, Stokes, Gauss) | P2 | `TP10 - Teoremas.pdf` |
| TP11 | Ecuaciones diferenciales ordinarias (EDO) | P2 | `TP11 - EDO 1.pdf` / `2.pdf` |

Los enunciados de ejercicios de cada TP están dentro de `Guia - v digital.pdf` (guía única, sin resueltos ni respuestas oficiales en el repo — ver más abajo).

## Detalle teórico por tema

El contenido matemático fino (definiciones, teoremas, métodos de resolución, errores frecuentes) **no vive en este archivo** para no duplicar ni desactualizarse respecto de la guía oficial. Vive en `.claude/memoria/1x-*.md`, un archivo por TP, que se completa progresivamente a medida que se estudia cada tema — nunca inventar contenido teórico ahí sin haberlo visto antes en la presentación o la guía.

## Documentos de referencia

- **`Guia - v digital.pdf`**: guía de ejercicios completa de la cátedra — fuente de verdad de los enunciados. **No hay resueltos ni respuestas oficiales en el repo**: la autocorrección se hace resolviendo con el asistente y guardando el desarrollo propio en `Resueltos propios/`.
- **`Presentaciones/`**: teoría de la cátedra en diapositivas, por TP.
- **`Resueltos propios/`**: un archivo Markdown por TP con las resoluciones propias (GitHub renderiza LaTeX en Markdown con `$...$` / `$$...$$`, no hace falta compilar nada).
- **`Estructura evaluaciones.pdf`**: régimen de evaluación y calificación (ver resumen arriba).
- **`.claude/memoria/`**: memoria persistente del asistente (índice, estado, forma de trabajo, y resumen por TP).
- **`SETUP.md`**: pasos para retomar el repo en otra máquina (clonar, configurar Claude Code, validar `lumen.json`).

## Estado de avance

El estado canónico (temas cerrados, en curso, pendientes y próximo paso) está en `.claude/memoria/01-estado-actual.md`, que se carga automáticamente al inicio. Se actualiza al final de cada sesión que avance algo.

## Lumen

Este repo alimenta a Lumen (https://github.com/solasantiago/lumen), la web que muestra el progreso de todas las materias. Lumen lee **`lumen.json`** (raíz del repo, contrato `lumen/materia@1`): es la fuente de verdad del **progreso** (nivel por tema, repasos, sesiones, fechas de evaluación). El **detalle** de cada tema (teoría, métodos, errores frecuentes) sigue viviendo en `.claude/memoria/1x-*.md`, y los ejercicios resueltos en `Resueltos propios/`. Contrato completo: https://github.com/solasantiago/lumen/blob/main/docs/contrato.md

### Cómo es una sesión

**Al empezar**

1. Leé `lumen.json` y `.claude/memoria/01-estado-actual.md`.
2. Contá en dos o tres líneas cómo viene la materia: porcentaje, próxima evaluación y cuántos días faltan, y repasos vencidos (`proximo_repaso` ≤ hoy).
3. Proponé el foco de la sesión: primero los repasos vencidos, después los temas de la próxima evaluación con nivel más bajo y unidad de más peso. Si el estudiante trae otro tema, seguí el suyo.

**Durante**

- El estilo por defecto sigue siendo el de `.claude/memoria/02-como-trabajamos.md` (resolver paso a paso, salvo que se pidan pistas). Para **medir** un tema y poder subirle el nivel, preguntá antes de explicar: una pregunta conceptual y un ejercicio corto que el estudiante resuelva solo. Un ejercicio resuelto en modo guiado cuenta como "seguir un ejercicio resuelto" (nivel 2), no como "resolver sin mirar la solución" (nivel 3).
- Los ejercicios resueltos (de la guía, de modelos de parcial o propuestos) van a `Resueltos propios/`, con el formato de `02-como-trabajamos.md`. No se usa `practica/`.
- Lo que cueste se anota en dos lugares: una línea concreta en `notas` del tema en `lumen.json` ("confunde X con Y") y el detalle en "Errores frecuentes propios" del `.claude/memoria/1x-*.md` correspondiente.

**Al cerrar** (siempre, aunque la sesión haya sido corta)

1. Actualizá el `nivel` de cada tema trabajado **solo con evidencia** (tabla de abajo).
2. Actualizá `evidencia`: `ejercicios`, `autoevaluaciones`, `ultimo_repaso` (hoy), `proximo_repaso` y `minutos`.
3. Agregá la sesión a `sesiones` (`fecha`, `minutos`, `tipo`, `temas`).
4. Poné `actualizado` con la fecha y hora actuales (ISO 8601, -03:00; el estudiante está en Argentina).
5. Actualizá también `.claude/memoria/01-estado-actual.md` y el `1x-*.md` de cada TP trabajado.
6. Validá y, si el estudiante está de acuerdo, hacé commit y push:
   ```bash
   curl -fsSL https://raw.githubusercontent.com/solasantiago/lumen/main/scripts/validar.mjs -o /tmp/validar-lumen.mjs
   node /tmp/validar-lumen.mjs lumen.json
   ```
7. Resumí qué cambió: temas que subieron o bajaron de nivel y el próximo repaso.

### Niveles

| Nivel | Nombre | Cuándo asignarlo | Evidencia mínima |
|:-:|---|---|---|
| 0 | No visto | Todavía no se estudió. | — |
| 1 | Visto | Leyó la teoría o fue a la clase; lo reconoce pero no lo explica. | `ultimo_repaso` |
| 2 | Entendido | Lo explica con sus palabras y sigue un ejercicio resuelto. | respondió bien preguntas de comprensión |
| 3 | Practicado | Resuelve ejercicios de la guía sin mirar la solución. | `ejercicios` con ≥ 70 % bien |
| 4 | Dominado | Resuelve ejercicios tipo parcial sin ayuda y lo sostuvo en un repaso posterior. | `autoevaluaciones` ≥ 0,7 en un repaso a 7 días o más del nivel 3 |

- Nunca subas un nivel sin evidencia. Se sube de a uno por sesión, salvo evidencia contundente (un simulacro completo bien resuelto).
- Si falla en un repaso lo que antes resolvía, bajá un nivel y reprogramá.
- Próximo repaso según el nivel resultante: 1 → 2 días, 2 → 4 días, 3 → 7 días, 4 → 21 días.

### Reglas de `lumen.json`

- Los `id` de unidades y temas son estables. Si un tema se divide, el original conserva su id.
- No borres temas con progreso. Si un tema no está en el programa pero la cátedra lo da (en la guía o en las presentaciones), agregalo con un id nuevo en la unidad que corresponda.
- `evaluaciones` va en orden cronológico. Pedí las fechas de parciales apenas se conozcan (P2 sigue en `null`); cuando llegue la nota, completá `nota` y `estado`.
- `aprobacion` ya tiene el régimen completo de `Estructura evaluaciones.pdf`; si la cátedra lo cambia, actualizalo ahí y en la sección "Régimen de evaluación" de arriba.
- Lo que quieras guardar para vos va en `extra`; el detalle de teoría y errores frecuentes, en `.claude/memoria/1x-*.md`.
- El workflow `.github/workflows/lumen.yml` valida `lumen.json` en cada push a `main` y avisa a Lumen si existe el secret `LUMEN_DISPATCH_TOKEN` (sin él, Lumen sincroniza solo cada 6 horas).

### TP → unidades de `lumen.json`

La numeración de unidades de `lumen.json` sigue el programa analítico, no la de los TP: usá esta tabla para saber dónde anotar el progreso.

| TP (guía) | Tema | Unidad en `lumen.json` | Parcial |
|---|---|---|---|
| TP0 | Repaso: superficies en R³ | `u1` (tema `u1-repaso-planos-cuadricas`) | P1 |
| TP1 | Topología, funciones, curvas y superficies | `u1` | P1 |
| TP2 | Límite y continuidad | `u1` | P1 |
| TP3 | Derivabilidad: recta tangente y plano normal | `u2` | P1 |
| TP4 | Diferenciabilidad: plano tangente y recta normal | `u3` | P1 |
| TP5 | Funciones compuestas e implícitas | `u4` | P1 |
| TP6 | Taylor y extremos | `u5` | P1 |
| TP7 | Curvas, integral de línea, función potencial | `u6` | P2 |
| TP8 | Integrales múltiples | `u7` | P2 |
| TP9 | Integrales de superficie / flujo | `u8` | P2 |
| TP10 | Teoremas integrales (Green, Gauss, Stokes) | `u9` | P2 |
| TP11 | EDO (en la guía: TP XI 1ª parte y TP XII 2ª parte) | `edo1` (1ª parte) y `edo2` (2ª parte) | P2 |
