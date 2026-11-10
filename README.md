# Plantilla LaTeX — Informe final de tesis de posgrado

**Versión inicial de formato v1.0, derivada de una auditoría visual de un informe Word suministrado por el usuario.** Es un punto de partida técnico, no una certificación de normativa institucional.

## Compilar en Overleaf / VS Code
- Archivo principal: `main.tex`.
- Motor: **XeLaTeX** (obligatorio por `fontspec`).
- En VS Code, usar `latexmk -xelatex`, no `latexmk -pdf`.
- Subir `figuras/escudo_upao.jpg` si se desea ver el escudo institucional real; en GitHub, mientras falte esa imagen, el modelo emplea un marcador visual. El ZIP de prueba contiene el escudo extraído del Word que facilitó el usuario.

## Organización
- `main.tex`: ejemplo **sin contenido académico real**.
- `estilos.sty`: márgenes, fuente, interlineado y número de página.
- `estructura.sty`: capítulos, divisorias, títulos y listas semánticas.
- `tablas.sty`: leyendas, notas, fuentes, tablas horizontales y figuras.
- `AGENTS.md`: instrucciones para otras instancias de ChatGPT/Codex.
- `NORMAS_FORMATO.md`: reglas implementadas y pendientes.
- `AUDITORIA_FORMATO_REFERENCIA.md`: análisis del informe Word.

## Modelo de informe
Portada, Declaración, Acreditación, Presentación, Dedicatoria, Agradecimiento, Resumen, Abstract, Índice, Índice de tablas, Índice de figuras; capítulos I Introducción, II Marco teórico, III Metodología, IV Resultados, V Discusión, VI Conclusiones y recomendaciones; Referencias y anexos.

La numeración de tablas y figuras es consecutiva y los títulos de capítulo y subtítulos son editables sin perder su jerarquía.

## Estado de QA
La versión local con el escudo incluido compiló dos veces con XeLaTeX y produjo un PDF de **27 páginas** de ejemplo (muchas páginas son preliminares y divisorias obligatorias). La tipografía local de comprobación es Tinos, no Times New Roman auténtica. La equivalencia exacta con Word requiere comparar en Overleaf/Word.


## Matriz de operacionalización de variables (opcional)

La plantilla incorpora en \`tablas.sty\` un entorno dedicado para reproducir
el estilo de la plantilla de **proyecto de tesis**: hoja A4 apaisada, tabla
con bordes completos, agrupación de variables mediante \`\multirow\`,
separación horizontal entre dimensiones con \`\cline\`, columna **Indicador**
(en singular) e indicadores presentados individualmente.

**Para insertarla en el lugar deseado del informe** (por ejemplo, en Metodología
o Anexos), agregue al archivo \`main.tex\`:

\`\`\`latex
\input{ejemplos/matriz_operacionalizacion.tex}
\`\`\`

El ejemplo es **opcional** y no se incluye automáticamente. Es necesario
reemplazar los valores de ejemplo, definir variables/dimensiones/indicadores
reales y verificar el contenido metodológico.

Comandos disponibles:

- \`\begin{matrizOperacionalizacion} ... \end{matrizOperacionalizacion}\`:
  crea una página horizontal, sin alterar el estilo del resto del documento,
  con numeración centrada en la parte inferior visible de la página.
- \`\tituloMatrizOperacionalizacion[tab:operacionalizacion]{Título}\`:
  genera número automático, leyenda y entrada al índice de tablas.
- \`\iniciotablaHorizontal\`: alinea la matriz con el margen de texto.
- \`\celdaIndicadores{\item Primer indicador. \item Segundo indicador.}\`:
  genera elementos individuales dentro de una celda.
- \`\paginaHorizontalCentro\`: disponible para otras páginas horizontales
  construidas manualmente; en \`matrizOperacionalizacion\` se aplica de forma
  automática y no debe llamarse una segunda vez.

**Cuidado con los marcadores**: si el texto de un \`\item\` empieza con
\`[\`, escriba \`\item \relax [texto]\` para evitar que LaTeX interprete los
corchetes como una etiqueta opcional de lista.

Para matrices que excedan una página, divida la información en bloques
horizontales con encabezados repetidos. No divida filas de una
\`\multirow\` entre páginas. Cada tabla mantiene bordes y alineación propios.
