## Alcance técnico y metodológico declarado en el perfil

Los siguientes campos reproducen la información declarada por el equipo en el documento principal del perfil (identificado en el inventario documental como `S22`; consulta la lista completa de archivos al final de esta página). Representan la formulación técnica del perfil y se actualizan conforme avanza la validación del proyecto.

### Territorio y escala

**Ciudad, sector o territorio.** Municipio de Santiago de los Caballeros (provincia Santiago, región Cibao Norte), República Dominicana

**Escala principal de análisis.** Municipal (huella urbana, aptitud y escenarios de crecimiento); barrio/paraje (indicadores y priorización); microcuenca urbana piloto en la cañada o arroyo de mayor exposición (detalle de drenaje)

**Superficie aproximada.** 42.927 ha (≈ 429,3 km²), calculada sobre el límite municipal oficial (UTM 19N)

**Centroide (lat, lon).** 19.49818, -70.73656

**¿Cuenta con archivos geoespaciales?.** Sí

**Archivo cargado.** Límites ONE: municipio, secciones y barrios/parajes

Compuestos Sentinel-2 L2A 10 m (2018, 2021, 2024) y huella urbana 2018–2036

Copernicus DEM GLO-30, HAND y red de drenaje

GHSL: GHS-POP, GHS-BUILT-S 10 m y GHS-BUILT-H

**Descripción de los archivos.** Paquete del prototipo construido con productos Copernicus: compuestos Sentinel-2 L2A sin nubes (10 m) de 2018, 2021 y 2024; clasificación construido/no construido; huella proyectada 2027–2036; Copernicus DEM GLO-30 con altura sobre el drenaje (HAND); población GHS-POP 2020–2030 y altura de edificación GHS-BUILT-H. Se complementa con límites y cartografía de la ONE y vías de OpenStreetMap. No se usan modelos de inundación de terceros.

### Instrumentos y productos

**Instrumento de planificación o gestión al que aportaría.** Plan Municipal de Ordenamiento Territorial (PMOT) de Santiago: zonificación de suelo no urbanizable por riesgo y suelo urbanizable condicionado

Normativa de uso de suelo y otorgamiento de permisos de construcción (Planeamiento Urbano municipal)

Plan municipal de gestión de riesgo de desastres

Priorización de proyectos de inversión pública (drenaje, estabilización de laderas)

**Tipo de producto o entregable.** Mapa

Capa geoespacial

Indicadores por barrio

Flujo de trabajo / metodología

Visor web

**Descripción del producto.** Simulador web de escenarios (demostrador ya publicado): el usuario fija el nivel del agua en cañadas, tributarios y el Yaque, el año de exposición (2024–2036), el crecimiento poblacional y el costo de reposición, y el visor recalcula la mancha de inundación, la población expuesta y las pérdidas económicas por píxel y por barrio.

Huella urbana observada y proyectada a 10 m con Sentinel-2 y un modelo de cambio de uso del suelo tipo MOLUSCE (red neuronal + autómata celular) hasta 2036.

Mapa de valor económico del territorio construido por píxel, siguiendo el enfoque del Servicio 12 de CopernicusLAC (desagregación estadística de valores), y mapa de pérdidas probables.

Módulo de deslizamientos por lluvia y sismo con el modelo abierto CRISIS sobre el Copernicus DEM, para las laderas de la Cordillera Septentrional y la Falla Septentrional.

Aptitud territorial y polígonos normativos para el PMOT, entregados en GeoPackage y servicios OGC, con metodología replicable en un repositorio.

**Avance mínimo esperado en la jornada presencial.** Ya disponible (avance previo a la jornada): clasificación Sentinel-2 2018–2024 (F1 = 0,97), proyección tipo MOLUSCE a 2036 validada contra 2024 (AUC = 0,95; 96 % del cambio simulado a menos de 100 m de un cambio observado), modelo HAND con Copernicus DEM, valor económico por píxel y simulador web de pérdidas.

Durante la jornada: calibrar los niveles de agua con eventos observados (Copernicus EMS, Global Flood Monitoring con Sentinel-1) y caudales del Yaque; configurar CRISIS en una ladera piloto; revisar con los asesores la validación del modelo de crecimiento.

Al cierre: escenarios calibrados en el simulador y una ficha de lectura para el Ayuntamiento.

### Datos

**Datos satelitales o productos geoespaciales útiles.** Sentinel-2 L2A (10 m), 2018–2026: huella urbana y cambio (clasificación y proyección)

Sentinel-1 SAR: inundaciones observadas para calibrar escenarios (Global Flood Monitoring, Copernicus EMS)

Copernicus DEM GLO-30: HAND, red de drenaje, pendientes e insumo de CRISIS

GHSL (Copernicus/JRC): GHS-POP 2020–2030, GHS-BUILT-S 10 m y GHS-BUILT-H

Copernicus EMS: activaciones históricas en el Cibao

ERA5 / ERA5-Land (Copernicus C3S): lluvias extremas para escenarios de inundación y deslizamiento

ESA WorldCover: referencia de cobertura del suelo

**Datos locales, institucionales o de campo disponibles.** Límites ONE (municipio, secciones, 222 barrios/parajes) y Censo XCNPV 2022

Cartografía de edificaciones de la ONE (212.909 puntos) para validar la exposición

Avances del Servicio 12 de CopernicusLAC (cartografía de valor económico) y su tabla de insumos estadísticos

Costos de construcción por m² (ONE ICDV y referencias de mercado 2025)

Fallas geológicas y geología para parametrizar CRISIS

**Datos que hacen falta.** PMOT vigente de Santiago y su zonificación en formato vectorial (Ayuntamiento)

Caudales y niveles del río Yaque del Norte (INDRHI) y curvas IDF de lluvia (INDOMET)

Red de drenaje pluvial y catastro de cañadas (Ayuntamiento / CORAASAN)

Inventario de deslizamientos y parámetros de resistencia del suelo para CRISIS

Cifras nacionales pendientes del Servicio 12: stock de capital, vehículos, tierras e infraestructura

**Enlaces relacionados.** Simulador demostrativo: https://claude.ai/artifact/CeTpKKh4j3n7BTKmXQCFEe

MOLUSCE: https://github.com/nextgis/qgis_molusce

CRISIS (DesignSafe PRJ-6509): https://doi.org/10.17603/ds2-qs1s-1f14

Hydrata (referencia de simulador web, ANUGA): https://hydrata.com

Copernicus Data Space Ecosystem: https://dataspace.copernicus.eu

### Método y herramientas

**Métodos o pasos previstos.** Extracción de edificaciones y huella urbana (clasificación / deep learning)

Modelación de crecimiento urbano / escenarios (MOLUSCE)

Modelación de inundación (HAND y ANUGA)

Modelación de deslizamientos por lluvia y sismo (CRISIS)

Análisis de exposición, vulnerabilidad y pérdidas económicas

Visualización en dashboard, visor o app

**Flujo de trabajo preliminar.** 1. Huella urbana: compuestos Sentinel-2 L2A sin nubes (mediana, máscara SCL) de 2018, 2021 y 2024; clasificador entrenado con GHS-BUILT-S 10 m; regla de no reversión del suelo construido.

2. Crecimiento (tipo MOLUSCE): matriz de transición de Markov; potencial de transición con red neuronal y regresión logística (pendiente, elevación, distancia a vías, al centro y a lo construido, densidad vecinal); autómata celular. Calibración 2018→2021, validación contra 2024 y proyección por pasos de 3 años hasta 2036 (140 km²).

3. Inundación: HAND sobre el Copernicus DEM GLO-30 con tres clases de drenaje (cañadas < 10 km², tributarios 10–500 km², Yaque > 500 km²); el usuario fija el nivel del agua. En la cañada piloto se correrán escenarios 2D con ANUGA (motor abierto que usa Hydrata) con lluvias de diseño y ERA5.

4. Población: total proyectado con la tendencia GHS-POP (editable) y distribuido sobre la huella del año elegido.

5. Valor económico (Servicio 12): huella de edificación × niveles (GHS-BUILT-H) × costo de reposición por m² × (1 + contenido), por píxel de 20 m.

6. Pérdidas: curvas profundidad-daño del JRC para Sudamérica (Huizinga et al., 2017); pérdida anual esperada al calibrar los escenarios con periodos de retorno.

7. Deslizamientos (CRISIS): estabilidad de laderas por lluvia y sismo sobre el Copernicus DEM, calibrada con inventarios de deslizamientos; aceleraciones sísmicas de la Falla Septentrional.

8. Norma: traducción de pérdidas y aptitud a polígonos normativos del PMOT y criterios de permisos.

**Índices, algoritmos o herramientas.** Python (rasterio, geopandas, scikit-learn, pysheds), réplica del flujo MOLUSCE (QGIS), ANUGA, CRISIS, Copernicus Data Space / openEO, Leaflet; métricas: F1 de la clasificación, AUC y figura de mérito del modelo de crecimiento, superficie inundada, población expuesta, pérdida probable en RD$ y US$.

### Operación y acompañamiento

**Frecuencia de actualización o análisis.** Anual (huella urbana y exposición con nuevas imágenes Sentinel)

Por ciclo del plan (cada 5–10 años) para la zonificación normativa

**Nivel(es) de acceso.** Público: visor de consulta e indicadores por barrio

Institucional: descarga de capas y servicios OGC para el Ayuntamiento, MEPYD y Defensa Civil

**Componentes para usar o desplegar.** Repositorio GitHub (código y documentación)

Visor web (Leaflet/MapLibre)

Servicios OGC WMS/WFS (GeoServer o pygeoapi)

Flujo en Copernicus Data Space / openEO

**Uso previsto por otras personas.** Técnicos de Planeamiento Urbano y de la Oficina Municipal de Gestión de Riesgo de Santiago; Gobierno Central

**¿Requiere actualización periódica?.** Sí

**Actualización requerida.** Actualización anual de la huella urbana y de los indicadores de exposición con el compuesto Sentinel-2 del año; actualización de amenazas cuando existan nuevos estudios de detalle; revisión de la zonificación en cada ciclo del PMOT. El proceso quedará documentado para que el equipo técnico municipal lo ejecute sin dependencia externa.

**Pregunta principal.** ¿Cómo calibrar con datos Copernicus (Sentinel-1, Global Flood Monitoring, EMS y ERA5) los escenarios de inundación del simulador para asignarles periodos de retorno y estimar la pérdida anual esperada, y cómo validar y comunicar la incertidumbre de la proyección tipo MOLUSCE a 2036 para que pueda sustentar la zonificación del PMOT de Santiago?

**Áreas en las que necesita asesoría.** Procesamiento de imágenes Copernicus / openEO

Modelación hidrológica e hidráulica (HAND, ANUGA)

Modelos de crecimiento urbano (MOLUSCE)

Valoración económica y pérdidas

Despliegue digital

## Referencias documentales del expediente

- `S21` — `0. Perfiles de Proyectos/Grupo 6_Republica Dominicana_Zonificación/Ficha_06_Republica_Dominicana_Zonificacion_Riesgo_Gran_Santo_Domingo.docx`.

- `S22` — `0. Perfiles de Proyectos/Grupo 6_Republica Dominicana_Zonificación/Ficha_06_Republica_Dominicana_Zonificacion_Riesgo_Santiago.docx`.
