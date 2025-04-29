
- Función de Transferencia Dada:

$$G(s) = \frac{25}{s^2 + 6s + 25}$$

- Comparación con la Forma Estándar de Segundo Orden:

La forma general es:

$$G(s) = \frac{k \omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$$

Igualamos coeficientes:

- $$a_1 = 6 = 2\zeta\omega_n$$
- $$a_0 = 25 = \omega_n^2$$

- Cálculo de los Parámetros:

De $$\omega_n^2 = 25$$, obtenemos:

$$\omega_n = \sqrt{25} = 5$$

De $$2\zeta\omega_n = 6$$, sustituimos $$\omega_n = 5$$:

$$2\zeta(5) = 6 \quad \Rightarrow \quad \zeta = \frac{6}{10} = 0.6$$

Verificación del valor de $$k$$:

$$b_0 = k\omega_n^2 = 25 \quad \Rightarrow \quad k(5)^2 = 25 \quad \Rightarrow \quad k = 1$$

- Función Reescrita:

Sustituyendo los valores en la forma estándar:

$$G(s) = \frac{(1)(5)^2}{s^2 + 2(0.6)(5)s + (5)^2} = \frac{25}{s^2 + 6s + 25}$$

- Agregando un Cero en $$s = -2$$

Nueva función de transferencia:

$$G(s) = \frac{25(s + 2)}{s^2 + 6s + 25}$$

Para encontrar la respuesta al escalón, dividimos entre $$s$$:

$$Y(s) = \frac{25(s + 2)}{s(s^2 + 6s + 25)}$$

- Descomposición en Fracciones Parciales:

Proponemos:

$$\frac{25(s + 2)}{s(s^2 + 6s + 25)} = \frac{A}{s} + \frac{Bs + C}{s^2 + 6s + 25}$$

Multiplicamos por el denominador común:

$$25(s + 2) = A(s^2 + 6s + 25) + (Bs + C)s$$

Desarrollamos:

$$25s + 50 = A s^2 + 6A s + 25A + B s^2 + C s
= (A + B)s^2 + (6A + C)s + 25A$$

- Sistema de Ecuaciones:

$$
\begin{cases}
A + B = 0 \\
6A + C = 25 \\
25A = 50
\end{cases}
\quad \Rightarrow \quad
A = 2,\; B = -2,\; C = 13
$$

Entonces:

$$Y(s) = \frac{2}{s} + \frac{-2s + 13}{s^2 + 6s + 25}$$

- Completando Cuadrados en el Denominador:

$$s^2 + 6s + 25 = (s + 3)^2 + 16$$

Reescribimos el numerador:

$$-2s + 13 = -2(s + 3) + 19$$

Así:

$$\frac{-2s + 13}{(s + 3)^2 + 16} = \frac{-2(s + 3)}{(s + 3)^2 + 4^2} + \frac{19}{(s + 3)^2 + 4^2}$$

- Transformadas Inversas de Laplace:

Usamos las siguientes transformadas:

- $$\mathcal{L}^{-1}{\frac{1}{s}} = 1$$
- $$\mathcal{L}^{-1}{\frac{s + 3}{(s + 3)^2 + 4^2}} = e^{-3t} \cos(4t)$$
- $$\mathcal{L}^{-1}{\frac{4}{(s + 3)^2 + 4^2}\} = e^{-3t} \sin(4t)$$

Por lo tanto:

$$y(t) = 2 - 2e^{-3t} \cos(4t) + \frac{19}{4} e^{-3t} \sin(4t)$$

- Respuesta Temporal Final:

$$
\boxed{
y(t) = 2 - 2e^{-3t} \cos(4t) + \frac{19}{4} e^{-3t} \sin(4t)
}
$$

Esta expresión describe la *respuesta al escalón unitario* del sistema con un cero adicional en $ s = -2 $.
