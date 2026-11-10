# Auditoría visual y estructural del Word de referencia — Informe de tesis

**Fecha de análisis:** 2026-11-09  
**Documento:** informe de tesis de maestría proporcionado por el usuario, únicamente como **referencia de formato**.  
**Estado:** especificación observada, **no** norma institucional oficial validada. No copiar su contenido académico ni datos personales.

## 1. Método y alcance
- Inspección directa del DOCX y propiedades OOXML mediante `python-docx`.
- Documento: 4 secciones, 923 párrafos, 44 tablas y 23 imágenes en línea.
- Inspección visual de portada, preliminares, índices, divisorias de capítulos, cuerpo, encabezados de varios niveles, tablas, figuras, referencias y anexos.
- El renderizado de referencia efectuado con LibreOffice dio 146 páginas; el procesamiento de archivo original exhibe 144. **Los saltos pueden variar entre motores**: validar finalmente en Microsoft Word y XeLaTeX; no garantizar paginación idéntica.

## 2. Página y párrafos
- Papel vertical: A4 (21 × 29,7 cm).
- Sección vertical inicial: márgenes superior/inferior 2,50 cm, izquierdo 3,00 cm, derecho 2,50 cm. Otras secciones verticales tienen cambios (incluido derecho 3,25 cm); no asumir que todos sean normativos.
- Secciones horizontales: A4 apaisado, márgenes de aprox. 2,54 cm.
- Estilo `Normal`: Times New Roman 12 pt; interlineado 1,5; espacio posterior 12 pt; primera línea +1,27 cm y sangría izquierda base 0,30 cm.
- Títulos y elementos preliminares a menudo sobreescriben localmente los estilos; reconstruir en comandos reutilizables, no copiar tabulaciones/espacios manuales.
- Números de página del cuerpo centrados abajo en páginas verticales. Validar posición centrada abajo también para horizontales.

## 3. Carátula
Orden visual:
1. Universidad (mayúsculas, negrita, centrada; en el Word, primer bloque ~18 pt).
2. Escuela de Posgrado (centrado, negrita; ~14 pt).
3. Escudo centrado.
4. Denominación «TESIS PARA OPTAR EL GRADO DE…» (centrada, negrita, varias líneas).
5. Título académico en mayúsculas y negrita, **entre dos líneas horizontales**.
6. Línea y sublínea de investigación.
7. Autor y jurado evaluador (Presidente/Secretario/Vocal), asesor, ORCID.
8. Ciudad y año centrados.
9. Resolución directoral inferior a la izquierda.

Los valores de nombres, título, grado, resolución y demás son variables; la estructura y formato son de la plantilla.

## 4. Preliminares y orden
Carátula → Declaración de originalidad → Acreditación → Presentación → Dedicatoria → Agradecimiento → RESUMEN → ABSTRACT → ÍNDICE → ÍNDICE DE TABLAS → ÍNDICE DE FIGURAS.

- Declaración y acreditación: bloques textuales y firmas con campos editables, no fijar identidades.
- Dedicatoria y agradecimiento: alineación peculiar a la derecha en el Word; **documentar**, no imponer aún como norma universal.
- Resumen y Abstract: encabezado centrado en mayúsculas; debajo se repite el título del trabajo y luego el resumen; palabras clave al final.
- Los índices deben ser automáticos mediante comandos LaTeX. El archivo de referencia muestra inconsistencias tipográficas y de tabulaciones que no deben copiarse.

## 5. Estructura del cuerpo
Cada capítulo principal observado tiene **página divisoria independiente**, con «CAPÍTULO [ROMANO]» y el nombre centrados; en la página siguiente se repite el encabezado completo antes del contenido.

Capítulos:
I INTRODUCCIÓN; II MARCO TEÓRICO; III METODOLOGÍA; IV RESULTADOS; V DISCUSIÓN; VI CONCLUSIONES Y RECOMENDACIONES.
Después: REFERENCIAS BIBLIOGRÁFICAS y ANEXOS.

Subpartes observadas (contenido de los títulos configurable por tesis):
- Introducción: problema, enunciado, alcance, viabilidad, justificación, hipótesis, objetivos.
- Marco teórico: antecedentes, bases teóricas, operacionalización/matriz en el cuerpo.
- Metodología: material, población, muestra, técnicas/instrumentos, procedimientos, diseño de contrastación, análisis de datos, ética.
- Resultados: descripción del caso y base, resultados descriptivos, supuestos, contrastación de hipótesis, síntesis.
- Discusión.
- Conclusiones y recomendaciones.
- Referencias y anexos.

## 6. Niveles de título: modelo semántico que conviene implementar
- Capítulo: romano + título en mayúsculas, centrado en divisoria; título del capítulo nuevamente en la primera página de contenido.
- Nivel 2 (`1.1.`, `3.1.`, `4.5.`): negrita de cuerpo, sin tamaño grande; alineación izquierda, sangría pequeña (~0,25 cm desde estilo, además del margen de página).
- Nivel 3: subsecciones con número opcional, formato contextual (se observan estilos Heading 3 y 3Subtitulo).
- Nivel 4 (p. ej. `1.1.1.1.`): negrita, con sangría más profunda (~2 cm) y posible envoltura a segunda línea.
- Algunos subtítulos sin número (p. ej. «Conveniencia», «Características problemáticas») aparecen en el cuerpo; distinguir títulos semánticos sin número de encabezados numerados, aunque puedan compartir jerarquía.
- Espacios entre título/título, título/párrafo, título/lista y título/tabla deben depender del tipo de transición, no del texto ni de `\\vspace` aislados.
- No copiar directamente numeraciones duplicadas o inconsistencias del Word (p.ej. «1. CAPÍTULO I»).

## 7. Tablas y figuras
- Leyendas **encima** del elemento. Primera línea «Tabla N» o «Figura N» en **negrita**. Segunda línea: título en *cursiva*, alineado al margen izquierdo; formato de párrafo `Caption`: interlineado 1, espacio posterior 10 pt.
- Tablas de resultados: bordes principalmente horizontales finos; número y título arriba; nota abajo. Matriz de operacionalización: 7 columnas con cuadrícula y celdas fusionadas; anexos de instrumentos con cuadrícula y columnas de fondo azul muy claro.
- Las notas son después del elemento; se observan notas de 9 o 10 pt, a menudo en cursiva; la palabra `Nota.` debe poder distinguirse y la fuente no debe quedar pegada a la tabla.
- Figuras: número/título arriba; gráfico/imagen inmediatamente debajo; nota o fuente después. No introducir segundo número de figura dentro del gráfico si puede evitarse; el documento original tiene algunos.
- Respetar `\\linewidth` del bloque de texto; usar `landscape` únicamente cuando el contenido lo requiera. En secciones horizontales, numeración centrada en el borde inferior visual de la página.

## 8. Referencias
- Encabezado «REFERENCIAS BIBLIOGRÁFICAS» en negrita.
- Entradas: Times New Roman 12 pt, sangría francesa de 1,27 cm; separación anterior local observada de 6 pt.
- Enlaces y DOI deben conservar familia tipográfica `\\urlstyle{same}`, permitir cortes de línea y no cambiar a monoespaciada.

## 9. Anexos
- Anexos con rótulo semántico «Anexo N: [nombre]», después título del instrumento.
- Anexos extensos en horizontal con tablas que aprovechan el ancho; algunos campos con fondo azul claro.
- El tamaño del texto de tablas puede ser reducido de forma controlada respecto al cuerpo.

## 10. Distinción entre estructura y contenido
**Estructura invariable:** página divisoria de capítulos, jerarquías, leyendas, índices automáticos, estilos de tabla, ubicación de números, espacios, portada y preliminares.
**Contenido variable:** texto de títulos, capítulos, variables, instrumentos, números estadísticos, tablas, figuras, citas, anexos, identidades personales y resolución.
**Cuidado:** El modelo observado pertenece a **un** informe de tesis. No declara por sí solo la norma universitaria vigente.

## 11. Pendientes antes de implementar plantilla final
1. Confirmar si la página divisoria por capítulo es obligatoria o solo característica de este informe.
2. Validar ubicación y estilo de la numeración de preliminares y páginas horizontales.
3. Normalizar jerarquías mezcladas, índices mal espaciados y numeración anómala.
4. Crear comandos independientes para portada, declaración, acreditación, resumen/abstract, divisorias, títulos numerados/no numerados, figuras, tablas, fuentes/notas, bibliografía y anexos.
5. Compilar e inspeccionar PDF por cada nivel y cada tipo de transición, comparándolo con este Word.
