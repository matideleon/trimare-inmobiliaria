---
name: trimare-contratos
description: Genera documentos inmobiliarios para Uruguay con el formato de Trimare — contrato de arrendamiento de vivienda, boleto de reserva y compromiso de compraventa. Úsala siempre que el usuario quiera redactar, armar, preparar o completar un contrato de alquiler/arrendamiento/locación, una reserva o seña de una propiedad, o un compromiso/boleto de compraventa, aunque solo mencione "el alquiler de tal propiedad", "el contrato del inquilino", "reservar el apto", "la seña del comprador" o pase los datos de las partes. Cubre el mercado uruguayo (cédula de identidad, padrón, reajuste por IPC/UR/UI, garantías locales, seña, escrituración).
---

# Trimare — Documentos inmobiliarios (Uruguay)

Esta skill arma documentos inmobiliarios para **Uruguay** a partir de modelos estándar, con el sello de
Trimare. Cubre tres documentos:

1. **Contrato de arrendamiento** de vivienda (casa-habitación).
2. **Boleto de reserva** (seña previa a la compra).
3. **Compromiso de compraventa** (contrato formal de venta).

El objetivo es que cada documento salga completo, ordenado y con el lenguaje habitual del mercado
uruguayo, sin que se olviden cláusulas clave.

**Importante — siempre decírselo al usuario:** lo generado es un **borrador basado en un modelo estándar**.
No es asesoramiento legal y debe ser revisado por un escribano o abogado antes de firmarse. Incluí esta
advertencia al entregar cada documento.

## Paso 0 — Identificar qué documento es

Según lo que pida el usuario, elegí el modelo y la guía correspondientes:

| Si el usuario quiere… | Modelo (`assets/`) | Guía (`references/`) |
|---|---|---|
| Contrato de alquiler / arrendamiento / locación | `contrato-arrendamiento.md` | `arrendamiento-uy.md` |
| Reservar una propiedad / dejar seña / oferta | `boleto-reserva.md` | `compraventa-uy.md` |
| Compromiso o boleto de compraventa / venta | `compromiso-compraventa.md` | `compraventa-uy.md` |

Si no queda claro cuál necesita, preguntá antes de seguir.

## Cómo trabajar (igual para los tres)

El flujo es: reunir datos → elegir opciones de cláusulas → completar el modelo → entregar.

### 1. Reunir los datos

Tomá los datos que el usuario ya haya dado (en el mensaje o en archivos de la propiedad) y pedí solo lo
que falte, en una sola tanda y de forma clara. Los datos comunes son:

- **Las partes:** nombre completo, cédula de identidad, domicilio y nacionalidad de cada una
  (arrendador/arrendatario, reservante, o vendedor/comprador según el documento).
- **Inmueble:** dirección, número de padrón, localidad y departamento; si es apartamento, número de unidad.
- **Montos:** según el documento — precio mensual y garantía (arrendamiento); seña y precio ofrecido
  (reserva); precio, seña, saldo y plazo de escrituración (compraventa).

No frenes el trabajo por detalles menores: si algo no es crítico, usá un valor por defecto razonable y
avisá qué asumiste para que el usuario lo confirme (p. ej. plazo de arrendamiento de 2 años, o plazo de
reserva de 7 días).

### 2. Elegir las opciones de cada cláusula

Las decisiones que cambian según el caso están explicadas en las guías de `references/`:

- **`references/arrendamiento-uy.md`** — plazos, precio, reajuste (IPC/UR/UI), garantías, depósito,
  tributos y gastos comunes para el contrato de alquiler.
- **`references/compraventa-uy.md`** — seña, plazo de escrituración, escribano, gastos, estado de
  ocupación y reglas de incumplimiento para reserva y compraventa.

Leé la guía correspondiente cuando tengas que decidir cualquiera de estos puntos. No improvises cláusulas
legales sin consultarla.

### 3. Completar el modelo

Tomá la plantilla del documento elegido y reemplazá cada campo `{{...}}` con los datos reunidos. Pautas:

- Escribí los montos en letras y cifras: "treinta y cinco mil pesos uruguayos ($ 35.000)".
- En el arrendamiento, calculá `fecha_fin` a partir de la fecha de inicio más el plazo.
- En la compraventa, verificá que **seña + saldo = precio total**.
- Si un campo opcional no aplica (p. ej. `inmueble_unidad` en una casa, o `clausulas_adicionales`),
  dejalo vacío y asegurate de que la redacción quede natural, sin huecos ni `{{...}}` sueltos.
- Revisá que no quede ningún `{{placeholder}}` sin reemplazar antes de entregar.

### 4. Entregar

Mostrá el documento completo y limpio. Ofrecé guardarlo como archivo (`.md` o `.docx`) si el usuario lo
necesita para imprimir o firmar. Cerrá siempre con la advertencia de que conviene la revisión de un
escribano/abogado.

## Ampliar la skill

Si el usuario pide otro documento que aún no está cubierto (recibos, autorización de venta, etc.), decíselo
y ofrecé agregar ese modelo a la skill más adelante.
