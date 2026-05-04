# Inventario de activos

Inventario de los activos de información que componen el sistema de DentaCare bajo análisis. La identificación se realiza siguiendo la tipología de **MAGERIT**.

---

## 1. Tipología de activos (MAGERIT)

MAGERIT clasifica los activos en categorías. Para este proyecto se utilizan las siguientes:

| Código | Tipo | Descripción |
|---|---|---|
| **[D]** | Datos / Información | Información manejada por la organización |
| **[S]** | Servicios | Servicios prestados por el sistema |
| **[SW]** | Software / Aplicaciones | Aplicaciones informáticas |
| **[HW]** | Equipamiento informático | Hardware (servidores, equipos, dispositivos) |
| **[COM]** | Redes de comunicaciones | Infraestructura de red |
| **[Media]** | Soportes de información | Soportes físicos de almacenamiento |
| **[AUX]** | Equipamiento auxiliar | Equipamiento de soporte (UPS, cableado, climatización) |
| **[L]** | Instalaciones | Espacios físicos |
| **[P]** | Personal | Personas que operan o usan el sistema |

---

## 2. Inventario de activos

### 2.1. Datos / Información [D]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| D-01 | Historiales clínicos | Expedientes médicos de pacientes (datos de salud) | Director clínico |
| D-02 | Radiografías digitales | Imágenes radiológicas asociadas a historiales | Director clínico |
| D-03 | Datos de facturación | Facturas, datos bancarios de pacientes y mutuas | Administración |
| D-04 | Datos de empleados | Información laboral, nóminas, datos personales | Gerencia |
| D-05 | Consentimientos informados | Documentos de consentimiento firmados | Director clínico |
| D-06 | Copias de seguridad | Backups de toda la información anterior | Proveedor de TI |
| D-07 | Logs del sistema | Registros de acceso y eventos | Proveedor de TI |

### 2.2. Servicios [S]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| S-01 | Servicio de gestión clínica | Acceso al software para registrar consultas, citas, historiales | Director clínico |
| S-02 | Servicio de citas online | Plataforma web para que pacientes pidan cita | Administración |
| S-03 | Servicio de correo corporativo | Email de empleados y comunicaciones con mutua | Gerencia |
| S-04 | Servicio de facturación a mutua | Envío de facturación electrónica a mutua pública | Administración |

### 2.3. Software / Aplicaciones [SW]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| SW-01 | Klinikare | Software de gestión clínica (instalado en servidor local) | Proveedor de TI |
| SW-02 | Microsoft 365 Business | Suite ofimática y correo en la nube | Proveedor de TI |
| SW-03 | Software de contabilidad | Aplicación de facturación y contabilidad | Administración |
| SW-04 | Gestor de citas web | Aplicación web SaaS para citas de pacientes | Proveedor cloud |
| SW-05 | Windows Server 2019 | Sistema operativo del servidor local | Proveedor de TI |
| SW-06 | Windows 10/11 (puestos) | Sistema operativo de equipos de trabajo | Proveedor de TI |
| SW-07 | Windows Defender | Antivirus instalado en todos los equipos | Proveedor de TI |

### 2.4. Equipamiento informático [HW]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| HW-01 | Servidor local | Servidor físico con Windows Server y BBDD Klinikare | Proveedor de TI |
| HW-02 | Puestos de trabajo | 8 PCs en consultas y recepción | Proveedor de TI |
| HW-03 | Equipos de radiografía digital | 4 unidades de rayos X conectadas a red | Proveedor de TI |
| HW-04 | Firewall hardware | Cortafuegos perimetral | Proveedor de TI |
| HW-05 | Switch gestionable | Switch de red de la LAN | Proveedor de TI |
| HW-06 | NAS de backups | Sistema de almacenamiento para copias de seguridad | Proveedor de TI |
| HW-07 | Router ISP | Router proporcionado por el proveedor de internet | Proveedor de internet |

### 2.5. Redes de comunicaciones [COM]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| COM-01 | Red LAN cableada | Red interna que conecta servidor, puestos y radiografías | Proveedor de TI |
| COM-02 | Red Wi-Fi de invitados | Red Wi-Fi separada para pacientes y visitas | Proveedor de TI |
| COM-03 | Conexión a internet | Línea de fibra del proveedor | Proveedor de internet |

### 2.6. Soportes de información [Media]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| Media-01 | Discos duros del servidor | Almacenamiento del servidor local | Proveedor de TI |
| Media-02 | Discos del NAS | Almacenamiento de copias de seguridad | Proveedor de TI |
| Media-03 | Documentación en papel | Consentimientos y documentos archivados | Administración |

### 2.7. Equipamiento auxiliar [AUX]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| AUX-01 | UPS del servidor | Sistema de alimentación ininterrumpida | Proveedor de TI |
| AUX-02 | Cableado estructurado | Cables de red y eléctricos | Proveedor de TI |
| AUX-03 | Climatización de la sala servidor | Aire acondicionado de la sala técnica | Mantenimiento |

### 2.8. Instalaciones [L]

| ID | Activo | Descripción | Responsable |
|---|---|---|---|
| L-01 | Sala técnica | Sala con cerradura donde está el servidor | Gerencia |
| L-02 | Consultas | Salas donde se atiende a pacientes | Director clínico |
| L-03 | Recepción y administración | Zona de atención al público | Administración |

### 2.9. Personal [P]

| ID | Activo | Descripción |
|---|---|---|
| P-01 | Odontólogos e higienistas | 9 personas con acceso a historiales clínicos |
| P-02 | Personal administrativo | 2 personas con acceso a datos de facturación |
| P-03 | Dirección | 1 persona con acceso total |
| P-04 | Proveedor de TI externo | Acceso de administración a todos los sistemas |

---

## 3. Dependencias entre activos

Los activos no son independientes. La afectación de uno se propaga a los que dependen de él.

| Activo | Depende de |
|---|---|
| Servicio de gestión clínica (S-01) | SW-01 (Klinikare), HW-01 (Servidor), COM-01 (LAN), AUX-01 (UPS) |
| Servicio de citas online (S-02) | SW-04 (gestor citas), COM-03 (Internet) |
| Servicio de correo (S-03) | SW-02 (M365), COM-03 (Internet) |
| Historiales clínicos (D-01) | SW-01 (Klinikare), HW-01 (Servidor), Media-01 (discos) |
| Copias de seguridad (D-06) | HW-06 (NAS), Media-02 (discos NAS) |

> Las dependencias se utilizan en MAGERIT para propagar el valor de los activos: si los historiales clínicos son críticos, los activos de los que dependen heredan parte de esa criticidad.

---

## 4. Resumen del inventario

| Tipo | Cantidad |
|---|---|
| Datos / Información [D] | 7 |
| Servicios [S] | 4 |
| Software [SW] | 7 |
| Hardware [HW] | 7 |
| Comunicaciones [COM] | 3 |
| Soportes [Media] | 3 |
| Equipamiento auxiliar [AUX] | 3 |
| Instalaciones [L] | 3 |
| Personal [P] | 4 |
| **Total** | **41** |

El siguiente paso es la [valoración](./valoracion-activos.md) de cada activo en las cinco dimensiones de seguridad (CIDAT).
