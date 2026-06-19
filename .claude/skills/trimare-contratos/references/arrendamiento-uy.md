# Guía de referencia — Contrato de arrendamiento de vivienda (Uruguay)

Esta guía complementa el modelo de `assets/contrato-arrendamiento.md`. Sirve para decidir
correctamente las opciones de cada cláusula y para explicarle al usuario las alternativas.
No es asesoramiento legal: todo contrato debería revisarlo un escribano o abogado antes de firmar.

## Plazo (cláusula TERCERA)

- El plazo legal mínimo habitual para vivienda permanente es de **un (1) año**; lo más común son
  contratos de **1 o 2 años**.
- Si el usuario no indica plazo, sugerir 2 años como valor por defecto, pero preguntar.
- Calcular `fecha_fin` a partir de `fecha_inicio` + plazo (p. ej. inicio 01/07/2026, plazo 2 años → fin 30/06/2028).

## Precio y forma de pago (cláusula CUARTA)

- La moneda puede ser **pesos uruguayos ($)**, **dólares (USD)** o **Unidades Indexadas (UI)**.
- Escribir siempre el importe en letras y en cifras: p. ej. "treinta y cinco mil pesos uruguayos ($ 35.000)".
- `forma_pago`: transferencia bancaria a la cuenta indicada, depósito, o el mecanismo que use Trimare.

## Reajuste (cláusula QUINTA)

Opciones más usadas en Uruguay:

- **IPC (Índice de Precios al Consumo)** — reajuste anual por inflación. Es lo más frecuente.
- **UR (Unidad Reajustable)** — sigue la evolución de los salarios.
- **UI (Unidad Indexada)** — sigue el IPC con ajuste diario; usada cuando el precio se pacta en UI.

Periodicidad habitual: **anual**. Completar `reajuste_periodicidad` ("anualmente") y
`reajuste_indice` (p. ej. "la variación del Índice de Precios al Consumo (IPC) publicado por el INE").

## Garantía (cláusula SEXTA)

Tipos de garantía admitidos en Uruguay (elegir según el caso):

- **Garantía de alquileres de la Contaduría General de la Nación (CGN)** — para funcionarios públicos.
- **ANDA / Asociaciones / Fianzas privadas** (p. ej. PORTO Seguros, Finanzas Casa).
- **Fiador solidario** — un tercero que garantiza con su patrimonio; agregar sus datos como compareciente adicional.
- **Garantía real** — hipoteca o depósito de un bien.
- **Depósito en garantía / sin fiador** — al amparo de la Ley 19.889 (LUC), arrendamiento sin garantía con
  depósito y proceso de ejecución más ágil.

Si el usuario no especifica, preguntar cuál usa Trimare. Redactar `garantia` describiendo el tipo elegido
y, si hay fiador, sumar una cláusula con sus datos (nombre, CI, domicilio) y su carácter de
fiador solidario, liso, llano y principal pagador.

## Depósito (cláusula SÉPTIMA)

- Si hay depósito, redactar `deposito_clausula` con el monto (equivalente a uno o más meses) y la condición
  de devolución al finalizar el contrato, una vez verificado el estado del inmueble y pagos al día.
- Si no hay depósito, poner: "No se constituye depósito en garantía."

## Tributos, gastos comunes y servicios (cláusula OCTAVA)

- **Servicios de consumo** (UTE, OSE, gas, internet): normalmente a cargo del arrendatario.
- **Gastos comunes** (si es apartamento en propiedad horizontal): definir quién los paga. Si aplica,
  completar `gastos_comunes` con ", así como los gastos comunes del edificio"; si es casa, dejar vacío.
- **Tributos** (Contribución Inmobiliaria, Impuesto de Primaria): habitualmente a cargo del **arrendador**,
  salvo pacto distinto. Completar `tributos_cargo`.

## Inmueble (cláusula PRIMERA)

- `inmueble_unidad`: si es apartamento, agregar ", unidad N.º X" (p. ej. ", unidad 302"); si es casa, dejar vacío.
- `inmueble_padron`: número de padrón del inmueble (clave para identificar la finca).

## Cláusulas adicionales

Usar `clausulas_adicionales` para pactos especiales que pida el usuario, numerándolas como
"DÉCIMA QUINTA", "DÉCIMA SEXTA", etc. Ejemplos frecuentes:

- Prohibición o autorización de mascotas.
- Mantenimiento de jardín/piscina.
- Rescisión anticipada y penalidad.
- Inventario de mobiliario (si se alquila amueblado).

Si no hay cláusulas adicionales, dejar el campo vacío.
