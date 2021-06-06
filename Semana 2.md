# **Inteligencia Artificial**

## **Función de Costo**

Cuando definimos el aprendizaje automático decimos que tiene que tener una medida de desempeño, la función de costo nos va a permitir realizar o medir el desempeño del modelo en todo el conjunto de datos.

### **Función de Pérdida**

Sirve para medir el error de nuestro modelo que cuando estamos realizando el aprendizaje a este proceso se le suele llamar ***"El Entrenamiento*** y que es cuando se están utilizando los datos para ajustar o entrenar el modelo. Tenemos acceso a las etiquetas realies de las instancias que estamos leyendo y utilizando entonces tenemos la posibilidad de medir la predicción que da nuestro modelo y compararlo con la etiqueta real que tenemos, la diferencia que haya entre nuestra predicción y la etiqueta real va a ser un error si nuestra etiqueta es igual a la etiqueta real y a la etiqueta predecida que predice nuestro modelo es igual a la etiqueta real entonces el error va a ser o tendria que ser minimo o cero. Por lo que la función de perdida nos sirve para medir ese error pues se le llama perdida.

Existen múltiples funciones de pérdida que pueden utilizarse para hacer esta comparación sin embargo una sin embargo una de las más utilizadas es:

![image](https://drive.google.com/uc?export=view&id=1yarjd6oM9i1TbWYdw_Ou3fqDpNseZMeY)

Esta función está basada en el cálculo de logaritmos y aunque pareciera un poco larga es muy sencilla ya que al considerar que las etiquetas realies en clasificación binaria sólo tienen dos valores que serían 0 y 1 entonces:

- **y**: es la etiqueta real que puede ser 0 o 1.
- **y^**: es mla predicción

Entonces la función de perdida se divide en dos partes dependiendo de la etiqueta real, la siguiente grafica es de la pérdida con respecto a la predicción, en la que si predecimos que hay un valor de 1 entonces lo tomamos como que no hay algun error ni pérdida. Si se hace una predicción distinta de 1 como por ejemplo 0.5 (tomando en cuenta que si se puede predecir un 0.5 ya que los valores que tenemos sonb valores de probabilidad) podemos ver que el error es más alto y si yo llego a la predicción de 0 vemos que la pérdida va a tendiendo a infinito.

![image](https://drive.google.com/uc?export=view&id=1wKFxPgVU6c3eGa66V2laazjK751eREF1)

Vemos entonces que la función de pérdida nos sirve simplemente para medir la diferencia o un error que tengo entre la predicción real y la predicción entre la etiqueta real y la predicción hecha por el modelo.

### **Función de Costo**

El entrenamiento no se hace con una sola instancia, la función de pérdida mide el error entre una etiqueta real y una etiqueta predecida pero nuestro conjunto de entrenamiento va a tener más de una sola instancia osea que habran multiples etiquetas entre las que se encontrarán multiples etiquetas predecidas y multiples etiquetas reales por tanto necesitamos una función que dé una visión global del rendimiento de todo el modelo en todos los datos del modelo.

![image](https://drive.google.com/uc?export=view&id=1PcOkxsd4OLL_1oUom2ybxw27TXNAPWwo)

La función de costos se representa por la letra **J** y no es más que un promedio entre la sumatoria de las pérdidas y tenemos a la letra *i* que representa de desde 1 a m que indica todas las instancias de entrenamiento osea que se suman todas las pérdidas y las instancias de entrenamiento, esto se divide entre m y se obtiene el promedio de las pérdidas. También tenemos la ecuación que calcula el valor de la etiqueta predecida utilizando la regresión logística, este valor de la etiqueta predecida es igual a la función sigmoide de w transpuesta producto punto con x (atributos ya definidos) más b.

En la función de costo lo que se va a hacer es comparar las m etiquetas reales que vamos a tener en el vector de **y** con las etiquetas predecidas que son **y^** por lo que obtendremos m pérdidas distintas **L(y)** y **L(y^)** representan la pérdida en cada una de las instancias, se suman esas pérdidas y las divido entre m para obtener el costo depende de w ya que las etiquetas reales ya están definidas, no son algo que va a cambiar; mientras que las etiquetas cambiantes son las predecibles porque no dependen de x sino que dependen de w y de b que son los verdaderos parámetros del modelo.

## **Derivadas: un repaso** 

La derivada de una funciòn f es la  pendiente de la recta tangente a la curva de dicha funciòn en un punto determinado.

Dado un triàngulo rectàngulo como el de la figura, la pendiente de su hipotenusa es igual a la razòn entre la altura y la base.

## **Descenso de Gradiente**

El algoritmo de descenso de gradiente es un algoritmo de optimización que utilizamos para minimizar una función específica, en nuestro caso la función que queremos minimizar es la función de costo.

La función de costo nos servia para determinar o evaluar el desempeño de nuestro algoritmo con respecto a las etiquetas con las que contamos en el conjunto de datos, sin embargo desiamos tambien que la función depende de w y b donde w son los parámetros del modelo, entonces estos parámetros necesitamos encontrarlos pero necesitamos encontrarlos de forma tal que el costo sea minimo o sea que queremos parametros que minimicen el costo. Para eso debemos hacer uso del algoritmo de descenso de gradiente.

    El algoritmo de descenso de gradiente es un algoritmo iterativo que funciona paso a paso, empieza en un punto cualquiera de la gráfica e intenta paso a paso ir avanzando o moviendo cambiando los valores de w y b para que poco a poco vayamos buscando el valor donde el costo es minimo.

El algoritmo de descenso de gradiente no nos garantiza encontrar el valor exacto o el punto exacto sino un punto aproximado que generalemente ese punto es lo que nos basta.

Existen otras formas de encontrar el punto mínimo de una función, sin embargo las soluciones analíticas como ésta se vuelven intratables cuando tenemos muchas dimensiones, en nuestro caso es importante comenta que w apartentemente posee una dimensión pero unicamente w va a tener el mismo tamaño de x y d es el tamaño de atributos.

    Este algoritmo también es útil al trabajar con funciones que no son convexas sino que son funciones que tengan múltiples puntos mínimos. Como por ejemplo valles o montañas.

El algoritmo de descenso del gradiente itera una cantidad de veces buscando el punto mínimo por lo que consideramos que lo que hace es que el valor de un parámetro lo actualiza de forma que al valor que se tiene actualmente le resta una constante multiplicada por la derivada de función de costo con respecto al valor actual con el que se está trabajando (la derivada lo que da es la pendiente de la recta tangente a la función en un punto específico).

La constante que se le multiplica a la derivada sirve para aumentar o reducir el tamaño del salto que se hace. A esto se le llama *Ritmo de Aprendizaje* o *Learning great* entre más alto es se hacen saltos más largos o lo contrario.

El algoritmo de descenso de gradiente hace lo mismo con cada valor del parametro y hace lo mismo para b, la idea es escencialmente la misma ir moviendo y ajustando el parametro acercandose hacia el punto mínimo y ese punto minimo el tamaño del salto está determinado por el ritmo de aprendizaje y la magnitud de la derivada y la dirección del salto está determinada por la dirección de la derivada si es positiva o negativa.

Este algoritmo se dará por concluido cuando estemos satisfechos y ahí empecemos a considerar que se está llegando a un punto de costo muy pequeño y se suele definir que terminará con un número de iteraciones fijo y observar cuál es el comportamiento del algoritmo en esas iteraciones.

## **Grafo de Cálculo de la Regresión Logística: Propagación hacia adelante y hacia atrás**

El grafo de cálculo es una herramienta que nos muestra los pasos necesarios para obtener un valor final que necesitamos encontrar y las dependencias de estos pasos.

Ejemplo del grafo para la regresión logística:

![image](https://drive.google.com/uc?export=view&id=1mQxrsD3biKVS7yQ6RGXe3HKAylf-eoAU)

Según el algoritmo de descenso del gradiente para actualizar los valores de los parametros dicho algoritmo necesit saber los valores de las derivadas del costo con respecto a sus parámetros y para obtener el valor de esa derivada es que funciona la propagación hacia atrás.

Partiendo de la perdida, el primer paso de la propagación hacia atras seriía calcular la derivada de la pérdida con respecto a **y^**, y no con respecto a **y** porque no es un valor de interes. mientras que **y^** si porque depende de nustros parámetros.