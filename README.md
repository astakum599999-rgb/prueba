# NexoISP 2 para Windows con XAMPP

[**Descargar ZIP v2**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.zip)

[Checksum SHA-256](nexoisp-xampp-v2.sha256) · [ZIP anterior v1](nexoisp-xampp.zip)

Implementación propia de administración ISP basada en funciones de la documentación pública de WispHub. Incluye PHP 8.2, MariaDB/MySQL, panel React compilado, código fuente y worker PHP con cola persistente. No requiere Node.js, Docker, Redis ni Composer para ejecutarse. No se presenta como copia exacta del sistema privado de WispHub.

## Instalación nueva

1. Descarga el ZIP con el enlace superior. Si GitHub muestra la ficha del archivo, pulsa **Download raw file** o **Descargar archivo sin procesar**.
2. Extrae la carpeta `nexoisp` dentro de `C:\xampp\htdocs`; debe quedar `C:\xampp\htdocs\nexoisp\index.php`.
3. Inicia **Apache** y **MySQL** en XAMPP Control Panel.
4. Abre **http://localhost/nexoisp/** y completa el instalador con tus datos de MySQL y un administrador propio.
5. Ejecuta `INICIAR-WORKER.bat` y deja la ventana abierta para facturación, autocorte y operaciones de red.

El portal de clientes está en **http://localhost/nexoisp/portal/**. Sus accesos se crean desde **Acceso de clientes** en el panel administrativo.

## Actualización de v1 a v2

Lee **GUIA-ACTUALIZAR.txt** antes de reemplazar archivos. Respalda la base de datos y `storage\config.php`; detén el worker y Apache. Copia la carpeta nueva sobre la anterior conservando exactamente tu `storage\config.php`. Reinicia Apache y MySQL, abre el panel y sigue `actualizar.php` con tu administrador existente. No reinstales ni borres la base. La configuración contiene la clave que descifra las credenciales de tus routers.

La actualización se probó desde el ZIP v1 publicado, conservando configuración, clientes, factura con pago parcial, sesión, clave de API y acceso a la credencial cifrada del router de prueba.

## Funciones de v2

Clientes y servicios, planes, MikroTik API Socket/REST, cola de tareas, facturación y pagos, autocorte, portal de clientes, revisión de pagos informados, contratos, cargos, descuentos, primera factura proporcional, promesas de pago, caja y gastos, transferencias, inventario, agenda técnica, soporte, muestras de tráfico, reportes y exportaciones CSV.

Consulta **LEEME.txt**, **GUIA-MIKROTIK.txt**, **API-REFERENCIA.md**, **MATRIZ-WISPHUB.md**, **REFERENCIAS-WISPHUB.md** y **PRUEBAS.txt** dentro del ZIP. Los documentos fiscales, pasarelas bancarias y mensajería de terceros no se incluyen como integraciones verificadas.

## Integridad y validación

SHA-256 de `nexoisp-xampp-v2.zip`:

```
a9e95cf323436f734fa47fff3adfb6863d7b0ba6857e413c3161e8f881e63779
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.zip -Algorithm SHA256`.

El ZIP contiene un manifiesto adicional de todos sus archivos. No incluye contraseñas, configuración instalada, claves privadas ni base de datos de pruebas.

Validado con Apache/PHP 8.2/MariaDB 10.4 en Linux: más de 170 comprobaciones de API base, más de 190 de API v2, 85 comprobaciones PHP, sintaxis PHP, navegadores administrativo y de cliente, vistas móviles, compilación de la fuente aislada y actualización desde v1. Los protocolos RouterOS se probaron con servidores controlados; no se declara validación sobre routers físicos ni un escritorio Windows.
