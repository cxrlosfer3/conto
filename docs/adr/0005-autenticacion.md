# 0005. Autenticación

Estado: Aceptada

## Decisión
Inicio de sesión con **correo y contraseña, Google y Apple**, vía Firebase Authentication.
Apple es obligatorio en iOS al ofrecer login con Google.

## Consecuencias
- Hay que implementar verificación de correo y recuperación de contraseña.
- No se incluye login por SMS en el MVP.
- Bloqueo biométrico local (huella / Face ID) no fue elegido para el MVP; se puede reconsiderar por tratarse de datos financieros.
