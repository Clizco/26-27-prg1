# Reto 002 · 2Think

## Adaptación

`DevolverCambio2Think.java`: mismo procedimiento (dividir por la moneda más grande y seguir con el resto) con monedas de 4, 3 y 1.

## ¿Entrega siempre el menor número de monedas?

No. Contraejemplo: cambio de **6** unidades.

- El programa entrega 1 de 4 + 2 de 1 = **3 monedas**.
- Lo óptimo es 2 de 3 = **2 monedas**.

Coger primero la moneda más grande (4) deja un resto (2) que solo se puede pagar con monedas de 1, mientras que no cogerla permite usar dos de 3.

## ¿Por qué con el euro sí funciona?

Este procedimiento se llama *algoritmo voraz*: en cada paso coge la mayor moneda posible sin mirar atrás. Solo da el óptimo en los sistemas llamados **canónicos**, y el euro (1, 2, 5, 10, 20, 50, 100…) lo es.

La idea intuitiva: en el euro, cada moneda grande vale al menos tanto como cualquier combinación de monedas pequeñas con el mismo número de piezas o menos. Por ejemplo, dos monedas de 2 (4 €) nunca pueden sustituir con ventaja a una de 5, y 2+2+1 = 5 se cambia por una sola de 5. Por eso coger la grande nunca "estropea" el resto.

Con 4, 3 y 1 no pasa: 3 + 3 = 6 usa dos monedas, pero 4 + 1 + 1 = 6 necesita tres. Dos monedas pequeñas juntas superan a la grande y el voraz no lo ve.
