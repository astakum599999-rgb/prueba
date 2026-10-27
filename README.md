# NexoISP 2.1 para Windows/XAMPP: MikroTik en solo lectura

[**⬇ Descargar ZIP v2.1 — SOLO LECTURA**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.1-lectura.zip)

[Checksum SHA-256](nexoisp-xampp-v2.1-lectura.sha256)

Esta actualización agrega los secrets locales de MikroTik a **Clientes** mediante una importación de lectura. No modifica usuarios, perfiles, velocidades, colas, firewall ni conexiones del router. No copia las contraseñas PPP y no crea servicios gestionados, planes, facturas ni tareas de aprovisionamiento al importar.

**Antes de reemplazar archivos, detén el worker antiguo con Ctrl+C y detén Apache.** Un proceso de una versión anterior que siga abierto conserva su código anterior y debe cerrarse.

## Si ya instalaste el ZIP anterior

1. Respalda la base de datos y guarda de forma privada `nexoisp\storage\config.php`. Sigue **GUIA-ACTUALIZAR.txt** incluida en el ZIP.
2. Con el worker antiguo y Apache detenidos, copia los archivos nuevos sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y los archivos privados existentes.
3. Inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Entra con tu administrador y aplica la actualización. Desde v2 aparecerá pendiente **006_secret_import**.
4. Comprueba el aviso **MikroTik en modo solo lectura**. Puedes abrir el worker de esta versión; únicamente procesará tareas permitidas de consulta.
5. Entra en **Clientes → Importar secrets de MikroTik**, elige tu router o todos los registrados y pulsa **Leer e importar clientes**.

La tabla muestra usuario, router, perfil, dirección configurada y habilitación observada. Puedes repetir la lectura sin duplicar la misma combinación exacta de router y usuario. Los nombres coincidentes en routers diferentes permanecen separados. Los que dejen de aparecer conservan el cliente y su historial.

## Instalación nueva

Extrae `nexoisp` dentro de `C:\xampp\htdocs`, inicia Apache y MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y un administrador propio. Registra el router con su acceso API/REST y ejecuta la importación desde Clientes.

El paquete usa PHP 8.2 y MariaDB/MySQL; incluye interfaz compilada y código fuente. No requiere Node.js, Docker, Redis ni Composer para utilizarlo.

## Protección de la red

El modo de lectura es el valor predeterminado, también para configuraciones antiguas sin la opción nueva. Las escrituras se bloquean en API, controlador y transportes Socket/REST. El worker no agenda facturación automática ni autocorte y mantiene sin ejecutar los trabajos antiguos que modificarían la red. No hay un botón para activar escrituras.

Para importar basta un usuario de RouterOS con `read` y `api` (Socket) o `read` y `rest-api` (REST v7). `test` sólo es necesario si utilizarás ping. No se requieren permisos `write` ni `sensitive` para esta importación.

La fuente es `/ppp/secret`: incluye cuentas deshabilitadas y modalidades PPP diferentes, hasta 20 000 entradas por lectura de router; una respuesta inválida o excedida se rechaza sin importación parcial. No incluye usuarios externos de RADIUS ni usuarios exclusivos de Hotspot. **Habilitado no significa conectado**; las direcciones vacías o pools se conservan sin inventar una IP de sesión.

La importación guarda datos localmente. Esta entrega no accedió a tu XAMPP ni a tu MikroTik a distancia: debes instalar la actualización y ejecutar el botón en tu equipo.

## Verificación

316 comprobaciones PHP, 22 archivos PHP sin errores de sintaxis, 99 comprobaciones API/navegador en lectura y 132 secrets por router. El servidor de protocolo registró **cero solicitudes mutantes** durante la prueba de importación, API, worker y navegador. Se verificaron idempotencia, paginación, permisos, fallos atómicos, exclusión de contraseñas y conservación de tareas antiguas. La actualización desde el ZIP v2 publicado conservó config.php byte por byte, datos, sesión, clave de API y credenciales cifradas.

También pasó la regresión de los módulos anteriores en una configuración de laboratorio explícitamente autorizada, restaurada al modo de lectura al terminar. Esa configuración de prueba no se incluye en el ZIP. La fuente frontend incluida se compiló aisladamente y coincide con los assets entregados.

Probado con Apache/PHP 8.2/MariaDB 10.4 en Linux y servidores de protocolo; no se declara una prueba sobre routers físicos ni un escritorio Windows real.

SHA-256 del ZIP:

```
87f4068a71aa77a6709bbced143a69d3eb337dd7cc0345b058edd857d6fdd5d2
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.1-lectura.zip -Algorithm SHA256`.

Consulta **IMPORTAR-SECRETS.txt**, **LEEME.txt**, **GUIA-MIKROTIK.txt**, **GUIA-ACTUALIZAR.txt**, **PRUEBAS.txt** y la referencia de API dentro del paquete. No contiene configuración instalada, credenciales, base de prueba ni claves privadas.

## Versiones históricas

Se conservan [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip) para referencia. Esas distribuciones anteriores permitían operaciones de configuración; para el modo de lectura utiliza el ZIP **v2.1** del enlace superior.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
