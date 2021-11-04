# INTERFAZ DEL SENSOR DE PRESIÓN ARTERIAL CON RASPBERRY PI 3B+

*El que solo sabe de medicina, ni medicina sabe*

![Josep_Letamendi_Manjarres](https://user-images.githubusercontent.com/93683501/140416561-b107f6c8-59f5-48f6-8da0-9a35b4dabc20.jpg)
> José de Letamendi y Manjarrés.

## Introducción
Medición de la presión arterial y sistema de envío de informes detallados por correo electónico usando Raspberry Pi.

![unknown](https://user-images.githubusercontent.com/93683501/140417408-602948c1-c12d-4b2e-aeac-415a88a34094.png)
>Medidor de tensión arterial.

## RECURSOS:
      
* COMPONENTES DE HARDWARE:

  * Raspberry Pi 3 Modelo B.
  [Comprar.](https://www.amazon.es/Raspberry-Pi-Modelo-Quad-Core-Cortex-A53/dp/B01CD5VC92)
  * Regulador lineal (7805).
  [Comprar.](https://www.electronicaplugandplay.com/circuitos-integrados/product/257-l7805cv?search=regulador%207805)
  * Condensador electrolítico 470 uF.
  [Comprar.](https://www.electronicaplugandplay.com/componentes-pasivos/product/209-condensador-smd-electrolitico-470uf-16v?search=condensador%20470)
  * LED de 5 mm rojo.
  [Comprar.](https://www.electronicaplugandplay.com/optoelectronica/product/132-led-de-chorro-rojo-5mm?search=led%205%20mm%20rojo)
  * Puente rectificador.
  [Comprar.](https://www.electronicaplugandplay.com/componentes-discretos/product/881-rectifier-bridge-2a-600v?search=puente%20rectificador)
  * Sensor de presión arterial.
  [Comprar.](https://www.electronicaplugandplay.com/sensores-y-transductores/biometricos/product/789-max30102)
  * Resistencia de orificio pasante 470 ohmios.
  [Comprar.](https://www.electronicaplugandplay.com/componentes-pasivos/resistencias/resistencias-de-carbon/product/80-resistencia-470-1-4-watt?search=resistencia%20470)
  * DC POWER JACK 2.1MM.
  [Comprar.](https://www.taydaelectronics.com/dc-power-jack-2-1mm-barrel-type-pcb-mount.html)
  * Adaptador cc de 5 voltios y 2 amperios para Raspberry pi.
  [Comprar.](https://www.electronicaplugandplay.com/baterias-y-fuentes-de-poder/adaptadores-de-voltaje/product/870-12v-1a-adapter-plug)

* ALICACIONES DE SOFTWARE Y SERVICIOS EN LÍNEA:

  * Raspberry Pi Raspbian 
  [Link de descarga](https://www.raspberrypi.com/software/)

* HERRAMIENTAS MANUALES Y MÁQUINAS DE FABRICACIÓN:

  * Soldador (genérico).
  * Alambre de soldadura sin plomo.
  * Fuente de soldadura, soldadura.
  
      [Comprar kit de soldadura.](https://www.amazon.com/-/es/herramienta-temperatura-interruptor-desoldadura-electricista/dp/B085Y328GK/ref=sr_1_1?__mk_es_US=ÅMÅŽÕÑ&crid=2XVSNA1MB3VL9&keywords=lead+free+welding+wire&qid=1636060400&sprefix=alambre+de+soldadura+sin+plomo%2Caps%2C136&sr=8-1)

## Conceptos básicos sobre la presión arterial.

La presión arterial es la presión de la sangre en las arterias cuando el corazón bombea sangre por todo el cuerpo. Cuando su corazón late, se contrae y empuja la sangre a través de sus arterias hacia otras partes de su cuerpo. Esta fuerza crea presión sobre las arterias. La presión arterial se registra como dos números: presión arterial sistólica (cuando el corazón late) y presión arterial diastólica (cuando el corazón se relaja entre latidos). La unidad que lo mide se llama esfigmomanómetro.

Controlar su presión arterial en casa es importante para muchas personas, especialmente si tiene presión arterial alta. La presión arterial no permanecerá igual todo el tiempo. Cambiará para satisfacer las necesidades de su cuerpo. Se ve afectado por muchos factores, como la posición del cuerpo, la respiración o el estado emocional, el ejercicio y el sueño. Es mejor medir la presión arterial mientras se relaja, está sentado o acostado.

### **Clasificación de la presión arterial para adultos (mayores de 18 años)**

**Chart** | **Systolic (mm Hg)** | **Diastolic (mm Hg)**
------------ | ------------- | -------------
**Hypotension** | < 90 | < 60
**Desired** | 90 - 119 | 60 - 79
**Prehypertension** | 120 - 139 | 80 -89
**Stage 1 Hypertension** | 140 - 159 | 90 - 99
**Stage 2 Hypertension** | 160 - 179 | 100 - 109
**Hypertensive Crisis** | ≥ 180 | ≥ 110

> Clasificación de la presión arterial.

## Diagrama de bloques del sistema

![bd_1B1jX2d9DL](https://user-images.githubusercontent.com/93683501/140423712-c85ec779-9760-4c18-ab5f-b2026c1db687.jpg)
> Diagrama de bloques

## Sensor de presión arterial

![Sensor](https://user-images.githubusercontent.com/93683501/140423881-e97d421e-f644-428f-9892-3d19deedf154.jpg)
> Sensor de presión arterial de muñeca Bp.

### Caracteríasticas:

1. Compresión y descompresión automática.
1. Fácil de operar, cuenta con un botón de conmutación para comenzar a medir.
1. 60 grupos de almacenamiento de medidas de memoria.
1. Puede leer una o todas las medidas.
1. 3 minutos el dispositivo de ahorro de energía automático.
1. Depuración inteligente de dispositivos, potencia automática para detectar.
1. Pruebas locales para la circunferencia de la muñeca como 135-195 mm.
1. Pantalla de visualización de cristal líquido digital a gran escala, pantalla fácil de leer.
1. Totalmente automático, precisión clínica, alta precisión.
1. Alimentación externa + 5 V CC.
1. Datos de salida en serie para procesamiento o visualización de circuitos externos.

### Especificaciones.

1. Voltaje de funcionamiento: + 5 V, 200 mA regulado.
1. Formato de salida: datos en serie a una velocidad de 9600 baudios (datos de 8 bits, sin paridad, 1 bit de parada). Emite tres parámetros en ASCII.
1. La longitud del cable de la unidad sensora es de 2 metros.
1. TX-OUT = Salida de transmisión. Salida de datos en serie de nivel lógico de 3 V, generalmente conectado al pin RXD de microcontroladores / RS232 / USB-UART.
1. Más 5V = Entrada de suministro regulada de 5V.
1. GND = Tierra común de la placa.
1. Estado = Indica que el sensor de presión arterial está activo o no.

### Funcionamiento

Este proyecto utiliza Raspberry Pi 3 B+ para recibir los datos del sensor de presión arterial y procesarlos. El sensor de presión arterial proporciona datos a la Raspberry Pi a través de la comunicación UART. La Raspberry Pi recibe los datos del sensor a través del canal UART, y la velocidad en baudios del sensor se fija en 9600, por lo que debemos establecer la velocidad en baudios de la Raspberry Pi en 9600. Lo que se lee es un valor de 8 bits en formato ASCII de dígitos fijos, que va de 000 a 255. A continuación se muestra una lectura típica, donde los tres valores están separados por comas y espacios.

* Sistólica.
* Diastólica.
* Legumbres.

Después de convertir los valores, los datos se clasifican comparando los datos de presión arterial sistólica y diastólica de acuerdo con el formato estándar. Para enviar el informe por correo electrónico, se guardan los datos convertidos en formato de texto. Después de ordenar, el archivo se adjuntará al correo electrónico mediante la creación de detalles del asunto basados en los datos de presión arterial. Para el correo electrónico, se utilizó la biblioteca SMTP.

## Referencias
[Interfaz del sensor de presión](https://www.hackster.io/vinayyn/blood-pressure-sensor-interfacing-with-raspberry-pi-970f82)

