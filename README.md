# Análisis Comparativo de Modelos para Predicción de Cancelación (Churn) – Telecom X

Este repositorio contiene un análisis comparativo de diferentes modelos de Machine Learning aplicados a la predicción de **cancelación de clientes (churn)** en **Telecom X**.  

El objetivo es evaluar el rendimiento de distintos algoritmos y entender los factores más relevantes que influyen en la decisión de un cliente de abandonar el servicio.

---

## 📊 Resultados de Evaluación de Modelos

Se entrenaron y evaluaron principalmente **Regresión Logística** y **Random Forest**, obteniendo los siguientes resultados:

| Métrica       | Regresión Logística | Random Forest |
|---------------|----------------------|---------------|
| Exactitud     | 0.9037              | 0.9010        |
| Precisión     | 0.8280              | 0.8158        |
| Recall        | 0.8021              | 0.8073        |
| F1-score      | 0.8148              | 0.8115        |

### Interpretación
- **Exactitud:** Ambos modelos muestran un rendimiento alto (~90%).  
- **Precisión:** La Regresión Logística es ligeramente mejor, reduciendo falsos positivos.  
- **Recall:** Random Forest destaca identificando más clientes que realmente cancelan (menos falsos negativos).  
- **F1-score:** Muy similares, con ligera ventaja para la Regresión Logística.  

📌 **No se evidencian problemas de overfitting o underfitting**, ya que las métricas son consistentes.

---

## 🔍 Análisis de Variables Relevantes

### Regresión Logística
- **Coeficientes positivos (↑ churn):**
  - *Monthly Charges* → Cargos altos aumentan la probabilidad de cancelación.  
  - *Senior Citizen* → Adultos mayores tienen mayor riesgo de churn.  
- **Coeficientes negativos (↓ churn):**
  - *Tenure* → Clientes con mayor antigüedad tienden a permanecer.  
  - *Total Charges* → Clientes con alto gasto acumulado presentan menor churn.  

### Random Forest
- **Variables más importantes:**
  - *Tenure* → Factor más relevante en la segmentación de clientes.  
  - *Monthly Charges* → Altamente influyente en la decisión de cancelar.  
  - *Contract Type* → Contratos a largo plazo reducen la probabilidad de churn.  
  - *Payment Method* → Algunos métodos se asocian a mayor cancelación.  

---

## 📈 Recomendaciones Estratégicas

1. **Retención temprana:**  
   - Implementar programas de bienvenida y acompañamiento en los **primeros meses**, que son críticos para reducir el churn.  

2. **Ofertas personalizadas:**  
   - Paquetes y descuentos para clientes con **cargos mensuales elevados**.  
   - Planes específicos para **adultos mayores**, grupo con alta tasa de cancelación.  

3. **Fomentar contratos a largo plazo:**  
   - Incentivar con beneficios exclusivos para reducir la rotación de clientes mes a mes.  

4. **Optimizar métodos de pago:**  
   - Analizar qué medios están asociados a mayor churn y promover los más estables.  

---

## 🛠️ Modelos Evaluados y Técnicas de Interpretación

- **Regresión Logística:** coeficientes lineales (`coef_`).  
- **Random Forest:** importancia de variables (`feature_importances_`).  
- **KNN:** análisis indirecto mediante escalado y reducción dimensional (PCA).  
- **SVM:** coeficientes para kernel lineal; interpretaciones con LIME/SHAP en no lineales.  
- **Otros (XGBoost, Redes Neuronales):** importancias basadas en ganancia, frecuencia o SHAP.  

---

## 📌 Conclusiones

- Los **factores más influyentes** en la cancelación son:  
  - **Tenure (tiempo de permanencia)**  
  - **Monthly Charges (cargos mensuales)**  
  - **Senior Citizen (clientes mayores de 65 años)**  
  - **Tipo de contrato y método de pago**  

- Ambos modelos evaluados son altamente efectivos (~90% de exactitud).  
- Dependiendo del objetivo del negocio:  
  - **Regresión Logística** si se desea **minimizar falsos positivos**.  
  - **Random Forest** si se desea **minimizar falsos negativos**.  
- Un enfoque combinado (*ensemble*) puede aprovechar lo mejor de ambos.  

---

## ⚙️ Tecnologías Utilizadas

- Python 3.x  
- Pandas / NumPy  
- Scikit-learn  
- Matplotlib / Seaborn  
- SHAP / LIME (para interpretabilidad)  

---
