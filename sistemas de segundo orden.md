# Sistemas De Segundo Orden
Tenemos que los sistemas de segundo orden  son todos aquellos sistemas que tienen dos polos y están representados típicamente por ecuaciones diferenciales ordinarias de segundo orden. 

La estructura de un sistema de segundo orden se ve asi:

$$y''(t)+a_1 y'(t)+a_0 y(t)=b_0u(t)$$

Cuando hayamos la funcion de transferencia tenemos:

aplicamos la transformada de LaPlace


$$s²Y(s)+a_1sY(s)+a_0 Y(s)=b_0U(s)$$

Despues de esto despejamos la salida/entrada 

$$\frac{Y(s)}{U(s)}=\frac{b_0}{s²+a_1s+a_0}$$

Despues de esto para obetener la forma canonica\
**Usamos estos terminos**\
$$\left( a_1 = 2ζω_n\right)  \left( a_0 =  ω_{n}^2\right) \left( b_0 = K × ω_{n}^2\right)$$

Obtenemos su forma canónica

$$\frac{Y(s)}{U(s)}=\frac{K*ω_{n}^2}{s²+2ζω_ns+ω_{n}^2}$$


>🔑 *K:* Ganancia estática\
>🔑 *ω_n:* Frecuencia natural del sistema\
>🔑 *ζ:* Factor de amortiguamiento del sistema

### 1. Respuesta de un Sistema de Segundo orden para un escalón

**Despues de obtener nuestra ecuacion de forma canonica**

$$\frac{Y(s)}{U(s)}=\frac{K*ω_{n}^2}{s²+2ζω_ns+ω_{n}^2}$$

**Factorizando queda**

$$G(s) = \frac{K \cdot \omega_n^2}{\left( s + \zeta \omega_n + \omega_n \sqrt{\zeta^2 - 1} \right) \left( s + \zeta \omega_n - \omega_n \sqrt{\zeta^2 - 1} \right)}$$

**Despues se aplica el escalon**

$$Y(s) = \frac{K \cdot \omega_n^2 \cdot A}{\left( s + \zeta \omega_n + \omega_n \sqrt{\zeta^2 - 1} \right) \left( s + \zeta \omega_n - \omega_n \sqrt{\zeta^2 - 1} \right) s}$$

### 1.1. Factor de Amortiguamiento 
Es una medida que indica la capacidad de un amplificador para controlar el movimiento de un altavoz, especialmente en frecuencias bajas

-Si $$ζ>1$$\
$$\mathcal{L}^{-1}\{Y(s)\} = K \cdot A \cdot \left( 1 - e^{-\left( \zeta - \sqrt{\zeta^2 - 1} \right) \omega_n t} \right)$$

![image](https://github.com/user-attachments/assets/d914bb61-ffe0-4f15-bf02-00b997d609c6)\
Figura 1. Grafica de una recta sobre amortiguada://https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/\

-Si $$ζ<1$$\
$$\mathcal{L}^{-1}\{Y(s)\} = K \cdot A \cdot \left( 1 - e^{-\zeta \omega_n t} \left( \cos\left( t \omega_n \sqrt{\zeta^2 - 1} \right) + \frac{\zeta}{\sqrt{\zeta^2 - 1}} \sin\left( t \omega_n \sqrt{\zeta^2 - 1} \right) \right) \right)$$

![image](https://github.com/user-attachments/assets/4403c609-9f26-43de-9352-74e126a62c66)\
Figura 2. Grafica de una recta sobre sobre amortiguada://https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/\

-Si $$ζ=1$$\
$$\mathcal{L}^{-1}\{Y(s)\} = K \cdot A \cdot \left( 1 - e^{-\omega_n t} (1 + \omega_n t) \right)$$

![image](https://github.com/user-attachments/assets/e734bd25-560f-4aa5-a817-52fc69af6a0e)\
Figura 3. Grafica de una recta sobre criticamente amortiguado://https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/\

### 1.2. Ubicación de los polos 

-Si $$ζ<1$$\
![image](https://github.com/user-attachments/assets/e99d9ac4-d1bb-4394-aa62-ae6a952520c1)

Figura 4. Ubicacion de polos par un sistema sub amortiguado://https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/

-Si $$ζ=1$$\
![image](https://github.com/user-attachments/assets/7c6ab68f-a1ad-47ea-af99-80150d274f8f)

Figura 5. Ubicacion de polos par un sistema criticamente amortiguado://https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/

-Si $$ζ>1$$\
![image](https://github.com/user-attachments/assets/44ffe4b2-9a7a-4e45-aceb-824e018cb854)

Figura 6. Ubicacion de polos par un sistema sobre amortiguado://https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/

### 1.3. Efectos De Los Zeros

- Este efecto de presenta directamente en los estados transitorios de un sistema
- El estado estacionario no tiene afectacion por esto

💡**Ejemplo 1:**

$$
Y_1(s) = \frac{4}{s(s + 8)} \quad \text{y} \quad Y_2(s) = \frac{s + 4}{s(s + 8)}
$$

- Aplicando fracciones parciales:

$$
\gamma_1 = 0.5(1 - e^{-8t}) \quad\quad \gamma_2 = 0.5 + 0.5e^{-8t}
$$

![Captura de pantalla 2025-04-29 105000](https://github.com/user-attachments/assets/046f72ad-6250-4c13-8250-6f43169e494a)

Figura 7: Grafica de el comportamiento de los zeros

## 2. Ejercicios
📚 **Ejercicio 1:**

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

Esta expresión describe la *respuesta al escalón unitario* del sistema con un cero adicional 
$$s = -2$$.

📚 **Ejercicio 2:**

## 10. Conclusion
Los sistemas de segundo orden son fundamentales en la práctica para modelar y predecir el comportamiento dinámico de procesos más complejos, posibilitando un control y optimización avanzados en aplicaciones industriales. Su respuesta, caracterizada por posibles oscilaciones y sobreimpulsos, está determinada por parámetros como la frecuencia natural no amortiguada y el factor de amortiguamiento, que definen su evolución temporal y la transición entre los estados transitorio y estacionario. A diferencia de los sistemas de primer orden, su respuesta a un escalón puede ser sobreamortiguada, críticamente amortiguada o subamortiguada, alcanzando un valor constante. La respuesta a una rampa, en cambio, exhibe un error de estado estacionario constante. Comprender estos conceptos es crucial en el análisis y diseño de sistemas de control que requieren una respuesta dinámica específica y un comportamiento estable y eficiente.

## 11. Referencias

https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/
https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/
