# ADR-002 - Flutter con DDD ligero
**Categoría:** Estructura de la aplicación

## Contexto
Se quiere una sola base de código para iOS y Android. La parte difícil es el dominio (formatos por banco, duplicados, categorías), no la interfaz.

**Supuestos:** el equipo es pequeño y necesita un lenguaje común entre documentación, código y base de datos.
**Restricciones:** no sobredimensionar la arquitectura en un MVP.

## Alternativas
1. **Flutter con capas simples, sin DDD.** Estructura tradicional por capas. Descartado porque la lógica de cada banco se mezcla con el resto.
2. **DDD completo.** Agregados, eventos de dominio y CQRS. Descartado por ser excesivo para un MVP.
3. **Flutter con DDD ligero.** Lenguaje común y contextos delimitados, sin la ceremonia del DDD completo.

## Criterios de Elección
Una sola base de código, bajo acoplamiento entre fuentes de captura y velocidad de desarrollo.

## Decisión
Se adopta Flutter con DDD ligero, organizado en los contextos Captura, Movimientos, Categorización, Análisis y Cuenta y sincronización.

## Sustento
Agregar un banco nuevo solo toca Captura, y los nombres del glosario son los del código y la base de datos. El costo es escribir y mantener el glosario y el mapa de contextos, y respetar los límites entre contextos.

## Aplicación en conto
Captura actúa como capa anticorrupción: traduce cada formato externo al modelo de Movimientos. Un plugin nativo en Kotlin lee las notificaciones en Android.
