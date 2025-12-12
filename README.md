# Sistema-de-clasificacion-opto-electronica-automatica
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

### RTL

### Prototipo físico
