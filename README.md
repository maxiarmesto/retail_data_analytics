# Título del Proyecto: Ciencia de Datos aplicada en la Industria Retail

## Breve descripción del proyecto (descripción del dataset, problemas interesantes asociados)
Se provee de un dataset que contiene datos históricos de ventas correspondientes a 45 tiendas anónimas localizadas en diferentes departamentos. Además el dataset cuenta con información de contexto (temperatura, precio del combustible, tasa de desempleo, información de rebajas, feriados) para las fechas correspondientes a las ventas (ventas registradas semanalmente desde febrero de 2010 hasta noviembre de 2012). Se provee también de una caracterización por tipo y tamaño para cada tienda y una lista de los usuarios que frecuentan cada una.
Uno de los desafíos de modelar datos de esta industria se presenta debido a la necesidad de tomar decisiones basadas en operaciones históricas limitadas. Se busca la definición de estrategias y toma de decisiones, en base al análisis y procesamiento de los datos históricos disponibles, para el cumplimiento de un cierto objetivo, como lo puede ser aumento de la rentabilidad del negocio/mejora del servicio prestado al cliente.
El objetivo de este proyecto es que el estudiante a lo largo de las materias a cursar en la diplomatura identifique y aplique diferentes técnicas de análisis/procesamiento de los datos que generen información valiosa para un negocio que se desarrolla en la industria en cuestión. Algunos de los puntos interesantes asociados son:
- Predicción de ventas futuras (detección de altas y bajas), análisis de estacionalidad de los datos.
- Segmentación de las ventas en base a las características de su contexto.
- Sistema de recomendación de tiendas para los usuarios.
- Análisis del efecto de las rebajas en las ventas para las distintas tiendas.
- Análisis del impacto de los feriados en las ventas.
- Análisis de correlación entre las diferentes variables provistas y las ventas semanales, análisis del impacto que las mismas causan.

## Análisis y Visualización
- Correlación entre variables/análisis de independencia. A través de este análisis se puede ver el impacto de cada variable sobre las ventas semanales y de esta manera determinar cuales son las variables importantes a considerar.
- Distribución de los ejemplos con respecto a las diferentes clases. 
- Análisis de outliers.
- Visualización de las ventas con respecto al tiempo para cada tienda en un determinado departamento.
- Visualización de las ventas totales de cada tienda.
- Porcentaje que representan las rebajas sobre las ventas totales para una tienda.

## Análisis y Curación
Para análisis y curación podrán aplicarse sobre el dataset (en su totalidad) los siguientes puntos:
- Importación de datos.
- Chequeo de claves únicas por sample/eliminar duplicados.
- Despersonalización de datos.
- Normalización de los nombres de las columnas en los dataframes.
- Tratamiento de valores faltantes.
- Codificación de variables categóricas.
- Análisis de valores atípicos.
- Persistencia de los resultados.
- Ordenamiento de las columnas.
- Eliminar columnas que no aporten información.
- Crear un dataset único de las 3 tablas provistas incluyendo toda la información útil en una misma tabla.

## Introducción al ML
Los dataset provistos contienen muchas variables sobre las cuales se puede aplicar análisis y procesamiento. En esta materia puntual lo importante es que el estudiante aprenda a hacer la division de los datos, la elección del modelo, evaluación de metricas, independientemente de la complejidad del dataset. Razón por la cual para este práctico se tomaran dos variables simples de analizar, por ejemplo la fecha de las ventas y la columna que nos dice si es feriado o no, y con esto hacer un sistema predictivo en donde se introduce una fecha y el modelo predice si en esa semana hay feriados o no. Con esto podrá aplicarse:
- Carga de datos.
- Una pequeña reestructuración de las columnas optimizandolo para el análisis que se desea hacer (por ejemplo considerar todas las fechas de la semana y no solo la provista por el dataset).
- Division en conjuntos de entrenamiento y evaluación.
- Elección de un modelo.
- Selección de hyperparámetros.
- Métricas sobre el conjunto de evaluación.
- Curvas ROC.

## Aprendizaje Supervisado
En este caso, en la materia se van aplicando diferentes técnicas correspondientes a aprendizaje supervisado evaluando los resultados obtenidos. Lo ideal es partir de un baseline e ir complejizando el modelo. Sería interesante implementar en este caso un sistema predictivo de ventas para un determinado año en base a la información histórica. Se cuenta con features como la fecha (de la que se puede derivar mes o epoca del año), precio del combustible, desempleo, temperatura las cuales se pueden utilizar como entrada de un modelo que prediga las sales que se tendrá en una determinada fecha. Esto podría hacerse como un modelo general, o seleccionar una determinada tienda para hacer el análisis. Se cuenta con el registro de 3 años, la idea sería entrenar el modelo con los dos primeros y testear el comportamiento del modelo con los datos del tercero. Es decir, se entrena con 2010 y 2011, y se corre el modelo con las features del 2012 comparando la salida del predictor con la real.

## Aprendizaje No Supervisado
Para la aplicación de aprendizaje no supervisado sería interesante hacer dos análisis:
- Segmentación de las ventas: clusterizar las ventas junto con las diferentes variables disponibles y hacer un análisis de los grupos obtenidos. Si aplica, evaluar en que caso tenemos las mejores ventas, ante que condiciones, con que combinación de variables. Podría utilizarse un algoritmo como K Means con algún método de optimización de número de clusters como elbow method.
- Sistema de recomendación de tiendas: se cuenta con el dato de los usuarios que frecuentan cada tienda, puede armarse un pequeño sistema de recomendación de tiendas a usuarios a través de métodos matriciales.

## Optativas Relacionadas
Análisis de series temporales, Introducción al data Warehousing, Ciencia de datos en las Finanzas, Introducción al aprendizaje profundo.

## Contenido del Dataset
Se provee de datos históricos de ventas de 45 tiendas localizadas en diferentes regiones, cada tienda contiene un número determinado de departamentos. Cada compañía además organiza eventos de rebajas a lo largo del año. Estas rebajas preceden a feriados destacados como lo son: el Super Bowl, el Día del Trabajo, Día de Acción de Gracias y Navidad. Las semanas que incluyen estos feriados tienen un peso 5 veces mayor que las que no.

El contenido de los cuatro archivos (Stores, Users, Features y Sales) se presenta a continuación:

### Stores
Información anónima de las 45 tiendas, incluye tipo y tamaño de las mismas.

### Users
Lista de usuarios y las tiendas que frecuentan.

### Features
Contiene información adicional relacionada a las tiendas, la localidad y actividad regional para las fechas dadas.
- Store: el número de tienda.
- Date: la semana correspondiente.
- Temperatura: temperatura promedio de la región.
- Fuel Price: costo del combustible en la región.
- Markdown 1-5: datos anónimos relacionados a rebajas promocionales. Esta información esta sólo disponible a partir de Noviembre del 2011 y no esta disponible para todas las tiendas todo el tiempo. Lo valores faltantes están marcados como NA.
- CPI: índice de precios al consumidor.
- Unemployment: tasa de desempleo.
- IsHoliday: si la semana contiene al menos un día feriado.

### Sales
Datos historicos de ventas, cubren desde el 05-02-2010 hasta el 01-11-2012. Incluye los siguientes campos:
- Store: el número de tienda.
- Dept: el número de departamento.
- Date: la fecha correspondiente a la transacción.
- Weekly_Sales: ventas para el departamento dado en la tienda correspondiente.
- IsHoliday: indica si corresponde a una semana con días feriados o no.

Link a la fuente: https://www.kaggle.com/manjeetsingh/retaildataset#Features%20data%20set.csv

## Consigna práctico Análisis y Visualización

- Calcular estadísticos como la moda, media, mediana y desviación estándar del precio del combustible y la temperatura. ¿Responden a alguna distribución conocida?
- Seleccionar una tienda cualquiera, y calcular el promedio de ventas mensuales para los años en cuestión, graficar la distribución de las ventas promedios mensuales para cada año. ¿Responde a alguna distribución conocida?
- Realizar un análisis de outliers para 3 variables a elección.
- ¿Qué pasaría con las ventas si se baja el combustible?¿Que pasaría con las ventas si aumenta la tasa de desempleo?¿Qué sucede con las ventas si nos encontramos en un día feriado? En el caso de las ventas mensuales promedios, ¿existe una relación entre la variable ventas y el mes del año en que nos encontramos?
- Crear una columna adicional IsMarkdown la cual será True si ha habido una rebaja en esa fecha y será False si no la ha habido. Teniendo en cuenta las variables IsHolisday e IsMarkdown, calcular su probabilidades conjunta y marginal.
- ¿Que probabilidad hay de que haya rebajas una semana que se sabe que es feriado? Dividir en 4 partes el dataset y calcular bayes con respecto a estas dos variables, usando los resultados de cada iteración / partición para calcular. El objetivo es simular que los datos que van llegando en cada iteración recalculan la probabilidad

Para la entrega se pide un jupyter notebook que contenga el desarrollo y los cálculos que han sido necesario para responder las preguntas. Además el alumno deberá presentar las respuestas acompañadas de gráficos en un formato interactivo para el lector, como lo puede ser a través de un html.

## Consigna práctico Análisis y Curación: Limpiando un Dataset
1. Importando los datos:
    - Verificar si no hay problemas en la importación: importar los datos, visualizarlos, análisis de tipos, corrección en los tipos de los datos de entrada.
    - Asegurar que el archivo sales posee Ids/Claves únicas. Para el resto de los archivos, ¿tenemos algún atributo que se comporte como clave única?, en caso positivo chequear que no se repite. En caso de no tener una clave única identificatoria, ¿sería relevante asignar una clave única a cada registro?, chequear que no existen datos duplicados para estos casos.
    - Despersonalizar los datos y guardarlos en un nuevo archivo. Tener en cuenta nunca modificar los datos crudos u originales.
2. Pasos necesarios para limpieza del dataset:
    - Etiquetas de variables/columnas: no usar caracteres especiales. Verificar que no haya problemas de codificación/encoding.
    - Tratar valores faltantes (NaN).
    - Codificar variables: las variables categóricas deberán ser tratadas como variables numéricas.
    - Verificar la consistencia de las variables: constatar que los valores de cada atributo tienen sentido, detectar valores que no son consistentes con el resto.
    - Identificar valores atípicos en nuestro dataset. ¿Qué es conveniente hacer con ellos? Evaluar cada caso.
    - Juntar las columnas de interés en un mismo DataFrame (Sales con Features). 
    - Para simplificar el problema resamplear los datos ¿Transformar Weekly sales en ventas mensuales?. Graficar la distribución de las ventas mensuales para cada año para 5 tiendas a elección. Comparar sus distribuciones. ¿Se reconoce alguna distribución conocida?
    - Analizar correlación entre número departamento y ventas semanales/mensuales, ¿posee alguna incidencia el número de departamento sobre las ventas?, en caso negativo eliminar esta variable de nuestros dataframes.
    - Una vez que tenemos las features de interés de nuestro set de datos, aplicar algún método de normalización sobre los mismos, para evitar tener un sesgo de unas variables sobre otra (se pueden utilizar técnicas como z-score/min-max scaling). Guardar el dataset normalizado con un nombre representativo.
    - Finalmente, reducir los features de interés mediante sus combinaciones lineales (aplicando Principal Component Analysis). Guardar el dataset con nombre representativo.
    - Enumere formas eficientes de guardado y acceso de grandes volúmenes de datos.
    - Guardar todos los archivos depurados con nombres representativos.

Bonus: entregar el práctico corriendo en una imágen de Docker.

## Consigna Práctico Introducción ML:
En esta materia puntual lo importante es que el estudiante aprenda a hacer la division de los datos, la elección del modelo, evaluación de metricas, independientemente de la complejidad del dataset. Es por esto que se toman para el análisis variables simples del dataset. De esta manera el estudiante puede hacer foco en los conceptos que se desean fijar.

Las variables a tratar serán:
### Grupo Alpha:
- Fecha y columna IsHoliday. El objetivo será construir un predictor que tome la fecha (tratada según criterio de los estudiantes) y prediga si en esa semana hay un feriado o no.

### Grupo Omega:
- Ventas, IsHoliday y columna IsMarkdown. El objetivo es tomar como entrada el valor de las ventas para una semana y la información de si tiene un día feriado, y predecir si hubo rebajas esa semana.

Actividades:
1. Importaciones. Seteo de semilla para reproducibilidad. Carga del Dataset. Selección y armado del subconjunto de las variables deseadas.
2. División de los datos en conjunto de entrenamiento y test. El conjunto de entrenamiento se utilizará para la creación y selección de los clasificadores. Una vez elegido el model, este set también los servirá para la selección de los hiperparámetros. Una vez entrenado el modelo, se utilizará el conjunto de test (conjunto de datos independiente) para la evaluación del modelo final.
3. Elección de un modelo. En este punto se deberán seguir los siguientes pasos:
    - Selección de hipótesis: elegir la función/modelo que se utilizará para la implementación del clasificador.
    - Selección del regularizador: analizar si es mejor regularizar con módulo o por cuadrados.
    - Selección de la función de costo con la cual se va a optimizar el modelo.
    - Para todos los casos justificar las selecciones.
4. Selección de hiperparámetros. Luego de seleccionar y setear el modelo que se utilizará, variar sus hiperparámetros y quedarse con la mejor combinación.
5. Evaluación del modelo final. Una vez seleccionados los hiperparámetros y entrenado el modelo, correrlo sobre el conjunto de test/evaluación. Utilizar las métricas que se crean convenientes. Siempre es bueno evaluar con más de una métrica. Que significa la acuracy de un modelo? En que se diferencian Precision y Recall? Cuando es conveniente usar cada una de estas métricas?
6. Es el umbral por default el mejor umbral de decisión? En caso contrario, cual es el valor del umbral óptimo?

# Consigna Práctico Aprendizaje Supervisado
En este trabajo, se utilizarán herramientas y conocimientos adquiridos en materias previas para la preparación de los datos y selección de parámetros pero se hará foco en la evaluación de diferentes modelos de apredizaje supervisado para la resolución de un problema más complejo.

La idea es que ambos grupos trabajen con variables diferentes para poder luego hacer una comparación entre ambos resultados:
### Grupo Alpha:
- Construir un modelo que prediga el valor de ventas (sales) en base a las features disponibles sin utilizar la fecha (usar numero de store, departamento, temperatura, tasa de desempleo, cpi, precio del combustible, columna is holiday y columna is markdown).

### Grupo Omega:
- Construir un modelo que prediga el valor de las ventas (sales), utilizando las variables anteriores, más el valor de la fecha (pre tratada correspondientemente).

Luego de estos dos análisis podremos analizar como afecta la variable fecha a nuestros resultados. Si bien se considera la variable fecha, no se está teniendo en cuenta la secuencia de los datos como lo haríamos en un análisis de series temporales. Simplemente tomamos el valor día, mes, año sin evaluar la secuencia de los datos que tenemos. Este modelo no es el ideal para este tipo de análisis, pero es el adecuado para aplicar en base a los conocimientos vistos en la materia.

## Actividades:
1. Cargar el dataset, quedarse con las columnas de interés, division de los datos en conjuntos de train, test.
2. Buscar la mejor representación para nuestras variables de entrada.
2. Armar un baseline para resolver inicialmente nuestro problema (un modelo simple, como una regresión lineal, el cual nos sirve para evaluar como van mejorando nuestros resultados).
3. ¿Cuáles son las mejores métricas para evaluar nuestros modelos predictivos?
4. Armar modelos más complejos (logistic regression, SVMs, decision trees), entrenarlos y evaluar el comportamiento de cada uno con la métrica definida en 3. Quedarse con el modelo que mejor ajuste.
5. Evaluar el mejor conjunto de hiperparámetros para el modelo elegido.
6. Correr las métricas de evaluación contra el modelo final. Analizar puntualmente los casos en los que la predicción difiere mucho del valor real, ¿Qué sucede en estos casos?

Bonus track (opcional): correr una LSTM con la columna fechas y sales como salidas. Las LSTM si tienen en cuenta secuencia de las fechas y probablemente mejoren significativamente los resultados.

Link útil para corrida de LSTM: https://towardsdatascience.com/playing-with-time-series-data-in-python-959e2485bff8

# Consigna Práctico Aprendizaje No Supervisado

En este práctico se aplicarán algoritmos de clustering a los datos que venimos trabajando. La mayor parte del esfuerzo no va a estar en que algoritmo de clustering aplicar, sino en el trabajo/selección de los datos de entrada, variación de parámetros y análisis de las soluciones obtenidas. Se trabajará sobre dos ejes centrales. Uno será la agrupación de los datos en base a las features para poder analizar si las mismas nos ayudan a inferir el rango por el cual se mueven las ventas. El otro tratará de la agrupación de los usuarios en base a las tiendas que frecuentan, y la creación de un sistema de recomendación en base a los perfiles encontrados luego de la agrupación.

## 1. Preparación de Dataset:

### Grupo alpha

Tomar los datos del archivo Sales y armar un Dataset con las siguientes características:

- Fecha de la semana correspondiente a la venta.
- Ventas. Para un análisis mas sencillo pasaremos la Weekly Sale a variable categórica. Teniendo en cuenta los valores máximos y mínimos de venta los dividiremos de forma tal que nos queden 3 categorías: venta baja, media y alta.
- Store.
- Departamento.
- Temperatura, precio del combustible, CPI, tasa de desempleo, es feriado o no, hubo rebaja o no correspondientes a cada fecha.

### Grupo omega:

Tomar los datos del archivo Usuarios. Se deberá pasar la variable de las tiendas que frecuentan los usuarios a un vector tipo "One Hot" para poder procesarlo. Es decir se tendrá:

- Nombre del usuario (desperzonalizado).
- Vector con dimension igual al número de tiendas, con un 1 sobre las tiendas que frecuenta el usuario y un 0 sobre las que no frecuenta.
    
## 2. Aplicación, optimización y evaluación de modelo de aprendizaje no supervisado:

### Grupo alpha:

- Tomar las features (sin fecha y sin ventas) y correr un algoritmo de clustering (recomendado K Means), buscando encontrar un patrón por el cual podamos agrupar los datos. 
- Correr el algoritmo para diferentes valores de número de clusters.
- ¿Cómo podríamos encontrar un valor óptimo de número de clusters? Encontrar dicho valor.
- ¿Se ha logrado tener clusters con cantidades similares de elementos? Análisis de los resultados en función del balanceo que presentan los clusters.
- Evaluar los resultados con la medida de pureza tomando a la variable categórica Ventas para la evaluación de la pureza dentro de cada cluster. ¿Hemos logrado encontrar un patrón que defina nuestras ventas?
- Aplicar PCA para disminuir la cantidad de features y evaluar si este cambio arroja mejores resultados.

### Grupo omega:

- Tomar el vector correspondiente a las tiendas y correr un algoritmo de clustering (recomendado K Means), buscando encontrar un patrón por el cual podamos agrupar los datos. 
- Correr el algoritmo para diferentes valores de número de clusters. 
- ¿Cómo podríamos encontrar un valor óptimo de número de clusters? Encontrar dicho valor. 
- ¿Se ha logrado tener clusters con cantidades similares de elementos? Análisis de los resultados en función del balanceo que presentan los clusters.
- Crear un sistema de recomendación en donde dado un usuario nuevo que entra al sistema, se lo asigna a un perfil de usuario y se le recomiendan las tiendas que corresponden a su perfil y que aún no ha visitado.

Material de lectura recomendado:

https://www.machinelearningplus.com/time-series/time-series-analysis-python/

https://towardsdatascience.com/playing-with-time-series-data-in-python-959e2485bff8


https://sebastianraschka.com/Articles/2014_about_feature_scaling.html