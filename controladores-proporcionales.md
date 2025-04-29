# Análisis de la función de transferencia con controlador proporcional $$K_p$$

- Función de transferencia

$$G(s) = \frac{K_p}{s^3 + 6s^2 + 11s + 6}$$

- Entrada: escalón unitario

$$U(s) = \frac{1}{s}$$

- La salida en Laplace:

$$Y(s) = G(s)U(s) = \frac{K_p}{s(s^3 + 6s^2 + 11s + 6)}$$

## 1. Teorema del Valor Final

- Aplicamos:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} sY(s)$$

- Calculamos:

$$\lim_{s \to 0} s \times \frac{K_p}{s(s^3 + 6s^2 + 11s + 6)} = \lim_{s \to 0} \frac{K_p}{s^3 + 6s^2 + 11s + 6}$$

- Sustituyendo s = 0 

$$\frac{K_p}{6}$$

*Conclusión:*  
El valor final de la salida es:

$$ \lim_{t \to \infty} y(t) = \frac{K_p}{6}$$

## 2. Ubicación de Polos sin $$K_p$$

- El polinomio característico es:

$$s^3 + 6s^2 + 11s + 6 = 0$$

- Buscamos raíces: Probamos s = -1 :

$$(-1)^3 + 6(-1)^2 + 11(-1) + 6 = -1 + 6 - 11 + 6 = 0$$

- Entonces:

$$(s + 1) \text{ es un factor}$$

- Dividimos:

$$s^3 + 6s^2 + 11s + 6 = (s+1)(s^2 + 5s + 6)$$

- Factorizando el cuadrático:

$$s^2 + 5s + 6 = (s+2)(s+3)$$

*Polos:* 

$$s = -1, \quad s = -2, \quad s = -3$$

- Todos los polos están en el semiplano izquierdo sistema estable $$K_p$$


## 3. Aplicación del criterio de Routh-Hurwitz $$k_p$$

- Nuevo polinomio con controlador:

$$s^3 + 6s^2 + 11s + (6 + K_p) = 0$$

Coeficientes:

- $$a_0 = 1$$
- $$a_1 = 6$$
- $$a_2 = 11$$
- $$a_3 = 6 + K_p$$

### Tabla de Routh-Hurwitz:

| Fila  | Elementos |
|:-----:|:---------:|
| $$s^3$$ | 1 |
| $$s^2$$ | 6 |
| $$s^1$$ | $$b_1$$ |
| $$s^0$$ | $$6 + K_p$$ |

Cálculo de $$b_1$$:

$$b_1 = \frac{6(11) - 1(6+K_p)}{6}$$
$$b_1 = \frac{66 - (6+K_p)}{6}$$
$$b_1 = \frac{60 - K_p}{6}$$

## 4. Condiciones de Estabilidad

- Para estabilidad, todos los elementos de la primera columna deben ser positivos:

- $$1 > 0$$ → ✅
- $$6 > 0$$ → ✅
- $$b_1 > 0$$
- $$6 + K_p > 0$$

- Análisis de $$b_1 > 0$$:

$$\frac{60 - K_p}{6} > 0$$

Multiplicamos ambos lados por 6:

$$60 - K_p > 0$$
$$K_p < 60$$

### Análisis de $$6 + K_p > 0$$:

$$K_p > -6$$

Pero usualmente trabajamos con $$K_p > 0$$ en control proporcional.

## 5. Conclusión Final

Para estabilidad:

$$0 < K_p < 60$$
