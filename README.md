# CRISP-DM
Proyecto de análisis y modelado de aprobación estudiantil


---

## Fases de CRISP-DM

Este proyecto sigue las **6 fases principales de CRISP-DM**:

| Fase                       | Descripción |
|----------------------------|-------------|
| **1. Comprensión del Negocio** | Definición del problema, objetivos y métricas clave. |
| **2. Comprensión de los Datos** | Exploración inicial del dataset, identificación de datos faltantes y outliers. |
| **3. Preparación de los Datos** | Limpieza, codificación y creación de variables derivadas. |
| **4. Modelado** | Entrenamiento de modelos predictivos: Regresión Logística, Árboles de Decisión, Random Forest y SVM. |
| **5. Evaluación** | Comparación de métricas: Accuracy, Precision, Recall y F1-score. |
| **6. Despliegue** | Selección del mejor modelo y recomendaciones finales. |

---

## Dataset

- **Fuente:** [UCI Student Performance Dataset](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **Observaciones:** 395 estudiantes
- **Características principales:**
  - Factores académicos (`G1`, `G2`, `G3`, `absences`, `failures`)
  - Información familiar (`Medu`, `Fedu`, `famsize`, `guardian`)
  - Hábitos sociales (`goout`, `Walc`, `Dalc`)
  - Soporte educativo (`schoolsup`, `famsup`, `paid`, `internet`)

> **Nota:** Se creó una variable llamada `Aprobado` basada en el promedio de las tres notas (`G1`, `G2`, `G3`).

---

## Proceso de Limpieza y Preparación de Datos

- Tratamiento de valores nulos usando la mediana.
- Eliminación de *outliers* mediante método IQR.
- Codificación de variables categóricas a valores numéricos.
- Creación de variables nuevas:
  - `Promedio_Notas` → Promedio de G1, G2 y G3.
  - `Aprobado` → 1 si el promedio es >= 10, 0 en caso contrario.
  - `Faltas_Altas` → 1 si ausencias > 10.
  - `Grupo_Edad` → Clasificación por rango de edad.

---

## Modelos Probados

Los siguientes algoritmos fueron seleccionados para la clasificación:

| Modelo                | Ventajas |
|----------------------|----------|
| **Regresión Logística** | Sencillo e interpretable, modelo base. |
| **Árbol de Decisión**   | Buena interpretación visual y manejo de datos no lineales. |
| **Random Forest**       | Reduce el overfitting y maneja datos complejos. |
| **SVM**                  | Encuentra fronteras complejas entre clases. |

---
