# GIGARED ISP 2.4.1 para XAMPP

[**Descargar ZIP completo 2.4.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v2.4.1.zip)

[Checksum SHA-256](gigared-isp-xampp-v2.4.1.sha256)

## Acceso al equipo dentro de la página

Pulsar la IP del cliente carga la web del equipo en un **recuadro en la misma página**, inicialmente **HTTP:80**. Elige HTTP/HTTPS y el puerto web, y pulsa **Cargar acceso** para aplicar otro destino o recargar. No se abre otra pestaña. La actualización de la tabla conserva la sesión y los datos escritos en el recuadro.

**Límite de los firmwares:** algunos modelos Huawei, ZTE, Ubiquiti, ATW o TP-Link impiden mostrarse dentro de otra página mediante sus encabezados o reglas de cookies. En esos equipos puede continuar **ERR_BLOCKED_BY_RESPONSE**: el panel no puede anular esa política del dispositivo. Un panel HTTPS tampoco puede incrustar HTTP como contenido mixto. Se conserva el acceso directo desde el PC; no se añade un proxy ni se omiten autenticación o certificados.

## IP automática sin botón

Se eliminó **Consultar IP actual**. Con Clientes visible, ADMIN/TECHNICIAN consulta automáticamente las sesiones PPP cada **15 segundos**. Los clientes de la página comparten un lote y una sola lectura por router; las pestañas comparten un caché. No se solicitan contraseñas masivamente.

Cuando una IP cambia o una sesión desaparece, la siguiente observación reemplaza o retira su acceso activo. Los datos de sesión caducan a los **30 segundos** y un fallo retira las IP antiguas presentadas como actuales. Las IP configuradas en servicios/secrets conservan sus etiquetas y no demuestran que el cliente esté online. Los errores reintentan tras15,30 y hasta60 segundos.

Las consultas se pausan al ocultar Clientes y se reanudan al volver. La tabla no reinicia formularios ni recarga el iframe. Los routers se procesan por turnos; es consulta periódica y el tiempo de conexión puede aumentar la demora.

## Funciones conservadas

La marca **GIGARED ISP**, tabla compacta, notas internas, moneda PEN/S/ e historial de operaciones con su moneda original se mantienen. La importación de secrets conserva su intervalo independiente de **30 segundos** y usa el comentario como nombre. Ejecuta **INICIAR-WORKER.bat** para continuar esa importación aunque cierres el navegador.

Las ediciones manuales ADMIN de nombre y credenciales PPPoE conservan sus botones y verificación. Cortes, reconexiones, aprovisionamiento, firewall y trabajos mutantes antiguos permanecen bloqueados. No cambies **network_read_only** para usar estas consultas.

## Actualizar la instalación

1. Respalda la base y guarda una copia privada de **storage\config.php**.
2. Cierra el worker y detén Apache.
3. Extrae el ZIP y copia el contenido de **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente **storage\config.php** y tus archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN. Aplica las pendientes hasta **013_client_ip_live**.
5. Entra al panel, pulsa **Ctrl+F5** y abre Clientes. Las IP se actualizan sin pulsar un botón.
6. Reinicia **INICIAR-WORKER.bat** si mantienes la importación de secrets con el navegador cerrado.

La carpeta y URL **nexoisp** se conservan por compatibilidad. La migración013 añade sólo caché local y no contacta al router; SQL001–012 conservan sus bytes y checksums originales. No se reinstala la base ni se cambian claves.

## Instalación nueva

Extrae **nexoisp** en **C:\xampp\htdocs**, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB10.4+/MySQL8+. Incluye PHP, SQL, interfaz compilada y fuente completa. No necesitas Node.js, Docker, Redis ni Composer para usar el ZIP.

## Validación

- Compilación TypeScript/Vite correcta y30 archivos PHP sin errores de sintaxis.
- Política de lectura213, moneda/capacidades30, parser/caché15 y validadores21 comprobaciones aprobadas.
- 671 comprobaciones API/Chromium: secrets108, perfiles65, consulta PPP90, edición PPP112, nombre134, notas23, acceso IP35, IP automática47 y secrets automáticos57.
- Navegador en zonaAmerica/Lima: cambio de IP sin botón, expiración durante pausa, recuadro HTTP/HTTPS/IPv6, puertos válidos, ninguna pestaña extra y conservación de datos de formulario/iframe. Las nuevas funciones no enviaron cambios de configuración RouterOS.
- Actualización desde ZIP2.4.0:127 comprobaciones. Sólo SQL013 añadida; SQL001–012/historia, configuración privada byteexacta, clientes/notas/importaciones y finanzas USD/PEN conservados. Cero lecturas RouterOS durante migración/health checks y cero escrituras RouterOS.

Pruebas con Apache/PHP8.2/MariaDB10.4 Linux, Chromium y servidores de protocolo controlados. No se accedió al Windows, red real ni a los firmwares físicos del operador. No se garantiza la incrustación de un firmware que la prohíbe.

SHA-256:

```
3aeba6e0171cd280d5009e955ca17abec62206b71b97bb18c877c055b2da80c9
```

En PowerShell: `Get-FileHash .\gigared-isp-xampp-v2.4.1.zip -Algorithm SHA256`.

Lee **LEEME.txt**, **GUIA-ACTUALIZAR.txt**, **IP-CLIENTES.txt**, **IP-AUTOMATICA.txt** y **PRUEBAS.txt** incluidos. El ZIP no contiene instalación previa, datos reales, contraseñas ni claves.

## Versiones anteriores

Se conservan [2.4.0](gigared-isp-xampp-v2.4.0.zip), [2.3.3 IP](nexoisp-xampp-v2.3.3-ip-clientes.zip), [2.3.2 notas](nexoisp-xampp-v2.3.2-notas-clientes.zip), [2.3.1 nombre](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [2.2](nexoisp-xampp-v2.2-lectura.zip), [2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [2.1](nexoisp-xampp-v2.1-lectura.zip), [2](nexoisp-xampp-v2.zip) y [1](nexoisp-xampp.zip). Usa **2.4.1** para el recuadro y las IP automáticas. Las versiones1/2 anteriores al modo lectura permitían otras operaciones de configuración.
