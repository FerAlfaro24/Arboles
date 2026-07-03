# Actividad 2 - Arboles de decision y Naive Bayes (Iris)

Repositorio con los entregables de la Actividad 2 (arboles de decision ID3/J48
y Naive Bayes sobre el dataset Iris), dentro de la carpeta `arboles/` segun lo
solicitado.

## Contenido (`arboles/`)

| Carpeta | Entregable | Contenido |
|---|---|---|
| `punto2_id3/` | 1. PDF con el resultado de ID3 sobre Iris | `ID3_Iris_reporte.pdf` (reporte) + `ID3_Iris_resultado.xlsx` (datos, arbol, clasificacion y matriz de confusion con formulas) |
| `punto4_j48_weka/` | 2. Reporte de J48 en Weka | `J48_Weka_reporte.pdf` |
| `punto9_colab/` | 3 y 7. Liga al cuaderno Colab | `iris_arboles_naivebayes.ipynb` — abrir en Colab: https://colab.research.google.com/github/FerAlfaro24/Arboles/blob/main/arboles/punto9_colab/iris_arboles_naivebayes.ipynb |
| `punto6_naivebayes_r/` | 4. Rmd y html del punto 6 | `punto6_naiveBayes_iris.Rmd` (codigo R) + `punto6_naiveBayes_iris.html` (resultado real, generado con Knit en RStudio) |
| `punto2_id3/ID3_Iris_resultado.xlsx` (hojas `muestra_NB_20` y `matriz_confusion_NB`) | 5. Matriz del punto 7 | Muestra de 20 observaciones y matriz de confusion de Naive Bayes manual |
| `punto8_naivebayes_fci/` | 6. Rmd y html del punto 8 | `punto8_actividadNBFCI.Rmd` + `punto8_actividadNBFCI.html` (dataset ficticio FCI, resultado real generado con Knit) |

## Nota sobre los archivos .Rmd

Los `.html` de los puntos 6 y 8 fueron generados presionando **Knit** en
RStudio (R 4.6.1), por lo que reflejan la salida real de R, no una estimacion.
Lo mismo aplica al reporte de J48: se ejecuto en vivo en Weka 3.8.7 sobre
`iris.arff` (10-fold cross-validation).

## Resumen de resultados

- **ID3 (datos discretizados, punto 2):** atributo raiz `petalw`, accuracy
  97.33% (146/150).
- **J48 en Weka (punto 4):** atributo raiz `petalwidth <= 0.6`, accuracy
  96.0% (144/150), 5 hojas. Ejecucion real verificada en Weka.
- **Naive Bayes manual (punto 7, muestra de 20):** accuracy 90% (18/20).
- **Naive Bayes en R para Iris (punto 6):** accuracy real 91.11% (41/45)
  sobre particion 70/30 (`createDataPartition`, `set.seed(123)`).
- **Naive Bayes FCI (punto 8):** accuracy real 33.33% (2/6 en la matriz de
  confusion; algunas de las 8 observaciones de prueba quedan sin predecir por
  niveles no vistos en el entrenamiento, esperable con solo 40 datos) sobre 40
  estudiantes ficticios con particion 80/20 (`set.seed(99)`).

En todos los casos, la principal fuente de error se concentra entre
`Iris-versicolor` y `Iris-virginica`, el patron de confusion clasico del
dataset Iris.
