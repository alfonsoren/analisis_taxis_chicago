# Análisis de Viajes en Taxi en Chicago

El objetivo principal es analizar el comportamiento de los viajes en taxi en la ciudad de Chicago y evaluar si las condiciones climáticas afectan la duración de los viajes hacia el aeropuerto.

## 🧾 Descripción del Proyecto

Se realizó un análisis exploratorio y una prueba de hipótesis usando datos reales de viajes en taxi en Chicago durante noviembre de 2017.

### 📥 Extracción de Datos

Los datos fueron obtenidos inicialmente mediante **consultas SQL** realizadas sobre una base de datos estructurada. Los resultados de estas consultas se exportaron en archivos `.csv`, que posteriormente fueron utilizados en Python para el análisis.

### 📁 Archivos de datos

- `/datasets/project_sql_result_01.csv`: número de viajes por empresa de taxi el 15 y 16 de noviembre de 2017.
- `/datasets/project_sql_result_04.csv`: promedio de viajes finalizados en cada barrio de Chicago en noviembre de 2017.
- `/datasets/project_sql_result_07.csv`: viajes desde el Loop hasta el aeropuerto O’Hare, con duración y condiciones climáticas.

---

## 🧪 Paso 4: Análisis exploratorio de datos

1. **Importación de archivos y revisión de tipos de datos.**
2. **Limpieza de datos (detección de duplicados, valores nulos, formatos).**
3. **Análisis de las empresas de taxi con más viajes.**
4. **Identificación de los 10 barrios con mayor número de viajes finalizados.**
5. **Visualización de datos** con `matplotlib` y `seaborn`.

### 📊 Gráficos creados:

- Número de viajes por empresa de taxis.
- Los 10 barrios principales por número de finalizaciones.

### 📌 Conclusiones:

- Algunas empresas dominan claramente el volumen de viajes.
- Ciertos barrios concentran la mayoría de los viajes finalizados, lo que podría indicar zonas de alta demanda.

---

## 🧪 Paso 5: Prueba de hipótesis

Se evaluó la hipótesis:

> **"La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare cambia los sábados lluviosos."**

### ⚙️ Metodología

- Se clasificaron los viajes según las condiciones climáticas (`Good` o `Bad`).
- Se seleccionaron solo los sábados.
- Se aplicó la **prueba de Levene** para evaluar igualdad de varianzas.
- Se usó una **prueba de hipótesis (t-test de Welch)** debido a la posible diferencia de varianzas.

### 📌 Hipótesis planteadas

- **Hipótesis nula (H₀):** No hay diferencia significativa en la duración promedio de los viajes.
- **Hipótesis alternativa (H₁):** Sí hay una diferencia significativa en la duración promedio de los viajes.

### 🔍 Resultado

- Nivel de significancia: α = 0.05
- Resultado del valor p: *muy inferior a 0.05*, lo que llevó a rechazar la hipótesis nula.
- **Conclusión:** Hay evidencia estadísticamente significativa de que las condiciones climáticas influyen en la duración de los viajes los sábados.

---

## 🛠️ Tecnologías usadas

- SQL (PostgreSQL)
- Python 3.11
- Pandas
- Matplotlib / Seaborn
- Scipy (`stats.levene`, `ttest_ind`)


