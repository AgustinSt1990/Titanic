# Titanic
El famoso desafío propuesto por Kaggle, encarado gracias a Digital House.

Acceso al código: https://github.com/AgustinSt1990/Titanic/blob/main/CV_Desafio_titanic.ipynb

<font face='Arial Narrow'>

-------
    
![DATA SCIENCE 2](https://user-images.githubusercontent.com/95892143/171273667-a370cf8a-d3b5-4d30-87ee-450e1dae1ab4.png)

# LABORATORIO: 

# <u>Pipelines y Transformadores + Arboles de decisión CART + Modelos de ensamble</u>

<br>
    
dataset: [Titanic dataset](http://www.kaggle.com/c/titanic-gettingStarted/data).

<br>

## <u>Introducción</u>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;En este laboratorio vamos a trabajar con el dataset del trasatlántico más famoso. Los datos son una lista de pasajeros que abordaron **El Titanic**. El objetivo es predecir una columna del dataset llamada "Survived", que indica si la persona ha sobrevivido (1) o no (0) al naufragio - variable categórica binaria -.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;El proceso llevado a cabo para dicho objetivo será la implementación técnica de múltiples temas relacionados a **Machine Learning**. La dirección está centrada en poder automatizar la mayor parte de las actividades que ejecutará el código a través de las herramientas vistas de **"Programación orientada a objetos"**. La intensión se basa en que **"los datos se ajusten al modelo, y no el modelo a los datos"** aunque este dataset no vaya a tener actualizaciones en el futuro, por cuestiones didácticas se apunta a eso.

  
    
- <font color='DodgerBlue' face='Arial Narrow'><b><u>RESUMEN DEL CODIGO</u></b></font>
<font face='Arial Narrow'>
    
    - Aplicar ingeniería en features para el preprocesamiento inicial de los datos 
    
    - Aplicar ingeniería en features para la obtención de los sets de entrenamiento y testeo
    
    - Aplicar pipelines para comparar 3 modelos base, sin ajustes, sobre los sets obtenidos y obtener métricas preliminares
    
    - Aplicar árbol de decisión implementando criterio de parada, y método de poda por medio de los hiperparámetros, y evaluar métricas
    
    - Aplicar modelo de ensamble de RandomForest con GridSearch para obtener un modelo robusto y evaluar la relevancias de las métricas
    
    - Aplicar un modelo de ensamble de ADABoost, utilizando como modelo base el mejor de los 3 modelo evaluados al comienzo, habiendolo optimizando anteriormente
    
    - Implementar XGBoost con el fin de obtener el mejor de todos los modelos
    
    - Presentación de las conclusiones

<br>

<a id="indice_notebook"></a> 

<font face='Arial Narrow'>

## <u>Indice de la notebook</u>

*(El índice tiene links en Jupyter Notebook)*  


- [<font color='DodgerBlue' face='Arial Narrow'><b>PARTE 1.1: <u>PREPROCESAMIENTO DEL DATASET</u></b></font>](#p1)
<font face='Arial Narrow'>
    
    - (1.1) EXPLORACION DATASET 
    
    - (1.2) ESTUDIO DE LAS VARIABLES 
    
    - (1.3) CONSTRUCCION DE TRANSFORMADORES 1 
    
    - (1.4) APLICACION DE TRANSFORMADORES 1 




- [<font color='DodgerBlue' face='Arial Narrow'><b>PARTE 1.2: <u>FEATURES ENGINEERING, PRIMERAS METRICAS</u></b></font>](#p11)
<font face='Arial Narrow'>
    
    - (1.5) CONSTRUCCION DE TRANSFORMADORES 2 
    
    - (1.6) CREACION DE MODELOS BASE 
    
    - (1.7) DIVISION EN SET DE ENTRENAMIENTO Y EN SET DE TESTEO
    
    - (1.8) APLICACION DE TRANSFORMADORES 2 Y ENTRENAMIENTO
    
    - (1.9) RESULTADOS PRELIMINARES 

  


- [<font color='DodgerBlue' face='Arial Narrow'><b>PARTE 2: <u>CART: Arboles de Decisión</u></b></font>](#p2)
<font face='Arial Narrow'>
    
    - (2.1) INSTANCIACION DE LOS MODELOS 
    
    - (2.2) CRITERIO DE PARADA
    
    - (2.3) METODO DE PODA 
    



- [<font color='DodgerBlue' face='Arial Narrow'><b>PARTE 3: <u>MODELOS DE ENSAMBLE</u></b></font>](#p3)
<font face='Arial Narrow'>

    - (3.1) RANDOM FOREST
    
    - (3.2) ADA BOOST 
    
    - (3.3) XGBOOST 
    
  


- [<font color='DodgerBlue' face='Arial Narrow'><b>PARTE 4: <u>CONCLUSIONES</u></b></font>](#p4)
<font face='Arial Narrow'>

    - (4.1) CONCLUSIONES
    
    - (4.2) PROXIMAS ACTUALIZACIONES
    
    - (4.3) AGRADECIMIENTOS 
    
<br><br>
    
![23_conclusion](https://user-images.githubusercontent.com/95892143/171273975-7d24d970-90b3-40ad-9bbe-64d7a9fdfadf.jpg)

<font face='Arial Narrow'>

# PARTE 4: <u>CONCLUSIONES</u>
    
<font face='Arial Narrow'>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;La visión con la que estuvo encarado este trabajo fue la de poder tener multiples features de entrenamiento, tener multiples modelos de ensamble y poseer una métrica en común para evaluar; ya que si fuese necesario, se podría armar un modelo de ensamble, para que las decisiones finales se hagan por votación de algunos de los 8 modelos recién vistos.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;En la tabla que van a ver a continuación, están los "scores" durante una pasada de **5** corridas del código. La métrica para evaluar los modelos es la **exactitud** de las predicciones. Esa métrica representa la proporción de casos correctamente predichos, sobre el total de casos analizados. Se pueden ver los scores para "Train" y para "Eval" por cada corrida, siempre predomina el modelo que tenga mejor score en Eval. 
    
![tabla conclusiones](https://user-images.githubusercontent.com/95892143/171274131-5569134c-931e-4c06-822f-02251fe6497b.png)

<a id='conclusiones'></a>

- <font color='DodgerBlue' face='Arial Narrow'><b>-->(4.1)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <u>CONCLUSIONES</u></b>
<font face='Arial Narrow'>    

    - La proporción de la variable target es de 40/60, cualquier score mayor a 0.6 es un modelo que predice mejor que responder siempre con la opción más probable.

    - Ensamble 1: en la parte 1 armamos un ensamble de 3 modelos, y el mejor siempre fue regresión logística, con un score inicial de 0,78 y marcando un piso a superar el resto de los modelos.
    
    - Arboles: Aplicamos todos los pasos posibles para obtener un modelo superador, pero muchas veces nos encontramos con que se producía overfitting, y cuando nuestro modelo predecia mejor en "Test", perdiamos mucho socre en "Eval" (en color rojo). Dentro de las corridas obtuvimos un modelo superior en la etapa de "stopping" (en color verde).
    
    - Random Forest: Muy superior en los score de "Train", y respecto a "Eval" hubo mejorías respecto al modelo base, no significativas, pero si representativas mejorías.
    
    - Regresión Logística Optimizado: Hubo que realizarse ajustes manuales a la búsqueda de hiperparámetros, logró superar al modelo base.
    
    - ADA Boosting: Una total decepción no haber podido entrenar acordemente un modelo de ensamble potenciado con regresión logística de modelo base.
    
    - XGBoost: Sorprendido de este modelo. Es superior en score al resto, pero además una facilidad para ajustar sus hiperparámetros. Cero variabilidad en sus entrenamientos sucesivos, velocisimo, etc. Traza la diferencia con la mayoría de los otros modelos. Es el ganador con un score de 0.81

    
- <font color='DodgerBlue' face='Arial Narrow'><b>-->(4.2)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <u>PROXIMAS ACTUALIZACIONES</u></b>   
<font face='Arial Narrow'>
    
    - Prometo aprender a implementar LightGBM, me interesan estos modelos que tienen su propia librería y funcionan con matrices dispersas en vez de DataFrames.
    
    - Prometo aprendar a usar la libreria "pickle", para poder almacenar modelos que entrene, cosa de poder seleccionar los mejores luego de una serie de corridas como he hecho en este caso y no quedarme solamente con último.


- <font color='DodgerBlue' face='Arial Narrow'><b>-->(4.3)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <u>AGRADECIMIENTOS</u></b>   
<font face='Arial Narrow'>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Para todos aquellos que estén leyendo esta línea de código, ya que fuiste parte de la inspiración que me llevó a querer aprender lenguaje HTML para poder poner hipervínculos para el índice y dentro del código. También y muy importante el hecho de querer hacer un código sintético, para una lectura ágil, entendible para cualquier público, fue la razón por la que gran parte del código que hace posible esta ejecución está en el archivo "SmartPandas.py". El comienzo de una gran carrera está teniendo lugar a partir de estas líneas, y sentir que puedo compartirlo con ustedes es de gran soporte, así que gracias a vos yo seguiré esforzandome. El desafío más importante del siglo XXI es la sustentabilidad.
    
<br>  
    
