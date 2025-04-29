# Estabilidad 
Es la capacidad de un sistema para mantener su comportamiento deseado ante perturbaciones o cambios de entrada. Es decir, que su salida no es ±∞ sino un valor concreto. También podríamos definir a un sistema estable que evoluciona de un modo similar a la variable de entrada.


![image](https://github.com/user-attachments/assets/937ea8bc-eda9-4848-867e-c694bbac95e1)\
Figura 1. Como se ve un sistema estable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

![image](https://github.com/user-attachments/assets/227176bd-8b48-4cdb-a208-af1a332fc0ef)\
Figura 2. Como se ve un sistema inestable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

## 1. Teorema de valor final 

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

## 2. Criterio de Routh - Hurwitz
- Un sistema lineal es estable si y solo si las raíces de su polinomio característico (conocido como polinomio de Hurwitz) poseen partes reales negativas.
- El criterio de Routh-Hurwitz ofrece un método algebraico para verificar si un polinomio es de Hurwitz (y por lo tanto, si el sistema es estable) examinando la disposición y los signos de sus coeficientes, evitando la necesidad de calcular explícitamente sus raíces.
- Tenemos este polinomio con la siguiente forma
  
$$a_0 s^n + a_1 s^{n-1} + \cdots + a_{n-1} s + a_n = 0$$
- Para que un polinomio sea de Hurwitz, todos sus coeficientes deben ser estrictamente positivos. La presencia de al menos un coeficiente negativo o nulo descarta inmediatamente que el polinomio sea de Hurwitz. Si todos los coeficientes son positivos, el polinomio se considera un posible candidato a ser de Hurwitz, requiriendo un análisis adicional para confirmar la ubicación de sus raíces.
- Después realizamos el arreglo de Hurwitz:
  
$$
\begin{array}{c|cccccc}
s^n     & a_0 & a_2 & a_4 & a_6 & a_8 & \cdots \\
s^{n-1} & a_1 & a_3 & a_5 & a_7 & a_9 & \cdots \\
s^{n-2} & b_1 & b_2 & b_3 & b_4 & b_5 & \cdots \\
s^{n-3} & c_1 & c_2 & c_3 & c_4 & c_5 & \cdots \\
\vdots  & \vdots & \vdots & \vdots & \vdots & \vdots & \ddots \\
s^1     & \cdots & \cdots & \cdots & \cdots & \cdots & \cdots \\
s^0     & \cdots & \cdots & \cdots & \cdots & \cdots & \cdots \\
\end{array}
$$

- Despues de realizar el arreglo calculamos los coeficientes con las siguientes formulas:

$$
b_1 = \frac{a_1 a_2 - a_0 a_3}{a_1}
\quad\quad
b_2 = \frac{a_1 a_4 - a_0 a_5}{a_1}
$$

$$
c_1 = \frac{b_1 a_3 - a_1 b_2}{b_1}
\quad\quad
c_2 = \frac{b_1 a_5 - a_1 b_3}{b_1}
$$

💡**Ejemplo 3:**

- Polinomio:

$$s^3 + 7s^2 + 10s + 8 = 0$$

- Tabla de Routh-Hurwitz:

$$
\begin{array}{c|cc}
s^3 & 1 & 10 \\
s^2 & 7 & 8 \\
s^1 & b_1 & 0 \\
s^0 & c_1 & \\
\end{array}
$$

- Cálculos:
  
$$
\begin{aligned}
b_1 &= \frac{7 \cdot 10 - 1 \cdot 8}{7} = \frac{70 - 8}{7} = \frac{62}{7} \\
\\
c_1 &= \frac{\frac{62}{7} \cdot 8 - 7 \cdot 0}{\frac{62}{7}} = \frac{496}{62/7} = 8
\end{aligned}
$$

- Resultado

$$
\begin{array}{c|cc}
s^3 & 1 & 10 \\
s^2 & 7 & 8 \\
s^1 & \frac{62}{7} & 0 \\
s^0 & 8 & \\
\end{array}
$$

## 3. Ejercicios
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

- Los polos están en $$( -2 \pm j \)$$.
- Tienen parte real negativa → *El sistema es estable*.
  
- Análisis usando el Criterio de Routh-Hurwitz

- El polinomio característico es:

$$s^2 + 4s + 5$$

- Construimos la tabla de Routh:

| Orden | Coeficientes |
|:-----:|:------------:|
| $$s^2$$ | 1         |
| $$s^1$$ |< 4        |
| $$s^0$$ | 5         |

Tabla 1. Tabla Ejercicio 1

Todos los coeficientes son positivos → *No hay cambios de signo* → *Sistema estable*.

- Análisis de la función de transferencia con controlador $$K_p$$

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

- $$a_0 = 1$$
- $$a_1 = 4$$
- $$a_2 = 5 + 5K_p$$

- Construimos la tabla de Routh:

| Fila  | Coeficientes  |
|:-----:|:-------------:|
| $$s^2$$ | 1 |
| $$s^1$$ | 4 |
| $$s^0$$ | $$5 + 5K_p$$ |

Tabla 2. Tabla Ejercicio 1
- Condiciones de estabilidad:

Para estabilidad, todos los coeficientes deben ser positivos:

1. $$1 > 0$$→ ✅
2. $$4 > 0$$→ ✅
3. $$5 + 5K_p > 0$$

- Resolviendo:

$$5 + 5K_p > 0$$

$$5K_p > -5$$

$$K_p > -1$$

- Conclusión:

- El sistema es estable si:

$$K_p > -1$$

📚 **Ejercicio de Estabilidad 2:**
- Función de transferencia

$$G(s) = \frac{K_p}{s^3 + 6s^2 + 11s + 6}$$

- Entrada: escalón unitario

$$U(s) = \frac{1}{s}$$

- La salida en Laplace:

$$Y(s) = G(s)U(s) = \frac{K_p}{s(s^3 + 6s^2 + 11s + 6)}$$

- Teorema del Valor Final

- Aplicamos:

$$\lim_{t \to \infty} y(t) = \lim_{s \to 0} sY(s)$$

- Calculamos:

$$\lim_{s \to 0} s \times \frac{K_p}{s(s^3 + 6s^2 + 11s + 6)} = \lim_{s \to 0} \frac{K_p}{s^3 + 6s^2 + 11s + 6}$$

- Sustituyendo s = 0 

$$\frac{K_p}{6}$$

*Conclusión:*  
El valor final de la salida es:

$$\lim_{t \to \infty} y(t) = \frac{K_p}{6}$$

- Ubicación de Polos sin $$K_p$$

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


- Aplicación del criterio de Routh-Hurwitz $$k_p$$

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

Tabla 3. Tabla Ejercicio 2

Cálculo de $$b_1$$:

$$b_1 = \frac{6(11) - 1(6+K_p)}{6}$$
$$b_1 = \frac{66 - (6+K_p)}{6}$$
$$b_1 = \frac{60 - K_p}{6}$$

- Condiciones de Estabilidad

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

- Análisis de $$6 + K_p > 0$$:

$$K_p > -6$$

Pero usualmente trabajamos con $$K_p > 0$$ en control proporcional.

- Conclusión Final

Para estabilidad:

$$0 < K_p < 60$$

## 4. Concluciones

En conjunto, estos métodos ofrecen herramientas complementarias para el análisis de la estabilidad. El Teorema del Valor Final proporciona una visión del comportamiento final de la salida, la ubicación de polos ofrece una caracterización fundamental de la estabilidad basada en las raíces del sistema, y el Criterio de Routh-Hurwitz proporciona un método práctico para evaluar la estabilidad directamente a partir de los coeficientes del polinomio característico, especialmente útil cuando encontrar las raíces analíticamente es complejo. Los ejemplos presentados ilustran cómo estos criterios se aplican para determinar la estabilidad de diferentes funciones de transferencia y cómo la introducción de un controlador (como un control proporcional (K_p)) puede afectar la estabilidad del sistema en lazo cerrado.

## 5. Referencias

- https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/
- https://www.quora.com/How-do-I-make-a-control-system-stable
- https://www.uv.es/masefor/PAGINAS/estabilidad.html
- https://controlautomaticoeducacion.com/control-realimentado/criterio-de-estabilidad-de-routh-hurwitz/
