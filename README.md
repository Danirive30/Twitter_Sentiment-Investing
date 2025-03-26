# Twitter Sentiment Investing Strategy

## Descripción
Este proyecto desarrolla una estrategia de inversión basada en el sentimiento de Twitter aplicado a acciones bursátiles. La metodología emplea datos de interacciones en Twitter para identificar las acciones con mayor interés social y formar una cartera optimizada.

## Objetivo
Utilizar datos de sentimiento en Twitter para seleccionar las acciones con mayor interacción y evaluar su rendimiento en comparación con el NASDAQ (QQQ).

## Pasos del Análisis

### 1. Carga de Datos de Sentimiento de Twitter
- Se carga el dataset `sentiment_data.csv`.
- Se establecen los índices `date` y `symbol`.
- Se calcula la razón de interacción (`engagement_ratio`).
- Se filtran las acciones con un volumen significativo de interacciones.

### 2. Agregación Mensual y Cálculo del Sentimiento Promedio
- Se agrupan los datos a nivel mensual.
- Se calcula el promedio mensual de `engagement_ratio`.
- Se asignan rankings según la razón de interacción.

### 3. Selección de las 5 Mejores Acciones Mensuales
- Se seleccionan las 5 acciones con mayor `engagement_ratio` cada mes.
- Se ajustan las fechas para que la selección de acciones comience al inicio del siguiente mes.

### 4. Construcción de la Cartera de Acciones
- Se crea un diccionario con las fechas de selección y las acciones elegidas.

### 5. Descarga de Precios de Acciones
- Se obtienen los precios históricos de las acciones seleccionadas usando Yahoo Finance (`yfinance`).

### 6. Cálculo del Retorno del Portafolio
- Se calculan los retornos logarítmicos diarios.
- Se rebalancea la cartera mensualmente promediando los retornos de las acciones seleccionadas.

### 7. Comparación con el NASDAQ
- Se descargan los precios de `QQQ`.
- Se calculan sus retornos y se comparan con la estrategia de inversión basada en Twitter.

## Requisitos
### Librerías Utilizadas
- `pandas`
- `numpy`
- `matplotlib`
- `yfinance`
- `datetime`
- `os`

### Instalación de Dependencias
Ejecutar el siguiente comando para instalar las librerías necesarias:
```bash
pip install pandas numpy matplotlib yfinance
```

## Ejecución del Proyecto
Para ejecutar el análisis, simplemente corre el script principal en Python. Asegúrate de actualizar la ruta del archivo `sentiment_data.csv` en tu directorio de trabajo.

```python
python twitter_sentiment_strategy.py
```

## Resultados y Conclusiones
Los resultados de la estrategia se comparan con el rendimiento del NASDAQ, permitiendo evaluar la viabilidad de usar datos de Twitter para tomar decisiones de inversión.

# Twitter_Sentiment-Investing
