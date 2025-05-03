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


## 10. Conclusion
Los sistemas de segundo orden son esenciales para representar dinámicas complejas en procesos industriales, ya que permiten predecir y controlar su comportamiento con mayor precisión. Su respuesta está influenciada por parámetros como la frecuencia natural y el factor de amortiguamiento, que determinan si el sistema oscila, se estabiliza rápidamente o responde de forma lenta. A diferencia de los sistemas de primer orden, pueden presentar distintos tipos de amortiguamiento ante una entrada escalón y un error constante ante una entrada rampa. Dominar estos conceptos es fundamental para diseñar sistemas de control estables y eficientes.



## 11. Referencias

https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/
https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/
