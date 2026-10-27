# NexoISP 2.3.3 para XAMPP — IP y acceso al router del cliente

[**⬇ Descargar ZIP v2.3.3 con columna IP**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.3.3-ip-clientes.zip)

[Checksum SHA-256](nexoisp-xampp-v2.3.3-ip-clientes.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

## Clientes: IP y acceso web

La columna **Contacto** se sustituye por **IP**. Cada cliente muestra las direcciones válidas registradas en sus servicios actuales y en la dirección remota de sus secrets presentes. El correo y teléfono permanecen en **Editar** y **Ver detalle**.

**Pulsa una IP para abrir el recuadro de acceso web al equipo del cliente.** Puedes elegir **HTTP/HTTPS** y el **puerto web**. La dirección se abre directamente desde tu navegador; inicia sesión con las credenciales propias de ese equipo.

El recuadro incluye **Abrir en otra pestaña**. Úsalo cuando el router o navegador no permita mostrar la interfaz embebida. Tu PC necesita conectividad a esa IP, directamente o mediante VPN, y el servicio web del dispositivo debe estar disponible. No se omiten certificados ni políticas de seguridad.

Se admiten IPv4 e IPv6. Los pools, URLs, direcciones vacías/no utilizables y observaciones ausentes no generan enlaces. Una misma IP/router no se duplica al coincidir servicio y secret; distintos routers conservan su contexto.

## IP dinámica PPPoE

Si el secret usa un pool o no fija una IP, **ADMIN/TECHNICIAN** puede pulsar **Consultar IP actual**. Esa acción consulta `/ppp/active` únicamente para las cuentas de ese cliente. No hay lecturas implícitas del MikroTik al abrir o actualizar la tabla.

El resultado muestra la IP observada durante esa consulta; no se guarda como asignación estática ni confirma que su interfaz web esté disponible. Si no hay sesión o la lectura falla, se informa sin inventar una IP. Repite la consulta cuando necesites una observación nueva.

El acceso web no usa un proxy PHP, no incluye contraseñas en URLs ni reutiliza la credencial API del router principal. Estas funciones no modifican configuración o sesiones en MikroTik.

## Actualizar tu XAMPP

**Desde2.3.2 no hay migraciones nuevas.**

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, conservando exactamente **`storage\config.php`** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/**.
5. Vuelve a iniciar sesión y pulsa **Ctrl+F5**.
6. Abre **Clientes** y pulsa la IP correspondiente. Para IP dinámica usa **Consultar IP actual**.

Si vienes de una versión anterior con esquema pendiente, aplícala en **http://localhost/nexoisp/actualizar.php** como ADMIN hasta `011_client_notes`. Los SQL001–011 conservan sus bytes y checksums publicados. No se reinstala la base ni se cambian claves.

## Funciones conservadas

Notas continúa debajo de la fila GPS y es interna de NexoISP. El nombre completo se sincroniza con Comment del secret importado; usuario/contraseña PPPoE conservan su botón específico y sus permisos. PEN/S/ e importes históricos con su moneda original se mantienen.

Cortes, reconexiones, aprovisionamiento, firewall y trabajos mutantes antiguos siguen bloqueados. No cambies `network_read_only` para usar las IP o el acceso web. La demo de facturas/promesas/pagos está en **http://localhost/nexoisp/demo/** y sigue aislada.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB/MySQL. Incluye interfaz compilada y fuente; para utilizar el ZIP no necesitas Node.js, Docker, Redis ni Composer.

## Validación

33 nuevas comprobaciones API/Chromium de IPs registradas, servicios/secrets, IPv6, datos inválidos, sesiones dinámicas, permisos y acceso web directo. El navegador cargó un dispositivo HTTP simulado dentro del iframe y comprobó HTTPS/puerto8443, IPv6 con corchetes, puerto inválido, URL sin credenciales y enlace independiente. La suite nueva no envió modificaciones de configuración RouterOS.

766 comprobaciones PHP de regresión aprobadas y sintaxis de28 archivos; TypeScript/Vite compilado. Se repitieron suites anteriores de API/Chromium: secrets108, perfiles65, consultaPPP90, ediciónPPP112, nombre134 y notas23.

La actualización real desde el ZIP2.3.2 publicado pasó67 comprobaciones: sin migraciones, IP del servicio existente, notas previas, PEN, empresa, sesión, historial financiero USD y configuración privada idénticos. Cero modificaciones RouterOS durante esa actualización.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium con servidores de protocolo controlados. Los frames del dispositivo se interceptaron en el laboratorio. No se accedió al Windows, red real, clientes ni routers físicos del operador.

SHA-256:

```
57bb5db68bc07509875811941c4cefafcbf839fcb9ad6e954179b93eef72b380
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.3.3-ip-clientes.zip -Algorithm SHA256`.

Lee **IP-CLIENTES.txt**, **GUIA-ACTUALIZAR.txt**, **LEEME.txt** y **PRUEBAS.txt** dentro del ZIP. No contiene instalación previa, datos reales, notas privadas, contraseñas ni claves.

## Versiones anteriores

Se conservan [v2.3.2 notas](nexoisp-xampp-v2.3.2-notas-clientes.zip), [v2.3.1 nombre/comentario](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [v2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [v2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [v2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Usa **v2.3.3** para la columna IP y el recuadro de acceso. Las versiones v1/v2 anteriores al modo lectura permitían otras operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
