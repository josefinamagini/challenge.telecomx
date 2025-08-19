# 📉 TelecomX – Análisis de Churn (LATAM)

Este repositorio resume el trabajo del **Challenge TelecomX** para analizar la evasión de clientes (*churn*) y extraer recomendaciones accionables. El objetivo es **entender los factores que explican por qué los clientes se van** y proponer tácticas para reducir la deserción.

El informe completo y las visualizaciones están dentro del notebook del proyecto.

---

## 📂 Estructura del proyecto

- **/notebooks** → Notebook principal con el análisis: `TelecomX_LATAM_final.ipynb`.
- **/data** → Dataset original (`TelecomX_Data.json`).
- **README.md** → Este documento.

> El notebook carga, limpia y estandariza las columnas; realiza EDA (tablas y gráficos), y cierra con hallazgos y recomendaciones.

---

## ▶️ Cómo ejecutar el proyecto

1. Abre el notebook en **Google Colab** o **Jupyter Notebook**.
2. Ejecuta las celdas en orden. Se cargará `TelecomX_Data.json`, se hará la limpieza (normalización de texto, mapeo de *yes/no*, tipificación de numéricos) y se generarán las visualizaciones (barras, pie, distribuciones por categoría y por bines numéricos).
3. Revisa la **sección de informe** al final del notebook con conclusiones y recomendaciones.

**Dependencias**: `pandas`, `numpy`, `matplotlib`, `seaborn`.

---

## 📊 Resultados principales

**Tamaño de muestra**: 7.267 clientes.

### 1) Churn general
- **Churn total**: **25,7%**
- Se mantuvo: **71,2%**
- N/A (sin etiqueta): **3,1%**

### 2) Variables categóricas relevantes (churn)
- **Tipo de contrato**
  - *Month-to-month*: **41,3%** 
  - *One year*: **10,9%**  
  - *Two year*: **2,8%**
- **Método de pago**
  - *Electronic check*: **43,8%** 
  - *Credit card*: **14,8%**  
  - *Bank transfer*: **16,2%**  
  - *Mailed check*: **18,5%**
- **Servicio de internet**
  - *Fiber optic*: **40,6%** 
  - *DSL*: **18,4%**  
  - *No internet*: **7,1%**
- **Servicios de valor/soporte**  
  - *OnlineSecurity = Sí*: **14,2%** vs **30,3%** cuando *No*.  
  - *TechSupport = Sí*: **14,7%** vs **30,2%** cuando *No*.

### 3) Variables numéricas (churn)
- **Antigüedad (tenure)**  
  - 0–12 meses: **45,8%**  
  - 13–24: **28,1%**  
  - 25–48: **19,7%**  
  - 49–72: **9,2%**
- **Cargo mensual (ChargesMonthly)**  
  - 0–35: **10,5%**  
  - 36–70: **23,2%**  
  - 71–105: **36,8%**  
  - 106–140: **20,1%** (muestra menor)
---

## 🧭 Conclusiones e Insights

1. **Contrato mensual** es el principal factor de riesgo (41% churn). Contratos anuales/bianuales anclan permanencia.
2. **Electronic check** concentra clientes volátiles (44% churn). Métodos automáticos (tarjeta/transferencia) retienen mejor.
3. **Fiber optic** exhibe churn alto (41%), posiblemente por **expectativas de calidad/precio** y **cargos más altos**.
4. **Antigüedad temprana** (0–12 meses) es crítica: el riesgo cae drásticamente a medida que el cliente supera los 12–24 meses.
5. **Servicios de seguridad/soporte** (OnlineSecurity/TechSupport) reducen el churn a casi la mitad: buen *play* de retención.
6. **Cargos mensuales** altos (71–105) se asocian a mayor deserción; hay sensibilidad al precio/valor percibido.

---

## 🧩 Recomendaciones

- **Migración de contrato**: campañas para convertir *month-to-month* a **1–2 años** (bonificaciones iniciales, descuentos escalonados, bundles).
- **Early-life care (0–12 meses)**: onboarding proactivo, monitoreo de tickets/uso y ofertas de permanencia a los 90–120 días.
- **Cross-sell defensivo**: empujar **OnlineSecurity** y **TechSupport** como parte de paquetes de fidelización; muestran efecto protector claro.
- **Riesgo por método de pago**: segmentar **Electronic check** con ofertas de cambio a pago automático y *loyalty perks*.
- **Gestión de valor/precio** en **Fiber optic**: revisar *pricing*, comunicación de beneficios y calidad de servicio (SLA/tiempos de respuesta).
- **Alertas de riesgo**: reglas simples (p.ej., *tenure* ≤ 12, *Electronic check*, cargo 71–105, sin Security/Support, contrato mensual) para orquestar acciones en CRM.

---

## ❗ Posibles problemas y soluciones

- **No carga el dataset**: verifica la ruta a `/data/TelecomX_Data.json` o ajústala en la celda de carga.
- **Gráficos no se ven**: ejecuta todas las celdas previas o abre el notebook en **Colab/Jupyter**.
- **Advertencias de `pandas`**: el notebook incluye versiones y *workarounds* para *FutureWarnings* de `fillna`/`astype`.

---

## 🚀 Tecnologías utilizadas

- **Python 3.x**  
- **Pandas / NumPy** → manipulación y preparación de datos  
- **Matplotlib / Seaborn** → visualizaciones  
- **Google Colab / Jupyter** → entorno de ejecución

---

## 👩‍💻 Autora

Proyecto desarrollado por **Josefina Magini**.
