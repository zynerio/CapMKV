# CapMKV — Funcionamiento paso a paso

CapMKV facilita la creación, edición y guardado de capítulos para vídeos (MKV). A continuación se detalla el uso de todas las opciones de las tres áreas principales: Ventana principal, Capítulos por lote y Creación de capítulos automática.

## Ventana principal

- `Listado de capítulos`: muestra cada capítulo con dos columnas: tiempo (`HH:MM:SS.mmm...`) y nombre.
- `Hora/Min/Sec/milisegundos`: controles numéricos para fijar el tiempo del capítulo.
- `Nombre`: texto con el título del capítulo.
- `Añadir`: añade un capítulo usando los valores de tiempo y nombre.
-  Acceso rápido: pulsar `Enter` dentro de `Nombre del capítulo` también añade.
- `Editar`: modifica el capítulo seleccionado con los valores actuales de tiempo y nombre.
- `Borrar`: elimina los capítulos seleccionados del listado y muestra cuántos se borraron.
- `Borrar todo`: limpia completamente el listado.
- `Abrir`: carga un archivo de capítulos:
  - Filtros: `*.txt`, `*.xml` (o detección automática si el formato es válido).
  - Al cargar, los tiempos duplicados renombrarán el nombre como `Nombre (N)` para evitar colisiones.
- `Guardar`: guarda la lista de capítulos.
  - Si ya hay `ruta` activa, se guarda en ese archivo.
  - Si no hay `ruta`, se pedirá ubicación y formato (TXT o XML).
- `Capítulos por lote`: abre la herramienta para convertir texto pegado/cargado en capítulos.
- `Creación de capítulos automática`: abre la herramienta para generar capítulos a intervalos.
- `Información`: abre la ventana de información.

Acciones útiles:
- Tecla `Delete` sobre el listado: borra los capítulos seleccionados y muestra un aviso con el total.
- Cierre: si hay cambios sin guardar, se preguntará si deseas guardar. El cuadro indica el conteo de capítulos sin guardar y, si existe, el nombre del archivo actual.

Notas de edición y duplicados:
- Al editar o añadir, si existe otro capítulo con el mismo tiempo, el nombre se ajusta automáticamente con sufijos `(2)`, `(3)`, etc. para mantener diferenciación.

## Capítulos por lote (entrada masiva)

Objetivo: transformar bloques de texto (pegados, arrastrados o abiertos) en capítulos del listado principal.

Controles y flujo:
- `Cuadro de texto`: pega o carga aquí tus líneas de tiempos.
- `Pegar`: inserta el contenido del portapapeles.
- `Añadir`: procesa el contenido y añade capítulos al listado principal.
- `Abrir`: carga archivos `.txt` o `.csv` en el cuadro de texto.
- `Limpiar`: borra el contenido del cuadro (con confirmación).
- Drag & Drop: puedes arrastrar uno o varios archivos `.txt`/`.csv` al cuadro; se combinan y se informa del total de líneas.

Formatos admitidos por línea:
- `HH:MM:SS | título` (con barra vertical y otra columna intermedia opcional).
- `HH:MM:SS - título`.
- `HH:MM:SS\t título` (tabulador).
- `HH:MM:SS, título`.
- También acepta `MM:SS` (se normaliza a `HH:MM:SS.000`).

Resolución de duplicados y reporte:
- Si el tiempo ya existe, el nombre se renombra automáticamente: `Título (N)`.
- Al terminar, se muestra un resumen con:
  - Cuántos capítulos se agregaron.
  - Cuántos fueron renombrados por duplicados (con detalle de cambios).
  - Ejemplos de líneas ignoradas por formato inválido.

Añadir vs. Sustituir:
- Si el listado principal tiene capítulos, se pregunta si deseas `Añadir` al final o `Sustituir` (vacía la lista actual).
- Antes de `Sustituir`, puede ofrecer guardar la lista actual.

## Creación de capítulos automática (intervalos)

Objetivo: generar capítulos automáticamente cada `N` minutos a partir de una duración total del vídeo.

Controles:
- `Hora/Min/Sec`: duración total del vídeo.
- `NMin`: intervalo en minutos por capítulo (debe ser mayor que 0).
- `Añadir`: genera los capítulos.

Cómo genera:
- Empieza en el primer intervalo y continúa hasta alcanzar la duración total.
- Crea capítulos con nombre `Capítulo 1`, `Capítulo 2`, etc.
- Los tiempos se normalizan en el formato `HH:MM:SS.000000000`.
- Si el tiempo existe, el nombre se renombra automáticamente con sufijo `(N)`.

Añadir vs. Sustituir:
- Si ya hay capítulos, pregunta si deseas `Añadir` o `Sustituir` (con opción de guardar antes de sustituir).

Resultados:
- Muestra un resumen con cuántos capítulos se generaron y si hubo renombrados por duplicados.

## Guardado, apertura y avisos

- Se emplea un sistema de notificaciones uniforme (`avisos`) para información, advertencias y errores.
- Al cerrar la ventana principal, si hay cambios sin guardar, se ofrece guardar. El mensaje incluye el número de capítulos sin guardar y, si aplica, el nombre del archivo actual.

## Consejos

- Usa Capítulos por lote si tienes una lista de tiempos desde otra fuente (texto, CSV).
- Usa Creación de capítulos automática para series con intervalos regulares.
- En la ventana principal, aprovecha `Enter` en el nombre para añadir rápido y `Delete` para borrar seleccionados.

---
Si detectas comportamientos inesperados, consulta la guía de ayuda (`Guia_Ayuda_Consulta.md`).
