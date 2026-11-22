# ADR-001 - Alcance del MVP: iOS y Android, con registro automático solo en Android
**Categoría:** Alcance del producto

## Contexto
conto registra gastos de forma manual y automática. La captura automática por notificaciones solo es viable en Android, y hay que decidir qué plataformas y fuentes cubre el primer MVP.

**Supuestos:** el equipo quiere validar pronto la propuesta de valor (registro automático) y llegar a usuarios de iOS y Android.
**Restricciones:** iOS no permite leer notificaciones de otras apps; Google Play restringe el permiso de SMS; cada fuente exige su propio parser.

## Alternativas
1. **Solo Android primero.** Lanza únicamente en Android. Descartado por dejar fuera a los usuarios de iOS.
2. **Ambas plataformas con automático en las dos.** Resuelve iOS desde el inicio. Descartado por retrasar el MVP.
3. **Ambas plataformas, automático solo en Android.** iOS arranca con registro manual y suma captura después.

## Criterios de Elección
Validar el registro automático cuanto antes, cubrir ambas tiendas y limitar los parsers que mantener.

## Decisión
El MVP sale en iOS y Android, con registro automático solo en Android. Las fuentes automáticas son Yape, Plin y BCP / Interbank / BBVA; SMS queda fuera.

## Sustento
Llega a las dos tiendas sin bloquear el MVP por la limitación de iOS. El costo es mantener un parser por fuente, que se mitiga probándolos con notificaciones reales, y que iOS tendrá menos valor percibido hasta que llegue su captura (ver ADR-006).

## Aplicación en conto
Android lee las notificaciones de Yape, Plin y las apps bancarias; iOS ofrece registro manual en la primera versión.
