# 0002. Flutter y DDD ligero

Estado: Aceptada

## Contexto
Una sola base de código para iOS y Android. El dominio es lo difícil: formatos por banco, duplicados, categorías.

## Decisión
- **Flutter** para la app. Un plugin nativo en Kotlin para leer notificaciones en Android.
- **DDD ligero**: lenguaje común (`docs/glosario.md`) y contextos delimitados: Captura, Movimientos, Categorización, Análisis, Cuenta y sincronización.
- Captura actúa como capa anticorrupción: traduce cada formato externo al modelo de Movimientos.
- Sin agregados complejos, eventos de dominio ni CQRS hasta que el producto lo pida.

## Consecuencias
- Los nombres del glosario son los del código y la base de datos.
- Agregar un banco nuevo solo toca Captura.
