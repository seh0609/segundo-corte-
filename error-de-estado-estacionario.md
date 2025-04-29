- Análisis de la función de transferencia
- Función de transferencia
- Se considera la siguiente función de transferencia de segundo orden:

$$G(s) = \frac{5}{s^2 + 4s + 5}$$

- Y una entrada tipo escalón unitario:

$$U(s) = \frac{1}{s}$$

- La salida es:

$$Y(s) = G(s)U(s) = \frac{5}{s(s^2 + 4s + 5)}$$

- Análisis usando el Teorema del Valor Final

- Aplicamos el teorema del valor final:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} sY(s)$$

- Multiplicamos:

$$\lim_{s \to 0} s \times \frac{5}{s(s^2 + 4s + 5)} = \lim_{s \to 0} \frac{5}{s^2 + 4s + 5}$$

- Sustituimos \( s = 0 \):

$$\frac{5}{0 + 0 + 5} = 1$$

- Conclusión:

$$\lim_{t \to \infty} y(t) = 1$$

- El sistema responde a un valor finito y positivo → *El sistema es estable*.

- Análisis de la ubicación de polos

- El denominador es:

$$s^2 + 4s + 5 = 0$$

- Resolvemos utilizando la fórmula general:

$$s = \frac{-4 \pm \sqrt{4^2 - 4(1)(5)}}{2(1)}$$

$$s = \frac{-4 \pm \sqrt{16 - 20}}{2}$$

$$s = \frac{-4 \pm \sqrt{-4}}{2}$$

$$s = \frac{-4 \pm 2j}{2}$$

$$s = -2 \pm j$$

- Conclusión:

- Los polos están en \( -2 \pm j \).
- Tienen parte real negativa → *El sistema es estable*.
  
- Análisis usando el Criterio de Routh-Hurwitz

- El polinomio característico es:

$$s^2 + 4s + 5$$

- Construimos la tabla de Routh:

| Orden | Coeficientes |
|:-----:|:------------:|
| \( s^2 \) | 1         |
| \( s^1 \) | 4         |
| \( s^0 \) | 5         |

Todos los coeficientes son positivos → *No hay cambios de signo* → *Sistema estable*.

---

- Análisis de la función de transferencia con controlador \( K_p \)

- Nueva función de transferencia de lazo cerrado

- La función de lazo cerrado es:

$$G_0(s) = \frac{K_p G(s)}{1 + K_p G(s)}$$

- Sustituyendo \( G(s) \):

$$G_0(s) = \frac{5K_p}{s^2 + 4s + 5 + 5K_p}$$


- Nuevo polinomio característico

- El nuevo polinomio característico es:

$$s^2 + 4s + 5 + 5K_p = 0$$

- Que se puede reescribir como:

$$s^2 + 4s + (5 + 5K_p) = 0$$

- Aplicación del Criterio de Routh-Hurwitz

- Identificamos los coeficientes:

- \( a_0 = 1 \)
- \( a_1 = 4 \)
- \( a_2 = 5 + 5K_p \)

- Construimos la tabla de Routh:

| Fila  | Coeficientes  |
|:-----:|:-------------:|
| \( s^2 \) | 1 |
| \( s^1 \) | 4 |
| \( s^0 \) | \( 5 + 5K_p \) |

- Condiciones de estabilidad:

Para estabilidad, todos los coeficientes deben ser positivos:

1. \( 1 > 0 \) → ✅
2. \( 4 > 0 \) → ✅
3. \( 5 + 5K_p > 0 \)

- Resolviendo:

$$5 + 5K_p > 0$$

$$5K_p > -5$$

$$K_p > -1$$

- Conclusión:

- El sistema es estable si:

$$K_p > -1$$
