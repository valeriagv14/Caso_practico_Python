# Caso_practico_Python
Aquí se paresenta el caso práctico del módulo de Python donde se analiza la situación de un grupo de personas de 18 a 59 años en relación con su uso de teléfono móvil y aplicaciones.

1.	Descripción del problema:
Se tiene una base de datos con 1,000 registros de personas que poseen un teléfono móvil, las cuales están en el rango de edad entre 18 años hasta 59. Se tiene la columna de horas, género del usuario, horas usadas en aplicaciones, horas usadas frente a la pantalla móvil, número de aplicaciones usadas, horas usadas en redes sociales, horas usadas en aplicaciones de productividad, horas usadas en videojuegos y la locación de cada uno d ellos usuarios registrados.
Con esta base de datos se pretende responder a la siguiente pregunta: ¿qué tipo de aplicación utilizan más este grupo de personas?, siendo de aquí que se pueden derivar otras preguntas como; ¿usan más el teléfono los hombres o las mujeres?; ¿cuántas horas en promedio pasan frente a la pantalla móvil estas personas?, ¿de qué edad son las personas que más utilizan el celular?, etc.

2.	Preparación de los datos:
Se verificó la información por medio de la función print(df.info()), para asegurar que no haya valores nulos y se puede trabajar con la base de datos sin alteraciones, igualmente se descubrió que se tienen datos int, object y float.

3.	Análisis exploratorio de datos (EDA):
Por medio de la función print(df.describe()) se visualizó el resumen rápido del la base de datos, con esto se corroboró que son 1,000 registros, siendo la edad mínima 18 y la máxima 59. 
Se aprecia que el promedio de las horas utilizadas en aplicaciones es de 6.40 hrs, con una mínima de 1 hr y una máxima de 11.97 hrs.
En el caso de las horas frente a la pantalla se observa un promedio de 7.69 hrs, con una mínima de 1.01 hr y una máxima de 14 hrs.
En la cantidad de aplicaciones descargadas por celular, el promedio es de 16.64, la mínima de 3 y la máxima de 69.
Este grupo de personas dedica en promedio 2.45 horas a estar en redes sociales, una mínima de 0 hrs y una máxima de 4.99 hrs.
Por su parte, el promedio de horas que se usan en aplicaciones productivas es de 2.49 hrs, con una mínima de 1.44 hrs y una máxima de 5 hrs.
Por último, el promedio de las horas utilizadas en videojuegos es de 2.47 hrs, con una mínima de 0.01 hrs y una máxima de 5 hrs.
Por medio de la función filtered_data = (df [‘Gender’].value_counts()) y print(filtered_data), se descubrió que son 517 hombres en este estudio y 483 mujeres. También con esta función se descubrió que 243 personas son de Nueva York, 199 de Phoenix, 192 de Chicago, 185 de Los Ángeles y 181 de Houston.
Se creó la siguiente gráfica para visualizar el promedio de uso de redes sociales por edad:
 ![image](https://github.com/user-attachments/assets/e597b157-32c8-4824-b3a9-e73cc7d1bd6d)
Se aprecia que a la edad de 40 años es cuando menos actividad en redes sociales hay entre el grupo observado, siendo las personas de 47 quienes más las usan.
También del uso de aplicaciones productivas por edad:
![image](https://github.com/user-attachments/assets/17280e40-fcb2-4bfa-85e6-c24f700711a2)
Siendo las personas de 59 años quienes menos usan aplicaciones productivas, siendo los de 37 y 40 quienes más las usan.
Y, del uso de videojuegos por edad:
![image](https://github.com/user-attachments/assets/c1f5a7ba-2410-4277-9a14-58e1332523cf)
Se observa que las personas cerca de los 48 son quienes menos utilizan videojuegos, mientras que las personas de 56 son quienes más juegan.

4.	Modelado predictivo:
A través de una regresión lineal se puede apreciar que hay mucha dispersión entre las horas de uso en redes sociales y la edad. En todas las edades se muestran diferentes horas de uso en redes sociales. 
 ![image](https://github.com/user-attachments/assets/709080b4-17fd-4980-8ad4-a4b81dbb0f2d)
También se hizo una regresión lineal del uso de redes sociales y las horas jugando videojuegos. 
![image](https://github.com/user-attachments/assets/5a140a20-660a-4e4c-bc06-b401164fd634)

5.	Evaluación del modelo:
Se evaluó el modelo de horas de videojuegos, horas en redes sociales y locación de los usuarios. Se obtuvieron los siguientes resultados:
Mean Squared Error: 2.1863858658323325
R² Score: -0.020205041276287528
Por lo cual se concluye que hay dispersión en los datos.

6.	Visualización de resultados:
Añadiendo a todas las gráficas anteriores, se decidió crear una gráfica de los errores residuales del modelo antes mencionado.
![image](https://github.com/user-attachments/assets/5f116453-cb6b-475f-b8a0-05d1817ed4df)
También una gráfica de predicciones versus realidad.
![image](https://github.com/user-attachments/assets/28547a64-af4b-4b7c-9328-50de9685c314)

7.	Conclusiones:
Se concluye que en este grupo de estudio hay mucha dispersión en la información, tanto las edades son muy variables, como los usos que toma cada sujeto ya sea hombre, mujer, de 18 años, 30, 40 o 50. Los datos no arrojaron tendencias a un mayor uso de ciertas aplicaciones de acuerdo con ciertas edades o género.
Se recomienda extender la base de datos con rangos de edades seccionadas, considerar incluso personas que no se encuentren dentro del concepto de “población activa”, es decir, que no estén laborando o no estén en edad de laborar, para poder buscar patrones dentro de otros rangos de edad y tener más marcadas las comparativas.

8.	Despliegue del modelo:
Un despliegue de modelo requiere de machine learning, lo que podría permitir crear una API para interactuar con él y construir una interfaz de usuario de ser necesario. Usar servicios en la nube facilita el despliegue, es necesario monitorear el rendimiento del modelo y realizar mantenimiento. Pero, previo a esto, se requiere que el modelo este perfectamente entrenado y se haya evaluado.
