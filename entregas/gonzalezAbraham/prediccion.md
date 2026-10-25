# Reto 002 · Predicción

## Caso

Debe pagar **232 €** y paga con **200 €** (se incumple la condición "lo entregado es mayor o igual que el importe").

## Predicción (antes de ejecutar)

El cambio vale `200 - 232 = -32`. El programa no comprueba nada, así que sigue haciendo divisiones y restos con un número negativo.

En Java, la división entera trunca hacia cero y el resto `%` conserva el signo del dividendo:

| Paso | Operación | Resultado | Resto que queda |
|-|-|-|-|
| 100 € | `-32 / 100` | 0 | `-32 % 100 = -32` |
| 50 € | `-32 / 50` | 0 | `-32 % 50 = -32` |
| 20 € | `-32 / 20` | -1 | `-32 % 20 = -12` |
| 10 € | `-12 / 10` | -1 | `-12 % 10 = -2` |
| 5 € | `-2 / 5` | 0 | `-2 % 5 = -2` |
| 2 € | `-2 / 2` | -1 | `-2 % 2 = 0` |
| 1 € | resto | 0 | |

Predigo que mostrará:

```
0 billete(s) de 100 €
0 billete(s) de 50 €
-1 billete(s) de 20 €
-1 billete(s) de 10 €
0 billete(s) de 5 €
-1 moneda(s) de 2 €
0 moneda(s) de 1 €
```

Es decir, no falla ni avisa: muestra cantidades negativas que suman -32 € (lo que el cliente "debe" todavía).

## Resultado real y explicación

*(Se completa en un commit posterior, después de ejecutar el programa.)*
