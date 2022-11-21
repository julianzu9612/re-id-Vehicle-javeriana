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



