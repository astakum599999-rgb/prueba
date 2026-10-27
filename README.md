# NexoISP 2.3.0 para XAMPP — editar usuario y contraseña PPPoE

[**⬇ Descargar ZIP v2.3.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.3.0-editar-pppoe.zip)

[Checksum SHA-256](nexoisp-xampp-v2.3.0-editar-pppoe.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

## Edición desde Clientes

Como **ADMIN**, abre **Clientes → Editar → Credenciales PPPoE**. Modifica **Usuario PPPoE** y/o escribe **Nueva contraseña PPPoE (opcional)**. Pulsa **Guardar cambios PPPoE en MikroTik** en esa cuenta y espera la confirmación.

**Ese botón actualiza la cuenta existente en tu MikroTik.** Dejar vacía la nueva contraseña conserva la actual. El equipo del cliente deberá usar los nuevos datos al autenticarse de nuevo. NexoISP no solicita desconectar sesiones ni cambia perfiles, IP, comentarios, velocidades u otras cuentas.

El botón **Guardar cambios** del formulario principal continúa guardando los datos administrativos del cliente. Es independiente del guardado PPPoE. Al reimportar, el nombre sigue tomándose del comentario no vacío del router, según la regla anterior.

Sólo ADMIN puede editar o revelar credenciales. Los demás roles conservan la consulta. El acceso API RouterOS necesita permisos para escribir en `/ppp/secret`; para consultar contraseñas también necesita acceso a datos sensibles. NexoISP no cambia permisos del router.

## Actualizar tu XAMPP

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker con Ctrl+C y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** con tu ADMIN.
5. Aplica **009_pppoe_edits** y las versiones anteriores pendientes, si las hubiera. La migración añade el registro local de ediciones; no modifica el router.
6. Abre **http://localhost/nexoisp/**, vuelve a iniciar sesión y pulsa **Ctrl+F5** para cargar la interfaz nueva.
7. Entra en **Clientes → Editar** y usa el botón específico para guardar las credenciales PPPoE.

Los SQL 001–008 mantienen exactamente los bytes y checksums publicados. No se reinstala la base ni se cambian las claves de tu instalación. Se conservan PEN/S/, los nombres desde comentarios y el historial financiero con sus monedas originales.

## Escritura limitada a la cuenta seleccionada

Se verifica el cliente propietario, la versión de la cuenta, su identificador y usuario exactos en RouterOS. Los nombres duplicados y los vínculos ambiguos se rechazan antes de escribir. Renombrar actualiza la observación local y conserva cliente/código para que reimportar no lo duplique. Los servicios gestionados existentes requieren su comentario de propiedad y conservan sus vínculos y credenciales cifradas.

La autorización manual sólo permite `name` y `password` de un secret existente. **Cortes, reconexiones, aprovisionamiento, firewall y demás cambios de red siguen bloqueados.** El worker no ejecuta tareas mutantes antiguas ni agenda autocorte/facturación automática. No cambies `network_read_only` para usar esta función.

Si se pierde una respuesta después de enviar el cambio, el sistema no afirma que se deshizo ni repite la escritura automáticamente. Conserva la intención cifrada y muestra **Verificar cambios pendientes**; esa acción sólo consulta y sincroniza el resultado confirmado. Las importaciones de secrets y nuevas ediciones de ese router esperan a resolverlo para evitar duplicados. Otros routers siguen disponibles.

Las contraseñas no aparecen en auditoría ni respuestas ordinarias. Una contraseña nueva pendiente se cifra; se elimina del registro temporal al confirmar o rechazar definitivamente. En un servicio gestionado se conserva cifrada en el propio servicio. Mostrar contraseña continúa siendo explícito y temporal; la importación masiva sigue excluyéndola.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP 8.2 y MariaDB/MySQL. Incluye frontend compilado y fuente; para usarlo no necesitas Node.js, Docker, Redis ni Composer.

La demostración de facturas, pagos, promesas y suspensión está en **http://localhost/nexoisp/demo/**. Utiliza datos ficticios aislados y no configura el router.

## Validación

718 comprobaciones PHP aprobadas y sintaxis de 25 archivos PHP. TypeScript/Vite compilado. Las suites de API/Chromium de lectura pasaron 108 comprobaciones de secrets, 65 de perfiles y 90 de consulta de contraseñas sin escrituras al router. Otras 112 comprobaron la edición manual autorizada, permisos, colisiones, contraseña omitida, identidad estable al reimportar, intención cifrada, recuperación de respuesta perdida y ausencia de cambios ajenos. Las mutaciones permitidas se limitaron a PATCH del secret seleccionado con name/password.

La actualización real desde el ZIP 2.2.2 publicado pasó 59 comprobaciones: migración009, capacidad de edición manual, PEN, datos de empresa, configuración privada idéntica y registros financieros USD intactos. La actualización del esquema no envió cambios al router.

Pruebas en Apache/PHP 8.2/MariaDB 10.4 Linux y Chromium con servidores de protocolo controlados. No se accedió al Windows, MikroTik físico, clientes ni contraseñas reales del operador.

SHA-256:

```
079117a77a6163e9f1302c281ce971ff82a3e484668f500197eac25a5ca6055f
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.3.0-editar-pppoe.zip -Algorithm SHA256`.

Lee **USUARIO-PPPOE.txt**, **GUIA-ACTUALIZAR.txt**, **LEEME.txt** y **PRUEBAS.txt** dentro del ZIP. No contiene configuración instalada, datos reales, contraseñas ni claves privadas.

## Versiones anteriores

Se conservan [v2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [v2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Utiliza **v2.3.0** para editar las credenciales PPPoE. Las versiones v1/v2 anteriores al modo lectura permitían otras operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
