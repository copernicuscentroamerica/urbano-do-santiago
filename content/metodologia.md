## Metodología de clasificación multitemporal y simulación al 2036

1. **Clasificación supervisada trienal Sentinel-2 L2A (2018, 2021, 2024):** Procesamiento radiométrico libre de nubes en UTM Zona 19N (EPSG:32619) sobre los 429.27 km² municipales para extraer la huella urbana construida a 10 m.
2. **Validación independiente contra GHSL 2020:** Evaluación mediante matriz de coincidencia espacial que alcanza un **índice Jaccard = 0.7205** (umbral óptimo 0.75), confirmando alta consistencia estructural.
3. **Modelación prospectiva MOLUSCE (2027–2036):** Entrenamiento de probabilidades de transición sobre las matrices 2018–2021–2024 incorporando distancia a vías, topografía Copernicus DEM GLO-30 y contigüidad urbana para simular el crecimiento tendencial cada tres años hasta 2036.
4. **Síntesis web a 100 m:** Exportación reproducible (`src/exportar_expansion_urbana_web.py`) a una malla ligera de 5,369 polígonos en EPSG:4326.
