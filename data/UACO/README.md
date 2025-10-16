# UARG — Datos de la Unidad Académica Caleta Olivia

## Estructura
- `raw/`: exportes originales (sin transformar).
- `interim/`: limpiezas parciales, tabulados intermedios.
- `processed/`: dataset final para EDA/modelado.

## Archivos (convención de nombres)
- `raw/alumnos_UARG_YYYY.xlsx`
- `interim/uarg_clean_step1_YYYYMMDD.parquet`
- `processed/uarg_dataset_modelo_YYYYMMDD.parquet`

## Notas de anonimización
- Sin DNI/legajo/nombre/teléfono/correo/direcciones.
- Reemplazar IDs por códigos hash si hace falta trazabilidad.
- Fechas: considerar “año” o “mes/año” si el día expone identidades.

## Bitácora de cambios (ejemplo)
- 2025-10-14: subido `alumnos_UARG_2018.xlsx` a `raw/`.
- 2025-10-20: generado `uarg_clean_step1_20251020.parquet` en `interim/` (normalización de HS_TRAB, CANT_HIJOS, REINSCRIPT).
- 2025-10-25: `uarg_dataset_modelo_20251025.parquet` en `processed/`.
