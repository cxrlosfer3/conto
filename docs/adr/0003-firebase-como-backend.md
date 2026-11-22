# 0003. Firebase como backend

Estado: Aceptada

## Contexto
Se necesita cuenta de usuario y sincronización entre dispositivos, con el menor costo de montaje posible.

## Decisión
**Firebase**: Authentication, Firestore y Cloud Functions, con los SDK oficiales de Flutter.

## Consecuencias
- Rapidez de montaje y buen soporte offline propio de Firestore.
- Dependencia de Google; migrar después costaría trabajo.
- Las consultas analíticas pesadas son limitadas: los agregados del dashboard se calculan en el dispositivo o con Functions.
- Son datos financieros sensibles: reglas de seguridad estrictas por usuario y cumplimiento de la Ley 29733 (Perú) desde el inicio.
- Es la base para leer correos de bancos en iOS más adelante (0006).

## Alternativas evaluadas
- **PostgreSQL (propio o Supabase):** da SQL potente para el análisis, pero exige construir la API de sincronización o aceptar un SDK de Flutter menos maduro. Pospuesto; ver 0004.
