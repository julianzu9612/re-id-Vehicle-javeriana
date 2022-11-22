# re-identificacion-Vehículos-javeriana

**Prueba de Concepto re - identificación de vehículos**


 
Diego Fabián Barreto Bejarano
Julián David Zuluaga Ospina
 

Pontificia universidad Javeriana
Facultad de ingeniería 
Maestría Analítica para la Inteligencia de Negocios
2022 



**Resumen: **
 
En el ejercicio de analítica de clientes que visiten un establecimiento es de vital importancia
conocer si un cliente entró al negocio, si compro y el tipo de transacciones con el fin de
poder hacer perfilamiento del cliente y entre otras cosas, hacer cross selling y up selling.
Para esta labor la única forma es llenar una base de datos con las diferentes transacciones
y fechas de visitas de cliente. Enfocándose en un negocio de estaciones de servicio, es muy
poco común que se haga esta práctica, entre otras razones porque implica una dificultad
técnica importante, a no ser que se destinen recursos manuales para tal propósito,
elemento que no suelen estar dispuestos las administraciones de dichos comercios.
Para tal labor, se instaura el uso de tecnologías de visión por computador que automaticen
el proceso, este procedimiento de identificar un vehículo y cruzarlo con una base de datos
para saber qué cliente es, se conoce como re-identificacion de vehículos.
El presente trabajo busca resolver este problema mediante la implementación de técnicas
de visión por computador y Deep Learning. Teniendo a consideración que uno de los
objetivos y retos principales es el no uso de la placa como información para el modelo,
teniendo en cuenta que la empresa asesorada ya cuenta con algoritmos de este estilo.
Para la realización del modelo se busca replicar la arquitectura de un paper llamado: “TBENet:

A Three-Branch Embedding Network With Part-Aware Ability and Feature
Complementary Learning for Vehicle Re-Identiﬁcation” en donde se logró una solución con
muy buenas métricas de desempeño que pueden complementar algoritmos actuales con el
uso de placa para mejorar el accuracy en momentos donde quizás está no sea del todo
visible.


Teniendo presente que la empresa IGG cuenta actualmente con algoritmos de re identificación de
vehículos robustos, se plantea, como se ha anunciado anteriormente, el modelamiento de un
algoritmo que pueda funcionar sin informacion de la placa, únicamente con variables visuales del
vehículo, para este propósito la empresa sugirió basarse en el papper de Enero 2022:
TBE-Net: A Three-Branch Embedding Network With Part-Aware Ability and Feature
Complementary Learning for Vehicle Re-Identiﬁcation.
El cual es, a la fecha, la solucion más novedosa en el estado del arte en cuanto a modelos de reidentificacion
vehicular,
utilizando
arquitecturas
de Deep
Learning
mediante
uso
de CNN.

Para
tal
propósito
se
diseñó
el
siguiente
pipeline:



![image](https://user-images.githubusercontent.com/94332280/203133977-5ccd629b-5f06-4836-bd87-58db96a10398.png)

La arquitectura propuesta por el paper base  “TBE-Net: A Three-Branch Embedding Network
With Part-Aware Ability and Feature Complementary Learning for Vehicle Re-Identiﬁcation”, 
está estructurada de la siguiente manera; inicia con una red pre entrenada de Backbone, de la cual
se obtiene la entrada para las siguientes redes, la segunda parte se compone de tres ramas. La
siguiente gráfica muestra la arquitectura planteada por el paper base. 

![image](https://user-images.githubusercontent.com/94332280/203134203-d8ce586f-c9ad-4711-b38e-eeb3ad308e95.png)


Este proyecto cuenta con seis notebooks, en los cuales se trabajaron diferentes partes de proyecto, como se describen a continuación.
a.	Local Brach prep: este notebook continue la extracción de las imágenes del data lake asociándolas con las respectivas coordenadas de cada mascara, luego se realiza el proceso de  excluir la información que no hacia parte de estas y  se ajusta el tamaño al requerido por la ResNet50 de 512X512X3.
b.	Trabajo_de_grado_fase1_cb1: este notebook contiene el  cargue del data set, la construcción de la arquitectura de la primera red de la rama complementaria y adicionalmente, se entrena la red con el data set de muestra de la fase 1 del diseño del experimento.
c.	Trabajo_de_grado_fase1_datapreparation: en este notebook se extraen las imágenes del data lake y son ubicadas en una carpeta por vehículo para el cargue del data set de entrenamiento con la función de ImageDataGenerator.
d.	Trabajo_de_grado_fase1_lb: este notebook contiene el  cargue del data set, la construcción de la arquitectura de red de la rama local y el  entrenamiento de  la red con el data set de muestra de la fase 1 del diseño del experimento.
e.	Trabajo_de_grado_fase1_cb2_cb3_g: este notebook abarca el cargue del data set, la construcción de la arquitectura de las redes dos y tres de la rama complementaria y la red de la rama global y también, el entrenamiento y sintonización de cada red. Se agrupan en el mismo notebook porque son las red a las cuales se les iba a realizar el proceso de sintonización.
f.	Trabajo_de_grado_fase2_cb1_cb2_g: en este notebook se pone en marcha la fase dos del diseño del experimento, el cual consiste en  entrenar las redes de manera independiente con el data set de datos sintéticos, para identificar el comportamiento de cada red con un mayor número de imágenes.


