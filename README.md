# Practica Kaggle APC UAB 2022-23
### Nom: Erik Villarreal Gallardo
### DATASET: Heart Failure Prediction
### URL: [kaggle](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data)
## Resumen
El dataset utiliza datos de pacientes con falladas de corazon que han estado ingresados.
Tenemos 299 muestras con 13 atributs. 6 de ellos son binarios, el resto son numericos y tienen distintos rangos.
### Objetivos del dataset
Queremos aprender que relacion tienen estos atributos del dataset con la mortalidad de los pacientes.
## Experimentos
Durante el recorrido de esta practica se han realizado diversos experimentos.
### Preprocesado
Hemos analizado el rendimiento de los modelos sin eliminar outliers y ha sido bastante malo. De forma que se ha decidido eliminar estos outliers.
Los resultados han mejorado considerablemente despues de esto.

Se han normalizado los datos, esto ha supuesto que nuestros modelos no tendrian que trabajar con datos en distintos rangos lo cual podria influir en los resultados.
### Modelo
La metrica que utilizamos es el $F_1$ score.

| Modelo | Hiperparametros | Metrica | Tiempo |
| -- | -- | -- | -- |
| [Decision Tree](models/) | criterion="entropy" | 64% | 600ms |
| Random Forest | 100 Trees | 54% | 100ms |
| KNeighbors | n_neighbors:3 | 61% | 200ms |
| SVM | kernel: rbf C:1000 gamma:0.001 | 59% | 200ms |
| [ADA Boost](models/) | default | 64% | 100ms |
| -- | -- | -- | -- |
| [Random Forest de prasadposture121](https://www.kaggle.com/code/prasadposture121/heart-failure-prediction#Heart-Failure-Prediction) | default | 52% | 100ms |
| [Logistic Regression de nayansakhiya](https://www.kaggle.com/code/nayansakhiya/heart-fail-analysis-and-quick-prediction) | default | 74% | 100ms |

## Conclusiones
El mejor modelo que se ha conseguido ha sido el Decision Tree y el ADA Boost. Por las caracteristicas de cada modelo el ADA Boost parece ser el mas apropiado ya que se pueden predecir las probabilidades de que una muestra pertenezca a una clase o a otra.
A comparacion con el estado del arte y de otros trabajos que hemos analizado nuestro modelo obtiene resultados medios.
## Ideas para trabajar en un futuro
Creo que seria interesante investigar mas sobre este tipo de datasets y poder encontrar un modelo que pueda obtener unas predicciones mucho mejores.
## Llicencia
El projecte se ha desarrollado bajo la licencia Apache.