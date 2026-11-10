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
