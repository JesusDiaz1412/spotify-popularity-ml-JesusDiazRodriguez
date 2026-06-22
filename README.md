#  Predicción de Popularidad en Spotify

Proyecto de Machine Learning para predecir la popularidad de canciones en Spotify a partir de sus características de audio, utilizando técnicas de regresión supervisada.

---

##  Descripción

Este proyecto aplica técnicas de aprendizaje supervisado sobre el [Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset) para modelar y predecir la variable `popularity` (0–100) de una canción en función de sus atributos de audio como `danceability`, `energy`, `loudness`, `tempo`, entre otros.

---

##  Objetivos

1. Realizar un análisis exploratorio de los datos (EDA) e identificar las features más relevantes para predecir popularidad.
2. Preprocesar el dataset: normalización, manejo de outliers y codificación de variables categóricas.
3. Entrenar y comparar al menos **2 técnicas de regresión**:
   - **Técnica 1:** Regresión Lineal / Polinomial (baseline)
   - **Técnica 2:** Regresión Ridge o Lasso (regularización)
4. Evaluar los modelos con métricas MSE, RMSE y R².

---

##  Estructura del Repositorio

```
spotify-popularity-ml/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── .gitkeep              # El CSV no se sube al repo (ver instrucciones abajo)
│
└── notebooks/
    ├── fase1_exploracion.ipynb     # Dataset, objetivos, cronograma, EDA inicial
    ├── fase2_preprocesamiento.ipynb  # Preprocesamiento + técnica base
    └── fase3_comparacion.ipynb     # Comparación de modelos + resultados finales
```

---

##  Dataset

- **Fuente:** [Kaggle — Maharshi Pandya](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
- **Tamaño:** ~114,000 canciones | 125 géneros musicales
- **Features principales:** `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`, `duration_ms`, `track_genre`
- **Target:** `popularity` (int, 0–100)

### ¿Cómo obtener el dataset?

```bash
# Opción 1: Kaggle API
kaggle datasets download -d maharshipandya/-spotify-tracks-dataset --unzip

# Opción 2: Descargar manualmente desde Kaggle y colocar el CSV en data/
```

---

##  Instalación

```bash
git clone https://github.com/[tu-usuario]/spotify-popularity-ml.git
cd spotify-popularity-ml
pip install -r requirements.txt
```

---

##  Cronograma

| Semana | Entregable | Estado |
|--------|-----------|--------|
| 1 | Avance #1: Dataset, objetivos y cronograma |  |
| 1 | Avance #2: Preprocesamiento + técnica base |  |
| 1 | Entrenamiento técnica 2 + tuning | |
| 2 | Comparación de modelos |  |
| 2 | Entrega final |  |

---

##  Dependencias

Ver `requirements.txt`

---

##  Autores

- [Jesús Díaz Rodríguez] — [UAEM, ICCBA, CINC, Lic. en Inteligencia Artificial / Machine Learning]
