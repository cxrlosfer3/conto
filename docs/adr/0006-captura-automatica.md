# ADR-006 - Captura automática: notificaciones en Android, correos de bancos en iOS después
**Categoría:** Integración con fuentes externas

## Contexto
iOS no permite leer las notificaciones de otras apps. Hay que decidir cómo se captura el gasto de forma automática en cada plataforma.

**Supuestos:** en Android las notificaciones de Yape, Plin y apps bancarias traen monto, comercio o persona, y fecha.
**Restricciones:** Google Play restringe el permiso de SMS; leer Gmail exige OAuth, backend y la verificación de Google.

## Alternativas
1. **Android: lectura de SMS.** Algunos bancos avisan por SMS. Descartado porque Google Play restringe el permiso.
2. **iOS: captura de pantalla con OCR.** El usuario comparte el comprobante. Descartado por ser semiautomático.
3. **iOS: Atajos de iOS.** Automatización que envía los datos a conto. Descartado porque el usuario debe configurarla a mano.
4. **Android: lector de notificaciones; iOS: correos de aviso de los bancos.** Notificaciones en Android ahora y lectura de correos por OAuth en iOS después del MVP.

## Criterios de Elección
Que la captura sea realmente automática, la viabilidad por plataforma y la carga de backend y permisos.

## Decisión
Android usa `NotificationListenerService` en el MVP. iOS usará la lectura de correos de los bancos (Gmail / Outlook) después del MVP; mientras tanto, registro manual.

## Sustento
Es la única vía automática viable en cada plataforma. Los riesgos son que la verificación de Google puede tardar semanas y que una operación puede llegar por notificación y por correo, lo que se mitiga empezando el trámite temprano y detectando duplicados en Movimientos.

## Aplicación en conto
El lector de correos corre en Cloud Functions. Hay que explicar con claridad al usuario qué se lee y por qué (política de privacidad y requisitos de las tiendas).
