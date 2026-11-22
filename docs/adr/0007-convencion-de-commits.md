# ADR-007 - Convención de commits: Conventional Commits
**Categoría:** Proceso de desarrollo

## Contexto
Se quiere un historial legible y la posibilidad de generar changelog y versiones automáticamente más adelante.

**Supuestos:** el equipo es pequeño y revisa los mensajes a mano.
**Restricciones:** el proyecto no tiene Node, así que no hay commitlint por ahora.

## Alternativas
1. **Mensajes libres.** Sin reglas. Descartado porque el historial se vuelve inconsistente.
2. **Gitmoji.** Mensajes con emojis. Descartado por ser menos usado y menos fácil de automatizar.
3. **Conventional Commits 1.0.** Formato estándar con herramientas de automatización.

## Criterios de Elección
Legibilidad del historial, estándar extendido y posibilidad de automatizar.

## Decisión
Se adopta Conventional Commits 1.0.

## Sustento
Un commit equivale a un cambio con un solo propósito. El costo es la disciplina de seguirlo y que no hay verificación automática.

## Aplicación en conto
```
<tipo>(<alcance>): <descripción en minúsculas, imperativo, sin punto final>

[cuerpo opcional: el porqué]

[pie opcional: BREAKING CHANGE:, refs]
```
**Tipos:** `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `build`, `ci`, `perf`, `style`. `fix` solo corrige errores de comportamiento.
**Alcances:** `captura`, `movimientos`, `categorizacion`, `analisis`, `cuenta`, `android`, `ios`, `adr`, `docs`.
**Idioma:** tipo y alcance como arriba; descripción en español.
**Ejemplos:** `feat(captura): parsea notificaciones de yape`, `docs(adr): adopta formato propio de adrs`.
