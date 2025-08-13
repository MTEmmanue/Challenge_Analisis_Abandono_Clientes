# 📘 Informe Final: Challenge Telecom X – Análisis de Evasión de Clientes

## 🎯 Objetivo del Proyecto
Identificar los factores que influyen en la **cancelación de clientes (Churn)** en Telecom X, utilizando técnicas de ETL, análisis exploratorio y visualización de datos. El propósito es generar insights que ayuden a reducir la tasa de abandono.

---

## 🧾 Preparación de Datos

- **Fuente**: API pública en formato JSON.
- **ETL aplicado**:
  - Extracción y normalización de columnas anidadas (`customer`, `phone`, `internet`, `account`).
  - Unión de todas las tablas en un único DataFrame (`df_normalized`).
  - Limpieza de valores nulos y espacios en blanco, especialmente en `Charges.Total`.

---

## 📊 Análisis Exploratorio y Visualizaciones

### 🔹 Distribución de Abandono (`Churn`)
- Aproximadamente **26% de los clientes abandonaron**.
- El abandono se concentra en clientes con contratos mensuales y facturación electrónica.

### 🔹 Cargos Mensuales (`Charges.Monthly`)
- Clientes con **cargos bajos (~20-40 MXN)** tienden a permanecer.
- Clientes con **cargos altos (>100 MXN)** muestran mayor abandono.
- Gráfico KDE muestra densidades diferenciadas entre clientes que abandonan y los que no.

### 🔹 Tipo de Contrato (`Contract`)
- Contratos **mensuales** tienen la mayor tasa de abandono.
- Contratos **anuales o bianuales** presentan mayor fidelización.

### 🔹 Método de Pago (`PaymentMethod`)
- Métodos como **transferencia electrónica** y **tarjeta de crédito** tienen menor abandono.
- **Pago por cheque** muestra mayor abandono, posiblemente por menor digitalización.

### 🔹 Servicios Adicionales
- Clientes con **seguridad en línea, respaldo, soporte técnico y streaming** tienden a permanecer más tiempo.
- La falta de estos servicios correlaciona con mayor abandono.

### 🔹 Tenencia (`tenure`)
- Clientes con **menos de 12 meses** tienen mayor probabilidad de abandonar.
- La tenencia es uno de los **predictores más fuertes** del churn.

---

## 📈 Gráficos Clave Generados

| Gráfico | Insight Principal |
|--------|-------------------|
| Histograma de `Charges.Monthly` vs `Churn` | Cargos altos correlacionan con abandono |
| Gráfico de barras `Contract` vs `Churn` | Contratos mensuales tienen mayor churn |
| Boxplot `tenure` vs `Churn` | Tenencia baja = mayor abandono |
| Heatmap de correlaciones | `tenure`, `Charges.Total`, y `Contract` son variables relevantes |
| Countplot de `PaymentMethod` | Métodos digitales retienen más clientes |

---

## 🧠 Insights Estratégicos

- **Segmentación por contrato**: Ofrecer incentivos para migrar de contratos mensuales a anuales.
- **Optimización de precios**: Revisar planes con cargos altos que generan abandono.
- **Promoción de servicios adicionales**: Seguridad, respaldo y soporte técnico aumentan la retención.
- **Digitalización del pago**: Fomentar métodos electrónicos para mejorar la experiencia del cliente.

---

## ✅ Recomendaciones Finales

- Implementar un modelo predictivo de churn usando variables como `tenure`, `Contract`, `Charges.Monthly`, y `PaymentMethod`.
- Diseñar campañas de retención para clientes con baja tenencia y cargos altos.
- Evaluar la experiencia del cliente en contratos mensuales para detectar puntos de fricción.

---

## 📂 Recursos del Proyecto
