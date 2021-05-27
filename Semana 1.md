# **Inteligencia Artificial**

## **Introducción a las Redes Neuronales**

### **¿Qué es una Red Neuronal?**

A nivel esquemático, una neurona artificial se representa del siguiente modo:

![image](https://drive.google.com/uc?export=view&id=1VlROM23Yr-Rrs1WraMaesy2J9Qn3pIRS)

En el caso de las neuronas artificiales, la suma de las entradas multiplicadas por sus pesos asociados determina el “impulso nervioso” que recibe la neurona. Este valor, se procesa en el interior de la célula mediante una función de activación que devuelve un valor que se envía como salida de la neurona.

Del mismo modo que nuestro cerebro está compuesto por neuronas interconectadas entre sí, una red neuronal artificial está formada por neuronas artificiales conectadas entre sí y agrupadas en diferentes niveles que denominamos capas:

    "Una capa es un conjunto de neuronas cuyas entradas provienen de una capa anterior (o de los datos de entrada en el caso de la primera capa) y cuyas salidas son la entrada de una capa posterior." 

![image](https://drive.google.com/uc?export=view&id=17BdaJfpvS5YRnfrP4pM3URngEsIEVXEc)

Las neuronas de la primera capa reciben como entrada los datos reales que alimentan a la red neuronal.  Es por eso por lo que la primera capa se conoce como capa de entrada. La salida de la última capa es el resultado visible de la red, por lo que la última capa se conoce como la capa de salida. Las capas que se sitúan entre la capa de entrada y la capa de salida se conocen como capas ocultas ya que desconocemos tanto los valores de entrada como los de salida.

Una red neuronal, por lo tanto, siempre está compuesta por una capa de entrada, una capa de salida (si solo hay una capa en la red neuronal, la capa de entrada coincide con la capa de salida) y puede contener 0 o más capas ocultas. El concepto de Deep Learning nace a raíz de utilizar un gran número de capas ocultas en las redes.

## **Definiciones y Áreas de la IA**

### **Definición:**

    La Inteligencia Artificial (IA) es la parte de las ciencias de la computación relacionada con el diseño de sistemas informáticos inteligentes, es decir, sistemas que exhiben caracteristicas que asociamos con inteligencia en el comportamiento humano: compresión del lenguaje, aprendizaje, razonamiento, resolver problemas y así sucesivamente. (Barr y Feigenbaum, 1981)

### **Áreas de la IA**

- Computación Evolutiva
- Visión Artificial
- Procesamiento de Lenguaje Natural
- Sistemas Expertos y Presentación del Conocimiento
- Planificación Automática y Aprendizaje por Reforzamiento
- Aprendizaje Automático (Machine Learning)
- Robótica

## **Aprendizaje Automático (Machine Learning)**

### **Definición:**

    El aprendizaje automático consiste en el estidio de algoritmos que aprenden mediante la experiencia.

    Un programa de computadora "aprende" de la experiencia E con respecto a alguna clase de tareas T y la medida de desempeño P si su desempeño en tareas en T, medido por P, mejora con la experiencia E. (Mitchell, 1997)

***Ejemplo:*** Si tenemos un algoritmo que sirve para desempeñar una tarea **T** y desarrollarla, luego esta tarea **T** le podemos medir con que calidad se hizo esta tarea mediante **P** que es la medida de desempeño, después consideramos la experiencia **E** por la que puede pasar el algoritmo donde vuelve a hacer la tarea **T** pero esta vez su desempeño es mejor, con lo que llegamos a concluir que ha aprendido.

### **División del Aprendizaje Automático (ML)**

- Aprendizaje Supervisado (con etiquetas)
  - Clasificación (etiquetas discretas)
    - Binaria (de dos etiquetas se selecciona una).
    - Multiclase (de varias etiquetas se selecciona una).
    - Multietiqueta (de varias etiquetas se seleccionan varias).
  - Regresión (etiquetas continuas)

- Aprendizaje No Supervisado (sin etiquetas)
  - Agrupamiento (Clustering), Ingeniería de Atributos, etc.

- Aprendizaje Semisupervisado
- Aprendizaje por Reforzamiento

## **Aprendizaje Supervisado: Ejemplos y Tipos de Datos**

### **Ejemplos**

| Atributos (Entrada) | Etiqueta (Salida) | Aplicación |
|---|---|---|
|Caracteristicas de una casa|Precio|Bienes raíces|
|Info. del anuncio y del usuario| Probabilidad de click|Mercadeo en línea|
|Audio|Texto|Reconocimiento de voz|
|Rostro en fotografía|Id de la persona|Etiquetado de foto|
|Imagen tomográfica|Si hay tumor o no|Medicina|

### **Tipos de Datos**

- Datos Estructurados:
  - Se pueden colocar como columnas de una base de datos.

- Datos no Estructurados:
  - Su formato es el que usamos los seres humanos: imágenes, audio, conversación escrita.

## **Clasificación Binaria: Ejemplos y Notación**

La clasificación binaria es un problema de aprendizaje supervisado por lo que contamos con atributos y una etiqueta la cual es binaria lo cual da que de dos opciones solo podemos tomar en cuenta una. 

### **Ejemplo:** 

Si queremos determinar si en una imagen hay o no un gato tenemos como etiquetas posibles: *Gato* y *No Gato* de las cuales debemos seleccionar una para asignar a la imagen. Lo que nos combiene es obtener atributos numéricos de la imagen y la pregunta sería ¿Cómo encuentro esos atributos? como cada imagen esta compuesta por niveles de color entonces cada pixel de la imagen cuenta con un color en especifico este color va a variar de acuerdo a los 3 niveles de color en valores de 0 a 255 para rojo, azul y verde, entonces con estos 3 valores por cada color en el pixel se obtiene un vector de atributos.

### **Notación**

En cuanto a la notación decimos que el aprendizaje automático en general se aprende de un conjunto de datos o Dataset por lo que no nos basta solo una imagen para definir si se reconoce lo que prentendemos o no, a esto es a lo que se le conoce como entrenamiento; presentar un conjunto de elementos y saber si se reconocen de forma correcta y realizar el proceso de clasificación.

Por lo que necesitamos dos vectores, un vector **X** que posee las instancias del dataset o conjunto de datos y un vector **Y** que contiene las etiquetas que serán asignadas a estos datos.

![image](https://drive.google.com/uc?export=view&id=1I_RNgsv5pHiTUhk6vB5NmJ86UTOQpznH)

## **Regresión Logística**

Es un modelo matemático que su forma básica usa una función logística para modelar una variable binaria dependiente.

### **Función Logística**

Es una función sigmoide que va de menos infinito a más infinito en su dominio pero su rango va de 0 a 1 y esto es para modelar una probabilidad.