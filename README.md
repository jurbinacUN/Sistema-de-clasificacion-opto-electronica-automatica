# Sistema-de-clasificacion-opto-electronica-automatica
## Introducción:
Este proyecto consiste en el diseño y prototipado de un sistema de identificación y clasificación opto-electrónica de manzanas, por medio de sensores TCS3200; donde las manzanas son transportadas a través de una cinta transportadora. El sistema emula un proceso de control de calidad industrial para la selección de frutas.

### Objetivo:
El objetivo principal es discriminar o clasificar entre "producto válido" (manzanas) y "objetos extraños/desechos". El sistema opera bajo la siguiente lógica:

**Manzana verde:** Aceptada (la cinta continúa).

**Manzana roja:** Aceptada (la cinta continúa).

**Cualquier otro color:** Rechazada (un servomotor la saca de la cinta).

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
