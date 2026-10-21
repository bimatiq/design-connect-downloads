<p align="center">
  <img src="assets/biq.png" alt="BIMATIQ" width="88" height="88">
</p>

<h1 align="center">BIMATIQ Design Connect</h1>

<p align="center"><strong>Del chat al dibujo. Con control en cada paso.</strong></p>

<p align="center">Lee, crea y edita en AutoCAD desde OpenAI / Codex local o Claude Desktop.</p>

<p align="center">
  <a href="https://github.com/bimatiq/design-connect-downloads/releases/latest/download/BIMATIQ.DesignConnect-stable-Setup.exe"><img src="assets/download-windows.svg" alt="Descargar para Windows · x64" width="280" height="52"></a>
</p>

<p align="center">Versión 0.4.0 &nbsp; · &nbsp; Windows x64 &nbsp; · &nbsp; AutoCAD 2026</p>

<p align="center">
  <a href="#empieza-en-3-pasos">Instalación</a> &nbsp; / &nbsp;
  <a href="#qué-puedes-hacer">Funciones</a> &nbsp; / &nbsp;
  <a href="#compatibilidad">Compatibilidad</a> &nbsp; / &nbsp;
  <a href="#ayuda">Ayuda</a>
</p>

---

## Empieza en 3 pasos

### 01 · Instala

Descarga y ejecuta **BIMATIQ.DesignConnect-stable-Setup.exe** desde la carpeta Descargas de Windows. No necesitas una cuenta de GitHub, Python ni .NET SDK. Si ya usas 0.3.2 o posterior, pulsa **Pausar BIMATIQ** y espera **En pausa · conexiones liberadas** antes de actualizar.

### 02 · Configura

Abre **BIMATIQ Design Connect** desde Inicio. En **Conexiones**, pulsa **Elegir carpeta** y selecciona una carpeta de copias de trabajo. Pulsa **Guardar ajustes** en **Carpetas y permisos** para autorizarla; las selecciones pendientes no conceden acceso. Activa **Creación y edición** cuando necesites modificar dibujos; el editor de texto tiene un permiso separado. Ambos empiezan desactivados.

Cierra la app de IA que vayas a configurar. En **Conexiones**, pulsa **Configurar** junto a Claude Desktop u OpenAI / Codex. Después vuelve a abrirla. La ruta avanzada es opcional; no necesitas buscar archivos de configuración.

### 03 · Empieza desde tu chat

Abre AutoCAD con una copia de trabajo. Comprueba en tu app de IA que aparece **bimatiq_design_connect** y prueba esta primera consulta:

> Usa BIMATIQ Design Connect para identificar el dibujo activo y sus unidades. No cambies ni guardes nada.

**Configurado** confirma que se han guardado los ajustes de conexión. **Conectado** confirma que la app ha recibido las herramientas; **AutoCAD aún sin comprobar** significa que todavía no se ha consultado un dibujo. El panel también distingue qué conexión controla las herramientas y la última consulta realizada. Estos registros locales sirven para Codex local y Claude Desktop. No conectan ChatGPT web ni móvil.

<details>
<summary><strong>Ver el panel de BIMATIQ Design Connect</strong></summary>

<br>
<img src="assets/settings.png" alt="Panel de conexiones de BIMATIQ Design Connect: configuración de OpenAI / Codex y Claude Desktop" width="880">

</details>

## Qué puedes hacer

| Trabajo | Capacidad incluida |
| :--- | :--- |
| **Consultar y revisar** | Documentos, capas, objetos, tablas, puertas, ventanas, atributos y selección actual en Modelo. |
| **Crear en un DWG abierto** | Líneas, polilíneas, círculos, notas, cotas, capas, creación de bloques estáticos e inserción de definiciones propias o importadas de DXF. |
| **Editar en un DWG abierto** | Mover, copiar y borrar objetos ordinarios; cambiar atributos de bloques estáticos. |
| **Trabajar con DXF** | Crear y modificar geometría, curvas continuas, textos, bloques, cotas y hojas; exportar PDF, PNG o SVG. |
| **Revisar y medir DXF** | Inventario/cajetines, auditoría por lote, reglas CAD, Xrefs, anotaciones, cotas, unidades, comparación de revisiones, áreas, longitudes, hatches y candidatos de huecos. |
| **Preparar información de entrega** | Cuadro de aberturas por atributos, preflight de hojas, conciliación CAD–Excel de lectura y registro de observaciones con exportación JSON protegida. |

Las **39 herramientas** incluyen lectura, creación y edición. Para cambiar un dibujo, el flujo es identificarlo y comprobar sus unidades, preparar una vista previa y confirmar el cambio. Si cambia el estado comprobado, la aplicación del cambio se rechaza.

**En DWG**, revisas el resultado y guardas tú desde AutoCAD. **En DXF**, confirmar la aplicación guarda el archivo y conserva una copia inmediatamente anterior cuando se reemplaza. Un DXF se abre en AutoCAD, pero no se presenta como un DWG.

### Informes con alcance explícito

Los informes trabajan sobre copias DXF guardadas y autorizadas. Indica unidades, tolerancias, límites y expectativas cuando se soliciten. Geometría no admitida, identificadores ambiguos y detalle recortado se declaran. Los materiales y nombres de zonas los proporciona el usuario. No certifican cumplimiento DWS, diseño o impresión nativa; no actualizan CAD y Excel entre sí. **La lectura de información de PDF no está incluida.** La exportación de PDF existente se conserva.

La validación de esta ampliación es offline con archivos sintéticos. La mejora medida reduce memoria de generación de snapshots limitados; no se afirma una mejora de velocidad ni del pico de memoria de la llamada completa.

### Selección y bloques en Modelo

Selecciona objetos en AutoCAD y pide su lectura desde el chat. Una selección vacía devuelve cero objetos; no inicia un recorrido del dibujo. Puedes crear una definición estática con objetos ordinarios conservando los originales, o importar una definición de un DXF autorizado y colocarla con sus atributos.

La importación no traslada todo el DXF ni redefine bloques existentes. Admite hasta 100 objetos por definición, unidades iguales y capas de destino existentes desbloqueadas. Admite líneas, círculos, arcos, polilíneas continuas con curvas, texto/MTEXT compatibles, atributos simples, puntos y elipses. La vista previa identifica las capas y estilos de destino. Rechaza tipos no admitidos, bloques anidados o dinámicos, referencias externas y conversiones implícitas.

## Compatibilidad

| Necesitas | Entorno de esta versión |
| :--- | :--- |
| **Sistema** | Windows x64. |
| **CAD** | AutoCAD 2026 y AutoCAD Architecture 2026 (25.1), con tu licencia correspondiente. Consulta el alcance comprobado debajo. |
| **App de IA** | OpenAI / Codex local o Claude Desktop, con tu propia cuenta y acceso a herramientas MCP. |
| **Internet** | Para la app de IA, las descargas y las actualizaciones. El procesamiento CAD del conector es local. |
| **Dependencias** | El instalador incluye el entorno del conector. No hace falta instalar Python ni .NET SDK. |

**Alcance comprobado.** Se ha trabajado con AutoCAD Architecture 2026 y también se han comprobado la conexión, la lectura, la creación de una nota y la edición de su texto en modo AutoCAD 2026, sin funciones de Architecture cargadas. Esta última prueba se realizó con el modo AutoCAD incluido en la instalación de Architecture; una instalación independiente de AutoCAD aún no se ha comprobado. Otras versiones, AutoCAD LT y macOS quedan fuera de la validación actual.

## Tu trabajo, bajo control

- **Carpetas autorizadas.** Trabaja sobre copias y limita el acceso a las carpetas que elijas.
- **Cambios con confirmación.** Creación, edición y sustitución de texto requieren sus permisos correspondientes. Las actualizaciones no los activan por sí solas.
- **Una conexión al mando.** Varias apps pueden ver las herramientas; la primera que las usa conserva el control hasta cerrarse. Cierra todas las conexiones para cambiar ajustes de conexión o actualizar.
- **Recuperación antes de continuar.** Si una acción queda interrumpida o su resultado es incierto, revisa AutoCAD y los archivos afectados antes de repetirla o guardar.

### Datos y privacidad

El conector procesa el CAD localmente. Los datos que pidas en el chat se envían al proveedor de IA que estés usando. GitHub recibe las solicitudes de descarga y su dirección IP; esta función no envía dibujos a GitHub. Los comentarios de uso son opcionales y están desactivados; esta versión no tiene un servicio receptor configurado.

## Actualizaciones

### Actualizar sin cerrar Claude ni tus chats

Con 0.3.2 o posterior, abre **Conexiones → Pausar BIMATIQ**. Espera **En pausa · conexiones liberadas**, usa **Buscar y aplicar** y después **Reanudar BIMATIQ**. Si Claude no lo reintenta automáticamente, reconecta solo BIMATIQ en Claude sin cerrar tus chats. Durante la pausa puede aparecer desconectado.

La pausa espera al trabajo admitido y al worker real de AutoCAD. No cancela operaciones, no guarda dibujos ni elimina los bloqueos de un resultado incierto. Las carpetas, permisos, recuperación y el catálogo de 39 herramientas se conservan.

**Si tienes 0.3.0 o 0.3.1:** libera sus conexiones BIMATIQ y cierra Ajustes para esta primera instalación. Si una app mantiene una conexión activa, ciérrala una última vez para esta transición. Después podrás usar Pausar para futuras actualizaciones compatibles. Cambiar el registro/configuración de una app sigue requiriendo cerrarla para proteger sus ajustes.


**Si tienes 0.2.x:** ejecuta una vez el instalador actual sobre la instalación existente, desde Descargas de Windows y con las conexiones de BIMATIQ cerradas. No desinstales ni borres carpetas: se conservan tus ajustes, permisos y dibujos. La nueva versión añade tres herramientas; el actualizador antiguo no amplía automáticamente el catálogo autorizado. Después reabre Claude. En OpenAI / Codex, con esa app cerrada, pulsa Configurar para actualizar su catálogo gestionado; las listas personalizadas se conservan.

**Desde 0.3.2 y versiones posteriores:** Buscar y aplicar recibe las siguientes versiones aprobadas de catálogo compatible.

El canal de versiones aprobadas está disponible. BIMATIQ comprueba las actualizaciones al iniciar una sesión que obtiene el control o desde **Ajustes → Actualizaciones**. Se aplican entre sesiones, con verificación de aprobación e integridad, conservando tus ajustes y la recuperación de la versión anterior.

Puedes pausar las actualizaciones o buscarlas manualmente. Si no hay conexión o la versión no está aprobada, se conserva la instalación actual. **Los usuarios no necesitan claves privadas, copias de claves ni una cuenta de GitHub.**

## Ayuda

<details>
<summary><strong>La conexión aparece ocupada o no puedo configurar otra app</strong></summary>

Cierra por completo las conexiones de BIMATIQ en las apps de IA. Desactivar un interruptor puede dejar el proceso abierto. Los ajustes y las actualizaciones requieren cerrar también las conexiones que solo muestran el catálogo. BIMATIQ no cerrará tus apps ni tus dibujos automáticamente.

Después de cambiar permisos, guarda los ajustes y desconecta y vuelve a conectar para aplicarlos. Configurar una conexión no guarda permisos pendientes.

</details>

<details>
<summary><strong>Windows muestra un aviso sobre el editor</strong></summary>

La versión 0.3.2 no lleva firma de editor de Windows. La aprobación de las actualizaciones de BIMATIQ es una comprobación distinta y no sustituye ese certificado. Descarga únicamente desde este repositorio y respeta la política de seguridad de tu equipo.

</details>

<details>
<summary><strong>Una operación se interrumpió</strong></summary>

Comprueba AutoCAD y los archivos afectados antes de usar **Revisar sesión interrumpida** en Ajustes. No repitas, reviertas ni guardes automáticamente un resultado incierto. Un tiempo de espera agotado no cancela una operación que AutoCAD ya está ejecutando.

</details>

<details>
<summary><strong>Límites de esta versión</strong></summary>

La edición nativa se limita a objetos ordinarios directos del modelo y bloques estáticos. No incluye edición de objetos AEC/proxy, relaciones dinámicas ni comandos libres. Las acciones nativas admiten hasta 100 objetos/copias; las de DXF, hasta 500 elementos. La ruta DXF limita los archivos leídos y resultantes a 128 MiB.

Las hojas y exportaciones DXF no certifican una apariencia idéntica al trazado de AutoCAD. El usuario mantiene la revisión y la responsabilidad de diseño.

Los cambios DWG crean un grupo Deshacer y dejan el dibujo sin guardar. Los cambios DXF se guardan al aplicar, con una única copia `.biq-backup` del archivo reemplazado; no mantienen un historial ilimitado ni usan Deshacer de AutoCAD para el archivo en disco. Evita que otro editor escriba el mismo DXF. Las carpetas autorizadas no aíslan otros programas del sistema.

La instalación no abre AutoCAD ni modifica dibujos. Para desinstalar, cierra las conexiones y usa la opción de Windows; se conservan dibujos y ajustes. Una configuración modificada manualmente no se sustituye automáticamente. Ante una actualización de configuración incompleta, reconcilia los archivos antes de continuar.

</details>

<details>
<summary><strong>Verificar la descarga 0.3.2</strong></summary>

Archivo: **BIMATIQ.DesignConnect-stable-Setup.exe**

SHA-256:

```text
e0ce15a809e02ffc0418dcb13660a04b70768f6264134b69f9560bf090a5268b
```

Consulta los archivos de la [versión 0.3.2](https://github.com/bimatiq/design-connect-downloads/releases/tag/v0.3.2). El botón principal apunta siempre al instalador estable más reciente.

</details>

Para soporte, indica la versión, la app de IA y una descripción breve del problema. Revisa cualquier archivo antes de compartirlo y no incluyas dibujos, credenciales ni información confidencial sin autorización.

---

<p align="center"><strong>BIMATIQ · Design Connect</strong><br>Desarrollado y distribuido por BIMATIQ.<br>AutoCAD Connector para Windows</p>

<p align="center"><a href="LEGAL.md">Información legal y licencias</a> &nbsp; · &nbsp; <a href="https://github.com/bimatiq/design-connect-downloads/releases">Versiones</a></p>

## Detección de Claude en Windows

BIMATIQ identifica Claude Desktop instalado directamente o desde Microsoft Store. Reconoce el traslado a Claude-Data cuando hay evidencia del perfil; si las ubicaciones entran en conflicto, conserva la configuración. Si BIMATIQ no aparecía antes, cierra Claude y pulsa Configurar de nuevo. Si hay varias instalaciones, elige la app que utilizas. No necesitas editar archivos de configuración. Las rutas personalizadas y los ajustes existentes se conservan. Si no puede identificar la instalación, no cambia nada.

Configurar confirma el registro; Conectado confirma que Claude ha recibido las herramientas. La conexión real debe comprobarse después de configurar tu instalación.

## Actualizar y reparar

Usa Buscar y aplicar para las siguientes actualizaciones aprobadas. La recuperación identifica la versión instalada, admite copias idénticas y comprueba todo el archivo antes de continuar.

Si una versión anterior muestra No hay un único paquete actual para recuperación: cierra Claude, OpenAI y Ajustes de BIMATIQ cuando terminen su trabajo; descarga y ejecuta este instalador una sola vez sobre la instalación existente, desde Descargas de Windows. No desinstales ni borres carpetas: conserva tus ajustes y dibujos. Después reabre Claude. Esta reparación inicial sustituye el actualizador antiguo; la corrección no puede cambiar el código que ya está instalado antes de aplicarse.
