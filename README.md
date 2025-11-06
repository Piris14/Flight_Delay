# ✈️ Predicción de Retrasos en Vuelos

Proyecto de **predicción de retrasos en vuelos** a partir de datos históricos de la aviación comercial en EE. UU.  
Se explora, visualiza y modela la información para predecir si un vuelo tendrá un **retraso superior a 30 minutos**.

---

## 📊 Objetivos

1. Analizar patrones de retrasos por aerolínea, aeropuerto y época del año.  
2. Crear un modelo predictivo que clasifique vuelos en **puntuales** o **retrasados**.  
3. Visualizar los aeropuertos y rutas con mayores demoras.

---

## 🧩 Dataset

El dataset original contiene información de más de **3 millones de vuelos** (muestra reducida utilizada en GitHub).  
Entre las principales variables destacan:

| Variable | Descripción |
|-----------|--------------|
| `AIRLINE` | Aerolínea |
| `ORIGIN`, `DEST` | Aeropuertos de origen y destino |
| `CRS_DEP_TIME` | Hora programada de salida |
| `ARR_DELAY` | Retraso en minutos (variable continua) |
| `IS_DELAYED` | Variable objetivo (1 si el retraso > 30 min) |
| `MONTH`, `DAY_OF_WEEK` | Fecha desglosada |
| `DISTANCE` | Distancia del vuelo (millas) |

---

## ⚙️ Procesamiento de Datos

1. Conversión de fechas (`FL_DATE`) a día, mes y día de la semana.  
2. Creación de nuevas variables:
   - `IS_WEEKEND` (fin de semana)
   - `IS_SUMMER` (meses de verano)
   - Promedios de retraso por aerolínea, aeropuerto de origen y destino.
3. Escalado de variables numéricas y balanceo de clases (oversampling del conjunto de entrenamiento).

---

## 🤖 Modelos Entrenados

Se compararon tres modelos principales:

| Modelo | AUC-ROC |
|--------|----------|
| **Regresión Logística** | 0.616 |
| **Random Forest** | 0.632 |
| **XGBoost (opt.)** | **0.68** |
| **LightGBM (opt.)** | 0.677 |

El modelo **XGBoost optimizado** obtiene el mejor rendimiento, mostrando una capacidad razonable para distinguir entre vuelos con y sin retraso.

---

## 📊 Visualización en Tableau

He creado un dashboard interactivo en Tableau para visualizar los retrasos de vuelos por aerolínea, aeropuerto y mes.

👉 **Ver dashboard en Tableau Public:** [Flight Delays Dashboard]((https://public.tableau.com/app/profile/iris.mu.oz/viz/Retrasosenvuelos_17623637077250/Dashboard1))

El dashboard incluye:
- Retrasos promedio por aerolínea ✈️  
- Top aeropuertos con mayor demora 🏙️  
- Tendencias mensuales 📆  
- Mapa interactivo de retrasos 🌎  


---

## 🧠 Conclusiones

- Los **retrasos se concentran** en determinados aeropuertos y rutas de alta densidad.  
- Las variables de **hora, día de la semana y aerolínea** son determinantes para la predicción.  
- A pesar del desbalance de clases, el modelo XGBoost logra resultados estables.  
- Mejoras futuras: incorporar **datos meteorológicos** y variables de tráfico aéreo.

---

## 🧰 Requisitos

Archivo `requirements.txt`:

```txt
pandas
numpy
scikit-learn
matplotlib
seaborn
xgboost
lightgbm
folium
```
---

## 🧑‍💻 Estructura del Proyecto
```
Flight_Delay/
│
├── images/                # Gráficas y mapas del análisis
├── Notebooks/             # Jupyter notebooks principales
│   └── Proyecto.ipynb
├── Visuals/               # Archivos HTML con mapas interactivos
├── README.md
└── requirements.txt

```
---

## 🚀 Cómo Ejecutar

1. Clonar el repositorio
   ```bash
   git clone https://github.com/tu_usuario/Flight_Delay.git
   cd Flight_Delay
   ```
2. Instalar dependencias
   ```
   pip install -r requirements.txt
   ```
3. Ejecutar el notebook
   ```
   jupyter notebook Notebooks/Proyecto.ipynb
   ```
---


## 👨‍💻 Autor
- Nombre: Iris Muñoz Herrera
- Email: irismunozherrera@gmail.com
- LinkedIn: https://www.linkedin.com/in/iris-muñoz-herrera-554baa198/ 


