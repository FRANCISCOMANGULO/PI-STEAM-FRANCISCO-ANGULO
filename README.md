### Proyecto Individual  Machine Learning Operation Steam
<p align="center">
  <img src="src/MLops.png" alt="Descripción de la i ">
</p>



## Comenzando 🚀

Este proyecto final es el proceso de ETL, EDA y ML de un conjunto de datasets de steam, con el fin de encontrar ciertos parametros y poner en practica lo aprendido,desde la extraccion de los datos que en este caso fue en formato json, hasta la limpieza y obtencion de los datos que necesitamos para aplicar nuestras funciones y llevarlas a deploy por medio de apis



### Proceso 📋

### ETL 🔧

El proceso de este proyecto se basa en de un conjunto de datos hacer una limpieza, transformalos y obtener la informacion mas importante.
En la parte de Extracción, Transformación y Carga (ETL) que se utiliza para analizar datos de juegos y usuarios en una plataforma de juegos [ETL](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/ETL_PI.ipynb)

1. **Extracción**: Los datos se extraen de varios archivos parquet que contienen información sobre los juegos y las reseñas de los usuarios. Los archivos se leen en DataFrames de pandas para su posterior procesamiento.

2. **Transformación**: Los datos se transforman de varias maneras. Por ejemplo, se filtran los datos por año, desarrollador y otros criterios. Se agrupan los datos para contar el número de juegos por desarrollador y año, y se calcula el porcentaje de juegos gratuitos. También se realizan análisis de sentimientos en las reseñas de los usuarios.

3. **Carga**: Ya con los datos listos, se cargan ala nube por medio de render.

Además, el código también incluye la implementación de un sistema de recomendación utilizando la biblioteca `surprise`. Este sistema de recomendación se entrena con los datos de las reseñas de los usuarios y se utiliza para predecir los juegos que un usuario podría preferir, todo esto puede ser visto en el siguiente archivo link.

### EDA 🖇️

En este trabajo, utilizaremos un conjunto de datos previamente recopilado para llevar a cabo un EDA completo. Exploraremos las dimensiones y estructura de los datos, identificaremos tendencias, patrones y posibles anomalías. Además, aplicaremos visualizaciones y estadísticas descriptivas para comunicar de manera efectiva los hallazgos, el link al archivo es [EDA](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/EDA_PI.ipynb).

El objetivo de este trabajo es doble. En primer lugar, pretendemos profundizar en la comprensión de un conjunto de datos específico y ofrecer una visión detallada de sus características clave. En segundo lugar, nuestro trabajo servirá como un recurso útil para aquellos interesados en aprender cómo llevar a cabo un EDA completo, destacando las técnicas y herramientas esenciales utilizadas en el proceso.

A medida que avancemos en este análisis, descubriremos no solo la riqueza de información contenida en nuestros datos, sino también la importancia de un EDA exhaustivo en la ciencia de datos y la toma de decisiones basada en datos. A través de visualizaciones convincentes y análisis rigurosos, esperamos proporcionar una ventana al fascinante mundo de la exploración de datos y al potencial que puede desbloquear para la comprensión y la mejora en diversas disciplinas.


## Desarrollo de funciones en fast api ⚙️

Para el desarrollo de las funciones que van a correr en fast api, las cuales despues deployamos en render son las siguientes y pueden verser desarroladas en el siguiente archivo [ML](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/ML.ipynb) :

1. `top_desarrolladores_recomendados(year)`: Esta función toma un año como entrada y devuelve los tres principales desarrolladores que tienen la mayor cantidad de juegos recomendados en ese año. Los datos se extraen de un DataFrame previamente cargado llamado `merged_df`.

2. `developer(developer_name)`: Esta función toma el nombre de un desarrollador como entrada y devuelve una tabla que muestra la cantidad de juegos lanzados por ese desarrollador cada año y el porcentaje de esos juegos que son gratuitos. Los datos se extraen de un DataFrame previamente cargado llamado `df_f1`.

3. `developer_reviews_analysis(desarrolladora)`: Esta función toma el nombre de un desarrollador como entrada y devuelve un resumen de las reseñas de los juegos de ese desarrollador, incluyendo la cantidad de reseñas positivas y negativas. Los datos se extraen de un DataFrame previamente cargado llamado `df_limpio`.

4. `user_entrenado(user_id)`: Esta función toma un ID de usuario como entrada y devuelve una lista de los cinco juegos que el modelo de recomendación predice que el usuario preferiría. El modelo de recomendación se entrena utilizando la biblioteca `surprise` y los datos de las reseñas de los usuarios.



## Despliegue en Render 📦

Al final, para hacer deploy de este proyecto, usamos Render, el cual crea una máquina virtual donde especificamos lo que usaremos para arrancar nuestra API. La etapa en este proceso fue complicada debido a los múltiples errores que se presentaron, pero al final pudo completarse con éxito y este es el [Render](https://pi-francisco-angulo.onrender.com) .

La elección de Render como plataforma de implementación fue impulsada por su capacidad para simplificar el proceso de implementación, ofreciendo una solución robusta para ejecutar nuestras aplicaciones en la nube. Al configurar la máquina virtual en Render, pudimos definir cuidadosamente los recursos y entornos necesarios para asegurar un funcionamiento óptimo de nuestra API. Esta capacidad de personalización es crucial, ya que nos permitió adaptar la infraestructura a las necesidades específicas de nuestro proyecto.

Sin embargo, no todo fue un camino sin obstáculos. Durante la fase de implementación en Render, nos encontramos con una serie de desafíos técnicos que requirieron soluciones creativas y una depuración cuidadosa. Errores de configuración, problemas de dependencias y ajustes en el entorno de ejecución contribuyeron a la complejidad del proceso. A pesar de estos desafíos, el equipo perseveró, aprovechando la documentación de Render y recursos en línea para abordar los problemas de manera efectiva. Finalmente, después de un esfuerzo conjunto y determinado, pudimos completar con éxito el despliegue de nuestra API en Render, listos para ponerla en producción y ofrecer nuestros servicios de manera eficaz.

## Construido con 🛠️

Las principales herramientas para contruir este proyecto fueron:

1. Python: Es el lenguaje de programación principal utilizado en este proyecto. Python es conocido por su sintaxis clara y legible, lo que lo hace ideal para proyectos de análisis de datos y aprendizaje automático.

2. Pandas: Es una biblioteca de Python que proporciona estructuras de datos y herramientas de análisis de datos de alto rendimiento y fáciles de usar. En este proyecto, se utiliza para manipular y analizar los datos.

3. FastAPI: Es un moderno y rápido (de alto rendimiento) marco web para construir APIs con Python 3.6+ basado en las anotaciones de tipo estándar de Python.

4. Surprise: Es una biblioteca de Python para construir y analizar sistemas de recomendación. En este proyecto, se utiliza para entrenar un modelo de recomendación que predice los juegos que un usuario preferiría.

Además, el proyecto también parece utilizar otras herramientas y bibliotecas que no se mencionan en el extracto proporcionado.

## Conclusión 🖇️


En conclusión, la implementación de ML Ops en el contexto de una plataforma de juegos como Steam es fundamental para optimizar la gestión de modelos de recomendación, detección de fraudes y otros sistemas de inteligencia artificial. ML Ops permite un despliegue más rápido y seguro de modelos, asegurando una experiencia de usuario más personalizada y segura. Además, facilita la escalabilidad y el mantenimiento continuo de estos sistemas, lo que resulta en un beneficio significativo para la plataforma y sus usuarios. La integración exitosa de ML Ops en Steam ejemplifica cómo esta metodología es esencial para el éxito en entornos empresariales impulsados por datos y aprendizaje automático.

### Enlaces ⚙️
[Render](https://pi-francisco-angulo.onrender.com)


[ETL](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/ETL_PI.ipynb)


[EDA](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/EDA_PI.ipynb)


[ML](https://github.com/FRANCISCOMANGULO/PI-STEAM-FRANCISCO-ANGULO/blob/main/ML.ipynb)



## Autore ✒️


⌨️ con ❤️ por [FRANCISCOMANGULO](https://github.com/FRANCISCOMANGULO) 😊
