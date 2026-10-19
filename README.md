# BIMATIQ Design Connect · AutoCAD Connector

Versión 0.2.5 para Windows x64 y AutoCAD Architecture 2026 (25.1).
El chat de OpenAI/Codex local o Claude Desktop es la interfaz de trabajo.
Necesitas tu propia cuenta AI y licencia CAD correspondiente. Internet sirve
al proveedor AI; los datos que solicites en el chat llegan al proveedor elegido.
No hace falta Python ni .NET SDK en el ordenador del usuario.

## Crear y editar

Incluye 36 herramientas seleccionadas del conector existente:

- Lectura de documentos, capas, objetos, tablas, puertas/ventanas y atributos.
- En un DWG abierto: líneas, polilíneas, círculos, notas, cotas, capas e inserción
  de bloques existentes; mover, copiar, borrar objetos ordinarios y cambiar
  atributos de bloques estáticos. El usuario revisa y guarda desde AutoCAD.
- En un archivo DXF: crear un dibujo vacío, curvas continuas mediante bulge,
  geometría, textos, bloques, cotas y hojas; modificar objetos y exportar PDF,
  PNG o SVG. El DXF se abre normalmente en AutoCAD; no se presenta como un DWG.

No se incluyen comandos libres ni los procedimientos particulares de Danbury.
La modificación nativa de geometría está limitada a objetos ordinarios directos
del modelo y bloques estáticos, no a objetos AEC/proxy ni relaciones dinámicas.
Las hojas DXF y su PDF usan el motor existente; el resultado no certifica
apariencia idéntica al plotter de AutoCAD ni responsabilidad de diseño.

## Instalar y conectar

Abre **BIMATIQ Design Connect** desde Inicio. Autoriza una carpeta de copias de
trabajo. Activa **Creación y edición** cuando quieras producir cambios. Esta
opción y el editor de sustitución de texto tienen permisos separados; ambos
comienzan desactivados y una actualización no los activa automáticamente.
Los ajustes anteriores conservan carpetas y preferencias sin conceder el permiso
nuevo. Desconecta y vuelve a conectar para aplicar un cambio de permisos.

Cierra la app AI antes de cambiar su conexión y abre **BIMATIQ Design Connect**
desde Inicio. En **Conexiones**, pulsa **Configurar** junto a OpenAI
o Claude. No necesitas buscar un archivo: OpenAI usa los ajustes de tu usuario,
disponibles para otros proyectos locales; Claude usa sus ajustes de escritorio.
La ruta avanzada es opcional. Conectar no guarda cambios pendientes de permisos.

El panel muestra el registro real: sin configurar, configurado, retirado desde
la app, desactivado o modificado. No presenta un registro como conexión activa.
En OpenAI busca `bimatiq_design_connect` en **Plugins > MCPs**; en Claude,
**Configuración > Desarrollador**, o **+ > Conectores** en el chat. La visibilidad
final depende de la app instalada y se comprueba allí después de abrirla.
En **Ruta avanzada**, selecciona la app y usa **Desconectar** para retirar solo la entrada propia, también si fue creada
en una ruta avanzada. No se borran dibujos, carpetas autorizadas ni otros MCP.

Una conexión OpenAI anterior que solo pertenecía a este proyecto se traslada
al registro de usuario al pulsar **Conectar**. Se preparan ambos cambios antes
de escribir y se conservan copias de los archivos afectados. Una entrada
modificada manualmente no se sustituye. Un fallo parcial bloquea nuevas sesiones
y conserva la recuperación: no repitas ni confirmes una revisión sin reconciliar
los archivos de configuración. Desactiva la conexión BIMATIQ anterior antes de usar el paquete.
Varias conexiones pueden descubrir las herramientas. La primera que usa una
herramienta conserva el control exclusivo hasta cerrarse; las demás reciben un
aviso de conexión ocupada al intentar usarlas. Los ajustes y las actualizaciones
requieren cerrar todas las conexiones, incluidas las que solo muestran el catálogo.
La instalación no cierra apps,
no inicia AutoCAD y no abre ni cambia dibujos. Chat web/móvil no se configura
mediante estos archivos locales.

## Forma de trabajo

Primero comprueba el estado, la ruta exacta y las unidades. Para un archivo DXF,
consulta dxf_info antes de modificarlo y confirma unidades al crearlo.

Todas las nuevas acciones de creación/edición empiezan con una vista previa.
Para aplicar, la llamada lleva confirmación, dry_run=false y el expected_state
exacto de esa vista previa. Si cambian el archivo, los objetos o el estado
comprobado, se rechaza la aplicación. No deduzcas unidades, coordenadas ni
intención de diseño del usuario. Indica la capa expresamente en creación DWG.
Las acciones nativas admiten hasta 100 objetos/copias; DXF hasta 500 elementos.
Los archivos leídos/resultantes de esta ruta DXF están limitados a 128 MiB.

Las acciones DWG crean un grupo Undo y dejan el dibujo sin guardar. Revisa
los cambios y usa Ctrl+S en AutoCAD. El guardado DWG no se expone en esta versión.
Las acciones DXF preparan y validan el resultado aparte; al aplicar,
lo guardan y mantienen una `.biq-backup` por archivo reemplazado. La vista previa
no retiene un dibujo nuevo. No se usa Undo de AutoCAD para cambios DXF en disco.
Una sustitución conserva solo la copia inmediatamente anterior, no un historial
ilimitado. Trabaja sin otro editor escribiendo el mismo archivo.

Un fallo tras comenzar una acción o un resultado incierto requiere revisar lo
que ocurrió. No repitas, reviertas ni guardes automáticamente. Una sesión
interrumpida bloquea nuevas acciones/actualizaciones hasta revisarla en Ajustes.
Un timeout no cancela una operación COM; espera su finalización y reconcilia.
Las rutas permitidas no constituyen un aislamiento frente a otros programas.

## Actualizaciones y comentarios

El instalador utiliza la composición de BIMATIQ aceptada: edificio conceptual
entre líneas técnicas y materiales realistas, logo y paleta oscura. Su barra
indica el progreso real de Velopack. Los controles de ventana son los de Windows.
El panel sigue el diseño HTML aceptado: **Conexiones**, **Carpetas y permisos**
y **Ayuda**, con **Actualizaciones** como enlace secundario. Cada app muestra
una sola acción **Configurar**; **Ruta avanzada** conserva la selección de archivo
y la desconexión. Los tipos de letra se incluyen con sus licencias
y se cargan solo para este proceso; no se instalan en Windows.
La retícula, márgenes, altura de líneas y avisos siguen las medidas del HTML.
El icono usa los tamaños del archivo Windows; la barra de título conserva
los controles y la alineación propios del sistema, sin dibujar botones falsos.
El ICO contiene cuadros DIB de 16, 20, 24, 32, 40, 48, 64, 128 y 256 píxeles,
con transparencia. La exportación evita la conversión observada del ICO con
PNG al cargarlo en Tk/Windows; conserva los píxeles del BIQ original.
**Buscar y aplicar** reutiliza el verificador existente. Mientras trabaja muestra
una actividad indeterminada, sin porcentajes supuestos. Un aviso de versión
configurada o de comprobación terminada no afirma que un canal esté publicado.

Se reutiliza Velopack para versiones aprobadas entre sesiones. Puedes pausar o
buscar actualizaciones y recuperar la versión anterior. Los ajustes y la copia
de recuperación se conservan fuera de los archivos reemplazables. Nunca se
actualiza mientras otra sesión tiene el control. Añadir herramientas/permisos
exige una versión aceptada y una migración deliberada; no se amplían permisos
por recibir una actualización automática.

Esta versión prepara el canal público de descargas de BIMATIQ en GitHub.
La publicación requiere aprobación humana; configurar una dirección no confirma
que la descarga esté disponible. El instalador contiene solo la clave pública
de verificación. La clave privada de aprobación no se entrega al usuario.
Una vez publicado, se buscan versiones al iniciar una sesión que obtiene el
control o desde Ajustes. No hay sondeo continuo. Sin conexión o con una versión
no aprobada se conserva la instalación actual. GitHub recibe las solicitudes
de descarga y su dirección IP, nunca el contenido del dibujo por esta función.
Las descargas del instalador son públicas; el repositorio de desarrollo permanece
privado. No necesitas una cuenta ni un token de GitHub para descargar o actualizar.
La instalación anterior 0.2.3 necesita una actualización deliberada a este
instalador configurado; no puede descubrir por sí sola el nuevo canal.

Los comentarios de uso siguen sin receptor configurado y no se envían.
Los comentarios son opcionales y empiezan apagados. Antes de habilitarlos se
informarán proveedor, región, conservación y baja. Se excluyen dibujo, texto,
conversación, rutas, capturas, identidad de usuario y errores completos.
Puedes preparar una valoración local para revisar y compartir manualmente.

## Recuperación y soporte

Desconecta la app AI antes de desinstalar. Usa la opción de Windows, que pasa
por el control de sesiones de BIMATIQ. Solo se retira el registro propio intacto;
se conservan dibujos y ajustes. Ante una sesión interrumpida, comprueba AutoCAD
y los archivos afectados antes de elegir **Revisar sesión interrumpida**.
Las preferencias, baja de comentarios y pausa siguen disponibles conectado.
Para soporte indica versión, app AI y descripción breve; no envíes información
confidencial sin autorización. Los ejercicios previos permanecen cerrados.

## Descarga de esta versión

Versión 0.2.5. Instalador: `BIMATIQ.DesignConnect-stable-Setup.exe`.

SHA-256 del instalador: `64ac744823f111b4effeb1225167be5ca91749f84c94c05291f8fe1196a0fde5`.

Esta versión no lleva firma de editor de Windows. La firma de aprobación de BIMATIQ protege las actualizaciones y es independiente del aviso de Windows.
