# GIGARED ISP 3.0.0 para XAMPP — Fibra óptica nativa

[**Descargar ZIP completo 3.0.0**](https://github.com/astakum599999-rgb/prueba/raw/refs/heads/descargas-xampp/gigared-isp-xampp-v3.0.0-ftth.zip)

[Checksum SHA-256](gigared-isp-xampp-v3.0.0-ftth.sha256)

## Cambios incluidos

La columna **IP** muestra sólo las direcciones. Se ocultaron el router/origen, mensaje periódico y fecha de lectura dentro de esa columna. Se mantienen la IP automática, su caducidad y el recuadro HTTP en la misma página.

El módulo **Fibra óptica** se integra al menú y a la ficha del cliente: resumen, OLTs, ONUs autorizadas y sin autorizar, PON, VLAN, perfiles DBA/LINE/SERVICE/TRAFFIC, zonas, NAP, splitters, hilos/enlaces, mapa georreferenciado, consultas por modelo, preparaciones y tareas. Incluye filtros ONLINE/OFFLINE/LOS, potencia Rx/Tx y gráficos de muestras existentes, sin inventar mediciones ausentes.

La implementación es propia y usa los flujos observables del [manual público de AdminOLT](https://adminolt.com/documentacion/home-1/). El ZIP incluye **INVESTIGACION-ADMINOLT.md**, **MATRIZ-FTTH.md**, esquema y API documentada. No se afirma identidad de código, copia exacta de pantallas privadas ni compatibilidad binaria con una API privada de AdminOLT.

## Política de red

Se conserva el modo de lectura. Autorizar, reiniciar, configurar WiFi, suspender, reactivar o retirar una ONU crea una **preparación local revisable**, con claves cifradas. No aplica cambios al hardware ni cambia falsamente su estado observado. Los endpoints de aplicación permanecen bloqueados; no existe un escritor universal habilitado para todos los firmwares.

SSH usa phpseclib incluido y requiere verificar la huella del servidor. Telnet y SNMPv2c realizan consultas limitadas; SNMP sólo GET/GETNEXT. Hay bases de descubrimiento Huawei/ZTE y un registro de consultas/parsers para cada modelo. No se inicializan OLTs, habilitan puertos ni envían comandos de configuración automáticamente.

## VSOL V1600GS-F

La [ficha oficial](https://www.vsolcn.com/product/1-pon-gpon-olt-v1600gsf-v1600gszf) identifica **un puerto GPON**, con gestión Web/Telnet/CLI/SNMP. No se trata como EPON ni se reutilizan comandos de una OLT de chasis.

**Falta validar la versión de firmware y sus consultas CLI/OIDs ópticos.** El módulo permite inventario local, identificación SNMP estándar con acceso de lectura existente y consultas configurables. La prueba MIB-II no equivale a descubrir ONUs. Los planes Single-PON pueden ser informativos; no se promete aplicar QoS, WiFi o autorizaciones reales desde una preparación.

## Actualizar XAMPP

1. Respalda la base y guarda una copia privada de **storage\config.php**.
2. Cierra el worker y detén Apache.
3. Extrae el ZIP y copia el contenido de **nexoisp** sobre **C:\xampp\htdocs\nexoisp**, conservando exactamente **storage\config.php** y los archivos privados locales.
4. Inicia Apache/MySQL y abre **http://localhost/nexoisp/actualizar.php** como ADMIN. Aplica las pendientes hasta **014_fiber**.
5. Inicia sesión, pulsa **Ctrl+F5** y abre **Fibra óptica**.
6. Registra la OLT y sus accesos de lectura existentes. Prueba la conexión antes de activar sus consultas periódicas. Ejecuta **INICIAR-WORKER.bat** para procesar tareas con el navegador cerrado.

La migración014 crea13 tablas vacías y no contacta al router ni OLT. SQL001–013 mantiene sus bytes e historial. Se conservan notas, clientes, credenciales, cachés PPP e importes/monedas históricos USD/PEN.

## Instalación nueva y contenido

Extrae **nexoisp** en **C:\xampp\htdocs**, inicia Apache/MySQL y abre **http://localhost/nexoisp/**. Completa el instalador y crea tu administrador. Requiere PHP8.2 y MariaDB10.4+/MySQL8+. El ZIP incluye PHP, SQL, frontend compilado, fuente React completa y bibliotecas SSH con sus licencias. No necesitas Node.js, Docker, Redis, Composer ni extensión SSH2 para usar la distribución.

Se conservan todas las funciones anteriores, incluida la edición manual seleccionada de nombres/credenciales MikroTik y la importación de secrets30s. Cortes y automatismos de configuración continúan protegidos. No cambies **network_read_only** para forzar una función no validada para el firmware.

## Validación

- Compilación TypeScript/Vite y382 archivos PHP sin errores de sintaxis;11 suites PHP de regresión aprobadas.
- Regresiones API/Chromium existentes:671 comprobaciones aprobadas. Nueva suite FTTH API/protocolos/navegador:94 aprobadas.
- Telnet y SNMP reales contra servidores privados simulados: descubrimiento, parser, potencia, trabajos, cifrado, permisos, rechazo atómico y ausencia de comandos mutantes. Medidas negativas y Counter64 máximo conservado exactamente.
- Navegador: asistente de cuatro pasos, preparación WiFi, filtros, secreto no precargado, gráficas y mapa conNAP/enlacePON.
- Actualización desde ZIP2.4.1:180 comprobaciones. SQL anteriores, configuración privada y datos conservados. Cero conexiones OLT/RouterOS durante migración, salud y metadatos; cero cambios de configuración en las funciones nuevas.

Pruebas en Apache/PHP8.2/MariaDB10.4 Linux y Chromium con protocolos controlados; no se accedió al Windows, red real ni OLT física del operador. El detalle de intentos y correcciones se documenta en **PRUEBAS.txt**.

SHA-256:

```
634afddd6c3d8e885d9a06fe100c30934e32310fc44f62f453f942b78ff78152
```

PowerShell: `Get-FileHash .\gigared-isp-xampp-v3.0.0-ftth.zip -Algorithm SHA256`.

Lee **FTTH.txt**, **API-REFERENCIA.md**, **MATRIZ-FTTH.md**, **GUIA-ACTUALIZAR.txt** y **PRUEBAS.txt**. El paquete no contiene una instalación previa ni datos, contraseñas o claves reales.

## Versiones anteriores

Se conservan [2.4.1 recuadro/IP](gigared-isp-xampp-v2.4.1.zip), [2.4.0](gigared-isp-xampp-v2.4.0.zip), [2.3.3 IP](nexoisp-xampp-v2.3.3-ip-clientes.zip), [2.3.2 notas](nexoisp-xampp-v2.3.2-notas-clientes.zip), [2.3.1 nombre](nexoisp-xampp-v2.3.1-nombre-mikrotik.zip), [2.3.0 edición PPPoE](nexoisp-xampp-v2.3.0-editar-pppoe.zip), [2.2.2 consulta PPPoE](nexoisp-xampp-v2.2.2-pppoe.zip), [2.2.1 soles](nexoisp-xampp-v2.2.1-soles.zip), [2.2](nexoisp-xampp-v2.2-lectura.zip), [2.1.1](nexoisp-xampp-v2.1.1-lectura.zip), [2.1](nexoisp-xampp-v2.1-lectura.zip), [2](nexoisp-xampp-v2.zip) y [1](nexoisp-xampp.zip). Las versiones1/2 anteriores al modo lectura permitían otras operaciones de configuración.
