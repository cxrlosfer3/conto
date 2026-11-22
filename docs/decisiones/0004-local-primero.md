# 0004. Datos locales primero, sincronización después

Estado: Aceptada

## Contexto
Los gastos captados por notificación pueden llegar sin internet y no se pueden perder.

## Decisión
La app guarda todo primero en una **base de datos local (SQLite)** y sincroniza con Firebase cuando hay red. La fuente de verdad para la interfaz es la base local.

## Consecuencias
- Ningún gasto captado se pierde por falta de red.
- Hay que definir resolución de conflictos (propuesta inicial: gana la última modificación por movimiento) y evitar duplicar al sincronizar.
- Librería concreta para SQLite (por ejemplo Drift): pendiente de elegir al empezar la implementación.

## Alternativas evaluadas
- **PostgreSQL:** no corre dentro del móvil, así que solo podría ser la base del servidor. Se pospone: el MVP usa Firestore (0003). Se reconsidera si el análisis de gastos necesita consultas SQL pesadas.
