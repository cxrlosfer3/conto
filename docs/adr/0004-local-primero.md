# ADR-004 - Datos locales primero, sincronización después
**Categoría:** Datos y sincronización

## Contexto
Los gastos captados por notificación pueden llegar sin internet y no se pueden perder. Hay que definir cuál es la fuente de verdad de la app.

**Supuestos:** el usuario espera que la app funcione igual con o sin red.
**Restricciones:** PostgreSQL no puede ejecutarse dentro del móvil; solo podría ser la base del servidor (ver ADR-003).

## Alternativas
1. **Solo en línea contra el backend.** Más simple y sin conflictos. Descartado porque un gasto captado sin red se pierde o necesita una cola aparte.
2. **Local primero (SQLite) y sincronizar con Firebase cuando hay red.** La base local es la fuente de verdad de la interfaz.

## Criterios de Elección
No perder gastos captados sin conexión e interfaz rápida e independiente de la red.

## Decisión
Se adopta local primero: la app guarda todo en SQLite y sincroniza con Firebase cuando hay red.

## Sustento
Ningún gasto captado se pierde por falta de red. El costo es resolver conflictos de sincronización (propuesta inicial: gana la última modificación por movimiento) y evitar duplicados al sincronizar.

## Aplicación en conto
La librería de SQLite (por ejemplo Drift) queda pendiente de elegir al empezar la implementación.
