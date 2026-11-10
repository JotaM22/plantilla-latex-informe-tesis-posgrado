# Instrucciones para el agente de redacción

## Objetivo
Construir **informes finales de tesis de posgrado**, no proyectos de investigación. No incorporar automáticamente secciones como Generalidades, cronograma académico o presupuesto del plan de tesis.

## Principio semántico
- **Estructura**: jerarquía de capítulos, secciones, listas, tablas, figuras y numeración.
- **Presentación**: fuente, tamaño, márgenes, sangría, interlineado y espacios, definidos en archivos \`.sty\`.
- **Contenido**: texto de los títulos, párrafos, resultados, tablas y referencias; varía con cada investigación.
- Usar comandos de \`estructura.sty\`; jamás escribir manualmente números de capítulos y secciones.
- No insertar \`\\vspace\` para reparar un título particular. Resolver el estilo global o crear un componente semántico documentado.
- Usar \`listaTrasTitulo\` inmediatamente después de un encabezado y \`listaInforme\` tras texto normal.

## Integridad científica
- No inventar resultados, muestras, valores p, conclusiones, fuentes ni identificadores bibliográficos.
- Los resultados deben surgir de datos proporcionados y verificables.
- La discusión debe interpretar resultados reales; conclusiones deben responder a los objetivos.
- Mantener diferencias entre propuesta, ejecución y resultados.

## Validación editorial
1. Leer primero \`README.md\` y \`NORMAS_FORMATO.md\`.
2. Confirmar norma institucional vigente del **informe** antes de declarar el formato definitivo.
3. Compilar con XeLaTeX.
4. Inspeccionar PDF visualmente: portada, tabla de contenidos, títulos, párrafos, listas, tablas anchas, figuras, bibliografía, anexos y paginación.
5. No decir "idéntico a Word" sin comparación visual demostrable.
6. Mantener separadas la plantilla de proyecto y la plantilla de informe.

## Estado inicial
Los estilos y capítulos son una **base provisional**. La estructura exacta del informe y el diseño de portada deben decidirse a partir de documentos normativos del posgrado.
