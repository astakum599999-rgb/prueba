# NexoISP 2.2 para XAMPP — perfiles PPP, nombres y demostración

[**⬇ Descargar ZIP completo v2.2 — SOLO LECTURA**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.2-lectura.zip)

[**⬇ Descargar demostración independiente**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html) · [Checksum del ZIP](nexoisp-xampp-v2.2-lectura.sha256)

## Qué cambia

- **Clientes:** el nombre se toma del comentario del secret. Al repetir la importación, el comentario no vacío reemplaza el nombre local anterior, conservando usuario PPP, código, identidad, contactos y demás datos. Si el comentario está vacío se conserva el nombre existente; un cliente nuevo usa el usuario como alternativa.
- **Planes de Internet:** nuevo botón **Importar perfiles de MikroTik**. Copia todos los perfiles PPP a observaciones locales; los que tienen velocidad base representable generan planes locales inactivos, pendientes de tarifa. RX corresponde a subida del cliente y TX a bajada.
- Los perfiles sin `rate-limit`, ilimitados, no representables o reservados para corte se muestran para revisión; no se inventa velocidad ni se convierte el perfil de suspensión en un plan comercial.
- **Demostración:** factura, suspensión, promesa y pagos con datos ficticios en memoria. No utiliza API, cuenta, almacenamiento real ni conexión al MikroTik.

RouterOS no contiene el precio mensual ni la moneda comercial. Los planes importados muestran **Precio pendiente** hasta que un administrador complete esos datos; ese estado bloquea activación y facturación. El valor interno inicial cero no significa tarifa gratuita. Un precio cero sólo queda configurado si se establece explícitamente como tal.

## Actualizar desde el ZIP anterior

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. **Cierra el worker con Ctrl+C y detén Apache** antes de reemplazar archivos.
3. Extrae `nexoisp` sobre `C:\xampp\htdocs\nexoisp`, conservando exactamente tu `storage\config.php` y los archivos privados locales.
4. Inicia Apache/MySQL, abre **http://localhost/nexoisp/** y aplica **007_profile_import** con tu administrador existente.
5. En **Clientes → Importar secrets de MikroTik**, repite la lectura para actualizar los nombres desde los comentarios.
6. En **Planes de Internet → Importar perfiles de MikroTik**, elige un router o todos. Revisa las observaciones y completa las tarifas locales cuando corresponda.

Los SQL 001 a 006 conservan sus bytes y checksums. No se reinstala la base ni se restablecen usuarios o credenciales. Si tienes una versión anterior, el actualizador también muestra las migraciones intermedias necesarias.

## Probar la demostración

Después de instalar el ZIP abre **http://localhost/nexoisp/demo/** o usa el enlace **Ver demostración** del panel. También puedes descargar el HTML independiente del enlace superior y abrirlo en tu navegador; contiene todo su código y estilos.

Ejercicio de ejemplo:

1. Pulsa **Crear factura**: importe 100, saldo 100.
2. **Avanzar al fin de gracia → Revisar vencimientos → Procesar tarea simulada**: corte por deuda en la simulación.
3. **Registrar promesa → Procesar tarea simulada**: el compromiso cubre la deuda hasta la fecha indicada; no registra dinero ni reduce el saldo.
4. Registra un pago de **40**: saldo **60**. Completa los otros **60** con otra referencia para liquidar la factura.
5. Prueba **Suspender manualmente**: un pago o promesa no cancela un corte manual. También puedes agregar otra factura vencida para ver cómo mantiene la deuda.

Los estados solicitado/aplicado y la tarea simulada muestran que una operación encolada requiere confirmación. El reloj es virtual: no modifica la hora de Windows ni del router. **Reiniciar demostración** borra únicamente esos datos ficticios.

## Tu red sigue en solo lectura

Las importaciones sólo consultan `/ppp/secret` y `/ppp/profile`; no copian contraseñas PPP ni crean servicios, facturas o tareas de configuración. No enlazan perfiles y clientes mediante nombres ambiguos ni provisionan servicios automáticamente.

Los cambios de configuración, suspensiones y reconexiones reales permanecen bloqueados en API, controlador y transportes. El worker conserva pendientes los trabajos mutantes antiguos y no agenda facturación automática ni autocorte en este modo. No hay un botón para habilitar escrituras.

Una factura real necesita un servicio administrativo asociado y una tarifa revisada. Importar clientes/perfiles no crea ese servicio ni habilita el aprovisionamiento. Usa la demo para aprender los flujos durante la etapa de lectura.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache y MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y un administrador propio. Requiere PHP 8.2 y MariaDB/MySQL. Incluye frontend compilado y fuente; no requiere Node.js, Docker, Redis ni Composer para ejecutarse.

## Validación

486 comprobaciones PHP, 23 archivos PHP sin errores de sintaxis, 108 comprobaciones API/navegador de secrets y 65 de perfiles/planes. Se verificaron tarifas pendientes, bloqueo de facturas de importe cero desconocido, idempotencia, identidad por router, nombres desde comentarios y cero solicitudes mutantes RouterOS durante las suites de lectura.

La demo pasó 41 comprobaciones Chromium sobre Apache real sin llamadas API ni recursos externos. La actualización desde v2 preservó configuración byte por byte, facturas, pagos, sesiones, claves y acceso a credenciales cifradas. También pasó la regresión de 176 comprobaciones API base y 200 ampliadas en un laboratorio explícitamente autorizado; esa configuración de prueba no se incluye en el ZIP.

Las pruebas se ejecutaron con Apache/PHP 8.2/MariaDB 10.4 en Linux y servidores de protocolo controlados, sin routers físicos ni acceso a datos del operador. La velocidad importada es la BASE del perfil: burst y prioridad permanecen como texto observado, no una configuración QoS aplicada.

SHA-256 de `nexoisp-xampp-v2.2-lectura.zip`:

```
0fcb496727d4239f877e06e711e047ec039da1b83c340bf52b56b1ee9fa128de
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.2-lectura.zip -Algorithm SHA256`.

Lee **LEEME.txt**, **GUIA-ACTUALIZAR.txt**, **IMPORTAR-SECRETS.txt**, **IMPORTAR-PERFILES.txt**, **DEMOSTRACION.txt** y **PRUEBAS.txt** dentro del ZIP. No contiene configuración instalada, contraseñas, datos de prueba ni claves privadas.

## Historial

Se conservan [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Usa **v2.2** para perfiles y nombres desde comentarios. Las distribuciones v1/v2 anteriores al modo de lectura permitían operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
