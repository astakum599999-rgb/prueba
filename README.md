# NexoISP 2.3.2 para XAMPP — notas internas por cliente

[**⬇ Descargar ZIP v2.3.2 con Notas**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.3.2-notas-clientes.zip)

[Checksum SHA-256](nexoisp-xampp-v2.3.2-notas-clientes.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

## Recuadro Notas

En **Clientes → Editar** y **Nuevo cliente**, debajo de **Latitud GPS / Longitud GPS**, aparece **Notas**: un recuadro de ancho completo para guardar detalles administrativos de cada cliente. Admite varias líneas y hasta5000 caracteres. Se guarda con **Guardar cambios** y vuelve a aparecer al editar o consultar el detalle.

Puedes vaciar el recuadro y guardar para borrar las notas. Al editar otros datos se conservan, y reimportar los secrets tampoco las reemplaza. Los espacios y saltos de línea se mantienen; el texto se muestra como texto literal.

**Las notas son internas de NexoISP. No se envían al MikroTik ni aparecen en el portal del abonado.** Son independientes del comentario PPPoE que contiene el nombre completo. ADMIN, BILLING y TECHNICIAN pueden editarlas con los permisos existentes; VIEWER sólo consulta.

## Actualizar desde tu instalación

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, conservando exactamente **`storage\config.php`** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN.
5. Aplica **011_client_notes** y las migraciones anteriores pendientes, si las hubiera.
6. Vuelve a iniciar sesión y pulsa **Ctrl+F5**.
7. Abre **Clientes → Editar**, escribe tus notas debajo de GPS y pulsa **Guardar cambios**.

La migración011 añade únicamente la tabla local ClientNote. Los clientes existentes empiezan sin notas inventadas. No cambia datos financieros, claves, configuración instalada ni routers. Los SQL001–010 conservan sus bytes y checksums publicados.

## Funciones anteriores conservadas

**Nombre completo / razón social** sigue sincronizándose con **Comment** del secret PPPoE/any importado al guardar como ADMIN. **Usuario PPPoE** corresponde a **Name** en MikroTik y se modifica con el botón **Guardar cambios PPPoE en MikroTik**, junto con la nueva contraseña opcional. La corrección del nombre ya guardado localmente y la verificación de respuestas pendientes se mantienen.

Una edición sólo de notas no consulta la red. Si cambias también un nombre sincronizado, se aplican su permiso ADMIN y la confirmación del router. Cortes, reconexiones, aprovisionamiento, firewall y trabajos mutantes antiguos siguen bloqueados. No cambies `network_read_only` para usar Notas.

Se conservan PEN/S/, planes importados pendientes de tarifa y monedas/importes históricos. La demo de facturas, pagos, promesas y suspensión está en **http://localhost/nexoisp/demo/** y utiliza datos ficticios aislados.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB/MySQL. Incluye interfaz compilada y fuente; no necesitas Node.js, Docker, Redis ni Composer para utilizar el ZIP.

## Validación

23 comprobaciones nuevas API/Chromium de notas: persistencia, límite, tipos, espacios/saltos exactos, borrado, independencia entre clientes, permisos, privacidad del portal, reimportación, posición debajo de GPS y guardado/reapertura desde navegador. Las ediciones de notas no enviaron solicitudes al MikroTik.

766 comprobaciones PHP de regresión aprobadas, sintaxis de27 archivos y TypeScript/Vite compilado. Suites anteriores API/Chromium repetidas:108 de secrets,65 de perfiles,90 de consulta PPP,112 de edición de credenciales y134 de sincronización del nombre.

La actualización real desde el ZIP2.3.1 publicado pasó66 comprobaciones: migración011, notas multilínea para clientes existentes, PEN, empresa, sesión, histórico financiero USD y configuración privada idéntica. Cero escrituras RouterOS en esa actualización.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium con servidores de protocolo controlados. No se accedió al Windows, MikroTik físico ni datos reales del operador.

SHA-256:

```
428c50fc17e77f7f95588b9c9f71f888660b4e57c2dc98b4036c9da5291c2e7e
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.3.2-notas-clientes.zip -Algorithm SHA256`.

Lee **NOTAS-CLIENTES.txt**, **GUIA-ACTUALIZAR.txt**, **LEEME.txt** y **PRUEBAS.txt** dentro del ZIP. No contiene instalación previa, notas privadas, datos reales, contraseñas ni claves.

## Versiones anteriores

Se conservan [v2.3.1 nombre/comentario](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [v2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [v2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [v2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Usa **v2.3.2** para las notas internas. Las versiones v1/v2 anteriores al modo lectura permitían otras operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
