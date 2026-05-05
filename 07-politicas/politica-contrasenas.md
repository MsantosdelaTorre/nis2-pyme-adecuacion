# Política de contraseñas

| Campo | Valor |
|---|---|
| Documento | Política de contraseñas |
| Versión | 1.0 |
| Fecha de aprobación | 2026 |
| Aprobado por | Dirección de DentaCare |
| Revisión | Anual |

---

## 1. Objeto

Establecer las reglas de creación, uso y custodia de las contraseñas utilizadas en los sistemas de información de DentaCare, con el fin de proteger la confidencialidad e integridad de la información tratada.

---

## 2. Alcance

Esta política aplica a:

- Todo el personal interno de DentaCare (empleados y colaboradores).
- Proveedores externos con acceso a los sistemas de DentaCare (especialmente proveedor de TI).
- Todas las cuentas de acceso a sistemas, aplicaciones y servicios cloud.

---

## 3. Responsabilidades

| Rol | Responsabilidad |
|---|---|
| Dirección | Aprobar y revisar la política. |
| Responsable de seguridad | Velar por su cumplimiento. |
| Proveedor de TI | Configurar técnicamente los sistemas para forzar el cumplimiento. |
| Personal | Cumplir con las reglas de uso y custodia. |

---

## 4. Requisitos de las contraseñas

### 4.1. Longitud y composición

- **Longitud mínima:** 14 caracteres.
- **Debe contener al menos:**
  - Una letra mayúscula.
  - Una letra minúscula.
  - Un número.
  - Un símbolo (`!`, `@`, `#`, `$`, etc.).
- No se permite el uso de:
  - Información personal identificable (nombre, fecha de nacimiento, DNI).
  - Palabras de diccionario sin modificar.
  - Secuencias predecibles (`12345`, `qwerty`, `abcde`).
  - Las **20 contraseñas más comunes** según listas públicas (`password`, `dentacare`, etc.).

### 4.2. Caducidad

- Las contraseñas **no caducarán** salvo en caso de sospecha de compromiso.
- Esta decisión sigue las recomendaciones de NIST y INCIBE: la caducidad obligatoria sin motivo lleva a contraseñas más débiles.
- Se exigirá cambio inmediato si:
  - Se sospecha que la contraseña ha sido comprometida.
  - Un usuario abandona la organización (cuenta inactivada).
  - Una herramienta de detección la marca como expuesta.

### 4.3. Reutilización

- No se permite reutilizar las **5 últimas contraseñas** de la misma cuenta.
- Está prohibido usar la misma contraseña en cuentas personales y profesionales.

---

## 5. Custodia y uso

### 5.1. Gestor de contraseñas

DentaCare proporcionará un **gestor de contraseñas corporativo** (ejemplo: Bitwarden, KeePass) para todo el personal. Su uso es **obligatorio** para almacenar las contraseñas profesionales.

### 5.2. Prohibiciones expresas

- No se podrán anotar contraseñas en papel, archivos de texto, post-it ni notas en el navegador.
- No se podrán compartir contraseñas entre usuarios bajo ningún concepto. Cada usuario debe tener su propia cuenta nominal.
- No se podrán enviar contraseñas por correo electrónico, mensajería o cualquier otro canal no cifrado.

### 5.3. Envío seguro de credenciales

Cuando sea estrictamente necesario compartir credenciales (por ejemplo, alta de un nuevo usuario):

- Se utilizará el gestor de contraseñas corporativo.
- O se entregará verbalmente y de forma presencial.
- Nunca por correo, SMS o mensajería sin cifrado de extremo a extremo.

---

## 6. Doble factor de autenticación (MFA)

El uso de MFA es **obligatorio** en:

- Microsoft 365 (correo y herramientas).
- Acceso al software de gestión clínica (Klinikare).
- Acceso al gestor de citas web.
- Acceso al software de contabilidad.
- Cualquier acceso remoto al servidor o sistemas internos.

Métodos admitidos, en orden de preferencia:

1. Aplicación autenticadora (Microsoft Authenticator, Google Authenticator).
2. Token físico (YubiKey).
3. SMS solo como último recurso (vulnerable a SIM swapping).

---

## 7. Cuentas privilegiadas

Las cuentas con privilegios de administración (servidor, firewall, backups) cumplirán requisitos adicionales:

- **Longitud mínima:** 18 caracteres.
- **MFA obligatoria** en todos los casos.
- **Uso exclusivo** para tareas administrativas (no se navegará por internet ni se leerá correo con cuentas privilegiadas).
- **Auditoría de uso:** todos los accesos quedan registrados y se revisan trimestralmente.

---

## 8. Gestión del ciclo de vida de las cuentas

### 8.1. Alta de usuario

- La solicitud la realiza la Dirección o quien delegue.
- El proveedor de TI crea la cuenta con los permisos mínimos necesarios.
- Se entregan las credenciales mediante el gestor de contraseñas.
- El usuario debe cambiar la contraseña en el primer acceso.

### 8.2. Baja de usuario

- En caso de salida de la organización, las cuentas se **inactivan inmediatamente** (no se eliminan hasta pasados 90 días para conservar trazabilidad).
- Se redirige el correo a la dirección del responsable durante 30 días.
- Se revocan accesos a todos los servicios cloud.

### 8.3. Cambios de rol

- Si un usuario cambia de función, se revisan sus permisos antes de asignar los nuevos.
- No se acumulan permisos.

---

## 9. Incumplimiento

El incumplimiento de esta política puede dar lugar a:

- Aviso formal por parte de la dirección.
- Medidas disciplinarias internas según la normativa laboral.
- En caso de incidente derivado del incumplimiento: posible responsabilidad civil o penal.

---

## 10. Excepciones

Cualquier excepción a esta política debe ser:

- Solicitada por escrito al responsable de seguridad.
- Justificada técnica u operativamente.
- Aprobada por la dirección.
- Revisada al menos anualmente.

---

## 11. Revisión y actualización

Esta política se revisa **al menos una vez al año** o cuando se produzcan cambios significativos en la normativa, en la infraestructura o como consecuencia de un incidente de seguridad.

---

## Referencias

- **NIST SP 800-63B** — Digital Identity Guidelines.
- **INCIBE** — Guía sobre el uso de contraseñas robustas.
- **CCN-STIC 821** — Apéndice V — Política de contraseñas.
