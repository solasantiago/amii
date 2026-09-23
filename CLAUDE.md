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
  - **P1:** viernes 25/09/2026. Temas hasta extremos inclusive → TP0 a TP6.
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

| TP | Tema | Parcial | Presentación | Resueltos | Respuestas |
|---|---|---|---|---|---|
| TP0 | Preliminares / repaso | P1 | — | `TP12 - resueltos.pdf` (⚠️ a confirmar, ver nota abajo) | `RESPUESTAS TP 0.pdf` |
| TP1 | Funciones de varias variables | P1 | `TP1 - Funciones etc.pdf` | `TP1 - resueltos.pdf` | `RESPUESTAS TP I.pdf` |
| TP2 | Límite y continuidad | P1 | `TP2 - Limite.pdf` | `TP2 - resueltos.pdf` | `RESPUESTAS TP II.pdf` |
| TP3 | Derivadas parciales y direccionales | P1 | `TP3 - Derivadas.pdf` | `TP3 - resueltos.pdf` | `RESPUESTAS TP III.pdf` |
| TP4 | Diferenciabilidad | P1 | `TP4 - Diff.pdf` / `TP4 - Diff - demos.pdf` | `TP4 - resueltos.pdf` | `RESPUESTAS TP IV.pdf` |
| TP5 | Funciones compuestas (regla de la cadena) | P1 | `TP5 - Compuestas.pdf` | `TP5 - resueltos.pdf` (+ img "Otra forma ej 10") | `RESPUESTAS TP V.pdf` |
| TP6 | Taylor y extremos | P1 | `TP6 - Taylor a.pdf` / `b.pdf` | `TP6 - resueltos.pdf` | `RESPUESTAS TP VI.pdf` |
| TP7 | Integrales curvilíneas | P2 | `TP7 - Int Curvas.pdf` | `TP7 - resueltos.pdf` | `RTA TP VII - INT CURVILINEA...pdf` |
| TP8 | Integrales múltiples | P2 | `TP8 - Multiples a.pdf` / `b.pdf` | `TP8 - resueltos.pdf` | `RTA TP VIII - INT MULTIPLES...pdf` |
| TP9 | Integrales de superficie / Flujo | P2 | `TP9 - Flujo.pdf` | `TP9 - resueltos.pdf` | `RTA TP IX . INT SUP - FLUJO...pdf` |
| TP10 | Teoremas integrales (Green, Stokes, Gauss) | P2 | `TP10 - Teoremas.pdf` | `TP10 - resueltos.pdf` | `RTA TP X . TEOREMAS INTEGRALES...pdf` |
| TP11 | Ecuaciones diferenciales ordinarias (EDO) | P2 | `TP11 - EDO 1.pdf` / `2.pdf` | `TP11 - resueltos.pdf` | `RTA TP XI PRIMERA/SEGUNDA PARTE...pdf` |

> ⚠️ `Guias resueltas/TP12 - resueltos.pdf` no tiene presentación ni "Respuestas" con esa numeración. Por descarte probablemente sea el resuelto de TP0, pero no está confirmado — verificar al abrirlo y corregir esta tabla y `00-indice.md`.

## Detalle teórico por tema

El contenido matemático fino (definiciones, teoremas, métodos de resolución, errores frecuentes) **no vive en este archivo** para no duplicar ni desactualizarse respecto de la guía oficial. Vive en `.claude/memoria/1x-*.md`, un archivo por TP, que se completa progresivamente a medida que se estudia cada tema — nunca inventar contenido teórico ahí sin haberlo visto antes en la presentación o la guía.

## Documentos de referencia

- **`Guia de ejercicios-20260923/Guia - v digital.pdf`**: guía de ejercicios completa de la cátedra — fuente de verdad de los enunciados.
- **`Guia de ejercicios-20260923/Guias resueltas/`**: resueltos oficiales, un PDF por TP.
- **`Guia de ejercicios-20260923/Respuestas/`**: solo resultados finales (sin desarrollo), para autocorrección rápida.
- **`Presentaciones/`**: teoría de la cátedra en diapositivas, por TP.
- **`Estructura evaluaciones.pdf`**: régimen de evaluación y calificación (ver resumen arriba).
- **`.claude/memoria/`**: memoria persistente del asistente (índice, estado, forma de trabajo, y resumen por TP).

## Estado de avance

El estado canónico (temas cerrados, en curso, pendientes y próximo paso) está en `.claude/memoria/01-estado-actual.md`, que se carga automáticamente al inicio. Se actualiza al final de cada sesión que avance algo.
