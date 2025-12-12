# Sistema de clasificacion opto electronica automatica
Diseño e implementación de un sistema optoelectrónico automático para identificación y clasificación de manzanas basado en detección de colory control electromecánico.

## Introducción:
La automatización de procesos en la industria alimenticia es un requerimiento creciente para garantizar calidad, reducir tiempos de producción y minimizar el manejo manual de alimentos. Este proyecto presenta el desarrollo de un sistema optoelectrónico automático capaz de identificar manzanas según su color —clasificando entre manzanas rojas y verdes mientras se desplazan por una cinta transportadora.

Para lograrlo, se integraron tecnologías de sensado óptico, procesamiento digital con FPGA y accionamiento mecánico mediante servomotores, permitiendo que cada manzana sea clasificada en tiempo real y desviada si no es una manzana.

## Objetivo:
### Objetivo general

Desarrollar un sistema automático que detecte el color de manzanas transportadas en una banda mecánica y realice su clasificación mediante actuadores controlados digitalmente.

### Objetivos específicos

1. Implementar un módulo digital encargado de medir las señales ópticas provenientes de un sensor de color.

2. Diseñar la lógica de decisión para determinar el color predominante de cada manzana.

3. Controlar servomotores a través de señales PWM para desviar las manzanas.

4. Integrar el sensado, procesamiento digital y actuación mecánica en un prototipo funcional.

5. Evaluar el desempeño bajo condiciones reales de iluminación y movimiento en la cinta transportadora.

## Metodología y Desarrollo
### Descripción general del sistema

El sistema está compuesto por cuatro bloques principales:

1. Cinta transportadora: mueve las manzanas a una velocidad constante hacia el área de detección.

2. Módulo optoelectrónico: utiliza un sensor de color programable que mide la frecuencia de la luz reflejada.

3. Unidad de Procesamiento Digital (FPGA): ejecuta algoritmos de muestreo, filtrado, comparación y clasificación cromática.

4. Sistema de desviación con servomotores: cambia su posición según la categoría asignada, dirigiendo la fruta hacia la bandeja correcta.

### Sensado óptico

Se empleó un sensor óptico de color basado en fotodiodos con filtros selectivos que convierte la luz reflejada por la superficie de la manzana en una señal digital proporcional.
Las reflexiones varían según el color dominante:

* Rojo.

* Verde.

* Amarillo.

Para asegurar precisión se incluyó:

* carcasa opaca para reducir interferencia ambiental,

* ventana óptica que garantiza la distancia fija entre sensor y fruta.

### Procesamiento digital en FPGA

El procesamiento se implementó en lenguaje Verilog y consiste en:

a) Muestreo del sensor

El FPGA mide la frecuencia o nivel digital asociado al sensorde  color.
Estas mediciones se normalizan para evitar saturaciones.

b) Algoritmo de clasificación

Se utilizan comparadores y umbrales definidos experimentalmente:

* Si R o V → Deja continuar

* Si Otro color → Desviar

Un bloque de temporización asegura que solo se evalúe el color cuando la fruta está correctamente alineada con el sensor.

### Control de servomotores

Para cada categoría existe una compuerta mecánica accionada por un servomotor.
El FPGA genera señales PWM con:

* período de 20 ms

* ciclos de trabajo entre 5–10% para posicionar el eje

### Integración mecánica

La estructura final incluye:

* una cinta transportadora continua,

* un área de sensado aislada ópticamente,

* un sistema de compuertas móviles con servomotores,


## Diseño del prototipo

### Diagrama de flujo
<img width="571" height="760" alt="image" src="https://github.com/user-attachments/assets/847bb76f-9e5a-4bb7-9da4-ed36a4252dea" />


### RTL
#### top.v
<img width="1042" height="1548" alt="image" src="https://github.com/user-attachments/assets/7bcc79c7-bfa7-4080-a7b3-68421557855e" />

#### Sensor de color
<img width="1084" height="584" alt="image" src="https://github.com/user-attachments/assets/b4c57d31-af63-4c7a-92b9-63093ffb0829" />

#### Servomotores
<img width="642" height="405" alt="image" src="https://github.com/user-attachments/assets/9a978476-7880-4a1d-b6ca-90e84ef7a549" />

#### Motores paso a paso
<img width="616" height="421" alt="image" src="https://github.com/user-attachments/assets/92217755-9c1d-46d3-86cf-fe1edf3983a5" />


### Prototipo físico
La construcción del prototipo se realizó integrando elementos mecánicos, electrónicos y ópticos cuidadosamente alineados. A continuación se describen los componentes y el proceso de ensamblaje.

1. Estructura Mecánica

* Base de MDF para sostener la electrónica y la cinta transportadora.

* Cinta transportadora con motor paso a paso para control de velocidad.

* Guías laterales para mantener estable la fruta.

* Soporte del sensor óptico, ajustado al tamaño de la manzana.

* Carcasa óptica: estructura cerrada donde se ubica el sensor de color y el sensor infrarrojo, diseñada para bloquear luz externa.

2. Módulo Optoelectrónico

Incluye:

* Sensor de color fijado a una placa rígida.

* Conectores aislados para reducir ruido eléctrico.

El módulo se instala justo por encima de la banda transportadora, alineado con el centro de la manzana.

3. Unidad Electrónica (FPGA y Controladores)

Ubicada al lado de laestructura principal, incluye:

* FPGA encargada del procesamiento digital.

* Pines dedicados para señales PWM hacia los servomotores.

* Módulo de potencia para los motores de la cinta transportadora.

La FPGA se ubica lateralmente en la estructura para fácil acceso.

4. Sistema de Desviación Mecánica

Cada categoría de color posee una compuerta móvil accionada por un servomotor.
Construcción:

* Eje de madera ligera unidos a los servos.

El diseño asegura que el cambio de posición del servo sea rápido y preciso para que la manzana no pase sin clasificación.

5. Integración Final

* Se instala la cinta transportadora en el centro de la base.

* Sobre ella se fija la carcasa óptica con el sensor de color y el sensor infrarrojo.

* Los servomotores se posicionan a la salida de la cinta.

* Se cablea la FPGA al sensor y a los servos.

* Se realizan pruebas estáticas para calibrar:

* nivel de iluminación,

* distancia óptica,

* velocidad de la cinta,

* umbrales de color.

Finalmente se ejecutan pruebas completas con manzanas.

El prototipo resultante permite la clasificación automática continua, siendo un sistema funcional, robusto y replicable en entornos de laboratorio o premisas industriales de baja escala.

<img width="1223" height="687" alt="image" src="https://github.com/user-attachments/assets/10fcc421-1a95-42da-885c-928c30749ca0" />
