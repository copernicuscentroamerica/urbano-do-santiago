## Evidencias documentales y planificación inicial

- S22 incluye un enlace a un artefacto demostrativo de Claude, un reporte de avances y un mapa de referencia.
- El ZIP no contiene código ni bases de datos del demostrador, archivos de validación F1/AUC, ni modelos ANUGA/CRISIS ejecutados.

No se recibió backlog para esta iniciativa. Las tareas que Antigravity derive de esta ficha deben marcarse como propuestas y presentarse para revisión, sin atribuir responsables ni fechas acordadas.

## Especificación de módulos de aplicación

Estos componentes constituyen una propuesta de interfaz basada en el perfil. La primera versión entrega una página de proyecto completa y espacios de integración. Activar un mapa, indicador, descarga o simulador únicamente cuando exista el dato o servicio correspondiente.

- Botón Demostrador reportado que conserva el enlace de S22 y advierte que su disponibilidad no se verificó para este paquete.
- Vista de escenarios con año de exposición y niveles de agua; controles habilitados únicamente si existe motor y datos.
- Mapa y panel por barrio/paraje con población expuesta y pérdidas cuando los resultados estén disponibles.
- Pestaña de metodología que distinga HAND, eventual ANUGA, modelo tipo MOLUSCE y componente CRISIS.
- Panel de validación con métricas reportadas, fuente y evidencia pendiente, separado de resultados comprobados.

### Estados vacíos y navegación

Cuando no haya resultado disponible, mostrar «Resultado pendiente» y explicar qué insumo falta. Conservar los datos faltantes como `null`; no dibujar geometrías inventadas, rellenar indicadores con cero ni presentar gráficos de ejemplo como mediciones. El botón de fork/clonación apunta al repositorio canónico verificado, no al repositorio general del portal.
