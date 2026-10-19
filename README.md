# Ajuste de segmentación bancaria con proyecciones demográficas del INE

> Análisis de datos para evaluar si la segmentación de clientes de un banco debe adaptarse a la evolución demográfica prevista en España entre 2026 y 2036.

---

## El problema de negocio

Un banco segmenta a sus clientes por rangos de edad para diseñar productos y campañas. Esos rangos se definieron con la demografía de hoy, pero la población cambia: envejece, y no todos los tramos crecen al mismo ritmo.

**Pregunta:** ¿deben ajustarse los segmentos actuales según las proyecciones oficiales del INE?

## Resumen de hallazgos

| Indicador | 2026 | 2036 | Cambio |
|---|---|---|---|
| Índice de envejecimiento | 153,9 | 212,2 | +58,3 puntos |
| Edad media (años) | 44,71 | 46,75 | +2,04 |
| Tasa de dependencia | 32,0 | 39,8 | +7,7 puntos |

Variación de la población por tramo de edad (2026→2036):

| Tramo | Variación | Lectura |
|---|---|---|
| Senior-Mayores (61+) | **+25,8 %** | Mayor crecimiento |
| Jóvenes-Adultos (31-40) | +9,5 % | Crecimiento sostenido |
| Jóvenes (18-30) | +8,7 % | Crecimiento sostenido |
| Senior (51-60) | +4,6 % | Crecimiento moderado |
| Adultos (41-50) | **−11,6 %** | Único tramo en contracción |

**Conclusión:** el crecimiento no es homogéneo. Los tramos se mueven en direcciones distintas, lo que justifica revisar los segmentos y no tratarlos como bloques estables.

## Metodología

1. **Limpieza y filtrado** de cuatro tablas del INE: solo total nacional y sexo total, periodo 2026-2036.
2. **Normalización de datos:** conversión de formatos numéricos españoles (separador de miles y decimales) y extracción de edades desde texto.
3. **Agrupación en cinco tramos** y cálculo de población por tramo y año.
4. **Análisis de cobertura:** clientes del banco por millón de habitantes en cada tramo, en 2026 y en 2036.
5. **Visualización:** evolución normalizada de indicadores, valores absolutos, evolución por tramo y variación relativa.

## Visualizaciones

Los gráficos se generan al ejecutar el notebook (no se incluyen en el repositorio):

- `grafico1_completo.png`: índice de envejecimiento y tasa de dependencia, normalizados y en valores absolutos.
- `grafico2_poblacion.png`: evolución de la población por tramo.
- `grafico3_variacion.png`: variación de la población por tramo.

## Stack

- **Python** · pandas · numpy · matplotlib
- **Fuente:** Instituto Nacional de Estadística (INE)
- **Entorno:** Jupyter Notebook

## Estructura del repositorio

```
├── 06-15-2026_Analisis-proyeccion-poblacional-Espana_(2026-2036).ipynb
├── 06-15-2026_edad_media_2024-2039.csv
├── 06-15-2026_indice_envejecimiento.csv
├── 06-15-2026_tasa_dependencia_poblacion_mayor.csv
├── 06-15-2026_poblacion_2024-2074.csv
├── 06-08-2026_Clean.csv
└── README.md
```

## Cómo reproducirlo

```bash
pip install pandas numpy matplotlib
jupyter notebook
```

Coloca los CSV junto al notebook y ejecútalo de arriba abajo.

## Limitaciones

- Las proyecciones del INE son escenarios de referencia, no predicciones exactas.
- La cobertura compara clientes con población total del tramo, no con población bancarizada.
- La base de clientes tiene más variables (profesión, estado civil, saldo e historial de campañas), pero este análisis usa solo la edad.

## Próximos pasos

- Calcular el número esperado de clientes por segmento en 2036 y completar la tabla de segmentos.
- Contrastar los segmentos de edad con segmentos de comportamiento (productos, saldo, actividad).
- Traducir los hallazgos en recomendaciones concretas de producto para cada tramo.

---

**Autora:** Ana Cristina Urdaneta Flores · [LinkedIn](https://www.linkedin.com/in/urdanetaac) · urdanetafac@gmail.com
