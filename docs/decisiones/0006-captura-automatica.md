# 0006. Captura automática: Android ahora, iOS por correo después

Estado: Aceptada

## Contexto
iOS no permite leer notificaciones de otras apps.

## Decisión
- **Android (MVP):** `NotificationListenerService` para leer las notificaciones de Yape, Plin y apps bancarias.
- **iOS (después del MVP):** leer los **correos de aviso de los bancos** conectando Gmail / Outlook por OAuth. Mientras tanto, iOS usa registro manual.
- Descartado por ahora: OCR de capturas y Atajos de iOS.

## Consecuencias
- El lector de correos necesita backend (Cloud Functions) y la verificación de Google para acceder a Gmail.
- Los correos y las notificaciones pueden describir la misma operación: hace falta detección de duplicados en Movimientos.
- Hay que explicar con claridad al usuario qué se lee y por qué (política de privacidad y requisitos de las tiendas).
