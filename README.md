# Proyección Demográfica y Segmentación de Clientes — Banco Atlas

Análisis de las proyecciones de población del INE (2026-2036) para evaluar si los segmentos de clientes actuales del banco deben ajustarse.

## Pregunta de negocio (Hipótesis 1)

¿Debemos ajustar nuestros segmentos de clientes actuales basándonos en las proyecciones de población oficiales del INE?

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `06-15-2026_Analisis-proyeccion-poblacional-Espana_(2026-2036).ipynb` | Notebook principal: limpieza, integración y análisis de cobertura |
| `06-15-2026_edad_media_2024-2039.csv` | Edad media de la población (INE) |
| `06-15-2026_indice_envejecimiento.csv` | Índice de envejecimiento (INE) |
| `06-15-2026_tasa_dependencia_poblacion_mayor.csv` | Tasa de dependencia de la población mayor (INE) |
| `06-15-2026_poblacion_2024-2074.csv` | Población por edad y sexo (INE) |
| `06-08-2026_Clean.csv` | Base de clientes del banco (edad) |

## Requisitos

- Python 3.9+
- pandas, numpy, matplotlib

```bash
pip install pandas numpy matplotlib
```

## Uso

1. Colocar los CSV en el mismo directorio que el notebook (el código también los busca en el directorio personal).
2. Abrir y ejecutar el notebook de principio a fin con Jupyter.

Los gráficos se guardan como `grafico1_completo.png`, `grafico2_poblacion.png` y `grafico3_variacion.png`, y las tablas como CSV (`tabla_cobertura_por_cluster.csv`, `datos_ine_integrados.csv`, `poblacion_por_rango.csv`).

## Metodología

1. **Limpieza INE:** se filtra "Total Nacional" y sexo "Total" en edad media; se filtra el periodo 2026-2036 en índice de envejecimiento y tasa de dependencia.
2. **Población por rango:** se extrae la edad de los textos ("18 años") y se agrupa en cinco rangos: Jóvenes (18-30), Jóvenes-Adultos (31-40), Adultos (41-50), Senior (51-60) y Senior-Mayores (61+).
3. **Cobertura:** clientes del banco por rango frente a población 2026 y 2036, con variación porcentual y clientes por millón de habitantes.
4. **Visualización:** evolución normalizada de índice y tasa, valores absolutos, evolución por rango y variación por rango.

## Resultados principales (2026 → 2036)

- Índice de envejecimiento: 153,9 → 212,2 (+58,3 puntos)
- Edad media: 44,71 → 46,75 años
- Tasa de dependencia: 32,0 → 39,8
- Variación de población por rango: Jóvenes +8,67 %, Jóvenes-Adultos +9,48 %, Adultos −11,60 %, Senior +4,57 %, Senior-Mayores +25,80 %

Conclusión: los rangos no crecen al mismo ritmo y el rango Adultos (41-50) se contrae, lo que justifica revisar la segmentación.

## Limitaciones

- Las proyecciones del INE son escenarios, no certezas.
- La cobertura compara clientes actuales con población total del rango, no con la población bancarizada.
- La columna "Clientes Esperados" de la tabla de segmentos del notebook está pendiente (`TBD`).
- Los segmentos de la presentación (Directivos Senior, Mandos Intermedios, Jóvenes Profesionales, Técnicos de Base) no coinciden con los rangos de edad del notebook.
- Cifra de registros: 18 252 son filas brutas de las cuatro tablas del INE, no registros de un único dataset.

## Autoría

Proyecto del Sprint 4 — Tendencias Demográficas y Ajuste de Estrategia.
