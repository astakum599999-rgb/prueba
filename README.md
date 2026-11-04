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
