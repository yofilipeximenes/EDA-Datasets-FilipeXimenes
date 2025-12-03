# [Ejercicio Práctico]: Análisis Exploratorio (EDA) de la Filarmónica de Nueva York

## 1. Objetivo del Proyecto

Análisis Exploratorio de Datos (EDA) sobre el histórico de performances de la Filarmónica de Nueva York (1842-Actualidad). El objetivo principal es identificar patrones históricos, la evolución del repertorio y evaluar la calidad del dataset antes de cualquier modelado estadístico.

## 2. Hipótesis de Partida

Se plantea que el volumen del repertorio de la Filarmónica de Nueva York está fuertemente sesgado hacia las obras del período Clásico y Romántico, lo cual coincide con la prominencia de los instrumentos solistas más interpretados (Piano y Violín).

## 3. Estructura del Repositorio

```
├── data/
│   ├── ny_phil.csv           # Dataset principal de conciertos.
│   └── soloists.csv          # Dataset secundario de solistas.
├── notebooks/
│   └── eda.ipynb             # Notebook principal con todo el flujo de análisis.
└── README.md                 # Resumen ejecutivo.
```

## 4. Fases del Análisis y Hallazgos Principales

### 4.1. Limpieza y Saneamiento (Sección 3.3)

| Tipo de Limpieza | Decisión Justificada | Impacto |
| :--- | :--- | :--- |
| **Duplicados** | Eliminación de filas duplicadas exactas (más del 61% del DF) para corregir errores de ingesta. | Reducción del dataset a **308,087 registros únicos**. |
| **Homogeneización** | Conversión de la clave `programID` de `float` a `int64`. | Asegura la compatibilidad de tipos para futuras uniones. |
| **Normalización** | Conversión de nombres de compositores, obras y directores a minúsculas y *strip* para unificar categorías (ej. 'Wagner' vs 'wagner '). | Aumenta la precisión de los conteos de frecuencia. |

### 4.2. Conclusiones Exploratorias Clave

1.  **Debilidad Crítica:** Se encontró una gran cantidad de valores nulos (`nan`) en la columna `composerName`, lo que los convierte en el "compositor" más interpretado. Se requiere un tratamiento avanzado de estos nulos en el futuro.
2.  **Evolución:** La actividad de la Filarmónica presenta una clara tendencia al alza, con un crecimiento exponencial a partir de la década de 1920 y un pico de actividad cerca de 2007.
3.  **Repertorio:** El núcleo del repertorio está dominado por compositores del Romanticismo (Beethoven, Wagner) y Barroco (Händel), confirmando el sesgo histórico de la institución.

---

## 5. Próximos Pasos

El análisis se completará filtrando las obras por la presencia de instrumentos solistas clave para validar la hipótesis inicial.

---
