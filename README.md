# NexoISP 2.3.1 para XAMPP — nombre del cliente en MikroTik

[**⬇ Descargar ZIP corregido v2.3.1**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.3.1-nombre-mikrotik.zip)

[Checksum SHA-256](nexoisp-xampp-v2.3.1-nombre-mikrotik.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

## Corrección del nombre

En 2.3.0, el botón principal **Guardar cambios** guardaba el nombre del cliente únicamente en NexoISP. Esta corrección sincroniza **Nombre completo / razón social** con **Comment** del secret PPPoE correspondiente en MikroTik.

En WinBox revisa **PPP → Secrets → cuenta del usuario → Comment**. El campo **Name** del router es el **usuario PPPoE** y se conserva al cambiar el nombre completo. La contraseña, IP, perfil, velocidad y otras cuentas tampoco cambian con este guardado.

**Si ya habías cambiado el nombre localmente, no tienes que volver a escribirlo:** después de actualizar, abre el cliente y pulsa **Guardar cambios**. Se detecta la diferencia con el comentario observado y se envía ese nombre al router aunque el nombre local sea el mismo de tu guardado anterior.

El guardado requiere **ADMIN** y permisos de escritura del usuario API RouterOS. Un contacto editado por separado no consulta ni modifica el equipo. Los clientes manuales sin un secret PPP importado conservan su edición local. Los comentarios reservados `nexoisp:...` de servicios gestionados se protegen para no romper sus vínculos.

## Actualizar en XAMPP

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker con Ctrl+C y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN.
5. Aplica **010_client_name_sync** y las migraciones anteriores pendientes, si las hubiera.
6. Vuelve a iniciar sesión y pulsa **Ctrl+F5** para cargar la nueva interfaz.
7. Abre **Clientes → Editar**, revisa el nombre y pulsa **Guardar cambios** al final del formulario. Espera la confirmación y revisa **Comment** en WinBox.

La migración010 añade el registro local de sincronización. No accede al router por sí sola ni cambia nombres automáticamente. Los SQL001–009 conservan exactamente sus bytes y checksums. No se reinstala la base ni se cambian claves. PEN/S/ e historial financiero con sus monedas originales se conservan.

## Confirmación del guardado

Antes de escribir se comprueban la versión del cliente, el id del secret, su usuario binario exacto y el comentario observado. Reimportar después de una modificación confirmada conserva el nombre, el código y la identidad del cliente sin duplicarlo.

Si el router rechaza el comentario, no se informa éxito ni se confirma parcialmente el nombre y los contactos de esa misma solicitud. Si pudo aplicar el comentario pero se perdió la respuesta, queda pendiente. Usa **Verificar nombre pendiente** en Editar cliente: sólo consulta y confirma el resultado, sin repetir la escritura. Mientras tanto se bloquean nuevas ediciones de ese cliente e importaciones/ediciones PPP del router para conservar la identidad. Otros routers siguen disponibles.

## Funciones conservadas

**Guardar cambios PPPoE en MikroTik** continúa editando el usuario y la contraseña de la cuenta seleccionada. La nueva contraseña vacía conserva la anterior. **Mostrar contraseña** sigue siendo explícito para ADMIN; la importación masiva no copia contraseñas.

Las escrituras manuales están limitadas a esos campos y al comentario del nombre. Cortes, reconexiones, aprovisionamiento, firewall y tareas mutantes antiguas siguen bloqueados. No cambies `network_read_only` para usar la corrección.

Los planes se importan desde los perfiles PPP y requieren tarifa comercial explícita. La demo de facturas, pagos, promesas y suspensión permanece aislada en **http://localhost/nexoisp/demo/**, con datos ficticios y sin configurar la red.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB/MySQL. Incluye interfaz compilada y fuente; para utilizarlo no necesitas Node.js, Docker, Redis ni Composer.

## Validación

766 comprobaciones PHP aprobadas, incluidas 149 de protocolos Socket/REST, y sintaxis de26 archivos PHP. TypeScript/Vite compilado. Las suites API/Chromium anteriores pasaron108 comprobaciones de secrets,65 de perfiles,90 de consulta de contraseñas y112 de edición de credenciales. Otras134 comprobaron el guardado principal del nombre, reparación del nombre ya editado localmente, comentario como único campo remoto, credenciales intactas, reimportación sin duplicados, versiones, permisos, rechazo sin guardado parcial y verificación de respuestas perdidas.

La actualización real desde el ZIP2.3.0 publicado pasó77 comprobaciones: migración010, datos de empresa, PEN, historial financiero USD y configuración privada idénticos. La actualización no escribió al router; un guardado explícito posterior reparó el nombre que ya se había editado en la versión anterior, cambiando únicamente Comment y conservando el mismo cliente al reimportar.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium con servidores de protocolo controlados. No se accedió al Windows, MikroTik físico, clientes ni credenciales reales del operador.

SHA-256:

```
2ed2664369002585e391c7ed975d8dc7adaa6998f1669372aaaeabf2a055e6a6
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.3.1-nombre-mikrotik.zip -Algorithm SHA256`.

Lee **NOMBRE-MIKROTIK.txt**, **GUIA-ACTUALIZAR.txt**, **LEEME.txt**, **USUARIO-PPPOE.txt** y **PRUEBAS.txt** en el ZIP. No contiene configuración instalada, datos reales, contraseñas ni claves privadas.

## Versiones anteriores

Se conservan [v2.3.0](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [v2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [v2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Usa **v2.3.1** para sincronizar el nombre completo con el comentario. Las versiones v1/v2 anteriores al modo lectura permitían otras operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
