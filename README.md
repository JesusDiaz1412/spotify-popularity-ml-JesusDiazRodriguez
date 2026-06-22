# Predicción de Popularidad en Spotify

Proyecto de Machine Learning para predecir la popularidad de canciones en Spotify a partir de sus características de audio, utilizando técnicas de clasificación supervisada multiclase.

---

## Descripción

Este proyecto aplica técnicas de aprendizaje supervisado sobre el [Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset) para modelar y predecir el **rango de popularidad** de una canción en función de sus atributos de audio como `danceability`, `energy`, `loudness`, `tempo`, entre otros.

### Cambio de enfoque: de regresión a clasificación

El proyecto comenzó planteado como un problema de **regresión continua** sobre la variable `popularity` (0–100). Tras el análisis exploratorio de la Fase 1, se decidió reformular el problema como una **clasificación multiclase** por las siguientes razones:

1. **Distribución del target:** la variable `popularity` presenta un fuerte sesgo hacia valores bajos, con una alta concentración de canciones con popularidad cercana a 0. Predecir el valor exacto en ese contexto introduce ruido innecesario.
2. **Utilidad práctica:** desde una perspectiva de negocio, conocer el *rango* de popularidad (baja / media / alta) es más accionable que un valor numérico exacto.
3. **Robustez de las métricas:** las métricas de clasificación (accuracy, F1-score, matriz de confusión) son más interpretables y permiten un análisis de errores por clase, lo cual enriquece la comparación entre modelos.
4. **Compatibilidad con técnicas más diversas:** el cambio permite incorporar algoritmos como Support Vector Classifier (SVC), que son referentes en problemas de clasificación.

La variable `popularity` se transforma en una variable categórica con rangos definidos, manteniendo el resto del pipeline (limpieza, encoding, escalado) bajo las mismas buenas prácticas de ingeniería.

---

## Objetivos

1. Realizar un análisis exploratorio de los datos (EDA) e identificar las features más relevantes para predecir el rango de popularidad.
2. Preprocesar el dataset: limpieza, codificación de variables categóricas (Target Encoding sin data leakage) y escalado.
3. Entrenar y comparar **3 técnicas de clasificación**:
   - **Modelo base:** Decision Tree Classifier
   - **Modelo 2:** Random Forest Classifier
   - **Modelo 3:** Support Vector Classifier (SVC)
4. Evaluar los modelos con métricas Accuracy, F1-Score (macro y weighted) y matriz de confusión.

---

## Estructura del Repositorio

```
spotify-popularity-ml/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── .gitkeep              
│
└── notebooks/
    ├── 01_fase1_eda.ipynb              # Dataset, objetivos, cronograma, EDA inicial
    ├── 02_fase2_preprocessing.ipynb    # Preprocesamiento + modelo base
    └── 03_final_classification.ipynb   # Clasificación multiclase + comparación de 3 modelos
```

---

## Dataset

- **Fuente:** [Kaggle — Maharshi Pandya](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
- **Tamaño:** ~114,000 canciones | 125 géneros musicales
- **Features principales:** `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`, `duration_ms`, `track_genre`
- **Target original:** `popularity` (int, 0–100)
- **Target transformado:** variable categórica multiclase con rangos de popularidad

### ¿Cómo obtener el dataset?

```bash
# Opción 1: Kaggle API
kaggle datasets download -d maharshipandya/-spotify-tracks-dataset --unzip

# Opción 2: Descargar manualmente desde Kaggle y colocar el CSV en data/
```

---

## Instalación

```bash
git clone https://github.com/[tu-usuario]/spotify-popularity-ml.git
cd spotify-popularity-ml
pip install -r requirements.txt
```

---

## Cronograma

| Semana | Entregable | Estado |
|--------|-----------|--------|
| 1 | Avance #1: Dataset, objetivos y cronograma | Completado |
| 1 | Avance #2: Preprocesamiento + técnica base | Completado |
| 1 | Entrenamiento técnicas finales + tuning | En curso |
| 2 | Comparación de modelos | Pendiente |
| 2 | Entrega final | Pendiente |

---

## Dependencias

Ver `requirements.txt`

---

## Autores

- [Jesús Díaz Rodríguez] — [UAEM, ICCBA, CINC, Lic. en Inteligencia Artificial / Machine Learning].
