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
<div align="center">
  <img src="![Captura de pantalla 2025-04-29 105000](https://github.com/user-attachments/assets/3bbdf571-3a59-4393-9310-0ab302ef2e91)


Figura 7: Graica de el comportamiento de los zeros

## 10. Conclusion
Los sistemas de segundo orden son fundamentales en la práctica para modelar y predecir el comportamiento dinámico de procesos más complejos, posibilitando un control y optimización avanzados en aplicaciones industriales. Su respuesta, caracterizada por posibles oscilaciones y sobreimpulsos, está determinada por parámetros como la frecuencia natural no amortiguada y el factor de amortiguamiento, que definen su evolución temporal y la transición entre los estados transitorio y estacionario. A diferencia de los sistemas de primer orden, su respuesta a un escalón puede ser sobreamortiguada, críticamente amortiguada o subamortiguada, alcanzando un valor constante. La respuesta a una rampa, en cambio, exhibe un error de estado estacionario constante. Comprender estos conceptos es crucial en el análisis y diseño de sistemas de control que requieren una respuesta dinámica específica y un comportamiento estable y eficiente.

## 11. Referencias

https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/
https://analisisdecircuitos1.wordpress.com/parte-2-estado-transitorio-cap-61-a-70/capitulo-61-circuito-rlc-en-paralelo-sin-fuentes-criticamente-amortiguado/
