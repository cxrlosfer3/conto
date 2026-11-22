# ADR-005 - Autenticación con correo, Google y Apple
**Categoría:** Seguridad y acceso

## Contexto
Los usuarios necesitan una cuenta para sincronizar sus datos. Hay que decidir qué métodos de inicio de sesión ofrece el MVP.

**Supuestos:** Firebase Authentication es el proveedor de identidad (ADR-003).
**Restricciones:** Apple exige ofrecer Sign in with Apple en iOS si hay login con Google; los datos son financieros y sensibles.

## Alternativas
1. **Número de celular con SMS.** Muy común en Perú. Descartado por el costo por SMS y el riesgo de fraude.
2. **Bloqueo biométrico local como único acceso.** Protege datos financieros. Descartado porque no sustituye al login y añade trabajo; se puede reconsiderar como capa adicional.
3. **Correo y contraseña, Google y Apple.** Métodos estándar y universales.

## Criterios de Elección
Estandarización, sin costos variables por SMS y cumplimiento de las reglas de las tiendas.

## Decisión
Se adopta inicio de sesión con correo y contraseña, Google y Apple mediante Firebase Authentication.

## Sustento
Es lo más estándar y no depende de costos por SMS. El costo es implementar verificación de correo y recuperación de contraseña.

## Aplicación en conto
El bloqueo biométrico no entra en el MVP; se reconsiderará por tratarse de datos financieros.
