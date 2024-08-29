<p align="left">
  <img src="https://semanadelcannabis.cayetano.edu.pe/assets/img/logo-upch.png" width="200">
  <h1 align="center">Entregable 01: Regresión Lineal</h1>
</p>

## Introducción
<p align="justify">La Agencia de Protección Ambiental de los Estados Unidos (EPA) es una institución clave en la protección de la salud pública y el medio ambiente. Su misión es desarrollar e implementar políticas y regulaciones que aseguren la calidad del aire, agua y suelo, protegiendo así tanto a las personas como a los ecosistemas. La EPA no solo establece normas estrictas para la emisión de contaminantes, sino que también realiza investigaciones científicas, monitorea la calidad ambiental y promueve prácticas sostenibles a nivel nacional (Our Mission and What We Do | US EPA, 2024).</p>

<p align="justify">El ozono a nivel del suelo, también conocido como ozono troposférico, es un contaminante del aire que representa una amenaza significativa tanto para la salud humana como para el medio ambiente. A diferencia del ozono estratosférico, que protege la vida en la Tierra al bloquear la radiación ultravioleta dañina, el ozono en el aire cercano a la superficie contribuye al smog y puede causar serios problemas respiratorios, como asma, bronquitis y otros trastornos pulmonares. Este contaminante nocivo afecta a la biodiversidad.(Cáceres, 2024).</p>

<p align="justify">La EPA regula los niveles de ozono troposférico debido a su capacidad para causar daños significativos. En este informe, se ha elegido el ozono (O3) como el principal contaminante para el análisis de la calidad del aire, utilizando datos recopilados durante los años 2022 y 2023. La elección del ozono se basa en su relevancia como indicador de la calidad del aire y su impacto directo en la salud pública y el medio ambiente. Este análisis tiene como objetivo entender las tendencias en la concentración de ozono, identificar posibles fuentes de emisión y evaluar la efectividad de las políticas implementadas por la EPA para mitigar este problema. Los resultados de este estudio no sólo permitirán una mejor comprensión de la situación actual.</p>

<p align="justify">Las variables que más destacan es la concentración máxima diaria de ozono en un periodo de 8 horas, el índice de calidad del aire(AQI), y el porcentaje de datos capturados en relación con la posible cobertura completa(Percent complete)
En las cuales contienen información sobre la fecha de medición, la concentración de ozono, el nombre de la zona, las coordenadas geográficas, etc.</p>

<p align="justify">Filtraremos, a criterio personal, las variables más importantes para el desarrollo de un modelo de regresión Lineal, ignorando elementos que no aporten a la predicción y enfocándonos en la metodología que nos permitirá dicho objetivo, que será establecida a continuación.</p>

## Metodología
<p align="justify">Nuestro análisis comienza con la carga de los conjuntos de datos correspondientes a los años 2022 y 2023, utilizando la biblioteca pandas para leer los archivos CSV. Estos datos se combinan en un único DataFrame para facilitar un análisis global y comprehensivo. Acto seguido, realizamos una exploración inicial de los datos para comprender su estructura, dimensiones y la presencia de valores faltantes o anómalos. Esta etapa incluye la verificación y manejo de datos faltantes, asegurando que el análisis subsiguiente no se vea afectado por la ausencia de información crítica.</p>

![image](https://github.com/user-attachments/assets/06dd756f-d511-4160-931a-a6415802c11f)
<div align="center"; style="display: flex; justify-content: space-between;">
  <img src="https://github.com/user-attachments/assets/ebad87d4-8ef3-49bd-9d6f-dbb5f8573992" width="489px"/>
  <img src="https://github.com/user-attachments/assets/46a0f469-88e3-4128-9ce7-358940a54ba1" width="518px"/>
</div>

<p align="justify">Una vez establecida la integridad de los datos, procedemos a organizarlos en orden cronológico, desde las mediciones más antiguas hasta las más recientes. Este ordenamiento es crucial para evitar inconsistencias en etapas posteriores, especialmente al dividir los datos en conjuntos de entrenamiento y prueba. Paralelamente, llevamos a cabo la normalización o estandarización de las variables necesarias, garantizando que todas las características tengan el mismo peso y relevancia en el análisis, lo cual es fundamental para que el modelo de regresión lineal pueda procesarlas adecuadamente.</p>

![image](https://github.com/user-attachments/assets/1228029a-f160-461a-ad82-f1aca789bf48)

<p align="justify">Con la información debidamente preparada, avanzamos hacia la realización de nuestra regresión lineal. Utilizamos un mapa de calor para identificar las variables con mayor correlación, las cuales serán consideradas para la predicción de nuestro objetivo: la "Daily Max 8-hour Ozone Concentration". Empleando la función LinearRegression de la librería sklearn, construimos un modelo al que introducimos nuestros datos, aprovechando el orden cronológico para evitar problemas temporales, para así no predecir valores del pasado entrenándonos con datos del futuro. Finalmente, entrenamos este modelo con los valores de X_train para la predicción de la concentración de ozono, estableciendo así las bases para nuestro análisis predictivo.</p>

![image](https://github.com/user-attachments/assets/5ad84333-f06b-4d51-a71b-a4af678f7fe8)

## Resultados
<p align="justify">Una vez logramos obtener un modelo entrenado, usaremos las medidas de dispersion como RMSD, obteniedno un valor de 0.877, que es cercano al valor de 1 esperado, al igual que:</p>

- Desviación Cuadrática Media (RMSD): 0.877, un valor próximo al esperado de 1
- Error Medio Absoluto (MAE): 0.00374
- Error Cuadrático Medio (MSE): 2.71e-05
- Raíz del Error Cuadrático Medio (RMSE): 0.00520

<p align="justify">Así como un histograma de valores predichos vs valores reales,  que representa la distribución normal, con una campana de Gauss que demuestra la predicción adecuada de los valores de “Daily Max 8-hour Ozone Concentration”	</p>

<p align="center">
<img align="center" width="500" height="500" src="https://github.com/user-attachments/assets/f8b3bbb9-76bd-45d5-9ee6-599c2b438944">
</p>

## Referencias [IEEE]
- Cáceres, S. B. (2024). Efectos de la salud en infantes por contaminación atmosférica: Una revisión. Revista Científica Higía de la Salud, 10(1). https://www.itsup.edu.ec/myjournal/index.php/Higia/article/view/971

- Our Mission and What We Do | US EPA. (2024, 1 mayo). US EPA. https://www.epa.gov/aboutepa/our-mission-and-what-we-do
