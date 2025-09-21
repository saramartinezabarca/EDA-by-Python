# 📊 Proyecto de Análisis Exploratorio de Datos (EDA)

Este proyecto realiza un análisis exploratorio de dos datasets distintos:

1. **Customer Details (Excel con varias hojas, 2012–2014)**
2. **Bank Marketing – Bank Additional (CSV de la UCI Machine Learning Repository)**

El objetivo es practicar:
- Lectura de datos desde diferentes fuentes (Excel con múltiples hojas y CSV delimitado).
- Limpieza de datos (duplicados, nulos, tipos).
- Análisis descriptivo.
- Visualizaciones univariantes y bivariantes.
- Conclusiones sobre la calidad y utilidad de los datos.

---

## 📂 1. Customer Details (Excel)

### Lectura y limpieza
- El Excel contenía **3 hojas** (`2012`, `2013`, `2014`).
- Se verificó que todas se unieron correctamente en un único DataFrame → **43.170 registros**.
- Columnas finales: `Income`, `Kidhome`, `Teenhome`, `Dt_Customer`, `NumWebVisitsMonth`, `year`.
- Sin **nulos** ni **duplicados**.
- Los ceros son **valores válidos** (ej. 0 hijos, 0 visitas).

### Exploración univariante
- **Income**: rango 5.841–180.802, distribución casi uniforme y estable en los 3 años.
- **Kidhome / Teenhome**: distribuciones equilibradas (0, 1, 2 hijos en proporciones ~33% cada una).
- **NumWebVisitsMonth**: 1–32 visitas mensuales, dispersa pero sin relación con ingresos.
- **Dt_Customer**: altas estables entre 2012–2014.

### Exploración bivariante
- Income vs Hijos: no se observan diferencias claras en ingresos según número de hijos.
- Income vs Visitas web: no existe correlación.
- Hijos vs Año: proporciones estables.

### Conclusiones
- Dataset sintético, generado con fines didácticos.
- No refleja patrones reales de negocio, pero sirve para practicar:
  - Limpieza de datos.
  - Análisis de variables categóricas y numéricas.
  - Visualización comparativa por años.

---

## 📂 2. Bank Additional (CSV)

### Lectura y limpieza
- Archivo `bank-additional.csv`, separado por `;`.
- **41.188 registros**, **21 variables**.
- Variables incluyen: edad, estado civil, nivel educativo, ocupación, contacto, duración de campaña, etc.
- Objetivo principal: variable `y` (si el cliente suscribe o no un depósito a plazo).
- Se detectaron:
  - Variables categóricas con valores `"unknown"`.
  - Variables numéricas con rangos amplios (ej. edad 18–95, duración de llamada 0–4918s).
  - No hay duplicados significativos.

### Exploración univariante
- **Edad**: concentración en 30–40 años, pero con clientes hasta 90.
- **Duración de llamadas**: muy sesgada (la mayoría corta, pocas muy largas).
- **Estado civil y ocupación**: distribución heterogénea con categorías minoritarias.
- **Variable objetivo (`y`)**: muy desbalanceada (≈ 88% “no” vs 12% “sí”).

### Exploración bivariante
- Edad vs Suscripción: clientes de mediana edad tienden más al “sí”.
- Duración vs Suscripción: cuanto mayor la duración de la llamada, más probable el “sí”.
- Variables de campaña (`previous`, `pdays`, `campaign`) muestran alta asimetría.

### Conclusiones
- Dataset realista y útil para análisis de marketing.
- Retos principales:
  - Datos desbalanceados (predomina el “no”).
  - Outliers en duración de llamadas.
  - “Unknown” en variables categóricas.
- Ideal para practicar modelos de clasificación después del EDA.

---

## 📌 Resumen General del Proyecto
- **Customer Details (Excel):**  
  Datos sintéticos, perfectos para practicar limpieza y visualización, aunque sin insights reales.  

- **Bank Additional (CSV):**  
  Datos de marketing reales, con problemas de calidad típicos (outliers, desbalance, valores desconocidos). Mucho más útil para un análisis predictivo o segmentación de clientes.  

---

## 🚀 Herramientas utilizadas
- Python 3.x  
- Librerías: `pandas`, `matplotlib`, `seaborn`  

---

