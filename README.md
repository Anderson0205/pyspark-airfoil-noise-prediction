# Predicción de Ruido Aerodinámico con PySpark

Proyecto de ingeniería de datos y Machine Learning desarrollado con **PySpark MLlib**, orientado a la predicción del nivel de ruido aerodinámico a partir de características físicas de perfiles aerodinámicos.

El proyecto implementa un flujo completo de preparación de datos, entrenamiento, evaluación y persistencia de un modelo de regresión lineal.

## Tecnologías

Python · PySpark · Apache Spark · Spark MLlib · Parquet · Docker · JupyterLab

## Flujo del proyecto

```text
Dataset CSV
     ↓
Limpieza y transformación (ETL)
     ↓
Almacenamiento en Parquet
     ↓
VectorAssembler
     ↓
StandardScaler
     ↓
Regresión lineal
     ↓
Evaluación del modelo
     ↓
Persistencia y reutilización
```

## Resultados

El modelo fue entrenado utilizando el 70 % de los datos y evaluado con el 30 % restante.

| Métrica | Resultado |
| ------- | --------: |
| MSE     |     25.00 |
| MAE     |   3.91 dB |
| R²      |      0.50 |

El modelo explicó aproximadamente el **50 % de la variabilidad del nivel de ruido**, con un error absoluto promedio de 3.91 dB. Estos resultados representan un rendimiento moderado y ofrecen oportunidades de mejora.

## Ejecución

El entorno se ejecuta mediante Docker Compose.

Configura la URL del dataset en un archivo `.env`, tomando como referencia `.env.example`.

```bash
docker compose up --build -d
```

Accede a JupyterLab en:

`http://localhost:8889`

El desarrollo completo se encuentra en `notebooks/airfoil_noise_prediction.ipynb`.

## Datos

El proyecto utiliza una versión modificada del conjunto de datos **Airfoil Self-Noise**, basado en el dataset de Brooks, Pope y Marcolini (NASA), disponible en el [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/291/airfoil+self+noise), bajo licencia CC BY 4.0.

Los datos originales del laboratorio y los modelos generados no se incluyen en este repositorio.
