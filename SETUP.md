# Retomar el repo en otra máquina

El chat con el asistente **no viaja**: queda en la computadora donde se abrió. Todo lo necesario para retomar sí está en el repo:

- `CLAUDE.md` carga solo la memoria de `.claude/memoria/` al abrir Claude Code en esta carpeta.
- `.claude/memoria/01-estado-actual.md` tiene dónde quedamos y el próximo paso.
- `.claude/memoria/02-como-trabajamos.md` tiene el estilo de trabajo, incluido el **modo repaso por preguntas** y cómo escribir la matemática en el chat.
- `Plan P1.md` tiene el checklist y el horario, y `lumen.json` el progreso (niveles, errores, repasos).

## Pasos

1. **Clonar:**
   ```bash
   git clone git@github.com:solasantiago/amii.git
   cd amii
   ```
2. **Instalar Claude Code** (si no está) y abrirlo **dentro de la carpeta del repo**, para que lea `CLAUDE.md`:
   ```bash
   claude
   ```
3. **Desactivar las sugerencias de prompt.** Si no, la caja de texto muestra en gris la respuesta que el asistente espera. Es una configuración de la máquina, no del repo, así que hay que hacerlo en cada computadora:
   ```
   /config promptSuggestionEnabled=false
   ```
4. **Instalar Node.js** (opcional, para validar `lumen.json` antes del push). En esta máquina no estaba instalado. El workflow de GitHub valida igual en cada push a `main`.
   ```bash
   curl -fsSL https://raw.githubusercontent.com/solasantiago/lumen/main/scripts/validar.mjs -o /tmp/validar-lumen.mjs
   node /tmp/validar-lumen.mjs lumen.json
   ```

## Primer mensaje sugerido

> Leé el estado actual y el plan del P1, y seguimos en modo repaso por preguntas desde donde quedamos.
