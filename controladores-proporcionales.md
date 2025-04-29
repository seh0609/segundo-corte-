# 📘 Diseño de controladores proporcionales 
El control proporcional es una estrategia de control que ajusta la salida del controlador de forma lineal con respecto al error de control. Este error se define como la diferencia entre la variable controlada y su valor de referencia. El controlador calcula una señal de control que es directamente proporcional a este error: cuanto mayor es la desviación, más fuerte es la acción correctiva aplicada al sistema. El objetivo principal es minimizar el error y llevar la variable controlada lo más cerca posible del punto de ajuste deseado.

## 1. Que compone un sistema de control 

- **Señal (v o i) de Entrada (Referencia):** Es la señal que representa el valor deseado o setpoint de la variable que queremos controlar. En el diagrama, entra al Comparador.
- **Comparador:** Este bloque resta la Señal (v o i) del Sensor (que representa la salida real del sistema) de la Señal (v o i) de Entrada (Referencia). La salida del comparador es la señal de Error.
- **Error:** Es la diferencia entre el valor deseado y el valor real de la variable controlada. Esta señal indica cuánto se desvía el sistema de su objetivo. El Error es la entrada al Controlador.
- **Controlador:** Este bloque procesa la señal de Error de acuerdo con una ley de control (por ejemplo, proporcional, integral, derivativa). Su objetivo es generar una Acción de Control que corrija el error y lleve la salida del sistema al valor deseado.
- **Acción de Control:** Es la señal generada por el Controlador que se aplica al Actuador. Esta señal manipula la entrada a la Planta para influir en su comportamiento.
- **Actuador:** Este componente recibe la Acción de Control y la convierte en una Entrada física a la Planta. Por ejemplo, podría ser la posición de una válvula, el voltaje aplicado a un motor, o la potencia suministrada a un calentador.
- **Planta (Sistema/Proceso):** Es el sistema que queremos controlar. Recibe la Entrada del Actuador y produce una Salida, que es la variable que nos interesa regular.
- **Salida:** Es la variable real que está produciendo la Planta. Esta es la variable que el Sensor mide.
- **Sensor:** Este dispositivo mide la Salida de la Planta y la convierte en una Señal (v o i) del Sensor que puede ser comparada con la Señal (v o i) de Entrada (Referencia), cerrando así el lazo de control (retroalimentación).

![image](https://github.com/user-attachments/assets/b71c550d-450c-4dff-895c-ef653e9c22f5)\
Figura 1. Imagen de un lazo cerrado

### 1.1. Efectos la tener un lazo cerrado 

- La configuración en lazo cerrado, a diferencia del lazo abierto, ofrece la capacidad de manipular dinámicas de respuesta mediante el diseño de controladores, además de permitir el ajuste del estado estable a través de la referencia y la mejora general del desempeño, aunque la inclusión de sensores para la retroalimentación introduce complejidad adicional en el sistema.

#### 1.1.1. Funcion de Trasferencia de un lazo cerrado

Dado:
- \( G = 2 \)
- \( C = 5 \)

La función de transferencia es:

$$\text{FT}(s) = \frac{GC}{1 + GC}$$

Sustituyendo:

$$\text{FT}(s) = \frac{2 \cdot 5}{1 + 2 \cdot 5} = \frac{10}{11}$$

### 1.2. Controlador de accion proporional

- El control proporcional ajusta la acción de control multiplicando el error por una ganancia constante, cuyo valor se determina mediante diseño para alcanzar el comportamiento deseado del sistema.

![image](https://github.com/user-attachments/assets/20eef776-18a1-4b6a-a039-60821a7ed592)\
Figura 2. Controlador proporcional
