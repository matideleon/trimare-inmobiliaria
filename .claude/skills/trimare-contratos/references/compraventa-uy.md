# Guía de referencia — Boleto de reserva y Compromiso de compraventa (Uruguay)

Complementa los modelos `assets/boleto-reserva.md` y `assets/compromiso-compraventa.md`.
No es asesoramiento legal: todo documento debe revisarlo un escribano antes de firmar.

## Diferencia entre los dos documentos

- **Boleto de reserva:** documento breve y previo. El interesado deja una **seña** para reservar la
  propiedad mientras el propietario decide si acepta la oferta. Lo firma el reservante con Trimare.
  Es una oferta con garantía, no una venta.
- **Compromiso de compraventa:** contrato formal entre vendedor y comprador, ya acordada la operación.
  Fija precio, forma de pago, plazo y escribano para escriturar. Puede inscribirse en el Registro.

## Boleto de reserva

- **Seña:** monto que entrega el reservante (suele ser un porcentaje del precio o un monto fijo).
  Escribir en letras y cifras.
- **Plazo (`plazo_fecha`):** fecha límite para que el propietario acepte o rechace. Si no se indica,
  sugerir un plazo corto (p. ej. 5 a 10 días) y confirmarlo.
- **`plazo_compromiso`:** plazo para firmar el compromiso de compraventa una vez aceptada la oferta
  (p. ej. "15 días").
- Regla clásica de la seña: si el reservante desiste, la pierde; si el propietario no acepta, se devuelve.

## Compromiso de compraventa

- **Forma de pago (`forma_pago`):** detallar seña + saldo, o cuotas si las hay. Indicar moneda
  (USD es lo más común en compraventa de inmuebles en Uruguay).
- **Seña y saldo:** `sena_*` es lo entregado al firmar; `saldo_*` es lo que se paga en la escritura.
  Verificá que seña + saldo = precio total.
- **Escrituración (`plazo_escritura`):** plazo para otorgar la escritura (p. ej. "60 días"). Indicar el
  escribano (`escribano`) y quién lo designa (`escribano_designado_por`) — normalmente lo designa el
  comprador. Gastos de escritura (`gastos_escritura`): habitualmente a cargo del comprador.
- **Estado/ocupación (`estado_ocupacion`):** p. ej. "libre de ocupantes" o "ocupado por inquilino con
  contrato vigente". `entrega_posesion`: cuándo se entrega (al firmar la escritura, o antes).
- **Seña duplicada:** regla habitual del incumplimiento — si incumple el vendedor, devuelve la seña
  duplicada; si incumple el comprador, la pierde.
- **Tributos al día:** el vendedor declara estar al día (Contribución Inmobiliaria, Primaria, gastos
  comunes). Desde la escritura los asume el comprador.

## Campos opcionales comunes a ambos

- `inmueble_unidad`: si es apartamento, ", unidad N.º X"; si es casa, vacío.
- `clausulas_adicionales`: pactos especiales numerados como cláusulas siguientes. Si no hay, dejar vacío.
- Montos siempre en letras y cifras. Revisar que no quede ningún `{{placeholder}}` sin reemplazar.
