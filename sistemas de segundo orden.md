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
Usamos estos terminos\
$$\left( a_1 = 2ζω_n\right)  \left( a_0 =  ω_{n}^2\right) \left( b_0 = K × ω_{n}^2\right)$$
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.




### 2.1. Ecuaciones fundamentales 

![image](https://github.com/user-attachments/assets/1280c34f-177e-4cb0-a0ad-cb0737c62ae5)

fIGURA 1.ECUACION DE LA PLACE 


### 3.2. Ejemplo
💡**Ejemplo 1:** 

•Planta: Transmisión movimiento
•Entrada: Torque
•Sensor: Potenciómetro
•Salida: Distancia
•Actuador Motor

## 3.3. Ejercicios
📚 **Ejercicio de tanque**

![image](https://github.com/user-attachments/assets/51ff01c0-f0a2-48ad-9e85-77a2123ae0e6)

Figura 4. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/e9f392e7-5a43-44e1-a5bf-f94ab7526c11)

Figura 5. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/067b00f1-8580-4533-8766-d7f705f3fb97)

Figura 6. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/5ca84043-3101-4393-9d86-9e07db990488)

Figura 7. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/d8084f4d-daa4-4542-98d3-27d98a56f0b9)

Figura 8. Funcion de tranferencia,  sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

cambio 

Transformada de la PLACE
Nos ayuda en lo visto en clase a definir que partir de una integral que transforma ciertas funciones, simplifica el proceso de derivación al convertirlo en un producto. De esta manera, las ecuaciones diferenciales se convierten en ecuaciones algebraicas que muchas veces son más fáciles de resolver.

### 2.1. Ecuaciones fundamentales 

>🔑 *Entrada --- REGLAS --- Salida *

### 3.2. Ejemplo
💡**Ejemplo 1:** 

•Planta: Transmisión movimiento
•Entrada: Torque
•Sensor: Potenciómetro
•Salida: Distancia
•Actuador Motor

## 3.3. Ejercicios
📚 **Ejercicio de tanque**

![image](https://github.com/user-attachments/assets/51ff01c0-f0a2-48ad-9e85-77a2123ae0e6)

Figura 4. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/e9f392e7-5a43-44e1-a5bf-f94ab7526c11)

Figura 5. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/067b00f1-8580-4533-8766-d7f705f3fb97)

Figura 6. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/5ca84043-3101-4393-9d86-9e07db990488)

Figura 7. Ejercicio 1 sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

![image](https://github.com/user-attachments/assets/d8084f4d-daa4-4542-98d3-27d98a56f0b9)

Figura 8. Funcion de tranferencia,  sacado de https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/

## 10. Conclusion
los sistemas de primer orden nos sirven en la práctica para modelar y predecir el comportamiento dinámico de diversos procesos, permitiendo un mejor control y optimización en aplicaciones industriales. Su respuesta exponencial está determinada por parámetros temporales que definen su evolución en el tiempo, diferenciando dos estados clave: el transitorio y el estacionario. Mientras que la respuesta a un escalón está acotada por un valor constante, la respuesta a una rampa presenta un crecimiento con pendiente constante. Estos conceptos son fundamentales en el análisis y diseño de sistemas de control, garantizando estabilidad y eficiencia en su funcionamiento.

## 11. Referencias
[
https://dademuchconnection.wordpress.com/2018/06/12/dinamica-de-un-sistema-de-nivel-de-liquidos/](https://matefacil.net/t-de-laplace/#:~:text=%C2%BFQu%C3%A9%20es%20la%20Transformada%20de,al%20convertirlo%20en%20un%20producto.)

https://controlautomaticoeducacion.com/analisis-de-sistemas/tanque-nivel/
