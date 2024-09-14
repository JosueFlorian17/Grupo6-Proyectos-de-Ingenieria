## Guía Nº2 - TIny-ML

### INTEGRANTES:
- Edwin Jara
- Josué Florian
- Romina Pérez 
- Cindy Pérez

Grupo: 4

## Introducción: 
TinyML (Tiny Machine Learning) es una subdisciplina de la inteligencia artificial centrada en la implementación de modelos de aprendizaje automático en dispositivos de bajo consumo y recursos limitados, como microcontroladores y sensores. A diferencia de los modelos tradicionales de machine learning, que demandan grandes capacidades de procesamiento y almacenamiento, TinyML permite ejecutar algoritmos de IA en hardware que consume milivatios o incluso microvatios de energía, lo que lo hace especialmente adecuado para dispositivos en el borde de la red ("Edge Computing") (Diego et al., 2021).

Este avance es posible gracias a innovaciones en la compresión de modelos y la optimización del hardware, lo que permite que los dispositivos realicen tareas como reconocimiento de voz, detección de imágenes y análisis de datos en tiempo real sin depender de una conexión constante a internet. TinyML resulta ideal para aplicaciones en automatización industrial, dispositivos portátiles de salud, agricultura de precisión, monitoreo ambiental y hogares inteligentes (Manzoni y De València, 2024). Además, su capacidad para operar en entornos con limitaciones energéticas lo convierte en una solución eficiente y sostenible para un mundo cada vez más interconectado.

En este contexto, el presente trabajo tiene como objetivo implementar un modelo de TinyML en un Arduino Nano 33 BLE Sense para reconocer patrones de movimiento específicos. Este proyecto, denominado Magic Hand, aprovecha los sensores integrados del Arduino, particularmente el acelerómetro, para identificar gestos y figuras dibujadas en el aire.

El sistema está diseñado para realizar las siguientes acciones:

- Encender el LED rojo cuando reconoce el dibujo del círculo.
- Encender el LED verde cuando reconoce el dibujo del número 1.
- Encender el LED azul cuando reconoce el dibujo del número 3.

Este proyecto demuestra cómo se puede aplicar la inteligencia artificial en dispositivos con recursos limitados para tareas de reconocimiento de gestos, abriendo posibilidades para la creación de interfaces de usuario innovadoras y sistemas interactivos en el campo de la electrónica y la robótica.


A lo largo de este informe, se detallarán los procedimientos de desarrollo, desde la recolección de datos hasta la implementación del modelo en el hardware, así como los resultados obtenidos y las conclusiones alcanzadas.


## Metodología 

Para la realización y planificación de este proyecto, hhicimos uso de un repositorio encontrado en la plataforma de Github, que usa la carpeta train para descargar, gracias a un código de python, un grupo grande de imágenes de resultados de mover el acelerómetro integrado en el arduino, obtenemos de esta manera las imágenes con el siguiente formato

<p style="text-align: center;">
    <img src="https://github.com/user-attachments/assets/f4501f9d-0163-4ba1-86a5-7c709721384f" alt="Descripción de la imagen" width="300">
</p>

que luego de ser rasterizada, obtiene el siguiente formato

<p style="text-align: center;">
    <img src="https://github.com/user-attachments/assets/eb7fe2d3-0191-4c39-bc24-968321eb4f5c" alt="Descripción de la imagen" width="300">
</p

  
y seguimos todos los pasos estudiados para la creación de una red convolucional, con las diferentes capas, aplicando reescalado, normalizado, Dropout, y diferentes épocas para el entrenamiento de nuestro modelo y pueda estar preparado para el reconocimiento de imágenes.

Luego, encontramos el código de arduino que se encarga de desplegar el modelo en nuestra placa de Arduino Nano 33 BLE, que con información del giroscopio y acelerómetro, mostrará en el puerto serial del Arduino IDE, adicionalmente, se creó la función para iluminar los LEDS del color indicado dependiendo del número detectado.

Entonces, con la recaudación de información, así como la modificación del código y entrenamiento del modelo, logramos realizar el objetivo esperado





## Resultados:
A continuación, podrán observar imágenes que demuestran el reconocimiento de los movimientos de la "varita mágica" y cuando el modelo de machine learning incluído en el arduino lo reconoce como el número adecuadi (0,1,3) enciende los leds correspondientesm, además de un video de demostración que esperamos puedan darse el tiempo de ver.


![image](https://github.com/user-attachments/assets/37a31cd0-318b-45f5-9f9b-21db855fab5b)
![image](https://github.com/user-attachments/assets/3c683b60-300b-4925-8003-02b38483909f)
![image](https://github.com/user-attachments/assets/359a63aa-8c91-4ac0-859b-8891f5a52ebe)

[Video de prueba de funcionamiento](https://drive.google.com/file/d/1veLdM0e54wWmebo7Vo889T_UlEQCH55d/view?usp=sharing)


Referencias:

Diego, C. S., Emilio, S. O., María, M. M. J., Juan, G. S., Marcelino, M. S., Pedro, D. M., & Regino, B. C. (2021). Tiny ML: La nueva revolución en la IoT. https://roderic.uv.es/items/bae51b9b-e128-48e7-aa73-367dd8d45081

Manzoni, P., & De València Departamento de Informática de Sistemas y Computadores - Departament D’Informàtica de Sistemes I Computadors, U. P. (2024, 26 julio). Comparativa de plataformas software para TinyML. https://riunet.upv.es/handle/10251/206637


