# Titanic
El famoso desafío propuesto por Kaggle, encarado gracias a Digital House.

Acceso al código: https://github.com/AgustinSt1990/Titanic/blob/main/CV_Desafio_titanic.ipynb

<font face='Arial Narrow'>

-------
    
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
