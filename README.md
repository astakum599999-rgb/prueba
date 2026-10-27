# NexoISP 2.1.1 para XAMPP — corrección de importación PPP

[**⬇ Descargar ZIP corregido v2.1.1 — SOLO LECTURA**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.1.1-lectura.zip)

[Checksum SHA-256](nexoisp-xampp-v2.1.1-lectura.sha256)

Esta corrección resuelve casos donde el importador rechazaba textos PPP legítimos con el mensaje **«El router devolvió texto PPP inválido; no se importó ningún registro»**, por ejemplo comentarios o nombres recibidos mediante Socket con bytes heredados, acentos o controles no imprimibles.

El UTF-8 válido se conserva. Para bytes no UTF-8 se utiliza una interpretación Windows-1252 al mostrarlos, sin requerir iconv ni mbstring; los controles se representan visiblemente y los comentarios mantienen tabulaciones y saltos de línea. Los bytes originales del usuario siguen siendo su identidad exacta: no se cambia el usuario del router ni se fusionan identidades de distinto contenido.

## Aplicar la corrección en una instalación existente

1. Guarda una copia privada de `storage\config.php` y tu respaldo habitual de la base.
2. **Cierra el worker con Ctrl+C y detén Apache** antes de copiar los archivos.
3. Extrae el ZIP nuevo y copia la carpeta `nexoisp` sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y los archivos privados existentes.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/**.
5. Entra en **Clientes → Importar secrets de MikroTik**, selecciona el router y pulsa **Leer e importar clientes**.

**Si ya aplicaste `006_secret_import`, no hay otra migración.** Los seis archivos SQL conservan sus bytes y checksums. Esta corrección no reinstala la base ni restablece usuarios o credenciales.

Si vienes de una versión más antigua, sigue también **GUIA-ACTUALIZAR.txt** para las migraciones que te falten. Un proceso del worker anterior que siga abierto conserva su código hasta cerrarlo.

## Modo de red solo lectura

La importación consulta `/ppp/secret`, incluidos los deshabilitados y otras modalidades PPP, y guarda una copia local en Clientes. No copia contraseñas PPP ni crea servicios gestionados, planes, facturas o tareas de aprovisionamiento al importar. Repetir la misma combinación de router y usuario no duplica clientes. Los ausentes conservan su historial.

Los cambios de configuración, cortes y reconexiones permanecen bloqueados en API, controlador y transportes. El worker sólo procesa consultas permitidas, conserva pendientes los trabajos mutantes antiguos y no agenda facturación automática ni autocorte en lectura. No hay un botón para activar escrituras.

Para importar basta un usuario RouterOS con `read` y `api` (Socket) o `read` y `rest-api` (REST v7). `test` sólo es necesario para ping. La importación no necesita `write` ni `sensitive`.

La lista muestra usuario, router, perfil, dirección configurada y habilitación observada. **Habilitado no significa conectado.** Las IP vacías o nombres de pool se conservan sin inventar direcciones de sesión. La lectura admite hasta 20 000 entradas por router dentro de los límites del transporte; una respuesta inválida no se guarda parcialmente. Las cuentas RADIUS externas y usuarios exclusivos de Hotspot no forman parte de `/ppp/secret`.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y un administrador propio. Registra el acceso API/REST de tu router y ejecuta la importación desde Clientes.

El paquete incluye PHP, SQL, frontend compilado y código fuente. Utiliza PHP 8.2 y MariaDB/MySQL; no requiere Node.js, Docker, Redis ni Composer para ejecutarse.

## Verificación de la corrección

- **351 comprobaciones PHP** y sintaxis de 22 archivos de aplicación sin errores.
- **26 comprobaciones Socket TCP** con respuestas fragmentadas: el fallo se reprodujo antes del fix y pasa después; sólo `/login` y `/ppp/secret/print`, sin comandos de configuración.
- **108 comprobaciones API/Chromium** con 132 secrets por router, paginación, comentarios con acentos y controles, consulta/búsqueda de identidades heredadas, errores de campo/fila sin valores privados e idempotencia.
- MariaDB con identidades CP1252 y NUL persistidas exactamente en VARBINARY, sin colapsar usuarios de igual presentación; DTO JSON válido y hashes anteriores estables para UTF-8 imprimible.
- Actualización desde el ZIP v2.1 publicado: el error se reproduce antes de reemplazar archivos y la misma respuesta se importa después. Configuración y sesión se conservan, sin migración nueva.
- **Cero solicitudes mutantes de red** en las pruebas de lectura y actualización.

Se probaron Apache/PHP 8.2/MariaDB 10.4 en Linux y servidores de protocolo controlados. No se accedió al Windows ni al MikroTik real del operador ni se declara una prueba sobre un router físico. Una respuesta REST estructuralmente inválida sigue siendo rechazada por el transporte; los errores residuales del importador indican campo y fila sin mostrar su contenido.

SHA-256 del ZIP:

```
5efa7abbfd91bbac00b9ffa8fb99db6f51209edb1d3adae14875cdaf4029b0fa
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.1.1-lectura.zip -Algorithm SHA256`.

Consulta **CORRECCION-IMPORTACION.txt**, **IMPORTAR-SECRETS.txt**, **LEEME.txt**, **GUIA-ACTUALIZAR.txt**, **GUIA-MIKROTIK.txt** y **PRUEBAS.txt** dentro del ZIP. No contiene configuración instalada, contraseñas, datos de prueba ni claves privadas.

## Versiones históricas

Se conservan [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip) para referencia. Utiliza **v2.1.1** para la corrección de texto. Las versiones v1/v2 anteriores al modo de lectura permitían operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
