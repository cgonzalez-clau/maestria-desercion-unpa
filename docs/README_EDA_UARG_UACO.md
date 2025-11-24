Notas metodológicas sobre el EDA UARG vs UACO

En esta etapa el objetivo fue realizar un **EDA descriptivo y comparativo** entre las unidades académicas **UARG** y **UACO** a partir de los datos del sistema **SIU-Guaraní**, tomando la carrera _Analista de Sistemas_ como caso de estudio común. No se buscó todavía ajustar modelos predictivos, sino **explorar la estructura de los datos, describir patrones y explicitar las limitaciones del registro**.

### Tratamiento de valores faltantes

En las variables con problemas estructurales se realizó una **limpieza básica y documentada**:

- Se eliminaron columnas completamente vacías o residuales (por ejemplo, columnas con 100 % de valores faltantes o sin contenido relevante).
- Se unificaron columnas duplicadas o inconsistentes (por ejemplo, `PLAN ` y `PLAN`) en una sola versión coherente.
- Se recodificaron códigos como `\\N` y otros valores especiales a **valores faltantes (`NaN`)**.

A partir de esta limpieza, se construyeron **indicadores derivados** más claros, que se utilizaron en los análisis comparativos:

- `TRABAJA` (Sí / No), a partir de la variable `HS TRAB`.
- `TIENE_HIJOS` (Sí / No), a partir de la variable `CANT HIJOS`.
- `ANTIG_CARR` (años en la carrera), a partir de `ANIO_CORTE` y `AÑO_ING_Carrera`.

En todos los casos, las proporciones y gráficos se calcularon **solo sobre el subconjunto de estudiantes con dato válido**, indicando explícitamente el tamaño de ese subconjunto.

No se aplicaron técnicas de **imputación de missing**, ya que en algunas variables la proporción de valores faltantes supera el 80 %. Bajo estas condiciones, cualquier imputación podría introducir sesgos importantes. En lugar de “inventar” valores, se decidió utilizar los porcentajes de datos disponibles como evidencia de la **calidad del registro**, y discutir esa limitación en la sección correspondiente.

### Tratamiento de outliers

En la variable `PORCENTAJE` (avance en el plan de estudios) se detectaron algunos valores superiores a 1 (por ejemplo, 1,10), que se interpretan como **posibles errores de carga o casos particulares**. Estos valores:

- **No se eliminaron del dataset**, para respetar la información original y mantenerlos disponibles para futuros análisis más avanzados.
- Solo se ajustó la **visualización de los boxplots**, recortando la escala vertical y ocultando los outliers en el gráfico, con el objetivo de mejorar la legibilidad de la distribución central.

### Alcance de este EDA

El EDA presentado aquí:

- Unifica los cortes 2018–2025 de UARG y UACO.
- Caracteriza el volumen de matrícula y las carreras más numerosas.
- Analiza en detalle la carrera Analista de Sistemas, comparando UARG y UACO en términos de:
  - matrícula por año,
  - indicadores socioeconómicos (situación laboral e hijos),
  - avance académico (`PORCENTAJE`),
  - antigüedad en la carrera (`ANTIG_CARR`).

Estos resultados constituyen la **base descriptiva** sobre la cual se proyectarán futuras etapas de trabajo, incluyendo el diseño del ICT y el desarrollo de modelos predictivos de riesgo de deserción.

