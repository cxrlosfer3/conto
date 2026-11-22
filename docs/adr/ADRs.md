# Registros de decisiones de arquitectura (ADR)

Cada decisión es un archivo `NNNN-titulo-en-minusculas.md` con el formato de [0000-plantilla.md](0000-plantilla.md): Categoría, Contexto, Alternativas, Criterios de Elección, Decisión, Sustento y Aplicación.
Para cambiar una decisión se crea un ADR nuevo que cita al anterior; no se reescribe el viejo.

| ID | Decisión | Categoría |
|---|---|---|
| [ADR-001](0001-alcance-mvp.md) | Alcance del MVP: iOS y Android, automático solo en Android | Alcance del producto |
| [ADR-002](0002-flutter-y-ddd-ligero.md) | Flutter con DDD ligero | Estructura de la aplicación |
| [ADR-003](0003-firebase-como-backend.md) | Firebase como backend | Infraestructura y backend |
| [ADR-004](0004-local-primero.md) | Datos locales primero, sincronización después | Datos y sincronización |
| [ADR-005](0005-autenticacion.md) | Autenticación con correo, Google y Apple | Seguridad y acceso |
| [ADR-006](0006-captura-automatica.md) | Captura automática: notificaciones en Android, correos en iOS después | Integración con fuentes externas |
| [ADR-007](0007-convencion-de-commits.md) | Convención de commits: Conventional Commits | Proceso de desarrollo |
