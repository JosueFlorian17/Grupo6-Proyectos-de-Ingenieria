<p align="left">
  <img src="https://github.com/user-attachments/assets/7d175927-ada3-49d1-9feb-c539e3595c73" width="200">
  <h1 align="center">Entregable 03: Magic Hand - TinyML</h1>
</p>

## Introducción
<p align="justify">TinyML (Tiny Machine Learning) es una subdisciplina de la inteligencia artificial que permite la ejecución de modelos de aprendizaje automático en dispositivos de bajo consumo y recursos limitados, como microcontroladores y sensores. A diferencia de los modelos tradicionales de ML, que requieren grandes capacidades de procesamiento, TinyML optimiza tanto el hardware como el software, permitiendo operar con recursos mínimos de procesamiento y energía, incluso en dispositivos que consumen milivatios o microvatios (Diego et al., 2021).</p>

<p align="justify">Estas innovaciones permiten realizar tareas como reconocimiento de voz, detección de imágenes y análisis de datos en tiempo real, sin necesidad de una conexión constante a internet, siendo ideales para aplicaciones en salud, agricultura, monitoreo ambiental y hogares inteligentes (Manzoni y De València, 2024).</p>

<p align="justify">En este contexto, el objetivo de este trabajo es implementar un modelo de TinyML en un Arduino Nano 33 BLE Sense para reconocer patrones de movimiento específicos. El proyecto, denominado Magic Hand, utiliza los sensores integrados del dispositivo, como el acelerómetro, para identificar gestos y figuras dibujadas en el aire.</p>

El sistema está diseñado para realizar las siguientes acciones:
- Encender el LED rojo cuando reconozca el dibujo del círculo.
- Encender el LED verde cuando reconozca el dibujo del número 1.
- Encender el LED azul cuando reconozca el dibujo del número 3.

<p align="justify">Este proyecto demuestra cómo la IA puede aplicarse en dispositivos con recursos limitados para tareas de reconocimiento de gestos, abriendo nuevas posibilidades en interfaces interactivas. A lo largo del informe, se detallarán los procedimientos de desarrollo, la implementación del modelo y los resultados obtenidos.</p>

## Metodología
<p align="justify">Para la realización y planificación de este proyecto, hhicimos uso de un repositorio encontrado en la plataforma de Github, que usa la carpeta train para descargar, gracias a un código de python, un grupo grande de imágenes de resultados de mover el acelerómetro integrado en el arduino, obtenemos de esta manera las imágenes con el siguiente formato.</p>

<p style="text-align: center;">
    <img src="https://github.com/user-attachments/assets/f4501f9d-0163-4ba1-86a5-7c709721384f" alt="Descripción de la imagen" width="300">
</p>

que luego de ser rasterizada, obtiene el siguiente formato

<p style="text-align: center;">
    <img src="https://github.com/user-attachments/assets/eb7fe2d3-0191-4c39-bc24-968321eb4f5c" alt="Descripción de la imagen" width="300">
	</p>

y seguimos todos los pasos estudiados para la creación de una red convolucional, con las diferentes capas, aplicando reescalado, normalizado, Dropout, y diferentes épocas para el entrenamiento de nuestro modelo y pueda estar preparado para el reconocimiento de imágenes.

Luego, encontramos el código de arduino que se encarga de desplegar el modelo en nuestra placa de Arduino Nano 33 BLE, que con información del giroscopio y acelerómetro, mostrará en el puerto serial del Arduino IDE, adicionalmente, se creó la función para iluminar los LEDS del color indicado dependiendo del número detectado.

Entonces, con la recaudación de información, así como la modificación del código y entrenamiento del modelo, logramos realizar el objetivo esperado

## Resultados
<p align="justify">El reconocimiento de gestos por el modelo de TinyML fue evaluado a través de múltiples pruebas realizadas con el Arduino Nano 33 BLE Sense. A continuación, se detallan los principales resultados obtenidos:</p>

### Precisión del reconocimiento de gestos
<p align="justify">Durante las pruebas, se realizaron diferentes movimientos con la mano para dibujar las figuras programadas (círculo, número 1 y número 3). El modelo entrenado fue capaz de identificar correctamente el gesto en el 88.33% de los casos. A continuación se presentan los resultados obtenidos en términos de precisión:</p>

- Círculo: El modelo tuvo una precisión del 85% en la detección del número 1, encendiendo el LED rojo cuando fue identificado correctamente.
- Número 1: El modelo reconoció correctamente el gesto en el 95% de los intentos. En estos casos, el LED verde se encendió de manera inmediata, validando la inferencia del modelo.
- Número 3: El reconocimiento del número 3 presentó una precisión del 85%, con el LED azul iluminándose al detectar el patrón.

### Tiempo de respuesta
<p align="justify">El tiempo de respuesta del sistema, medido desde la realización del gesto hasta el encendido del LED correspondiente, fue en promedio de 1000 milisegundos, lo que demuestra una inferencia rápida y adecuada para aplicaciones en tiempo real.</p>

A continuación se presentan algunas imágenes capturadas durante las pruebas:

| LED rojo encendido al reconocer el dibujo del círculo.  | LED verde encendido al reconocer el dibujo del número 1.  | LED azul encendido al reconocer el dibujo del número 3.  |
| :------------: | :------------: | :------------: |
| <p align="center"><img src="https://github.com/user-attachments/assets/37a31cd0-318b-45f5-9f9b-21db855fab5b" width="720" style="margin: auto;"></p>  | <p align="center"><img src="https://github.com/user-attachments/assets/3c683b60-300b-4925-8003-02b38483909f" width="900" style="margin: auto;"></p>  |  <p align="center"><img src="https://github.com/user-attachments/assets/359a63aa-8c91-4ac0-859b-8891f5a52ebe" width="680" style="margin: auto;"></p> |

<p align="justify">Adicionalmente, el siguiente video muestra una demostración del sistema en funcionamiento, donde se puede observar cómo los gestos dibujados son reconocidos y los LEDs se encienden de acuerdo con el patrón detectado.</p>

https://github.com/user-attachments/assets/1bd3488f-ea7e-41ee-b677-4f520464b4f8

## Referencias
- Diego, C. S., Emilio, S. O., María, M. M. J., Juan, G. S., Marcelino, M. S., Pedro, D. M., & Regino, B. C. (2021). Tiny ML: La nueva revolución en la IoT. https://roderic.uv.es/items/bae51b9b-e128-48e7-aa73-367dd8d45081
- Manzoni, P., & De València Departamento de Informática de Sistemas y Computadores -Departament D’Informàtica de Sistemes I Computadors, U. P. (2024, 26 julio). Comparativa de plataformas software para TinyML. https://riunet.upv.es/handle/10251/206637
