# 0007. Convención de commits

Estado: Aceptada

## Decisión
Se usa [Conventional Commits 1.0](https://www.conventionalcommits.org/es/v1.0.0/):

```
<tipo>(<alcance>): <descripción en minúsculas, imperativo, sin punto final>

[cuerpo opcional: el porqué]

[pie opcional: BREAKING CHANGE:, refs]
```

**Tipos:** `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `build`, `ci`, `perf`, `style`.

**Alcances** (los contextos de 0002 y áreas comunes): `captura`, `movimientos`, `categorizacion`, `analisis`, `cuenta`, `android`, `ios`, `docs`.

**Idioma:** el tipo y el alcance van como arriba; la descripción en español.

Ejemplos:
- `docs(adr): agrega decisiones del MVP`
- `feat(captura): parsea notificaciones de yape`
- `fix(movimientos): evita duplicar yapeos que llegan por dos fuentes`
- `chore: ignora .idea en git`

## Consecuencias
- Historial legible y base para generar changelog y versiones automáticamente más adelante.
- Un commit = un cambio con un solo propósito.
- Sin verificación automática por ahora (no hay commitlint); se revisa a mano.
