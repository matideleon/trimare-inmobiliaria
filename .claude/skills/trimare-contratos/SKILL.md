---
name: trimare-contratos
description: Genera contratos de arrendamiento de vivienda para Uruguay con el formato de Trimare. Úsala siempre que el usuario quiera redactar, armar, preparar o completar un contrato de alquiler, contrato de arrendamiento, contrato de locación de vivienda o casa-habitación, aunque solo mencione "el alquiler de tal propiedad", "el contrato del inquilino" o pase los datos de un arrendador e inquilino. Cubre el mercado uruguayo (cédula de identidad, padrón, reajuste por IPC/UR/UI, garantías locales).
---

# Trimare — Contratos de arrendamiento (Uruguay)

Esta skill arma contratos de **arrendamiento de vivienda (casa-habitación) para Uruguay** a partir
de un modelo estándar, con el sello de Trimare. El objetivo es que cualquier contrato salga completo,
ordenado y con el lenguaje habitual del mercado uruguayo, evitando que se olviden cláusulas clave.

**Importante — siempre decírselo al usuario:** el documento generado es un **borrador basado en un modelo
estándar**. No es asesoramiento legal y debe ser revisado por un escribano o abogado antes de firmarse.
Incluí esta advertencia al entregar cada contrato.

## Cómo trabajar

El flujo es: reunir datos → elegir opciones de cláusulas → completar el modelo → entregar el contrato.

### 1. Reunir los datos

Necesitás estos datos para completar el contrato. Si el usuario ya dio algunos (en el mensaje o en
archivos de la propiedad), tomalos de ahí; pedí solo lo que falte, en una sola tanda y de forma clara:

- **Arrendador (propietario):** nombre completo, cédula de identidad, domicilio, nacionalidad.
- **Arrendatario (inquilino):** nombre completo, cédula de identidad, domicilio, nacionalidad.
- **Inmueble:** dirección, número de padrón, localidad y departamento; si es apartamento, número de unidad.
- **Plazo:** duración (p. ej. 1 o 2 años) y fecha de inicio.
- **Precio:** monto mensual y moneda ($, USD o UI); forma de pago.
- **Garantía:** qué tipo usa (ver opciones abajo); si hay fiador, sus datos.
- **Depósito:** si lo hay y por cuánto.

No frenes el trabajo por detalles menores: si algo no es crítico, usá un valor por defecto razonable
y avisale al usuario qué asumiste, para que lo confirme. Por ejemplo, si no dice plazo, proponé 2 años.

### 2. Elegir las opciones de cada cláusula

Las decisiones que cambian según el caso (tipo de garantía, índice de reajuste, quién paga los tributos,
cómo calcular la fecha de fin, casa vs. apartamento, cláusulas especiales) están explicadas en
**`references/arrendamiento-uy.md`**. Leé ese archivo cuando tengas que decidir cualquiera de estos
puntos: te da las alternativas reales del mercado uruguayo y cómo redactarlas. No improvises cláusulas
legales sin consultarlo.

### 3. Completar el modelo

Tomá la plantilla de **`assets/contrato-arrendamiento.md`** y reemplazá cada campo `{{...}}` con los
datos reunidos. Pautas al completar:

- Escribí los montos en letras y cifras: "treinta y cinco mil pesos uruguayos ($ 35.000)".
- Calculá `fecha_fin` a partir de la fecha de inicio más el plazo.
- Si un campo opcional no aplica (p. ej. `inmueble_unidad` en una casa, o `clausulas_adicionales`),
  dejalo vacío y asegurate de que la redacción quede natural, sin huecos ni `{{...}}` sueltos.
- Revisá que no quede ningún `{{placeholder}}` sin reemplazar antes de entregar.

### 4. Entregar

Mostrá el contrato completo y limpio. Después de revisarlo internamente, ofrecé guardarlo como archivo
(p. ej. `.md` o `.docx`) si el usuario lo necesita para imprimir o firmar. Cerrá siempre con la
advertencia de que conviene la revisión de un escribano/abogado.

## Sobre el alcance

Por ahora esta skill cubre el **contrato de arrendamiento de vivienda**. Si el usuario pide otro
documento (boleto de reserva, compromiso de compraventa, recibos), decíle que esta skill aún no lo cubre
y ofrecé ampliarla más adelante con esos modelos.
