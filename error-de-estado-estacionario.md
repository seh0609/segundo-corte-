
Dada la función de transferencia:

$$G(s) = \frac{48}{s^2 + 8s + 48}$$

Queremos:

- Llevarla a su forma canónica.
- Agregar un cero en $ s = -4 $ y analizar cómo afecta la respuesta al escalón unitario.

Forma Canónica del Sistema
- Forma estándar de segundo orden:

$$G(s) = \frac{K \omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$$

- Identificar coeficientes

De la función original:

- $$a_1 = 8$$
- $$a_0 = 48$$
- $$b_0 = 48$$

- Calcular $$\omega_n$$

$$\omega_n = \sqrt{a_0} = \sqrt{48} \approx 6.928$$

- Calcular $$\zeta$$

$$2\zeta\omega_n = a_1 = 8 \quad \Rightarrow \quad \zeta = \frac{8}{2 \cdot 6.928} = \frac{8}{13.856} \approx 0.577$$

Calcular $$K$$

$$K = \frac{b_0}{\omega_n^2} = \frac{48}{48} = 1$$

Función en forma canónica:

$$G(s) = \frac{1 \cdot 48}{s^2 + 2(0.577)(6.928)s + (6.928)^2} = \frac{48}{s^2 + 8s + 48}$$

- Efecto de un Cero en $$s = -4$$

Agregamos el cero multiplicando por $$(s + 4)$$:

$$G_z(s) = \frac{48(s + 4)}{s^2 + 8s + 48}$$

Para encontrar la *respuesta al escalón unitario*, dividimos entre $$s$$:

$$Y(s) = \frac{48(s + 4)}{s(s^2 + 8s + 48)}$$

- Descomposición en fracciones parciales
Proponemos:

$$\frac{48(s + 4)}{s(s^2 + 8s + 48)} = \frac{A}{s} + \frac{Bs + C}{s^2 + 8s + 48}$$

Multiplicamos ambos lados por el denominador común:

$$48(s + 4) = A(s^2 + 8s + 48) + (Bs + C)s$$

Desarrollamos:

$$48s + 192 = A s^2 + 8A s + 48A + B s^2 + C s
= (A + B)s^2 + (8A + C)s + 48A$$

- Sistema de ecuaciones:

$$
\begin{cases}
A + B = 0 \\
8A + C = 48 \\
48A = 192
\end{cases}
\quad \Rightarrow \quad
A = 4,\; B = -4,\; C = 16
$$

Entonces:

$$Y(s) = \frac{4}{s} + \frac{-4s + 16}{s^2 + 8s + 48}$$

- Completar cuadrados en el denominador

$$s^2 + 8s + 48 = (s + 4)^2 + 32$$

Reescribimos el numerador:

$$-4s + 16 = -4(s + 4)$$

Por lo tanto:

$$\frac{-4s + 16}{(s + 4)^2 + 32} = \frac{-4(s + 4)}{(s + 4)^2 + (\sqrt{32})^2}$$

Donde $$\omega = \sqrt{32} \approx 5.657$$

- Transformada inversa de Laplace

Usamos las siguientes transformadas:

- $$\mathcal{L}^{-1}\{\frac{1}{s}\} = 1$$
  
- $$\mathcal{L}^{-1}{\frac{s + a}{(s + a)^2 + \omega^2}} = e^{-at} \cos(\omega t)$$

Aplicamos:

$$y(t) = 4 - 4e^{-4t} \cos(5.657t)$$

- Respuesta Temporal Final con el Cero:

$$
\boxed{
y(t) = 4 - 4e^{-4t} \cos(5.657t)
}
$$

Esta expresión describe la *respuesta al escalón unitario* del sistema con un cero adicional en $$s = -4$$.
