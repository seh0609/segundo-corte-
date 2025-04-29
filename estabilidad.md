# Estabilidad 
Es la capacidad de un sistema para mantener su comportamiento deseado ante perturbaciones o cambios de entrada. Es decir, que su salida no es ±∞ sino un valor concreto. También podríamos definir a un sistema estable que evoluciona de un modo similar a la variable de entrada.


![image](https://github.com/user-attachments/assets/937ea8bc-eda9-4848-867e-c694bbac95e1)\
Figura 1. Como se ve un sistema estable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

![image](https://github.com/user-attachments/assets/227176bd-8b48-4cdb-a208-af1a332fc0ef)\
Figura 2. Como se ve un sistema inestable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

## 1. Toerema de valor final 

Para poder saber si nuestro sistema es estable necesitamos tener en cuenta el teorema de valor final, este teorema se nos hace muy útil  ya que este nos va a permitir encontrar el límite de una función en infinito, para esto tenemos que tener en dominio de la transformada de Laplace, para esto tenemos estos términos:

$$\lim_{t \to \infty} f(t) = \lim_{s \to 0} sF(s)$$

💡**Ejemplo 1:**
- La función de transferencia del sistema es:

$$G(s) = \frac{6}{7s + 1}$$

- Con una entrada escalón unitario:

$$U(s) = \frac{1}{s}$$

- Entonces la salida en Laplace es:

$$Y(s) = G(s) \cdot U(s) = \frac{6}{s(7s + 1)}$$

- Teorema del Valor Final:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{6s}{s(7s + 1)} = \frac{6}{1} = 6$$

- Resultado final:

$$\lim_{t \to \infty} y(t) = 6$$

### 1.1. Análisis de estabilidad por medio del Teorema de Valor final y por medio de los polos 
#### 1.1.1. Criterios de Teorema de Valor Final 
- Después de tener claro el teorema de valor final, se debe evaluar el valor final de la entrada y la salida para saber si están limitadas de la misma manera
- Se tiene una entrada de escalón tal que:
  
Nueva función de transferencia:

$$G(s) = \frac{10}{5s + 2}$$

- Con una entrada escalón unitario:

$$U(s) = \frac{1}{s}$$
- Entonces la salida en Laplace es:

$$Y(s) = G(s) \cdot U(s) = \frac{10}{s(5s + 2)}$$

- Teorema del Valor Final:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{10s}{s(5s + 2)} = \frac{10}{2} = 5$$

- Resultado final:

$$\lim_{t \to \infty} y(t) = 5$$

#### 1.1.2. Criterios Por Ubicacion de Polos 
- Un sistema será estable si la totalidad de sus polos se encuentran en el semiplano izquierdo del plano complejo, lo que implica que la parte real de cada polo es negativa.
- Si existe al menos un polo situado en el semiplano derecho del plano complejo, es decir, con una parte real positiva, el sistema será inestable.
  
💡**Ejemplo 2:**

- La función de transferencia es:

$$G(s) = \frac{10}{5s + 2}$$

- Respuesta a una entrada escalón de magnitud \( A \):

- Entrada en Laplace:

$$U(s) = \frac{A}{s}$$

- Salida:

$$Y(s) = G(s) \cdot U(s) = \frac{10}{5s + 2} \cdot \frac{A}{s}$$

- Aplicando el teorema del valor final:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} s \cdot Y(s) = \lim_{s \to 0} s \cdot \frac{10A}{s(5s + 2)} = \frac{10A}{2} = 5A$$

- Estabilidad del sistema:

- El sistema es **estable** porque su único polo está en:

$$s = -\frac{2}{5}$$

$$\lim_{t \to \infty} y(t) = 5A$$
- Y por tanto se encuentra en el semiplano izquierdo del plano \( s \). La salida no crece indefinidamente y tiende a un valor finito.

### 2. Criterio de Routh - Hurwitz

### 3. Ejercicios

📚 **Ejercicio de Estabilidad 1:**
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

📚 **Ejercicio de Estabilidad 2:**

