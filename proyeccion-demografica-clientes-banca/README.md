# Análisis de Proyección Poblacional y Perfil del Cliente - Simulador Bancario (Banco Atlas)

## Sobre este repositorio

Este proyecto forma parte de un simulador empresarial grupal desarrollado durante el bootcamp de Data Analytics en IT Academy (Barcelona Activa). Este repositorio contiene específicamente **mi contribución individual**: el análisis del perfil del cliente mediante clustering K-Prototypes, cruzado con proyecciones demográficas oficiales del INE (2026-2036) para un banco simulado con ~2.700 clientes.

## Contenido

```
06-15-2026_Analisis-proyeccion-poblacional-Espana_(2026-2036).ipynb
```

### Descripción

**06-15-2026_Analisis-proyeccion-poblacional-Espana_(2026-2036).ipynb**
- *Función:* Cruce de los clústeres de clientes (obtenidos mediante K-Prototypes) con las proyecciones demográficas oficiales del INE para España, horizonte 2026-2036.
- **Hallazgo principal:** el segmento de Directivos Senior (51-60 años) crece +6,63% en el período proyectado, mientras que Operativos Senior (41-50 años) se contrae -6,13%, contradiciendo la asunción inicial de que todos los segmentos "Senior" crecen de forma uniforme. El segmento Senior-Mayores muestra un crecimiento proyectado de +25,8%.

## Metodología

- **Clustering:** K-Prototypes (variables mixtas numéricas y categóricas)
- **Datos demográficos:** Proyecciones oficiales del INE, horizonte 2026-2036
- **Herramientas:** Python (pandas, scikit-learn, kmodes), visualizaciones con matplotlib/seaborn
- **Enfoque:** identificar cómo la evolución demográfica española impacta la composición futura de la cartera de clientes por segmento

## Nota sobre el proyecto grupal

Este análisis fue parte de un proyecto colaborativo más amplio (simulador bancario), que incluyó también módulos de EDA, limpieza de datos, marketing y riesgo crediticio-financiero, desarrollados por otros miembros del equipo. Este repositorio recoge únicamente la parte de la que fui responsable.
