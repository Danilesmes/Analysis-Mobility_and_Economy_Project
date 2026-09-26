# LADB Mobility & Economy Analysis – Sprint 5

Análisis de cómo la **movilidad urbana se relaciona con la productividad económica** en las principales ciudades latinoamericanas.

Este repositorio contiene el análisis realizado durante el Sprint 5 usando datos reales del **TomTom Traffic Index** y **OECD Cities**, que incluyen indicadores de congestión de tráfico, tiempos de viaje y productividad económica (PIB per cápita) en múltiples ciudades. :book:

## 📂 Contenido del repositorio

```
├── notebooks/
│   └── S5_ladb_mobility_economy_project.ipynb
│       → Notebook principal con EDA, limpieza, unión de datasets y análisis de relaciones.
│
├── data/
│   ├── tomtom_traffic.csv
│   │   → Dataset de TomTom Traffic Index (congestión, tiempos de tráfico)
│   │
│   ├── oecd_city_economy.csv
│   │   → Dataset de OECD con indicadores económicos (PIB per cápita, productividad)
│   │
│   └── ladb_mobility_economy_2024_clean.csv
│       → Dataset limpio y consolidado (output final)
│
└── README.md
```

---

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón para ejecutar el análisis directamente en la nube:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/Danilesmes/Analysis-Mobility_and_Economy_Project/blob/main/S5_mobility_economy_project.ipynb)

O:

1. Abre el archivo `.ipynb` en GitHub
2. Haz clic en **Open in Colab**
3. Carga los datasets desde `/data/` o desde un enlace público

---

## 📘 Cómo reproducir el análisis

### Opción 1: En Colab (recomendado – sin instalación)
1. Haz clic en el botón de arriba
2. Ejecuta las celdas en orden
3. Los datasets se cargarán automáticamente

### Opción 2: En tu máquina local
```bash
# Clonar el repositorio
git clone https://github.com/TU_USUARIO/ladb-mobility-economy.git
cd ladb-mobility-economy

# Instalar dependencias
pip install pandas numpy seaborn matplotlib

# Ejecutar el notebook (requiere Jupyter)
jupyter notebook notebooks/S5_ladb_mobility_economy_project.ipynb
```

---

## 🧠 Objetivo del análisis

- ✅ **Cargar y explorar** dos datasets heterogéneos (tráfico y economía)
- ✅ **Limpiar y transformar** datos con valores faltantes, inconsistencias y outliers
- ✅ **Consolidar** múltiples fuentes en un único dataset coherente (merge)
- ✅ **Analizar relaciones** entre movilidad urbana y productividad económica
- ✅ **Identificar patrones** en ciudades latinoamericanas para orientar inversiones en infraestructura
- ✅ **Visualizar hallazgos** con gráficos claros (scatter plots, box plots, análisis temporal)

---

## 📊 Pasos del análisis

### 🧩 Paso 1: Cargar y explorar
- Importar librerias (`pandas`, `numpy`, `seaborn`, `matplotlib`)
- Cargar los archivos CSV en DataFrames
- Revisar estructura, columnas, tipos de datos y primeras filas
- Detectar inconsistencias preliminares

### 🧩 Paso 2: Limpiar datos de tráfico (TomTom)
- Validar y convertir tipos de datos
- Manejar valores faltantes y atípicos (outliers)
- Estandarizar formatos de fecha y valores numéricos

### 🧩 Paso 3: Limpiar datos económicos (OECD)
- Validar estructura del dataset económico
- Renombrar columnas para claridad
- Manejar inconsistencias y valores faltantes

### 🧩 Paso 4: Preparar datos agregados
- Promediar indicadores por ciudad y año
- Calcular estadísticas descriptivas
- Preparar para merge

### 🧩 Paso 5: Unir movilidad y economía
- Combinar ambos datasets usando `merge()` (inner join)
- Validar la consolidación
- Explorar el dataset unificado

### 🧩 Paso 6: Visualización y análisis
- **Scatter plots**: Relación entre congestión y PIB per cápita
- **Box plots**: Distribución de indicadores por ciudad
- **Series de tiempo**: Evolución de la congestión y economía
- **Correlaciones**: Matriz de correlaciones entre variables clave

### 🧩 Paso 7: Exportar y documentar
- Guardar dataset limpio como CSV
- Documentar metodología y hallazgos
- Completar resumen ejecutivo

---

## 📈 Datos principales

| Dataset | Origen | Filas | Columnas | Tema |
|---------|--------|-------|----------|------|
| **TomTom Traffic Index** | TomTom | ~10K | 12 | Congestión, tiempos de viaje, retardos |
| **OECD Cities** | OECD | ~500 | 8+ | PIB per cápita, productividad, años |
| **Dataset Consolidado** | Merge | ~2K | 15+ | Movilidad + Economía |

---

## 🔍 Variables clave del análisis

### Movilidad Urbana (TomTom)
- `TrafficIndexLive`: Índice de tráfico en tiempo real (0-100)
- `JamsDelay`: Retardo acumulado en minutos
- `JamsCount`: Número de atascos activos
- `TravelTimePer10KmsMins`: Tiempo de viaje por 10 km

### Economía (OECD)
- `GDP_per_capita`: PIB per cápita (USD)
- `Productivity_Index`: Índice de productividad
- `Year`: Año del dato

---

## 💡 Hallazgos clave

- **Ciudad de México lidera en congestión**: Presenta el mayor tiempo promedio de tráfico entre todas las ciudades latinoamericanas analizadas, con un `JamsDelay` elevado que impacta la movilidad urbana.

- **No hay correlación directa entre PIB y congestión**: Aunque Ciudad de México muestra un PIB per cápita relativamente alto, también tiene congestión muy elevada. Esto contradice la hipótesis inicial de que mayores economías necesariamente tendrían mejor infraestructura de transporte.

- **Ciudades eficientes en movilidad**: Metropolis como Montevideo, Buenos Aires y São Paulo demuestran que es posible mantener PIB per cápita alto con niveles de congestión relativamente bajos, sugiriendo que la gestión de infraestructura de transporte es independiente del nivel económico.

- **Oportunidad de inversión en infraestructura**: Los datos sugieren que mejoras en infraestructura de transporte en ciudades de alto PIB (como Ciudad de México) podrían incrementar aún más la productividad económica, haciendo estas ciudades focos prioritarios para inversión.

---

## 🛠️ Librerías utilizadas

```python
pandas       # Manipulación de datos
numpy        # Cálculos numéricos
matplotlib   # Visualización estática
seaborn      # Visualización avanzada y estadística
```

---

## 📝 Entregables

✅ **Notebook `.ipynb`**: Todas las celdas con código, outputs y comentarios explicativos  
✅ **Dataset limpio**: `ladb_mobility_economy_2024_clean.csv`  
✅ **README.md**: Este archivo (documentación del proyecto)  
✅ **Resumen ejecutivo**: Incluido en el notebook (Paso 7)

---

**Última actualización**: Enero 2025  
**Sprint**: S5 - LADB Mobility & Economy  
**Proyecto académico**: Universidad  
**Estado**: ✅ Completado
