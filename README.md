# Sistema-de-clasificacion-opto-electronica-automatica
Diseño e implementación de un sistema optoelectrónico automático para identificación y clasificación de manzanas basado en detección de colory control electromecánico.

## Introducción:
La automatización de procesos agroindustriales es un requerimiento creciente para garantizar calidad, reducir tiempos de producción y minimizar el manejo manual de alimentos. Este proyecto presenta el desarrollo de un sistema optoelectrónico automático capaz de identificar manzanas según su color —clasificando entre manzanas rojas, verdes y amarillas— mientras se desplazan por una cinta transportadora.

Para lograrlo, se integraron tecnologías de sensado óptico, procesamiento digital con FPGA y accionamiento mecánico mediante servomotores, permitiendo que cada manzana sea clasificada en tiempo real y desviada hacia la bandeja correspondiente.

## Objetivo:
###Objetivo general

Desarrollar un sistema automático que detecte el color de manzanas transportadas en una banda mecánica y realice su clasificación mediante actuadores controlados digitalmente.

###Objetivos específicos

Implementar un módulo digital encargado de medir las señales ópticas provenientes de un sensor de color.

Diseñar la lógica de decisión para determinar el color predominante de cada manzana.

Controlar servomotores a través de señales PWM para desviar las manzanas a diferentes compartimientos.

Integrar el sensado, procesamiento digital y actuación mecánica en un prototipo funcional.

Evaluar el desempeño bajo condiciones reales de iluminación y movimiento en la cinta transportadora.

## Hardware y materiales:
La lista de componentes electrónicos y materiales utilizados para el montaje físico:
### Electrónica
* Sensores TCS3200.

* Sensor infrarrojo.

* Servomotores.

* Motores paso a paso.

* FPGA.
### Construcción física
* Lámina de MDF.

* Tubos de PVC.

* Neumático.
## Funcionamiento y lógica:
El sistema funciona mediante un bucle de control continuo:

1. **Arranque:** Se inicia el funcionamiento de los motores que mueven la cinta transportadora, además se inicia la detección de los sensores y el pocesamiento de la FPGA.
   
2. **Detección:** El objeto pasa frente al sensor infrarrojo que detecta la presencia de un objeto, luego pasa frente al sensor de color que captura los datos de la frecuencia de la luz capturada.

3. **Procesamiento:** La FPGA compara las lecturas con rangos precalibrados.

4. **Funcionamiento y lógica:**
