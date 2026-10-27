# NexoISP 2.2.2 para XAMPP — credenciales PPPoE en Editar cliente

[**⬇ Descargar ZIP v2.2.2**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/nexoisp-xampp-v2.2.2-pppoe.zip)

[Checksum SHA-256](nexoisp-xampp-v2.2.2-pppoe.sha256) · [Demostración independiente](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/demostracion-nexoisp.html)

## Usuario y contraseña en Editar cliente

Abre **Clientes → Editar → Credenciales PPPoE**. Aparecen el usuario, router y origen de cada cuenta asociada. Como **ADMIN**, pulsa **Mostrar contraseña** para consultar esa cuenta concreta. **Ocultar contraseña** elimina el valor de la interfaz; al cerrar la ventana también se descarta.

Los campos PPPoE son de **solo lectura**. Mostrar contraseña no guarda datos del cliente ni modifica usuarios, contraseñas o configuración del MikroTik. La consulta no necesita habilitar escritura en la red.

Para cuentas importadas se lee únicamente la entrada seleccionada de `/ppp/secret`, comprobando su identificador y usuario exacto. La contraseña no se persiste en NexoISP y la importación masiva sigue excluyéndola. Si RouterOS la oculta, omite o deniega por permisos de lectura sensible, se muestra **No disponible** con una explicación. No se cambian las políticas del router. RADIUS externo no está incluido.

Si existen servicios PPPoE locales anteriores, su contraseña cifrada guardada puede consultarse por separado; se identifica como **NexoISP** y puede diferir del valor actual en el router. El personal sin rol ADMIN puede consultar usuarios, pero no revelar contraseñas. Las cuentas del portal de clientes no tienen acceso a estas rutas.

## Actualizar desde tu XAMPP

1. Respalda la base y guarda una copia privada de `storage\config.php`.
2. Cierra el worker con Ctrl+C y detén Apache.
3. Copia la carpeta `nexoisp` del ZIP sobre `C:\xampp\htdocs\nexoisp`, **conservando exactamente tu `storage\config.php`** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/**.
5. Desde **2.2.1 no hay migraciones nuevas**. Si vienes de una versión anterior, aplica las pendientes en `actualizar.php` como ADMIN; la última es `008_currency_pen`.
6. Vuelve a iniciar sesión y pulsa **Ctrl+F5** para cargar la nueva interfaz.
7. Abre **Clientes → Editar** y consulta los campos PPPoE.

Los SQL 001–008 mantienen sus bytes y checksums. La actualización no reinstala la base ni cambia credenciales. No sobrescribas tu configuración privada: contiene la clave de cifrado de tu instalación.

## Funciones conservadas

La moneda local predeterminada es **PEN — soles peruanos**, presentada como **S/**. Los importes y monedas históricos se conservan. Los nombres de clientes siguen viniendo del comentario del secret. **Planes de Internet → Importar perfiles de MikroTik** crea planes locales pendientes de tarifa; el precio comercial se configura explícitamente.

El MikroTik permanece en **solo lectura**: cortes, reconexiones y cambios de configuración siguen bloqueados. El worker no ejecuta tareas mutantes antiguas ni agenda autocorte/facturación automática en este modo. La demo en **http://localhost/nexoisp/demo/** utiliza datos ficticios aislados, sin conectar al router ni a la API.

## Instalación nueva

Extrae `nexoisp` en `C:\xampp\htdocs`, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador con tus datos y crea tu administrador. Se requiere PHP 8.2 y MariaDB/MySQL. El frontend compilado y su fuente están incluidos; no necesitas Node.js, Docker, Redis ni Composer para usar el paquete.

## Validación

617 comprobaciones PHP aprobadas, incluidas 101 nuevas para la lectura de credenciales; sintaxis correcta en los 24 archivos PHP. TypeScript/Vite compilado. Integración con instalador/MariaDB y suites API/Chromium: 108 comprobaciones de secrets, 65 de perfiles y 90 nuevas de credenciales. Se verificaron autenticación, roles, CSRF, pertenencia al cliente, valores exactos, contraseñas vacías/ocultas/omitidas, ausencia de persistencia en texto plano y botones que no guardan el formulario. **Cero solicitudes de configuración de RouterOS**.

Pruebas realizadas en Apache/PHP 8.2/MariaDB 10.4 Linux y Chromium, usando servidores de protocolo controlados. No se accedió al Windows, MikroTik físico ni contraseñas reales del operador.

SHA-256:

```
26d69f19c98faab30e03cffe8c04487677598413b38a3db5b20031a2d002bcb9
```

En PowerShell: `Get-FileHash .\nexoisp-xampp-v2.2.2-pppoe.zip -Algorithm SHA256`.

Lee **USUARIO-PPPOE.txt**, **GUIA-ACTUALIZAR.txt**, **LEEME.txt** y **PRUEBAS.txt** dentro del ZIP. El paquete no contiene configuración instalada, datos reales, contraseñas ni claves privadas.

## Versiones anteriores

Se conservan [v2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [v2.2](nexoisp-xampp-v2.2-lectura.zip), [v2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [v2.1](nexoisp-xampp-v2.1-lectura.zip), [v2](nexoisp-xampp-v2.zip) y [v1](nexoisp-xampp.zip). Utiliza **v2.2.2** para los campos PPPoE en Editar cliente. Las distribuciones v1/v2 anteriores al modo lectura permitían operaciones de configuración.

NexoISP es una implementación propia, sin código privado ni identidad gráfica de WispHub.
