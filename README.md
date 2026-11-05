# GIGARED ISP4.1.0 — Autocorte04:30 y Fecha de pago

[**Descargar ZIP completo para XAMPP Windows**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v4.1.0-autocorte-0430.zip) · [SHA-256](gigared-isp-xampp-v4.1.0-autocorte-0430.sha256)

Activa el autocorte solicitado a las **04:30 a. m., America/Lima**, solo para los clientes con Aplicar corte y cuenta de red configurados. Las condiciones se guardan cliente por cliente; una configuración posterior al horario entra en el siguiente ciclo. Los pagos/promesas pueden reconectar inmediatamente. El worker prepara las reglas propias al ejecutar su primera tarea elegible. El bloqueo general de red y `storage/config.php`/AES permanecen intactos.

En Clientes, **Zona** pasa a **Fecha de pago**: vencimiento pendiente más antiguo o próximo cobro, dd/mm/aaaa, resaltado de vencidas y Sin configurar cuando faltan datos. La zona original sigue almacenada.

**Actualizar:** respalda carpeta/base, detén Apache y worker, copia `nexoisp` sobre `C:\xampp\htdocs\nexoisp` conservando `storage/config.php`. Inicia Apache/MySQL y como ADMIN abre `http://localhost/nexoisp/actualizar.php`. Aplica **023_autocut_0430** y anteriores pendientes; reinicia el worker/tarea programada y pulsa Ctrl+F5. La migración añade un permiso y fija activación/horario; conserva SQL001–022 y datos comerciales.

El servidor y el worker deben estar funcionando. La cuenta API necesita permisos de escritura y FastTrack debe estar desactivado para garantizar el corte. Si el servidor estuvo apagado, procesa los cortes elegibles al volver a funcionar después del horario. Consulta `AUTOCORTE-0430.txt` y `PRUEBAS.txt` incluidos.

Validación: REST71, Socket72, navegador24, actualización4.0.0→4.1.0 con72 comprobaciones, transporte exclusivo41, perfil83 y regresiones de permisos/altas/acciones manuales. PHP8.2:397 archivos con sintaxis válida. Pruebas en simuladores, sin acceso a equipos del usuario. ZIP completo522 archivos, manifest SHA-256 y CRC verificados.

SHA-256: `15633ec94f5c0cda8eece7ed3bef186e35abe987b1949cc4e90c65352d7b041d`.

---

# GIGARED ISP 4.0.0 — Perfil de clientes

[**Descargar ZIP completo para XAMPP Windows**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v4.0.0-perfil-clientes.zip) · [SHA-256](gigared-isp-xampp-v4.0.0-perfil-clientes.sha256)

Pulsa el nombre del cliente para abrir Resumen, Servicios, Facturación, Tickets, Email & SMS, Documentos, Estadísticas y Logs. Incluye GPS editable, PDF, pagos/promesas, soporte con notas, avisos y configuración individual de fechas, gracia, mora, impuestos y corte/reducción por deuda. Basado en investigación de lectura del demo y documentación de Mikrowisp; implementación independiente integrada en GIGARED.

**Actualizar:** respalda carpeta/base, detén Apache y worker, copia `nexoisp` sobre `C:\xampp\htdocs\nexoisp` conservando exactamente `storage/config.php` y AES. Inicia Apache/MySQL, abre `http://localhost/nexoisp/actualizar.php` como ADMIN y aplica `022_client_profile_billing` (y anteriores pendientes). Reinicia el worker/tarea programada y pulsa Ctrl+F5. No reinstales ni borres la base. SQL001–021 permanecen idénticos; 022 añade nueve tablas.

Los cortes automáticos están desactivados por defecto y respetan el modo lectura. Las políticas pueden usarse para facturación local; controlar una cuenta importada requiere vinculación explícita y habilitar/preparar la red. Lee `PERFIL-CLIENTES.txt`, `INVESTIGACION-PERFIL-MIKROWISP.md` y `PRUEBAS.txt` del ZIP. Google Maps requiere clave propia; correo/SMS/Telegram requieren gateway. Los PDF son comprobantes internos, no facturación electrónica SUNAT.

Validado en Apache/PHP8.2/MariaDB10.4: perfil API82, motor REST115/Socket104, navegador26, actualización desde3.8.1 con197 comprobaciones; lint396archivos y regresiones de permisos/alta/activación. Las pruebas no accedieron a routers del usuario. ZIP completo519archivos; manifiesto SHA-256 interno, CRC y privacidad comprobados.

SHA-256: `e39cf7181e237700e25f0cf23fbdca98f31b192cc8c2db91abe868accbad89f4`.

---

# GIGARED ISP 3.8.1 para XAMPP Windows

[**DESCARGAR ZIP COMPLETO 3.8.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.8.1-activar-manual.zip)

Después de **Suspender manual**, la fila del cliente muestra el icono verde
**Activar manual**. Al confirmar habilita el mismo secret PPPoE, verifica la
respuesta y marca al cliente y servicio como Activos, conservando su perfil,
IP, usuario y contraseña. ADMIN y TÉCNICO pueden hacerlo. El equipo del cliente
podrá volver a conectarse con sus credenciales habituales. Las sesiones que ya
se hayan reconectado se mantienen abiertas.

Funciona también con suspensiones manuales realizadas en3.8.0. Una respuesta
perdida se verifica sin reenviar escrituras, con continuación explícita si falta
aplicar algo. No cambia network_read_only ni habilita cortes automáticos,
escrituras generales, cambios de plan o anulación de facturas.

Para actualizar: respalda carpeta/base, detén Apache/worker y copia `nexoisp`
sobre `C:\xampp\htdocs\nexoisp`, conservando exactamente `storage/config.php`.
Inicia Apache/MySQL; como ADMIN abre `/nexoisp/actualizar.php` y aplica
**021_client_ppp_reactivation** y las anteriores pendientes. Reinicia el worker
y pulsa **Ctrl+F5**. No reinstales ni borres la base. Lee `ACTIVAR-MANUAL.txt`.

Paquete completo: **503archivos**. Reactivación:92pruebas API y23de navegador;
actualización desde3.8.0:192pruebas. Simuladores REST/Socket y laboratorio aislado;
no se utilizaron equipos ni credenciales de tu instalación.

SHA-256: `a49914d58a2589e7fb2cf79fb6d7ccad1ed373632ee605751d47df18148436f1`

## Descargas e instrucciones anteriores

# GIGARED ISP 3.8.0 para XAMPP Windows

[**DESCARGAR ZIP COMPLETO 3.8.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.8.0-acciones-clientes.zip)

En **Clientes** aparecen los iconos **Suspender manual** y **Eliminar cliente**.
La suspensión deshabilita su secret PPPoE y cierra todas sus sesiones PPPoE.
La eliminación deshabilita/elimina su secret, cierra sus sesiones y retira el
cliente local conservando facturas, pagos y notas. ADMIN elimina; ADMIN/TÉCNICO
suspende. Cada acción presenta la cuenta y requiere confirmación. Las sesiones
ajenas o de otros protocolos permanecen intactas. Las respuestas perdidas tienen
verificación de lectura y continuación de la misma operación.

Estas acciones son excepciones manuales específicas al modo de lectura. No
habilitan escrituras generales, autocortes, cambios de perfil, firewall u ONUs.

Para actualizar: respalda carpeta/base, detén Apache/worker y copia `nexoisp`
sobre `C:\xampp\htdocs\nexoisp`, conservando exactamente `storage/config.php`.
Inicia Apache/MySQL; como ADMIN abre `/nexoisp/actualizar.php` y aplica
**020_client_ppp_actions** y las anteriores pendientes. Reinicia el worker y
pulsa **Ctrl+F5**. No reinstales ni borres la base. Lee `ACCIONES-CLIENTES.txt`.

Paquete completo: **501archivos**. Probado con simuladores REST/Socket y navegador;
no se utilizaron equipos ni credenciales de tu instalación.

SHA-256: `a678cc43093ed33a7128ebba77e6c168cdf5e9bbf13a4766cd54ab5fedf11c84`

## Descargas e instrucciones anteriores

# GIGARED ISP3.7.1 para XAMPP — Credenciales PPPoE automáticas

[**Descargar ZIP completo3.7.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.7.1-credenciales-automaticas.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.7.1-credenciales-automaticas.sha256)

En **Nuevo cliente → PPPoE**, usuario y contraseña son opcionales. El servidor
completa sólo los campos vacíos: genera un usuario disponible y una contraseña
segura cuando corresponda, y conserva exactamente los valores escritos.
Los reintentos y solicitudes repetidas usan la misma pareja de la reserva.

El resultado muestra el usuario asignado. Un administrador puede consultar la
clave desde **Editar cliente**, en las credenciales PPPoE. La contraseña se
almacena cifrada y no se incluye en el resultado público. Hotspot conserva sus
campos obligatorios y los clientes existentes mantienen sus credenciales.
También se conserva la IP al alternar el tipo de conexión y el correo opcional
puede quedar vacío al registrar desde el formulario.

## Actualizar

1. Respalda carpeta y base. Detén Apache y el worker o su tarea programada.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando EXACTAMENTE
   **storage\config.php** y su clave AES original.
3. Inicia Apache/MySQL, reinicia el worker y pulsa **Ctrl+F5**. Verifica **v3.7.1**.

**Desde3.7.0 no hay migraciones nuevas.** Si vienes de una versión anterior,
aplica las pendientes hasta019_client_provisioning como ADMIN en actualizar.php.
SQL001–019 conserva sus bytes/checksums; no reinstales ni reemplaces AES.
Lee **CREDENCIALES-AUTOMATICAS.txt** dentro del ZIP.

## Verificación

Compilación,11comprobaciones del generador,118de API específica,17del navegador
final y93de regresión de alta aprobadas. Se verificó conservación en reintentos,
creación REST/Socket y acceso explícito de administrador a la clave. Fixtures
sin equipos del operador. ZIP con CRC/manifiesto SHA256, sin configuración privada.

---

## Historial de descargas

# GIGARED ISP3.7.0 para XAMPP — Nuevo cliente con alta en MikroTik

[**Descargar ZIP completo3.7.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.7.0-nuevo-cliente.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.7.0-nuevo-cliente.sha256)

El botón **+ Nuevo cliente** incorpora un asistente de datos personales,
Google Maps/GPS y servicio. Permite seleccionar router, plan activo, pool/subred,
IP sugerida y credenciales. Registra cliente y servicio y crea/verifica la cuenta
PPPoE, usuario Hotspot o Simple Queue por API REST o Socket de MikroTik.

Valida IP/usuario duplicados y reservas simultáneas. Conserva una intención
cifrada y un resultado pendiente si se pierde la conexión; **Verificar alta**
sólo lee y **Reintentar este servicio** usa el mismo registro tras comprobar
su ausencia. Los editores existentes pueden cambiar nombre/comentario y
credenciales después de confirmar. Una activación pendiente protege su identidad.

Se revisó el demo oficial de Mikrowisp indicado por el usuario y se adaptó su
organización por pasos a GIGARED ISP y a los campos GPS/servicio solicitados.
Se mantienen ambos temas y el diseño móvil. El alta está autorizada para
ADMIN/TECHNICIAN; las restricciones de los demás cambios de red siguen vigentes.

## Actualizar

1. Respalda carpeta/base. Detén Apache y el worker o su tarea programada.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando EXACTAMENTE
   **storage\config.php** y su clave AES original.
3. Inicia Apache/MySQL. Como ADMIN abre **/nexoisp/actualizar.php** y aplica
   **019_client_provisioning** y las anteriores que estén pendientes.
4. Reinicia el worker o tarea programada y pulsa **Ctrl+F5**. Comprueba **v3.7.0**.

019añade **ClientProvisioning** y **ClientRegistrationSettings**, sin alterar
SQL001–018 ni registros anteriores. No reinstales ni cambies checksums/AES.
El ZIP incluye todo el código PHP/SQL, frontend fuente y frontend compilado.

## Configurar y usar

En **Ubicación GPS → Configurar Google Maps**, ADMIN puede guardar la clave
pública de su proyecto y su ID de mapa. Requiere Maps JavaScript API,
facturación de Google Cloud y restricciones de referente/API correctas.
Google recibe sólo el origen del sitio, no la ruta del cliente. Los campos
manuales de latitud/longitud están disponibles si el mapa no carga.

El router debe tener API accesible y permisos de escritura para crear el recurso.
PPPoE/Hotspot usan un perfil existente con nombre/velocidades coincidentes con
el plan; Simple Queue aplica sus velocidades. Se consultan rangos y ocupación
antes de guardar; no se cambia la configuración global del router.
El alta directa funciona sin esperar al worker. Los módulos financieros y
la sincronización1s conservan sus flujos. Consulta **NUEVO-CLIENTE.txt** e
**INVESTIGACION-MIKROWISP.md** dentro del ZIP.

## Validación

93comprobaciones API/REST/Socket,22de navegador,42de recuperación/editores,
169de actualización publicada3.6.0→3.7.0;57de IPv4/capacidad y las pruebas de
lectura/edición PPPoE, política general y moneda aprobadas. Fixtures aislados,
sin acceso a equipos del operador; el mapa se prueba por contrato del SDK,
sin claves ni cargos reales de Google. CRC/manifiesto SHA256 verificados,
sin configuración de instalación ni claves de prueba en el ZIP.

---

## Historial de descargas

# GIGARED ISP 3.6.0 para XAMPP — Sincronización MikroTik cada segundo

[**Descargar ZIP completo 3.6.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.6.0-sincronizacion-mikrotik.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.6.0-sincronizacion-mikrotik.sha256)

Ahora **cuentas PPPoE, perfiles, IP/sesiones activas y estado del router** se
consultan con un ciclo normal de **1 segundo**. El aviso muestra
**MikroTik · sincronización automática — Lecturas cada 1 s**.

Las lecturas se comparten entre panel y worker, con bloqueos que evitan
superposición. Los nombres siguen los comentarios y las velocidades los
perfiles; se conservan notas, precios, moneda e historial. Los planes nuevos
esperan su tarifa/activación local. No se importan contraseñas en masa ni se
configura el MikroTik. El detalle del router incorpora identidad, RouterOS,
uptime, CPU y memoria si dispone de permisos de lectura.

## Actualizar

1. Respalda carpeta y base. Cierra el worker y detén Apache.
2. Extrae el ZIP y copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp**,
   conservando EXACTAMENTE **storage\config.php** y su clave original.
3. Inicia Apache/MySQL y reinicia **INICIAR-WORKER.bat** con los archivos nuevos.
4. Abre el sistema y pulsa **Ctrl+F5**. Comprueba **v3.6.0** en el menú.

**Desde3.5.0 no hay migraciones nuevas.** Si vienes de versiones anteriores,
aplica sólo las pendientes hasta018_pppoe_online como ADMIN en actualizar.php.
Los routers con cuentas o perfiles previamente importados se incorporan solos;
en un router nuevo importa una vez. No reinstales ni cambies checksums/AES.

Mantén **INICIAR-WORKER.bat** activo para sincronizar con el navegador cerrado.
El ciclo no garantiza latencia cero: respuestas lentas y cantidad de routers
pueden alargarlo. Fallos usan reintentos2–30s; IP/conteo caducan a5s. Las ediciones
manuales autorizadas mantienen sus permisos. Los diagnósticos e históricos
conservan sus flujos; esta versión se centra en el inventario y estado MikroTik.
Lee **SINCRONIZACION-MIKROTIK.txt** dentro del ZIP.

## Verificación

Compilación TypeScript/Vite,90comprobaciones API/Chromium,17de formularios/planes/router
y166de actualización
publicada3.5.2 a3.6.0, lectores PPP/perfiles y Socket, bloqueos de escritura y
moneda/capacidades aprobados. SQL001–018 y configuración privada conservados.
Pruebas con fixtures, sin acceder a equipos del operador. ZIP con CRC y
manifiesto SHA256 por archivo; no contiene configuración de instalación.

---

## Historial de descargas

# GIGARED ISP 3.5.2 para XAMPP — Aviso de lecturas aclarado

[**Descargar ZIP completo 3.5.2**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.5.2-aviso-de-lecturas.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.5.2-aviso-de-lecturas.sha256)

En Clientes, el aviso principal ahora dice:
**IP de clientes · actualización automática — Consulta cada 1 s**.

Los **30 segundos** corresponden a la sincronización de las **cuentas PPPoE
(secrets)**, que aparece dentro de su propio detalle. Ese intervalo se mantiene
y se informa con su nombre. Las IP activas y Clientes Online conservan su
lectura de un segundo de3.5.1, sin cambiar los temporizadores del backend.

Los errores y pausas de sincronización se identifican como información de
cuentas. El aviso de IP se muestra para los roles/vistas con esa lectura;
Routers o vistas sin ese permiso muestran el intervalo real de cuentas.

## Actualizar

1. Respalda base y carpeta. Detén Apache y el worker.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando EXACTAMENTE
   **storage\config.php** y su clave privada original.
3. Inicia Apache/MySQL y pulsa **Ctrl+F5**. Reinicia el worker si lo utilizas.
4. Desde3.5.0 no hay SQLnuevo; desde versiones anteriores aplica las pendientes
   hasta **018_pppoe_online** como ADMIN en actualizar.php.

Consulta **AVISO-DE-LECTURAS.txt**. SQL001–018 y backend de3.5.1 conservados;
sólo cambia la etiqueta de versión en PHP. No cambian datos, permisos ni red.

## Verificación

Compilación de producción,14 comprobaciones visuales en ambos temas y30 de
moneda/capacidades aprobadas. Se compararon los PHP y SQL con el ZIP3.5.1;
los lectores y temporizadores son idénticos. Se conserva su validación de
cadencia/API/actualización. Este ajuste no necesitó consultar routers ni tocar
la instalación del operador. Las descargas anteriores siguen disponibles.

---

# GIGARED ISP 3.5.1 para XAMPP — Lectura cada segundo

[**Descargar ZIP completo 3.5.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.5.1-lectura-un-segundo.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.5.1-lectura-un-segundo.sha256)

**Clientes Online** y las **IP activas de Clientes** se consultan cada **1 segundo**
mientras sus vistas están visibles. El intervalo se mide desde el inicio de la
solicitud para evitar sumar otro segundo al tiempo de respuesta.

Ambas vistas comparten una sola lectura por router. Varias pestañas y usuarios
comparten la misma caché y reserva; no se consulta a MikroTik por cada cliente.
Se mantiene una sola llamada en curso. Si el equipo tarda más, se espera su
respuesta antes de continuar. La velocidad también depende del router y la red.

Los datos observados caducan a los **5 segundos**, sin esperar treinta. Una
respuesta retrasada no restaura números, IPs ni puntos verdes antiguos. Las
consultas se pausan al ocultar la pestaña o salir y se reanudan al volver.
Ante una falla de conexión, se espacian los intentos de router de 2 a 30 segundos;
el panel sigue comprobando el estado cada segundo sin anunciar datos viejos.

## Actualizar

1. Respalda base y carpeta. Detén el worker y Apache.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando EXACTAMENTE
   **storage\config.php** y su clave privada original.
3. Inicia Apache/MySQL. Desde **3.5.0 no hay SQL nuevo**. Desde versiones
   anteriores aplica las pendientes hasta **018_pppoe_online** en actualizar.php.
4. Pulsa **Ctrl+F5**. Reinicia el worker nuevo si lo usas para otras automatizaciones.

Consulta **LECTURA-UN-SEGUNDO.txt**. Las reservas antiguas de 15 segundos se
adaptan automáticamente al consultar, sin migrar datos. SQL001–018, configuración
privada, cuentas y finanzas se conservan. Sólo se realizan lecturas de RouterOS;
no se envían cortes, reconexiones ni cambios de configuración.

## Verificación

71 controles API/Chromium y151 de actualización real desde3.5.0 aprobados.
Se midió una cadencia de un segundo con dos paneles y retraso de respuesta,
una sola consulta en curso, actualización real de ambos valores, caché compartida
y caducidad de cinco segundos. SQL/config/datos exactos, backoff y permisos
conservados; cero escrituras RouterOS ni trabajos de red/OLT. Compilación y
regresiones de lector/Socket63, moneda30 y sólo lectura213 aprobadas.
Pruebas de laboratorio, sin acceso a la instalación ni equipos del operador.
Las descargas anteriores se conservan a continuación.

---

# GIGARED ISP 3.5.0 para XAMPP — Clientes Online

[**Descargar ZIP completo 3.5.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.5.0-clientes-online.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.5.0-clientes-online.sha256)

La primera tarjeta del dashboard se llama **Clientes Online** y muestra el
número de **sesiones PPPoE activas de MikroTik**, equivalente a PPP/Active
Connections, con un **punto verde brillante** cuando el total es reciente.
Se actualiza cada15segundos mientras el dashboard está visible.

Cuenta todas las sesiones `pppoe`, incluidas cuentas no importadas y conexiones
simultáneas del mismo usuario, sumando los routers reales REST/Socket. No usa
el estado administrativo Activo del cliente y no cuenta personas únicas.
Otros tipos PPP y routers simulados no se suman.

Una lectura real de cero es válida. Si falta un router, hay error o el dato
caduca a30segundos, muestra **— y punto gris**; no presenta una falla como cero
ni conserva verde un número antiguo. Comparte la consulta de sesiones con las
IPs de Clientes y no modifica la configuración de MikroTik.

## Actualizar

1. Respalda base/carpeta. Detén el worker y Apache.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando EXACTAMENTE
   **storage\config.php** y su clave privada original.
3. Inicia Apache/MySQL. Abre **/nexoisp/actualizar.php** como ADMIN y aplica
   **018_pppoe_online**, además de las anteriores pendientes.
4. Pulsa **Ctrl+F5** y abre el dashboard. La primera lectura puede tardar unos
   segundos. Reinicia el worker nuevo si lo usas para otras funciones automáticas.

Consulta **CLIENTES-ONLINE.txt**. SQL001–017 mantiene sus bytes y datos;018 sólo
crea una tabla para el conteo y su fecha, sin identidades ni credenciales ajenas.
La migración no consulta equipos. Se conservan facturas, pagos, calendario por
instalación, permisos y modo de red sólo lectura. No reinstales ni cambies
checksums o la clave AES existente.

## Verificación

63 comprobaciones de lector/Socket,134 API/Chromium y180 de actualización real
desde3.4.0 aprobadas. Totales completos, cero real, sesiones ajenas/duplicadas,
privacidad, roles, caché compartida, seis routers, errores, caducidad y punto
verde en temas claro/oscuro. Config/SQL/datos exactos y cero escrituras RouterOS
o tareas de red/OLT. Compilación y regresiones de sólo lectura aprobadas.
Pruebas de laboratorio; no se accedió a la instalación Windows ni a equipos
físicos del operador. Las descargas anteriores se conservan a continuación.

---

# GIGARED ISP 3.4.0 para XAMPP — Facturación desde instalación

[**Descargar ZIP completo 3.4.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.4.0-facturacion-instalacion.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.4.0-facturacion-instalacion.sha256)

El formulario deja **Inicio de facturación** como fecha de instalación y
**Días de gracia**, además de Cliente y Plan. Se eliminan **Día de facturación**
y **Días para pagar**: el calendario se calcula automáticamente.

| Instalación | Emisión de primera factura | Primer pago |
| --- | --- | --- |
| 01/10/2026 | 30/10/2026 | 01/11/2026 |

Se cobra un mes después, en el día original de instalación, y se factura dos
días antes. Meses cortos usan su último día:31/01→28/02→31/03, con29/02 cuando
corresponde. El período identifica el mes del vencimiento (2026-11 en el ejemplo).
El calendario usa hora de Perú y conserva UTC para los instantes en la base.

Con pago01/11 y3días de gracia, se puede pagar todo el día01 y los días02–04;
el atraso comienza05/11 a00:00 de Perú. La gracia no cambia el siguiente pago.

## Actualizar y usar

1. Respalda base/carpeta. Detén el worker y Apache.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando EXACTAMENTE
   **storage\config.php** y su clave privada original.
3. Inicia Apache/MySQL. Desde3.3.0 **no hay SQLnuevo**. Desde versiones anteriores
   aplica las pendientes hasta **017_local_billing_start** en actualizar.php.
4. Pulsa **Ctrl+F5**. Guarda la instalación y gracia en el servicio local.
5. Ejecuta **INICIAR-WORKER.bat** para emitir automáticamente con el navegador
   cerrado. Mantén su ventana abierta y el equipo encendido. El panel autenticado
   también puede procesarlas mientras esté abierto.

Consulta **FACTURACION-INSTALACION.txt**. Se recuperan períodos pendientes sin
duplicar facturas; los anulados/eliminados siguen reservados. Las facturas
emitidas no se recalculan. Las fechas explícitas de3.3 se interpretan ahora
como instalación; los servicios sin fecha conservan su calendario anterior
hasta asignar una. No se utiliza el prorrateo del calendario anterior.

SQL001–017 mantiene sus bytes. La emisión automática habilitada en lectura sólo
crea facturas de asociaciones locales con instalación. Las tareas generales de
facturación, autocorte, sincronización y configuración continúan bloqueadas.
No se envían órdenes a MikroTik/OLT ni se cortan o reconectan clientes.

## Verificación

153 comprobaciones API/worker/Chromium,35 de calendario y157 de actualización
real desde3.3.0 aprobadas. Hora peruana, emisión/pago/gracia, meses cortos,
idempotencia/concurrencia, historial inmutable, scope LOCAL_ONLY estricto,
SQL/config exactos y cero RouterOS I/O o trabajos OLT. Compilación y regresiones
financieras/lectura aprobadas en laboratorio. No se accedió a la instalación
Windows ni a equipos físicos del operador. Las descargas anteriores se conservan.

---

# GIGARED ISP 3.3.0 para XAMPP — Búsqueda e inicio de facturación

[**Descargar ZIP completo 3.3.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.3.0-busqueda-inicio-facturacion.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.3.0-busqueda-inicio-facturacion.sha256)

En **Nuevo servicio de facturación**, Cliente ahora busca al escribir al menos
2 caracteres del nombre, código, documento o correo y presenta hasta10
coincidencias. No descarga ni despliega todo el directorio al pulsar el campo.
Los clientes retirados no aparecen; puedes seleccionar con clic o teclado.

**Inicio de facturación** permite elegir día, mes y año. **Día de facturación**
conserva el día mensual del1 al28. Plan, días para pagar y gracia mantienen su
funcionamiento. La fecha inicial puede ser anterior al alta del servicio;
una fecha futura impide emitir antes de que llegue. Las facturas emitidas y
la fecha de alta original se conservan. No se envían cambios a MikroTik/OLT.

## Actualizar

1. Respalda base/carpeta. Detén el worker y Apache.
2. Copia **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente
   **storage\config.php** con su clave original.
3. Inicia Apache/MySQL. Entra como ADMIN a **/nexoisp/actualizar.php** y aplica
   **017_local_billing_start**, junto con las anteriores pendientes.
4. Pulsa **Ctrl+F5** y consulta **BUSQUEDA-FACTURACION.txt** dentro del ZIP.

SQL001–016 conserva sus bytes. 017 sólo crea la tabla de fechas iniciales;
no rellena registros antiguos ni altera su calendario. Al editar un servicio
anterior, dejar la fecha inicial vacía conserva su comportamiento previo.
Las fechas explícitas no reescriben facturas ni liberan períodos/cargos reservados.
Los períodos previos al inicio no son facturables. No hay prorrateo automático.
No reinstales ni cambies checksums o la clave AES. Se conserva el modo de red
sólo lectura y las funciones anteriores, incluida la eliminación financiera.

## Verificación

182 comprobaciones API/Chromium y149 de actualización real desde3.2.0 aprobadas.
Búsqueda acotada, teclado, fechas pasadas/futuras, legacy, prorrateo, historial,
roles, SQL/config exactos y cero RouterOS I/O, tareas de red o trabajos OLT.
Compilación, sintaxis y regresiones financieras/lectura aprobadas en laboratorio.
No se accedió a la instalación Windows ni equipos físicos del operador.
Las descargas anteriores se conservan a continuación.

---

# GIGARED ISP 3.2.0 para XAMPP — Eliminar facturas, pagos y servicios

[**Descargar ZIP completo 3.2.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.2.0-eliminar-registros.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.2.0-eliminar-registros.sha256)

ADMIN y BILLING disponen de **papelera con confirmación** en Facturación, Pagos
 y Servicios de Internet para servicios de facturación local. También está
 disponible en Ver detalle. Al eliminar un pago se recalcula el saldo pendiente;
 los registros dejan de aparecer en listados, informes, CSV, portal y documentos,
 y conservan un historial de eliminación con usuario y fecha.

## Actualizar

1. Respalda base/carpeta. Cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente
   **storage\config.php** y su clave original.
3. Inicia Apache/MySQL. Entra como ADMIN a **/nexoisp/actualizar.php** y aplica
   **016_financial_deletions**, además de las anteriores pendientes.
4. Pulsa **Ctrl+F5** y consulta **ELIMINAR-REGISTROS.txt** dentro del ZIP.

SQL001–015 mantiene sus bytes. La migración016 sólo crea la tabla de historial.
No reinstales la base ni cambies checksums o la clave AES existente.

## Antes de eliminar

- **Pago:** revierte primero su ingreso de Caja si está vinculado. Su referencia
  seguirá reservada y no podrá acreditarse otra vez por webhook o reporte.
- **Factura:** elimina primero sus pagos y resuelve los reportes pendientes.
  Se cancelan sus promesas activas; el período del servicio y los cargos únicos
  facturados permanecen reservados. No se puede emitir otra del mismo período.
- **Servicio local:** elimina primero sus facturas y cancela contratos vigentes.
  El cliente se conserva. Los servicios de red mantienen su protección previa.

Estas eliminaciones no envían órdenes a MikroTik/OLT ni crean tareas de red.
Borrar un pago tampoco ejecuta cortes ni reconexiones. Se mantiene el modo de
red sólo lectura. Las referencias, caja e historia previa se conservan; no hay
restauración de registros desde la interfaz en esta versión.

## Verificación

268 comprobaciones API/Chromium aprobadas, incluida eliminación desde detalle y
filas, saldos, roles, auditoría única, concurrencia, caja, reservas, portal/CSV y
conservación de datos PEN/USD. Otras142 comprobaciones verificaron la actualización
real desde3.1.0, config y SQL001–015 exactos y sólo016 aplicada. Compilación y
sintaxis PHP aprobadas. Pruebas en
laboratorio desechable; no se accedió a instalaciones ni equipos del operador.
Las descargas anteriores se conservan a continuación.

---

# GIGARED ISP 3.1.0 para XAMPP — Facturación local

[**Descargar ZIP completo 3.1.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.1.0-facturacion-local.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.1.0-facturacion-local.sha256)

Permite vincular **cliente + plan + fechas de cobro** y emitir facturas manuales
sin modificar el MikroTik. Se resuelve el aviso que impedía crear facturas cuando
sólo había clientes y perfiles importados. ADMIN y BILLING pueden guardar y editar
estas asociaciones; no se piden IP, router ni contraseña PPPoE.

## Actualizar

1. Respalda base/carpeta, cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente
   **storage\config.php** y su clave privada original.
3. Inicia Apache/MySQL. Abre **/nexoisp/actualizar.php** como ADMIN y aplica
   **015_local_billing**, además de las anteriores que tengas pendientes.
4. Pulsa **Ctrl+F5** y consulta **FACTURACION-LOCAL.txt** dentro del ZIP.

SQL001–014 conserva sus bytes/historial. La nueva migración permite campos de red
vacíos en Service y añade el marcador LocalBillingService. Conserva los registros,
índices, claves y reservas anteriores; no consulta ni configura equipos.

## Usar

1. En **Planes de Internet**, configura precio, moneda PEN y activación del plan.
2. En **Servicios de Internet → Nuevo servicio de facturación**, selecciona cliente,
   plan y calendario. También puedes usar **Asignar plan de facturación** en el
   detalle del cliente. Guarda la asociación.
3. En **Facturación**, crea la factura seleccionando ese servicio y el periodo.
4. Registra pagos o promesas desde sus módulos habituales.

Estas asociaciones nunca ordenan cortes, reconexiones ni sincronizaciones de red,
aun si posteriormente cambia la configuración global de lectura. No se convierten
en servicios MikroTik mediante su edición. Las facturas emitidas conservan importe
y moneda. La emisión de esta guía es manual; no se habilita facturación masiva ni
autocorte automático en modo lectura. Las ediciones PPPoE previamente autorizadas
conservan sus botones y permisos y no forman parte de este flujo.

## Verificación

133 controles API/Chromium y121 de actualización desde3.0.5 aprobados. Se verificaron
facturas/PEN/pagos/promesas, cola inalterada, guardias permanentes, configuración
byteexacta y finanzas históricas PEN/USD. Pruebas aisladas: no se accedió al Windows,
MikroTik ni OLT físicos del operador. Las descargas anteriores siguen disponibles.

---

# GIGARED ISP 3.0.5 para XAMPP — IP en nueva pestaña

[**Descargar ZIP completo 3.0.5**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.5-ip-nueva-pestana.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.5-ip-nueva-pestana.sha256)

Al pulsar la IP del cliente, su router/ONU abre **directamente en una pestaña
nueva**. Clientes permanece abierto. Se retiran el recuadro y el botón intermedio.
Las IPs automáticas, temas, tablas compactas y funciones anteriores se conservan.

1. Respalda carpeta/base, cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando exactamente
   **storage\config.php** y sus claves privadas.
3. Inicia Apache/MySQL y pulsa **Ctrl+F5**.
4. En Clientes pulsa directamente la IP.

El enlace inicial usa HTTP/puerto80. Si el equipo usa HTTPS u otro puerto,
ajusta la barra de la pestaña nueva. La web debe ser alcanzable desde tu PC.

Desde3.0.0–3.0.4 no hay nuevas migraciones. Desde versiones anteriores aplica
las pendientes hasta014_fiber. Consulta IP-CLIENTES.txt dentro del ZIP.

Compilación y Chromium aprobados: IPv4/IPv6, nueva pestaña con web ficticia que
rechaza marcos, panel conservado, sin iframe/diálogo, opener aislado y móvil.
SQL001–014 idéntico a3.0.4; no se accedió a equipos reales del operador.

---

# GIGARED ISP 3.0.4 para XAMPP — Acceso a routers y ONUs

[**Descargar ZIP completo 3.0.4**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.4-acceso-equipos.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.4-acceso-equipos.sha256)

Si al pulsar una IP aparece **ERR_BLOCKED_BY_RESPONSE**, la web del equipo puede
estar rechazando su incrustación dentro del panel. Encima del marco se añade
**Abrir en esta misma pestaña**: abre directamente el protocolo y puerto elegidos,
sustituye temporalmente el panel por la web del equipo y mantiene una sola pestaña.
Usa **Atrás** del navegador para regresar a Clientes.

El recuadro se conserva para equipos compatibles. El acceso directo evita la
restricción de incrustación; tu PC debe poder llegar a la IP/puerto y usar las
credenciales y certificado propios del equipo. No cambia el firmware ni las
políticas del dispositivo. No hay proxy ni redirección automática.

1. Respalda carpeta/base, cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando exactamente
   **storage\config.php** y sus claves privadas.
3. Inicia Apache/MySQL y pulsa **Ctrl+F5**.
4. En Clientes pulsa la IP y luego **Abrir en esta misma pestaña**.

Desde3.0.0–3.0.3 no hay SQL nuevo. Para versiones anteriores aplica las pendientes
hasta014_fiber. Conserva las mejoras de temas, tablas y acceso LAN anteriores.

Compilación y Chromium aprobados: reproducción de bloqueo XFO/CSP con web ficticia,
acceso directo, Atrás, una sola pestaña, teclado, puertos y móvil. No se accedió
al Windows ni equipos reales del operador. SQL001–014 idéntico a3.0.3.

---

# GIGARED ISP 3.0.3 para XAMPP — Temas y tablas compactas

[**Descargar ZIP completo 3.0.3**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.3-temas-tablas.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.3-temas-tablas.sha256)

- El menú lateral completo cambia con el tema claro/oscuro: fondo, textos,
  selección, categorías, marca y scrollbar; el tema se conserva al recargar.
- Clientes y Planes ocultan el nombre del router y el prefijo **Perfil** en los
  listados. Se conserva el nombre real del perfil. Los nombres comerciales
  personalizados y los datos guardados se mantienen.
- Filas de Clientes más compactas: padding vertical10→6px; fila visual de prueba
  reducida de73 a61px sin achicar botones ni fuentes.

1. Respalda carpeta/base, cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando exactamente
   **storage\config.php** y sus claves privadas.
3. Inicia Apache/MySQL y pulsa **Ctrl+F5**, también en otros dispositivos.

Desde3.0.0–3.0.2 no hay migraciones nuevas. Para versiones anteriores aplica
las pendientes hasta014_fiber. Se incluyen las correcciones previas de acceso
LAN y Origen MikroTik; no se modifica la configuración de equipos.

Compilación de producción y revisión visual en Chromium de clientes, planes,
ambos temas, persistencia y móvil390px aprobadas. SQL001–014 idéntico a3.0.2;
no se accedió a instalaciones ni equipos reales. Descargas anteriores conservadas.

---

# GIGARED ISP 3.0.2 para XAMPP — Columna Origen MikroTik

[**Descargar ZIP completo 3.0.2**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.2-origen-clientes.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.2-origen-clientes.sha256)

En Clientes, la columna **Origen MikroTik** conserva usuario PPPoE, router y
perfil. Oculta **Secret habilitado/deshabilitado** y la dirección remota.
Presenta **IP estática**, **IP dinámica / pool** o **IP según perfil** cuando
el secret no define la dirección. La columna **IP** y la ficha detallada
conservan su información completa.

1. Guarda respaldo, cierra el worker y detén Apache.
2. Extrae **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando exactamente
   **storage\config.php**.
3. Inicia Apache/MySQL y pulsa **Ctrl+F5** en el navegador.

Desde3.0.0/3.0.1 no hay SQL nuevo. Para versiones anteriores aplica las pendientes
hasta014_fiber. Se incluye el arreglo de acceso por red local de3.0.1.

Compilación TypeScript/Vite y revisión visual en Chromium aprobadas para cinco
casos de asignación. SQL001–014 y comportamiento backend conservados. No se
accedió a instalaciones ni equipos reales. Las descargas anteriores siguen aquí.

---

# GIGARED ISP 3.0.1 para XAMPP — Acceso por red local

[**Descargar ZIP completo 3.0.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.1-red-local.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.1-red-local.sha256)

Corrige **«Origen no autorizado»** al iniciar sesión desde otro dispositivo
por la IP privada del Windows que ejecuta XAMPP. Se conserva el acceso desde
localhost y la protección frente a sitios externos. La IP automática debe
corresponder al socket Apache, con Host, protocolo y puerto coincidentes.
Los alias, dominios y proxies se autorizan explícitamente con
`allowed_web_origins`; el ZIP incluye **RED-LOCAL.txt** con instrucciones.

1. Respalda la instalación/base, cierra el worker y detén Apache.
2. Extrae la carpeta **nexoisp** sobre **C:\xampp\htdocs\nexoisp** conservando
   exactamente **storage\config.php**. El ZIP no incluye ese archivo privado.
3. Inicia Apache/MySQL. Desde otro equipo abre **http://IP-DEL-SERVIDOR/nexoisp/**,
   con el puerto de Apache si corresponde, y pulsa **Ctrl+F5**.

Desde3.0.0 **no hay migraciones nuevas**. Desde versiones anteriores aplica
las pendientes hasta014_fiber. Puedes aplicar sólo el arreglo de origen
reemplazando **app/auth.php** del ZIP con Apache detenido. No reinstales ni
cambies la clave AES. Las cookies previamente seguras siguen requiriendo HTTPS.

Validación:399 controles de origen,42 de integración API/Chromium,213 de lectura
y30 de moneda/capacidades aprobados. SQL001–014 idéntico al ZIP3.0.0.
Pruebas aisladas; no se accedió a equipos ni datos del operador.

El ZIP completo conserva el módulo FTTH, las IPs automáticas y las funciones
anteriores. Las descargas previas y sus notas permanecen a continuación.

---

# GIGARED ISP 3.0.0 para XAMPP — Fibra óptica nativa

[**Descargar ZIP completo 3.0.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.0-ftth.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.0-ftth.sha256)

## Cambios incluidos

La columna **IP** muestra sólo las direcciones. Se ocultaron el router/origen, mensaje periódico y fecha de lectura dentro de esa columna. Se mantienen la IP automática, su caducidad y el recuadro HTTP en la misma página.

El módulo **Fibra óptica** se integra al menú y a la ficha del cliente: resumen, OLTs, ONUs autorizadas y sin autorizar, PON, VLAN, perfiles DBA/LINE/SERVICE/TRAFFIC, zonas, NAP, splitters, hilos/enlaces, mapa georreferenciado, consultas por modelo, preparaciones y tareas. Incluye filtros ONLINE/OFFLINE/LOS, potencia Rx/Tx y gráficos de muestras existentes, sin inventar mediciones ausentes.

La implementación es propia y usa los flujos observables del [manual público de AdminOLT](https://adminolt.com/documentacion/home-1/). El ZIP incluye **INVESTIGACION-ADMINOLT.md**, **MATRIZ-FTTH.md**, esquema y API documentada. No se afirma identidad de código, copia exacta de pantallas privadas ni compatibilidad binaria con una API privada de AdminOLT.

## Política de red

Se conserva el modo de lectura. Autorizar, reiniciar, configurar WiFi, suspender, reactivar o retirar una ONU crea una **preparación local revisable**, con claves cifradas. No aplica cambios al hardware ni cambia falsamente su estado observado. Los endpoints de aplicación permanecen bloqueados; no existe un escritor universal habilitado para todos los firmwares.

SSH usa phpseclib incluido y requiere verificar la huella del servidor. Telnet y SNMPv2c realizan consultas limitadas; SNMP sólo GET/GETNEXT. Hay bases de descubrimiento Huawei/ZTE y un registro de consultas/parsers para cada modelo. No se inicializan OLTs, habilitan puertos ni envían comandos de configuración automáticamente.

## VSOL V1600GS-F

La [ficha oficial](https://www.vsolcn.com/product/1-pon-gpon-olt-v1600gsf-v1600gszf) identifica **un puerto GPON**, con gestión Web/Telnet/CLI/SNMP. No se trata como EPON ni se reutilizan comandos de una OLT de chasis.

**Falta validar la versión de firmware y sus consultas CLI/OIDs ópticos.** El módulo permite inventario local, identificación SNMP estándar con acceso de lectura existente y consultas configurables. La prueba MIB-II no equivale a descubrir ONUs. Los planes Single-PON pueden ser informativos; no se promete aplicar QoS, WiFi o autorizaciones reales desde una preparación.

## Actualizar XAMPP

1. Respalda la base y guarda una copia privada de **storage\config.php**.
2. Cierra el worker y detén Apache.
3. Extrae el ZIP y copia el contenido de **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente **storage\config.php** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN. Aplica las pendientes hasta **014_fiber**.
5. Inicia sesión, pulsa **Ctrl+F5** y abre **Fibra óptica**.
6. Registra la OLT y sus accesos de lectura existentes. Prueba la conexión antes de activar sus consultas periódicas. Ejecuta **INICIAR-WORKER.bat** para procesar tareas con el navegador cerrado.

La migración014 crea13 tablas vacías y no contacta al router ni OLT. SQL001–013 mantiene sus bytes e historial. Se conservan notas, clientes, credenciales, cachés PPP e importes/monedas históricos USD/PEN.

## Instalación nueva y contenido

Extrae **nexoisp** en **C:\xampp\htdocs**, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB10.4+/MySQL8+. El ZIP incluye PHP, SQL, frontend compilado, fuente React completa y bibliotecas SSH con sus licencias. No necesitas Node.js, Docker, Redis, Composer ni extensión SSH2 para usar la distribución.

Se conservan todas las funciones anteriores, incluida la edición manual seleccionada de nombres/credenciales MikroTik y la importación de secrets30s. Cortes y automatismos de configuración continúan protegidos. No cambies **network_read_only** para forzar una función no validada para el firmware.

## Validación

- Compilación TypeScript/Vite y382 archivos PHP sin errores de sintaxis;11 suites PHP de regresión aprobadas.
- Regresiones API/Chromium existentes:671 comprobaciones aprobadas. Nueva suite FTTH API/protocolos/navegador:94 aprobadas.
- Telnet y SNMP reales contra servidores privados simulados: descubrimiento, parser, potencia, trabajos, cifrado, permisos, rechazo atómico y ausencia de comandos mutantes. Medidas negativas y Counter64 máximo conservado exactamente.
- Navegador: asistente de cuatro pasos, preparación WiFi, filtros, secreto no precargado, gráficas y mapa conNAP/enlacePON.
- Actualización desde ZIP2.4.1:180 comprobaciones. SQL anteriores, configuración privada y datos conservados. Cero conexiones OLT/RouterOS durante migración, salud y metadatos; cero cambios de configuración en las funciones nuevas.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium con protocolos controlados; no se accedió al Windows, red real ni OLT física del operador. El detalle de intentos y correcciones se documenta en **PRUEBAS.txt**.

SHA-256:

```
634afddd6c3d8e885d9a06fe100c30934e32310fc44f62f453f942b78ff78152
```

PowerShell: `Get-FileHash .\gigared-isp-xampp-v3.0.0-ftth.zip -Algorithm SHA256`.

Lee **FTTH.txt**, **API-REFERENCIA.md**, **MATRIZ-FTTH.md**, **GUIA-ACTUALIZAR.txt** y **PRUEBAS.txt**. El paquete no contiene una instalación previa ni datos, contraseñas o claves reales.

## Versiones anteriores

Se conservan [2.4.1 recuadro/IP](gigared-isp-xampp-v2.4.1.zip), [2.4.0](gigared-isp-xampp-v2.4.0.zip), [2.3.3 IP](nexoisp-xampp-v2.3.3-ip-clientes.zip), [2.3.2 notas](nexoisp-xampp-v2.3.2-notas-clientes.zip), [2.3.1 nombre](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [2.2](nexoisp-xampp-v2.2-lectura.zip), [2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [2.1](nexoisp-xampp-v2.1-lectura.zip), [2](nexoisp-xampp-v2.zip) y [1](nexoisp-xampp.zip). Las versiones1/2 anteriores al modo lectura permitían otras operaciones de configuración.
