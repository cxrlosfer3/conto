# 0001. Alcance del MVP: plataformas y fuentes

Estado: Aceptada

## Contexto
conto registra gastos de forma manual y automática. La captura automática por notificaciones solo es viable en Android.

## Decisión
- El MVP sale en **iOS y Android**.
- El registro **automático solo en Android**. iOS arranca con registro manual (ver 0006).
- Fuentes automáticas del MVP: **Yape, Plin y BCP / Interbank / BBVA**.
- SMS queda fuera del MVP (Google Play restringe el permiso).

## Consecuencias
- Hay que mantener un parser por fuente, con ejemplos reales de notificaciones como pruebas.
- Cuatro o cinco formatos distintos desde el inicio: el parser de cada fuente debe estar aislado para que agregar uno no toque el resto.
- iOS tendrá menos valor percibido hasta que llegue su captura automática.
