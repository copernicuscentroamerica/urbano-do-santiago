# Exportación de expansión urbana para el geovisor

**Estado:** script reproducible incorporado; vista GeoJSON pendiente de subir y comprobar en el geovisor.

El script `src/exportar_expansion_urbana_web.py` genera una vista **cartográfica generalizada a 100 m** a partir de los datos locales `huella_2018_2036.tif` (2018, 2021, 2024, 2027, 2030, 2033, 2036) y del límite territorial de la **ONE**, disponible localmente en GeoPackage.

Dependencias técnicas opcionales, no requeridas para construir el sitio web: `numpy rasterio fiona shapely pyproj`.

```bash
python3 src/exportar_expansion_urbana_web.py \
  --raster /ruta/huella_2018_2036.tif \
  --limite /ruta/STG_limite_municipal_recuperado.gpkg \
  --salida geovisor/capas/santiago_expansion_urbana_100m_vista.geojson
```

**Verificaciones realizadas sobre el ráster local recortado:** 800151 píxeles en la base 2018, 87763 nuevas celdas en 2021, 106284 en 2024, 112918 en 2027, 105423 en 2030, 98702 en 2033 y 92683 en 2036 (píxeles de 10 m, 100 m² por píxel). Los valores coinciden con los indicadores versionados en el CSV.

**Precauciones:**
- La vista se calcula por clase temporal predominante por cuadrícula de 100 m, exige al menos 25 % de área municipal y al menos 10 % de ocupación hasta 2036. La generalización cambia la geometría y **no debe usarse para medir áreas, superponer amenazas con precisión ni tomar decisiones normativas**.
- La geometría original de 10 m y el límite ONE en EPSG:32619 se deben preservar para cálculos y trazabilidad.
- Los años 2018–2024 son clasificaciones y 2027–2036 son proyecciones exploratorias tipo MOLUSCE.
- Antes de habilitar la capa en `geovisor/layers.json`, incorporar el GeoJSON, comprobar su tamaño, la carga del sitio y la simbología temporal. El archivo no es una capa pública validada.
