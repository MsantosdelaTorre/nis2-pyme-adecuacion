# Política de respuesta a incidentes

| Campo | Valor |
|---|---|
| Documento | Política de respuesta a incidentes de seguridad |
| Versión | 1.0 |
| Fecha de aprobación | 2026 |
| Aprobado por | Dirección de DentaCare |
| Revisión | Anual o tras cada incidente significativo |

---

## 1. Objeto

Establecer el procedimiento que DentaCare aplica ante incidentes de seguridad de la información, garantizando una respuesta rápida, ordenada y efectiva, y cumpliendo con las obligaciones legales de notificación.

---

## 2. Alcance

Esta política aplica a:

- Cualquier incidente que afecte a la confidencialidad, integridad, disponibilidad, autenticidad o trazabilidad de la información de DentaCare.
- Todos los sistemas, aplicaciones, datos e instalaciones.
- Todo el personal de DentaCare y proveedores externos relacionados.

---

## 3. Responsabilidades

| Rol | Responsabilidad |
|---|---|
| Dirección | Aprobar la política, autorizar decisiones críticas durante un incidente, asumir comunicación con autoridades. |
| Responsable de seguridad | Coordinar la respuesta, decidir clasificación del incidente, redactar el informe final. |
| Proveedor de TI | Ejecutar acciones técnicas de contención, erradicación y recuperación. |
| Personal | Detectar y reportar inmediatamente cualquier sospecha de incidente. |
| Asesor legal externo | Apoyar en la valoración legal y en la notificación a autoridades. |

---

## 4. Definiciones

| Término | Definición |
|---|---|
| **Evento de seguridad** | Suceso observable en un sistema que puede tener implicaciones de seguridad |
| **Incidente de seguridad** | Evento o conjunto de eventos que comprometen la seguridad de la información |
| **Incidente significativo** | Incidente con impacto operativo, económico, reputacional o legal relevante |
| **Brecha de seguridad** | Incidente que afecta a datos personales (RGPD, Art. 33) |

---

## 5. Clasificación de incidentes

| Nivel | Criterios | Ejemplos |
|---|---|---|
| **Crítico** | Afecta a servicios esenciales, hay datos personales comprometidos o impacto > 24 h | Ransomware, exfiltración de historiales, caída total del servidor |
| **Alto** | Impacto operativo significativo o riesgo elevado de pérdida de datos | Acceso no autorizado detectado, malware en varios equipos |
| **Medio** | Impacto limitado, controlable | Phishing recibido sin clic, intento de fuerza bruta sin éxito |
| **Bajo** | Sin impacto real, anomalía menor | Alerta del antivirus aislada, error puntual de autenticación |

---

## 6. Ciclo de vida de la respuesta

DentaCare adopta el modelo de seis fases recomendado por el ENS y MAGERIT:
```
[1] Preparación
      │
      ▼
[2] Detección e identificación
      │
      ▼
[3] Contención
      │
      ▼
[4] Erradicación
      │
      ▼
[5] Recuperación
      │
      ▼
[6] Lecciones aprendidas
```
### 6.1. Fase 1 — Preparación

Acciones permanentes (antes de cualquier incidente):

- Mantenimiento de inventario, análisis de riesgos y políticas de seguridad.
- Formación periódica al personal.
- Realización de copias de seguridad conforme a la política correspondiente.
- Disponibilidad de herramientas y contactos clave (proveedores, INCIBE-CERT, asesoría legal).
- Realización de simulacros al menos una vez al año.

### 6.2. Fase 2 — Detección e identificación

**Canales de detección:**

- Reporte por parte del personal (canal interno).
- Alertas del antivirus, EDR o SIEM (cuando estén implantados).
- Notificaciones de proveedores o autoridades.
- Detección por terceros (clientes, mutua, pacientes).

**Procedimiento ante una sospecha:**

1. Cualquier persona que detecte un evento sospechoso lo comunica **inmediatamente** al responsable de seguridad.
2. Canal de reporte: teléfono o correo a una dirección dedicada (ejemplo: `incidentes@dentacare.local`).
3. El responsable de seguridad realiza una primera evaluación y clasifica el incidente.
4. Se abre un registro del incidente con identificador único.

### 6.3. Fase 3 — Contención

Objetivo: **detener la propagación del incidente** sin destruir evidencias.

Acciones típicas:

- Aislar el equipo afectado de la red (desconectar cable, deshabilitar Wi-Fi).
- Bloquear cuentas comprometidas.
- Cortar comunicaciones sospechosas en el firewall.
- **Conservar evidencias:** no apagar equipos comprometidos sin orden expresa.

### 6.4. Fase 4 — Erradicación

Objetivo: **eliminar la causa raíz** del incidente.

Acciones típicas:

- Eliminar malware identificado.
- Cerrar la vulnerabilidad explotada (parche, cambio de configuración).
- Eliminar cuentas no autorizadas creadas por el atacante.
- Cambiar todas las contraseñas potencialmente comprometidas.

### 6.5. Fase 5 — Recuperación

Objetivo: **restaurar el servicio** de forma segura.

Acciones típicas:

- Restaurar sistemas desde copias de seguridad verificadas.
- Validar la integridad de los datos restaurados.
- Devolver los sistemas a producción de forma controlada.
- Monitorizar de cerca durante los días posteriores para detectar reincidencias.

### 6.6. Fase 6 — Lecciones aprendidas

Objetivo: **mejorar a partir de lo ocurrido**.

Acciones obligatorias tras cada incidente significativo:

- Reunión de revisión post-incidente en un plazo máximo de **15 días**.
- Redacción de informe final con: cronología, causa raíz, acciones realizadas, impacto y recomendaciones.
- Actualización de procedimientos, formación o medidas técnicas según lo aprendido.
- Comunicación interna de las medidas adoptadas.

---

## 7. Notificación a autoridades

DentaCare cumple con las obligaciones legales de notificación.

### 7.1. NIS2 — Notificación al CSIRT competente (INCIBE-CERT)

Para incidentes con **impacto significativo**:

| Hito | Plazo | Contenido |
|---|---|---|
| Aviso temprano | **24 horas** desde la detección | Sospecha de incidente, posible carácter malicioso, posible impacto transfronterizo |
| Notificación oficial | **72 horas** desde la detección | Evaluación inicial de gravedad e indicadores de compromiso |
| Informe intermedio | A petición de la autoridad | Estado del incidente |
| Informe final | **1 mes** desde la notificación | Descripción detallada, causa raíz, medidas adoptadas |

Canal: portal del INCIBE-CERT y correo `incidencias@incibe-cert.es`.

### 7.2. RGPD — Notificación a la AEPD

Para incidentes que afecten a datos personales (brechas):

- Notificación a la AEPD en **72 horas** desde la detección, salvo que sea improbable que suponga un riesgo para los derechos de los afectados.
- Comunicación a los afectados sin dilación cuando exista alto riesgo para sus derechos.
- Registro interno de la brecha (obligatorio aunque no se notifique).

Canal: sede electrónica de la AEPD.

### 7.3. Otras notificaciones

- **Mutua pública:** notificación según los términos del convenio si afecta a la prestación.
- **Asesoría legal:** consulta inmediata en cualquier incidente significativo.
- **Compañía aseguradora** (si existe ciberseguro): notificación en el plazo establecido por la póliza.

---

## 8. Comunicación durante el incidente

### 8.1. Comunicación interna

- El responsable de seguridad coordina la información dentro de la organización.
- Se evita la difusión de información parcial o no contrastada.
- La dirección decide qué se comunica al personal y cuándo.

### 8.2. Comunicación externa

- La comunicación con clientes, pacientes, prensa o redes sociales corresponde **exclusivamente a la dirección**.
- Ningún empleado debe pronunciarse públicamente sobre el incidente sin autorización.
- En caso de comunicación pública, se elabora un mensaje breve, factual y sin información sensible.

---

## 9. Casos especiales

### 9.1. Ransomware

- **No se paga el rescate** salvo decisión expresa de la dirección con asesoría legal.
- Se prioriza la recuperación desde copias de seguridad offline.
- Se reportan los IoCs al INCIBE-CERT para apoyar a otras organizaciones.

### 9.2. Exfiltración de datos personales

- Notificación obligatoria a la AEPD en 72 h.
- Comunicación a los pacientes afectados si el riesgo es alto.
- Análisis de qué datos se han filtrado, en qué volumen y por qué medios.

### 9.3. Indisponibilidad prolongada

- Se activa el plan de continuidad de negocio.
- Se reprograman pacientes y se comunica el incidente con un mensaje preparado.

---

## 10. Conservación de evidencias

- Durante la respuesta, se conservan **todas las evidencias** posibles (logs, capturas, imágenes de disco si procede).
- Las evidencias se almacenan de forma íntegra y trazable.
- Si se sospecha actividad delictiva, se conservan en cadena de custodia para posible denuncia.

---

## 11. Formación y simulacros

- Todo el personal recibe formación básica sobre cómo detectar y reportar incidentes en su incorporación y al menos **una vez al año**.
- Se realizan simulacros de incidente al menos **una vez al año** (ejemplo: simulación de ransomware con prueba de restauración).
- El responsable de seguridad documenta los resultados y las mejoras aplicadas.

---

## 12. Documentación de cada incidente

Para cada incidente, independientemente de su nivel, se mantiene un registro con:

- Identificador único.
- Fecha y hora de detección.
- Origen del reporte.
- Clasificación (Bajo / Medio / Alto / Crítico).
- Activos afectados.
- Acciones realizadas.
- Cronología completa.
- Causa raíz.
- Lecciones aprendidas y mejoras aplicadas.
- Si hubo notificación a autoridades.

Este registro es la base de los KPIs definidos en el [apartado 08](../08-kpis/).

---

## 13. Contactos clave

| Entidad | Canal | Cuándo |
|---|---|---|
| INCIBE-CERT | `incidencias@incibe-cert.es` / 017 | Incidentes con impacto significativo (NIS2) |
| AEPD | Sede electrónica AEPD | Brechas de datos personales (RGPD) |
| Mutua pública | Según convenio | Incidentes que afecten al servicio prestado |
| Asesoría legal externa | (a definir) | Apoyo en cualquier incidente significativo |
| Compañía de ciberseguro | (a definir si se contrata) | Activación de cobertura |
| Proveedor de TI | (a definir) | Soporte técnico inmediato |

---

## 14. Revisión y actualización

Esta política se revisa:

- Al menos **anualmente**.
- Tras cada incidente significativo, como parte de las lecciones aprendidas.
- Tras cualquier cambio normativo relevante (NIS2, RGPD, ENS).

---

## Referencias

- **Directiva (UE) 2022/2555** (NIS2) — Artículos 23 y 24, notificación de incidentes.
- **RGPD** — Artículos 33 y 34, notificación de brechas.
- **RD 311/2022 (ENS)** — Anexo II, op.exp.7 (gestión de incidentes).
- **CCN-STIC 817** — Esquema Nacional de Seguridad — Gestión de ciberincidentes.
- **NIST SP 800-61 Rev. 2** — Computer Security Incident Handling Guide.
- **ISO/IEC 27035** — Information security incident management.
