# ADR-003 - Firebase como backend
**Categoría:** Infraestructura y backend

## Contexto
Se necesita cuenta de usuario y sincronización entre dispositivos con el menor costo de montaje posible.

**Supuestos:** el equipo prioriza llegar al MVP y necesita soporte para trabajar sin conexión.
**Restricciones:** son datos financieros sensibles, sujetos a la Ley 29733 (Perú) y a las políticas de las tiendas.

## Alternativas
1. **Supabase.** PostgreSQL administrado con Auth y API automática. Descartado por tener un SDK de Flutter menos maduro y exigir cuidar las políticas de acceso (RLS).
2. **Backend propio con PostgreSQL.** Control total. Descartado por ser lo más lento y caro de montar y mantener en un MVP.
3. **Firebase.** Authentication, Firestore y Cloud Functions con SDK oficial para Flutter.

## Criterios de Elección
Rapidez de montaje, madurez del SDK de Flutter y soporte sin conexión.

## Decisión
Se adopta Firebase como backend del MVP. PostgreSQL se pospone.

## Sustento
Cubre autenticación, datos y funciones sin construir una API, y es la base para leer correos de bancos en iOS más adelante (ADR-006). Los riesgos son la dependencia de Google y las consultas analíticas limitadas, que se mitigan calculando los agregados del dashboard en el dispositivo o con Functions. PostgreSQL se reconsidera si el análisis de gastos necesita consultas SQL pesadas.

## Aplicación en conto
Reglas de seguridad estrictas por usuario en Firestore y cumplimiento de la Ley 29733 desde el inicio.
