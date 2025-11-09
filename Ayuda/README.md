# CapMKV — Guía de ayuda y resolución de problemas

Esta guía te ayuda a identificar y resolver situaciones comunes al usar CapMKV.

## Conceptos clave
- `Capítulo`: entrada con un tiempo y un nombre.
- `Lista principal`: el listado de la ventana principal donde se agregan/edita/borra capítulos.
- `Archivo actual`: ruta donde se guarda/abre la lista de capítulos.
- `Cambios sin guardar`: modificaciones pendientes; se ofrece guardar al cerrar.

## Problemas frecuentes y soluciones

1) No puedo guardar porque la lista está vacía
- Causa: no hay capítulos en la ventana principal.
- Solución: añade al menos un capítulo (desde la ventana principal, Capítulos por lote o Creación de capítulos automática).

2) Al abrir un archivo, algunos nombres aparecen con `(2)`, `(3)`, etc.
- Causa: tiempos duplicados; los nombres se renombraron para distinguir entradas.
- Solución: edita los nombres si deseas títulos específicos o ajusta tiempos para evitar duplicados.

3) Capítulos por lote no reconoce mis líneas
- Causa: formato de línea no compatible.
- Solución: usa uno de los formatos admitidos:
  - `HH:MM:SS | título`
  - `HH:MM:SS - título`
  - `HH:MM:SS\t título` (tabulador)
  - `HH:MM:SS, título`
  - También `MM:SS` (se normaliza a `HH:MM:SS.000`)
- Consejo: revisa el resumen que muestra ejemplos de líneas ignoradas.

4) Creación de capítulos automática no genera capítulos
- Causas posibles:
  - Duración total `Hora/Min/Sec` es `0`.
  - Intervalo `NMin` es `0` o negativo.
- Solución: establece una duración total mayor a 0 y un intervalo en minutos mayor a 0.

5) Al cerrar, no aparece el aviso para guardar
- Causa: no hay cambios sin guardar.
- Solución: realiza alguna modificación (añadir/editar/borrar) para que se active el aviso.
- Nota: si abriste y modificaste directamente en la ventana principal, el aviso se mostrará correctamente.

6) Quiero añadir texto desde varios archivos a Capítulos por lote
- Solución: arrastra y suelta múltiples `.txt`/`.csv` sobre el cuadro de texto; se combinarán y se informará del total de líneas.

7) Quiero mantener mi lista actual al usar Capítulos por lote/Creación de capítulos automática
- Solución: al preguntar `¿Añadir o sustituir?`, elige `Añadir` para conservar y agregar al final.
- Si eliges `Sustituir`, se vaciará la lista actual; puedes guardar antes si lo deseas.

8) El nombre del archivo en el aviso de cierre
- Comportamiento: si existe `archivo actual`, el mensaje de cierre muestra el nombre.
- Ventaja: ayuda a decidir rápidamente si guardar sobre ese archivo.

## Buenas prácticas
- Guarda con frecuencia desde la ventana principal para registrar tus cambios.
- Usa nombres claros para los capítulos; el orden visual se basa en tiempo y después nombre.
- Verifica el formato de tus listas masivas antes de procesarlas en Capítulos por lote.
- En Creación de capítulos automática, escoge un intervalo razonable según la duración total.

## Preguntas frecuentes (FAQ)
- ¿Puedo usar milisegundos? Sí, el tiempo se muestra como `HH:MM:SS.mmm...`; la herramienta automática genera con precisión fija.
- ¿Puedo borrar rápido varios capítulos? Sí, selecciona en el listado y pulsa `Delete`; verás un aviso con el total borrado.
- ¿Qué pasa si edito un capítulo a un tiempo ya existente? El nombre se ajustará con sufijo `(N)` para evitar duplicados.

## Contacto y soporte
- Sitio: `https://www.zynerio.com.es`
- Si detectas un error, guarda un ejemplo del archivo o de las líneas problemáticas y describe los pasos para reproducirlo.

---
Esta guía se actualiza conforme se incorporan nuevas funciones o cambios.
