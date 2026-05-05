# Política de control de accesos

| Campo | Valor |
|---|---|
| Documento | Política de control de accesos |
| Versión | 1.0 |
| Fecha de aprobación | 2026 |
| Aprobado por | Dirección de DentaCare |
| Revisión | Anual |

---

## 1. Objeto

Establecer las reglas que regulan el acceso a los sistemas, aplicaciones, datos e instalaciones de DentaCare, garantizando que solo las personas autorizadas tengan acceso a los recursos estrictamente necesarios para sus funciones.

---

## 2. Alcance

Esta política aplica a:

- Todo el personal de DentaCare (empleados y colaboradores).
- Proveedores externos con acceso a sistemas o instalaciones.
- Visitas a las instalaciones que requieran acceso a zonas restringidas.
- Todos los sistemas, aplicaciones, dispositivos y espacios físicos.

---

## 3. Responsabilidades

| Rol | Responsabilidad |
|---|---|
| Dirección | Aprobar la política y autorizar accesos privilegiados. |
| Responsable de seguridad | Mantener la matriz de accesos y revisar accesos periódicamente. |
| Proveedor de TI | Implementar técnicamente los controles. |
| Responsables de área | Solicitar accesos para su personal y notificar bajas o cambios. |
| Personal | Cumplir con las normas de uso y custodiar sus credenciales. |

---

## 4. Principios rectores

### 4.1. Mínimo privilegio

Cada usuario tiene únicamente los permisos **estrictamente necesarios** para desempeñar sus funciones. No se conceden accesos por defecto ni por "si acaso".

### 4.2. Necesidad de conocer

El acceso a información sensible se limita a quienes la necesitan para su trabajo. Un odontólogo accede a los historiales de sus pacientes, no a los del resto de la clínica.

### 4.3. Segregación de funciones

Las tareas críticas requieren la intervención de **al menos dos personas** para evitar abusos. Por ejemplo, una persona configura los pagos a proveedores y otra los autoriza.

### 4.4. Trazabilidad

Todos los accesos a sistemas e información sensible quedan **registrados y son atribuibles** a una persona concreta.

---

## 5. Identificación de usuarios

- Cada persona dispone de una **cuenta nominal e individual**. Está prohibido el uso de cuentas compartidas o genéricas.
- El identificador sigue el formato `nombre.apellido` o similar definido por el proveedor de TI.
- Cada cuenta queda asociada a una **persona física responsable**.

---

## 6. Roles y matriz de accesos

DentaCare define los siguientes roles principales:

| Rol | Descripción | Accesos típicos |
|---|---|---|
| **Dirección** | Gerencia y dirección clínica | Acceso total a sistemas administrativos, lectura en clínicos |
| **Odontólogo** | Profesional sanitario | Lectura/escritura en historiales de sus pacientes |
| **Higienista dental** | Personal sanitario auxiliar | Lectura en historiales, anotaciones limitadas |
| **Auxiliar de clínica** | Personal de apoyo | Lectura limitada en historiales del día |
| **Recepción / Administración** | Gestión de citas y facturación | Acceso al gestor de citas y al software de contabilidad |
| **Proveedor de TI** | Soporte técnico externo | Acceso administrativo limitado y supervisado |

La matriz detallada de accesos por rol y por sistema se mantiene en un documento aparte gestionado por el responsable de seguridad.

---

## 7. Gestión del ciclo de vida de los accesos

### 7.1. Alta

1. El responsable de área solicita el alta indicando rol y necesidad.
2. La dirección o el responsable de seguridad aprueba la solicitud.
3. El proveedor de TI crea la cuenta con los permisos del rol asignado.
4. Las credenciales se entregan conforme a la [política de contraseñas](./politica-contrasenas.md).

### 7.2. Modificación

- Los cambios de rol o función requieren nueva solicitud y aprobación.
- Al cambiar de rol, se **eliminan los permisos antiguos** y se asignan los nuevos. No se acumulan.

### 7.3. Baja

- La baja de un usuario se notifica **antes** del último día de trabajo.
- El proveedor de TI inactiva la cuenta el último día.
- Las cuentas se conservan inactivas durante **90 días** para fines de trazabilidad y luego se eliminan.
- Se revocan accesos en M365, Klinikare, gestor de citas y todos los servicios cloud.

### 7.4. Revisión periódica

- El responsable de seguridad revisa **trimestralmente** las cuentas activas y sus permisos.
- Cualquier cuenta sin uso durante más de 60 días se inactiva.
- Se revoca cualquier permiso que no esté justificado.

---

## 8. Accesos privilegiados

Los accesos con privilegios elevados (administrador del servidor, configuración del firewall, gestión del NAS, administrador de M365) cumplen requisitos adicionales:

- **Autorización expresa** de la dirección.
- **MFA obligatoria** sin excepciones.
- **Cuentas separadas** del usuario diario (un mismo administrador tiene una cuenta normal y otra privilegiada).
- **Uso justificado y registrado:** cada acceso queda auditado y se revisa mensualmente.
- **Sesiones limitadas:** la cuenta privilegiada no se usa para tareas no administrativas (correo, navegación).

---

## 9. Acceso remoto

### 9.1. Personal interno

- El acceso remoto al sistema interno desde fuera de la sede solo está permitido a través de **VPN corporativa con MFA**.
- No se permiten conexiones directas a Klinikare ni al servidor desde fuera.

### 9.2. Proveedor de TI

- El proveedor de TI accede a través de VPN o herramienta de soporte remoto controlada (TeamViewer, AnyDesk Pro o equivalente con auditoría).
- Cada sesión queda registrada (qué, cuándo, durante cuánto tiempo).
- El acceso se autoriza puntualmente para cada intervención salvo casos de mantenimiento programado.

### 9.3. Acceso desde dispositivos personales

- No está permitido acceder a sistemas internos desde dispositivos personales no gestionados por el proveedor de TI.
- El correo corporativo en el móvil personal está permitido si:
  - Se accede mediante la app oficial de Microsoft 365.
  - El dispositivo tiene PIN o biometría activada.
  - El dispositivo está actualizado.

---

## 10. Acceso físico

### 10.1. Zonas

DentaCare define tres tipos de zonas:

| Zona | Quién accede |
|---|---|
| **Pública** (recepción, sala de espera) | Pacientes, visitas, personal |
| **Restringida** (consultas, despachos) | Personal autorizado, pacientes acompañados |
| **Crítica** (sala técnica, archivo de historiales) | Solo personal autorizado expresamente |

### 10.2. Sala técnica

- Cerradura permanente.
- Acceso registrado (libro físico o sistema electrónico).
- Acceso restringido al proveedor de TI, responsable de seguridad y dirección.
- Cualquier visita externa (mantenimiento, etc.) debe ser acompañada.

### 10.3. Visitas

- Las visitas se registran en recepción (nombre, motivo, hora de entrada y salida).
- Las visitas a zonas restringidas o críticas siempre van acompañadas.

---

## 11. Autenticación

- Todos los accesos a sistemas requieren autenticación.
- La autenticación cumple con la [política de contraseñas](./politica-contrasenas.md).
- **MFA obligatoria** para los servicios definidos en dicha política.

---

## 12. Bloqueo de sesiones

- Los puestos de trabajo se bloquean automáticamente tras **10 minutos de inactividad**.
- El bloqueo manual con `Win + L` es obligatorio al ausentarse del puesto.
- Tras **5 intentos fallidos** consecutivos, la cuenta se bloquea durante 15 minutos. Bloqueos repetidos se notifican al responsable de seguridad.

---

## 13. Registro de accesos

Se registran y conservan los siguientes eventos:

- Inicio y cierre de sesión en sistemas críticos.
- Accesos a historiales clínicos (qué usuario, qué paciente, cuándo).
- Accesos administrativos al servidor o a la consola de M365.
- Conexiones VPN.
- Accesos físicos a la sala técnica.

Los registros se conservan **al menos 12 meses** y están protegidos frente a manipulación.

---

## 14. Incumplimiento

El incumplimiento de esta política puede dar lugar a:

- Aviso formal por parte de la dirección.
- Medidas disciplinarias internas.
- Revocación inmediata de los accesos.
- En caso de incidente derivado, posibles consecuencias legales.

---

## 15. Excepciones

Cualquier excepción debe ser:

- Solicitada por escrito al responsable de seguridad.
- Justificada técnica u operativamente.
- Aprobada por la dirección.
- Documentada y revisada al menos anualmente.

---

## 16. Revisión y actualización

Esta política se revisa **anualmente** o tras cualquier incidente relacionado con accesos no autorizados.

---

## Referencias

- **RD 311/2022 (ENS)** — Anexo II, op.acc.* (medidas de control de acceso).
- **ISO/IEC 27002:2022** — Controles 5.15 a 5.18 (control de acceso).
- **CCN-STIC 821** — Apéndice IV — Política de control de accesos.
