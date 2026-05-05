# Política de copias de seguridad

| Campo | Valor |
|---|---|
| Documento | Política de copias de seguridad |
| Versión | 1.0 |
| Fecha de aprobación | 2026 |
| Aprobado por | Dirección de DentaCare |
| Revisión | Anual |

---

## 1. Objeto

Establecer las reglas para la realización, custodia, verificación y restauración de las copias de seguridad de los sistemas e información de DentaCare, garantizando la disponibilidad e integridad de la información ante incidentes.

---

## 2. Alcance

Esta política aplica a:

- Toda la información clasificada como crítica o sensible para la operación de DentaCare.
- Todos los sistemas que generan o almacenan dicha información.
- El personal responsable de su ejecución y verificación (proveedor de TI).

---

## 3. Responsabilidades

| Rol | Responsabilidad |
|---|---|
| Dirección | Aprobar la política y proveer los recursos necesarios. |
| Responsable de seguridad | Supervisar el cumplimiento y revisar los informes de verificación. |
| Proveedor de TI | Configurar, ejecutar y verificar las copias de seguridad. |
| Personal | Identificar la información crítica que deba ser respaldada. |

---

## 4. Estrategia 3-2-1

DentaCare adopta la regla **3-2-1** como base de su política de copias:

- **3 copias** de la información (la original y dos copias de seguridad).
- **2 medios distintos** de almacenamiento (disco local + disco en NAS).
- **1 copia offline** custodiada fuera de la sede principal.

---

## 5. Información a respaldar

| Activo | Tipo de copia | Frecuencia | Retención |
|---|---|---|---|
| Base de datos de Klinikare (D-01, D-02) | Completa | Diaria | 90 días |
| Base de datos de Klinikare | Snapshot incremental | Cada 6 horas | 30 días |
| Configuraciones del servidor (HW-01, SW-05) | Completa | Semanal | 6 meses |
| Configuración del firewall (HW-04) | Completa | Tras cada cambio | 1 año |
| Documentos administrativos (D-03, D-04) | Completa | Diaria | 90 días |
| Logs del sistema (D-07) | Completa | Diaria | 12 meses |
| Buzones de correo M365 | Completa | Continua (proveedor) | 30 días (estándar M365) |
| Imagen completa del servidor | Completa | Mensual | 12 meses |

---

## 6. Tipos de copia

| Tipo | Descripción | Cuándo se usa |
|---|---|---|
| **Completa** | Copia de todos los datos | Backup principal periódico |
| **Incremental** | Solo los datos modificados desde la última copia | Snapshots intermedios |
| **Diferencial** | Cambios desde la última copia completa | No se utiliza actualmente |
| **Snapshot** | Imagen consistente en un punto del tiempo | Recuperación rápida |

---

## 7. Ubicación de las copias

### 7.1. Copia primaria — NAS local

- Ubicación: NAS dedicado en la sala técnica de DentaCare.
- Acceso: solo desde el servidor con credenciales específicas.
- Aislamiento: el NAS está en una **VLAN aparte** sin acceso desde puestos de usuario.
- Snapshots **inmutables** activados (no se pueden borrar ni cifrar por ransomware durante el periodo de retención).

### 7.2. Copia secundaria — Disco extraíble offline

- Frecuencia: **mensual**.
- Soporte: disco duro externo cifrado (BitLocker o VeraCrypt).
- Custodia: en caja de seguridad fuera de la sede principal (domicilio del responsable de seguridad o caja en sucursal bancaria).
- Rotación: dos discos alternados (uno fuera, uno en sede para el siguiente ciclo).

### 7.3. Copia en cloud (opcional)

Si se contratase, almacenamiento cifrado en proveedor cloud español o europeo:

- Cifrado de extremo a extremo.
- Cumplimiento RGPD.
- Acceso con MFA.

---

## 8. Cifrado

- Todas las copias de seguridad se realizan **cifradas en reposo**.
- Se utiliza cifrado AES-256 como mínimo.
- Las claves de cifrado se custodian de forma separada del soporte (ver política de gestión de claves, cuando se redacte).

---

## 9. Verificación de las copias

> Una copia que no se verifica no existe.

### 9.1. Verificación automática

- Diaria: comprobación automática de integridad (hashes, logs del sistema de backup) tras cada copia.
- Cualquier fallo genera alerta al responsable de TI.

### 9.2. Verificación manual

- **Mensual:** restauración de un fichero al azar para comprobar que el proceso funciona.
- **Trimestral:** restauración completa de Klinikare en un entorno de prueba.
- **Anual:** simulacro completo de recuperación ante desastre.

Los resultados se documentan en un informe que el responsable de seguridad revisa.

---

## 10. Restauración

### 10.1. Procedimiento

1. Identificación del incidente y declaración de necesidad de restaurar.
2. Aprobación del responsable de seguridad o de la dirección.
3. Selección del punto de restauración adecuado (cumpliendo el RPO definido en el [BIA](../04-bia/bia-dentacare.md)).
4. Ejecución de la restauración por el proveedor de TI.
5. Verificación de la integridad de los datos restaurados.
6. Reanudación del servicio.
7. Documentación del incidente y de la restauración.

### 10.2. Tiempos de recuperación

Los tiempos máximos de restauración están alineados con los **RTO** definidos en el BIA:

| Sistema | RTO | RPO |
|---|---|---|
| Klinikare / atención clínica | 4 h | 24 h |
| Diagnóstico por imagen | 4 h | 24 h |
| Citas online | 24 h | 1 h |
| Facturación | 48 h | 24 h |

---

## 11. Custodia y acceso

- Solo el proveedor de TI y el responsable de seguridad pueden acceder a los soportes de copia.
- El acceso al disco offline requiere doble persona (responsable de seguridad + un miembro de dirección).
- Los soportes retirados de servicio se destruyen mediante borrado seguro (DoD 5220.22-M) o destrucción física documentada.

---

## 12. Retención de datos personales

Las copias contienen datos personales (incluidos datos de salud). Se respetan las siguientes condiciones:

- Las copias se conservan durante el tiempo definido en este documento, alineado con la base legal del tratamiento.
- Si un paciente ejerce el derecho de supresión bajo RGPD, los datos se eliminan también de las copias en su próximo ciclo de rotación.
- Las copias antiguas se destruyen de forma segura una vez expirada su retención.

---

## 13. Incidencias y documentación

- Todas las ejecuciones, fallos y restauraciones quedan registrados.
- El responsable de seguridad recibe un informe **mensual** con el estado de las copias.
- Cualquier fallo en una copia se considera un **incidente de seguridad** y se gestiona conforme al procedimiento de respuesta a incidentes.

---

## 14. Revisión y actualización

Esta política se revisa al menos **una vez al año** o tras cualquier incidente que afecte a la integridad o disponibilidad de las copias.

---

## Referencias

- **CCN-STIC 814** — Recomendaciones para la realización de copias de seguridad.
- **NIST SP 800-34** — Contingency Planning Guide.
- **ISO/IEC 27002:2022** — Control 8.13 — Backup de información.
