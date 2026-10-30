# GIGARED ISP 2.4.0 para XAMPP

[**Descargar ZIP completo 2.4.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v2.4.0.zip)

[Checksum SHA-256](gigared-isp-xampp-v2.4.0.sha256)

## Cambios incluidos

- Marca visible **GIGARED ISP** y tabla/recuadros de Clientes más compactos.
- Acceso por IP sin iframe: el recuadro permite elegir HTTP/HTTPS y puerto; **Abrir router** abre una pestaña independiente. Evita el bloqueo al incrustar páginas del equipo. El navegador necesita conexión a la IP y el equipo debe tener disponible su interfaz web.
- Lectura automática de secrets con intervalo normal de **30 segundos** para routers que ya hayas importado. El comentario no vacío actualiza el nombre; se refrescan observaciones de perfil/IP y se conservan notas y datos administrativos locales.
- La sincronización funciona con un panel ADMIN/TECHNICIAN visible. Para continuar con el navegador cerrado o minimizado, ejecuta **INICIAR-WORKER.bat** y conserva abierta su ventana.

Es consulta periódica, no push instantáneo. Los routers se procesan por turnos, sin solaparse entre pestañas/worker. Ante fallos se conservan los últimos datos y el reintento aumenta hasta cinco minutos. El estado muestra la última lectura correcta de cada router. Los cambios manuales pendientes de comprobar aplazan la lectura.

Los perfiles y planes mantienen su importación independiente. La IP dinámica sigue consultándose mediante **Consultar IP actual**; no se inventan IPs de sesión a partir de pools. Un usuario renombrado directamente en RouterOS es otra identidad: para conservar su vínculo utiliza la edición PPPoE del panel.

## Actualizar la instalación

1. Respalda la base de datos y guarda una copia privada de **storage\config.php**.
2. Cierra el worker y detén Apache.
3. Extrae el ZIP y copia el contenido de **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente **storage\config.php** y tus archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN. Aplica las pendientes hasta **012_secret_auto_sync**.
5. Entra al panel y pulsa **Ctrl+F5**. Los routers previamente importados se incorporan a la lectura automática; para uno nuevo importa sus secrets una vez.
6. Ejecuta **INICIAR-WORKER.bat** para mantener la sincronización aunque cierres el navegador.

La carpeta y URL **nexoisp** se conservan para actualizar tu instalación existente. La migración012 añade únicamente el calendario local y no contacta al router. Los SQL001–011 mantienen sus bytes y checksums originales. No se reinstala la base ni se cambian las claves.

## Instalación nueva

Extrae **nexoisp** en **C:\xampp\htdocs**, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y crea tu administrador. Requiere PHP8.2 y MariaDB10.4+/MySQL8+. Incluye PHP, SQL, interfaz compilada y fuente completa; no necesitas Node.js, Docker, Redis ni Composer para usar el ZIP.

## Funciones conservadas

Notas sigue debajo de la fila GPS y es interna. El nombre completo se sincroniza manualmente con Comment del secret importado cuando ADMIN guarda el cliente; las credenciales PPPoE tienen su botón y verificación específicos. La lectura automática no solicita contraseñas masivamente. Se conserva PEN/S/ y la moneda de todas las operaciones históricas.

Cortes, reconexiones, aprovisionamiento, firewall y trabajos mutantes antiguos continúan bloqueados. No cambies **network_read_only** para utilizar la sincronización automática. La demostración independiente de facturas, promesas y pagos sigue en **http://localhost/nexoisp/demo/**.

## Validación

- Compilación TypeScript/Vite correcta y29 archivos PHP sin errores de sintaxis;11 suites PHP aprobadas.
- 623 comprobaciones API/Chromium: secrets108, perfiles65, consulta PPP90, edición manual PPP112, nombre134, notas23, acceso IP34 y sincronización automática57.
- La suite automática verifica reservas30s, exclusión concurrente, errores/backoff, conservación de datos, permisos, worker, actualización del listado y borradores sin sobrescribir. Cero cambios de configuración RouterOS en las funciones automáticas y de acceso IP.
- Actualización desde el ZIP2.3.3 publicado:115 comprobaciones. Sólo SQL012 añadida; configuración privada byteidéntica, notas e identidades intactas y finanzas USD/PEN conservadas. Cero lecturas del router durante la migración y cero escrituras RouterOS.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium, con servidores de protocolo controlados. No se accedió al Windows ni routers físicos del operador.

SHA-256:

```
6a109fac4440acc3186806215e1e35e32628304c8d801d135d58d38029539c3d
```

En PowerShell: `Get-FileHash .\gigared-isp-xampp-v2.4.0.zip -Algorithm SHA256`.

Lee **LEEME.txt**, **GUIA-ACTUALIZAR.txt**, **ACTUALIZACION-AUTOMATICA.txt**, **IP-CLIENTES.txt** y **PRUEBAS.txt** incluidos. El ZIP no contiene instalación previa, datos reales, contraseñas ni claves.

## Versiones anteriores

Se conservan [2.3.3 IP](nexoisp-xampp-v2.3.3-ip-clientes.zip), [2.3.2 notas](nexoisp-xampp-v2.3.2-notas-clientes.zip), [2.3.1 nombre](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [2.2](nexoisp-xampp-v2.2-lectura.zip), [2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [2.1](nexoisp-xampp-v2.1-lectura.zip), [2](nexoisp-xampp-v2.zip) y [1](nexoisp-xampp.zip). Usa **2.4.0** para los cambios actuales. Las versiones1/2 anteriores al modo lectura permitían otras operaciones de configuración.
