# Estabilidad 
Es la capacidad de un sistema para mantener su comportamiento deseado ante perturbaciones o cambios de entrada. Es decir, que su salida no es ±∞ sino un valor concreto. También podríamos definir a un sistema estable que evoluciona de un modo similar a la variable de entrada.


![image](https://github.com/user-attachments/assets/937ea8bc-eda9-4848-867e-c694bbac95e1)\
Figura 1. Como se ve un sistema estable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

![image](https://github.com/user-attachments/assets/227176bd-8b48-4cdb-a208-af1a332fc0ef)\
Figura 2. Como se ve un sistema inestable: https://dademuchconnection.wordpress.com/2018/03/15/estabilidad-de-un-sistema-de-control/

## 1. Toerema de valor final 

Para poder saber si nuestro sistema es estable necesitamos tener en cuenta el teorema de valor final, este teorema se nos hace muy útil  ya que este nos va a permitir encontrar el límite de una función en infinito, para esto tenemos que tener en dominio de la transformada de Laplace, para esto tenemos estos términos:

$$\lim_{q \to \infty} f(q) = \lim_{s \to 0} sF(s)$$

💡**Ejemplo 1:**
La función de transferencia del sistema es:

$$G (s) = \frac{Y(s)}{U(s)} = \frac{4}{5s + 1}$$

Entonces, la salida del sistema en el dominio de Laplace es:

$$Y(s) = \frac{4 \cdot U(s)}{5s + 1}$$

Cuando hayamos la funcion de transferencia tenemos:

aplicamos la transformada de LaPlace


$$s²Y(s)+a_1sY(s)+a_0 Y(s)=b_0U(s)$$

Despues de esto despejamos la salida/entrada 
