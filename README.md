# NexoISP 2.2.1 para XAMPP — soles peruanos

[**⬇ Descargar ZIP v2.2.1 — SOLES PERUANOS**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.2.1-soles.zip)

[Checksum SHA-256](nexoisp-xampp-v2.2.1-soles.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

La moneda local predeterminada es **PEN — soles peruanos**, mostrada como **S/**. Los formularios nuevos de planes, cajas/cuentas, inventario y visitas usan la preferencia de **Mi empresa**. La interfaz utiliza formato peruano y los documentos imprimibles en PEN muestran S/.

**No se convierten ni se renombran importes anteriores.** Los planes ya configurados, facturas, pagos, contratos y cuentas existentes en USD conservan su moneda y valores. El sistema mantiene cada moneda separada en los reportes. No se aplica un tipo de cambio.

## Actualizar

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker con Ctrl+C y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y archivos privados locales.
4. Inicia Apache/MySQL, abre **http://localhost/nexoisp/** y aplica **008_currency_pen** con tu administrador.
5. Vuelve al panel, inicia sesión de nuevo y usa **Ctrl+F5** si el navegador conserva la pantalla anterior.
6. Revisa **Mi empresa → Moneda ISO predeterminada**: debe indicar **PEN**.

Desde versiones anteriores también aparecerán las migraciones intermedias necesarias. Los SQL 001 a 007 conservan sus bytes y checksums. La nueva 008 cambia únicamente la preferencia monetaria de la empresa, conservando nombre, dirección, contacto y notas. No cambia credenciales ni reinstala la base.

## Planes importados y moneda

**Planes de Internet → Importar perfiles de MikroTik** copia los perfiles PPP como observaciones locales. Los perfiles con velocidades base representables generan planes inactivos pendientes de tarifa; RouterOS no guarda precios comerciales. El administrador debe introducir explícitamente precio y moneda antes de activar o facturar ese plan.

Al editar un plan importado que aún no tiene tarifa, se propone la preferencia local actual PEN y el precio queda vacío. Un borrador antiguo con moneda provisional USD no se convierte automáticamente en un plan gratuito ni se modifica silenciosamente. Un plan ya configurado conserva su moneda original al editarlo.

Los nombres de clientes siguen tomándose del comentario del secret, conservando el usuario PPP como identidad. Leer perfiles o secrets no crea servicios ni aplica configuración de red.

## MikroTik sigue en solo lectura

Las escrituras, cortes y reconexiones reales permanecen bloqueados en API, controlador y transportes. El worker no ejecuta trabajos mutantes antiguos ni agenda facturación automática/autocorte en lectura. Cambiar la moneda local no cambia esta política.

La demo está en **http://localhost/nexoisp/demo/** o puede descargarse como HTML independiente. Usa datos ficticios en memoria para practicar factura100, promesas, pagos40+60, suspensión manual o por deuda y tareas simuladas; no conecta al MikroTik ni utiliza API o datos reales.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y crea tu administrador. Se requiere PHP8.2 y MariaDB/MySQL. El frontend compilado y su fuente están incluidos; no necesitas Node.js, Docker, Redis ni Composer para usar el paquete.

## Validación

30 comprobaciones nuevas de preferencia PEN y whitelist de migración, más486 comprobaciones PHP de regresión; sintaxis de23 archivos sin errores. TypeScript/Vite y16 comprobaciones de formato/valores predeterminados pasaron.

La actualización real desde el ZIP2.2 publicado pasó59 comprobaciones API/Chromium: preferenciaPEN, símboloS/, formularios nuevosPEN, y monedas históricas intactas. Se compararon filas completas de planUSD, factura con pago parcial, pago, líneas de factura, contrato, caja, movimiento e inventarioUSD. También se preservó config.php byte por byte, los datos de la empresa y el saldo anterior. **Cero solicitudes de configuración RouterOS** durante la prueba.

Validado con Apache/PHP8.2/MariaDB10.4 en Linux y Chromium. No se accedió al Windows, MikroTik físico ni datos reales del operador.

SHA-256 del ZIP:

```
81da8618140be0ac246fb42be4ed706fea376a03db2f9e00e8d1aae82d5d711c
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.2.1-soles.zip -Algorithm SHA256`.

Lee **MONEDA-SOLES.txt**, **LEEME.txt**, **GUIA-ACTUALIZAR.txt**, **IMPORTAR-PERFILES.txt**, **DEMOSTRACION.txt** y **PRUEBAS.txt** dentro del paquete. No contiene configuración instalada, contraseñas, claves privadas ni base de pruebas.

## Versiones anteriores

Se conservan [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Utiliza **v2.2.1** para los valores predeterminados en soles. Las distribuciones v1/v2 anteriores al modo lectura permitían operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
