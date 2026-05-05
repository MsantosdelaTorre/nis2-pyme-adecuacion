# Plan de tratamiento del riesgo

Plan de salvaguardas a implantar en DentaCare para mitigar los riesgos identificados en la [matriz de riesgos](../03-analisis-riesgos/matriz-riesgos.md) y cerrar las brechas detectadas en el [GAP analysis](../05-gap-analysis/gap-ens-medio.md).

---

## 1. Estrategias de tratamiento del riesgo

Para cada riesgo identificado, MAGERIT contempla cuatro estrategias posibles:

| Estrategia | Cuándo aplicarla |
|---|---|
| **Mitigar / reducir** | El riesgo es relevante y se puede atacar con salvaguardas proporcionadas |
| **Transferir** | El riesgo es elevado pero asumible si se traslada a un tercero (seguro, proveedor) |
| **Evitar** | El riesgo es inaceptable y se elimina la actividad que lo genera |
| **Aceptar** | El riesgo es bajo o el coste de tratarlo es desproporcionado |

---

## 2. Tipología de salvaguardas

Las salvaguardas se clasifican en tres grupos:

| Tipo | Ejemplos |
|---|---|
| **Administrativas** | Políticas, procedimientos, formación, contratos, auditorías |
| **Técnicas** | Cortafuegos, EDR, MFA, cifrado, segmentación, copias de seguridad |
| **Físicas** | Cerraduras, control de acceso, sistemas anti-incendios, UPS |

---

## 3. Plan de tratamiento por riesgo

Se detallan las salvaguardas para los riesgos de mayor nivel (críticos y altos).

### 3.1. R-01 — Ransomware sobre historiales (Crítico, riesgo 20)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Implantar EDR en servidor y puestos | Técnica | Medio | 1 mes |
| Política de copias de seguridad **3-2-1** (3 copias, 2 medios, 1 offline) | Administrativa | Bajo | 2 semanas |
| Backups offline mensuales en disco extraíble custodiado fuera de sede | Técnica | Bajo | 1 mes |
| Snapshots inmutables en NAS | Técnica | Bajo (configuración) | 2 semanas |
| Segmentación de red (VLANs) entre puestos clínicos y administrativos | Técnica | Medio | 1 mes |
| Formación al personal sobre ransomware y phishing | Administrativa | Bajo | 1 mes |
| Plan de respuesta a incidentes específico para ransomware | Administrativa | Bajo | 1 mes |

**Riesgo residual estimado:** Medio (8-9). El riesgo no se elimina, pero el impacto se contiene gracias a los backups offline y la rapidez de recuperación.

### 3.2. R-02 — Phishing dirigido al personal (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Formación en concienciación: 4 sesiones anuales | Administrativa | Bajo | Continua |
| Simulaciones de phishing trimestrales | Administrativa | Bajo | Trimestral |
| Filtrado avanzado de correo (Microsoft Defender for Office 365) | Técnica | Medio | 2 semanas |
| MFA obligatoria en M365 y todos los servicios cloud | Técnica | Bajo | 1 semana |
| Procedimiento de doble verificación para cambios de cuentas o pagos | Administrativa | Bajo | 2 semanas |
| Canal de denuncia interna de correos sospechosos | Administrativa | Bajo | 2 semanas |

**Riesgo residual estimado:** Medio (6-8).

### 3.3. R-03 — Vulnerabilidades de software (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Inventario de versiones de software con responsable asignado | Administrativa | Bajo | 1 mes |
| Procedimiento de gestión de parches (mensual para SO, trimestral para Klinikare) | Administrativa | Bajo | 1 mes |
| Acuerdo formal con el proveedor de Klinikare para notificación de vulnerabilidades | Administrativa | Bajo | 1 mes |
| Hardening del servidor (CIS Benchmarks Windows Server) | Técnica | Bajo | 1 mes |
| Escaneo periódico de vulnerabilidades con Nessus o similar | Técnica | Medio | Continuo |

**Riesgo residual estimado:** Medio (8).

### 3.4. R-10 — Ransomware extendido al NAS (Crítico, riesgo 20)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| NAS aislado de la red de producción (VLAN dedicada) | Técnica | Bajo | 2 semanas |
| Acceso al NAS solo desde el servidor con credenciales específicas | Técnica | Bajo | 1 semana |
| Snapshots inmutables (retención mínima 30 días) | Técnica | Bajo | 2 semanas |
| Backups offline mensuales (ya recogido en R-01) | Técnica | Bajo | 1 mes |
| Pruebas trimestrales de restauración | Administrativa | Bajo | Trimestral |

**Riesgo residual estimado:** Bajo-Medio (5-7).

### 3.5. R-19 — Suplantación en cloud (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| MFA obligatoria en M365, gestor de citas y software de contabilidad | Técnica | Bajo | 1 semana |
| Política de contraseñas (mínimo 14 caracteres, gestor de contraseñas corporativo) | Administrativa | Bajo | 2 semanas |
| Acceso condicional por geolocalización en M365 | Técnica | Bajo | 1 semana |
| Revisión trimestral de cuentas activas y permisos | Administrativa | Bajo | Trimestral |

**Riesgo residual estimado:** Bajo (3-5).

### 3.6. Riesgos altos (10-15)

Para los riesgos de nivel alto se aplican salvaguardas adicionales o las mismas que cubren los críticos:

| Riesgo | Salvaguardas principales |
|---|---|
| R-04 — Acceso no autorizado a historiales | Matriz de roles, MFA, segmentación, registro de accesos |
| R-05 — Suplantación de identidad | Cubierto por R-19 (MFA + política de contraseñas) |
| R-06 — Destrucción accidental | Cubierto por R-01 (backups 3-2-1) + formación |
| R-07 — Alteración accidental | Permisos restringidos, registro de cambios, formación |
| R-11 — Backups corruptos no detectados | Verificación mensual de restauración + alertas |
| R-26 — Interceptación en Wi-Fi | VLANs separadas, WPA3, certificados |
| R-30 — Errores de monitorización | Implantar SIEM (recomendado: Wazuh) |
| R-31 — Indisponibilidad del proveedor TI | Contrato con segundo proveedor / formación a personal interno |
| R-32 — Deficiencias organizativas | Definir roles formales, designar responsable de seguridad |

---

## 4. Plan de implantación

### 4.1. Fase 1 — Quick wins (mes 1)

Acciones de bajo coste y alto impacto que se pueden implantar de inmediato:

- ✅ MFA obligatoria en M365 y servicios cloud.
- ✅ Política de contraseñas robustas + gestor de contraseñas corporativo.
- ✅ Política de copias de seguridad 3-2-1 documentada.
- ✅ Plan de respuesta a incidentes básico documentado.
- ✅ Inventario formal de activos (este proyecto).
- ✅ Análisis de riesgos formal (este proyecto).
- ✅ Designación de un responsable de seguridad de la información (puede ser una función adicional del director clínico inicialmente).

### 4.2. Fase 2 — Salvaguardas técnicas (mes 2-3)

Acciones que requieren inversión y configuración:

- ✅ Implantar EDR en servidor y puestos.
- ✅ Configurar snapshots inmutables en NAS.
- ✅ Segmentar red (VLANs).
- ✅ Implantar SIEM (Wazuh).
- ✅ Backups offline mensuales con custodia externa.
- ✅ Filtrado avanzado de correo.
- ✅ Hardening del servidor.

### 4.3. Fase 3 — Cultura y procesos (mes 4-6)

Acciones que requieren cambio organizativo:

- ✅ Plan de formación en ciberseguridad para todo el personal.
- ✅ Simulaciones de phishing trimestrales.
- ✅ Procedimientos formales de gestión de cambios y de incidentes.
- ✅ Auditoría interna de cumplimiento.
- ✅ Plan de continuidad documentado y probado.

### 4.4. Fase 4 — Mejora continua (a partir del mes 6)

- ✅ Auditoría externa anual.
- ✅ Revisión y actualización del análisis de riesgos.
- ✅ KPIs de seguridad operativos (apartado 08).

---

## 5. Estimación económica

| Concepto | Inversión inicial | Coste anual recurrente |
|---|---|---|
| EDR (15 licencias) | 1.500 € | 1.500 € |
| Filtrado avanzado de correo (Defender for O365) | — | 1.000 € |
| MFA (incluido en M365 Business) | — | — |
| Switch gestionable con VLANs (si fuera necesario sustituir) | 600 € | — |
| SIEM (Wazuh open source) | 2.000 € (despliegue) | 500 € (mantenimiento) |
| Disco extraíble cifrado para backups offline | 200 € | — |
| Formación inicial al personal | 800 € | 600 € (anual) |
| Consultoría externa (auditoría inicial + seguimiento) | 3.500 € | 1.500 € (anual) |
| **Total aproximado** | **8.600 €** | **5.100 €** |

> Estimación orientativa para una clínica del tamaño de DentaCare. Los precios reales dependen de proveedores y volumen.

---

## 6. Riesgos aceptados y justificación

Algunos riesgos de nivel bajo o medio se aceptan formalmente sin tratamiento adicional:

| Riesgo | Justificación |
|---|---|
| R-13 — Fuego en sala técnica | Probabilidad muy baja. Mitigado parcialmente por backups offline (R-01). Asumible. |
| R-29 — Manipulación de logs | Probabilidad muy baja. Riesgo residual bajo. Trazabilidad ya cubierta por logs centralizados (futuro SIEM). |
| R-22 — Caída del proveedor SaaS de citas | Probabilidad baja. Existe respaldo manual (gestión telefónica de citas). |

La aceptación se documenta y se revisa anualmente.

---

## 7. Riesgos transferidos

Algunos riesgos pueden transferirse mediante contratación de seguros o externalización:

| Riesgo | Mecanismo de transferencia |
|---|---|
| R-01, R-02, R-10 — Ciberataques | Ciberseguro con cobertura de respuesta a incidentes y rescate |
| R-13, R-15 — Daños físicos | Seguro multirriesgo de empresa |

---

## 8. Próximos pasos

1. Aprobación del plan por dirección.
2. Designación del responsable de seguridad.
3. Implantación de la **Fase 1** en el primer mes.
4. Seguimiento mensual del avance del plan.
5. Revisión global a los 6 meses con los KPIs definidos en el [apartado 08](../08-kpis/).

---

## 9. Observaciones

> Las salvaguardas propuestas son las mínimas razonables para una organización del perfil de DentaCare. En cada caso real conviene priorizar por riesgo, capacidad económica y plazos contractuales (por ejemplo, los del convenio con la mutua).

> El plan se considera vivo: se actualiza con cada análisis de riesgos posterior, con cada incidente y con cada cambio relevante en la infraestructura.# Plan de tratamiento del riesgo

Plan de salvaguardas a implantar en DentaCare para mitigar los riesgos identificados en la [matriz de riesgos](../03-analisis-riesgos/matriz-riesgos.md) y cerrar las brechas detectadas en el [GAP analysis](../05-gap-analysis/gap-ens-medio.md).

---

## 1. Estrategias de tratamiento del riesgo

Para cada riesgo identificado, MAGERIT contempla cuatro estrategias posibles:

| Estrategia | Cuándo aplicarla |
|---|---|
| **Mitigar / reducir** | El riesgo es relevante y se puede atacar con salvaguardas proporcionadas |
| **Transferir** | El riesgo es elevado pero asumible si se traslada a un tercero (seguro, proveedor) |
| **Evitar** | El riesgo es inaceptable y se elimina la actividad que lo genera |
| **Aceptar** | El riesgo es bajo o el coste de tratarlo es desproporcionado |

---

## 2. Tipología de salvaguardas

Las salvaguardas se clasifican en tres grupos:

| Tipo | Ejemplos |
|---|---|
| **Administrativas** | Políticas, procedimientos, formación, contratos, auditorías |
| **Técnicas** | Cortafuegos, EDR, MFA, cifrado, segmentación, copias de seguridad |
| **Físicas** | Cerraduras, control de acceso, sistemas anti-incendios, UPS |

---

## 3. Plan de tratamiento por riesgo

Se detallan las salvaguardas para los riesgos de mayor nivel (críticos y altos).

### 3.1. R-01 — Ransomware sobre historiales (Crítico, riesgo 20)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Implantar EDR en servidor y puestos | Técnica | Medio | 1 mes |
| Política de copias de seguridad **3-2-1** (3 copias, 2 medios, 1 offline) | Administrativa | Bajo | 2 semanas |
| Backups offline mensuales en disco extraíble custodiado fuera de sede | Técnica | Bajo | 1 mes |
| Snapshots inmutables en NAS | Técnica | Bajo (configuración) | 2 semanas |
| Segmentación de red (VLANs) entre puestos clínicos y administrativos | Técnica | Medio | 1 mes |
| Formación al personal sobre ransomware y phishing | Administrativa | Bajo | 1 mes |
| Plan de respuesta a incidentes específico para ransomware | Administrativa | Bajo | 1 mes |

**Riesgo residual estimado:** Medio (8-9). El riesgo no se elimina, pero el impacto se contiene gracias a los backups offline y la rapidez de recuperación.

### 3.2. R-02 — Phishing dirigido al personal (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Formación en concienciación: 4 sesiones anuales | Administrativa | Bajo | Continua |
| Simulaciones de phishing trimestrales | Administrativa | Bajo | Trimestral |
| Filtrado avanzado de correo (Microsoft Defender for Office 365) | Técnica | Medio | 2 semanas |
| MFA obligatoria en M365 y todos los servicios cloud | Técnica | Bajo | 1 semana |
| Procedimiento de doble verificación para cambios de cuentas o pagos | Administrativa | Bajo | 2 semanas |
| Canal de denuncia interna de correos sospechosos | Administrativa | Bajo | 2 semanas |

**Riesgo residual estimado:** Medio (6-8).

### 3.3. R-03 — Vulnerabilidades de software (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| Inventario de versiones de software con responsable asignado | Administrativa | Bajo | 1 mes |
| Procedimiento de gestión de parches (mensual para SO, trimestral para Klinikare) | Administrativa | Bajo | 1 mes |
| Acuerdo formal con el proveedor de Klinikare para notificación de vulnerabilidades | Administrativa | Bajo | 1 mes |
| Hardening del servidor (CIS Benchmarks Windows Server) | Técnica | Bajo | 1 mes |
| Escaneo periódico de vulnerabilidades con Nessus o similar | Técnica | Medio | Continuo |

**Riesgo residual estimado:** Medio (8).

### 3.4. R-10 — Ransomware extendido al NAS (Crítico, riesgo 20)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| NAS aislado de la red de producción (VLAN dedicada) | Técnica | Bajo | 2 semanas |
| Acceso al NAS solo desde el servidor con credenciales específicas | Técnica | Bajo | 1 semana |
| Snapshots inmutables (retención mínima 30 días) | Técnica | Bajo | 2 semanas |
| Backups offline mensuales (ya recogido en R-01) | Técnica | Bajo | 1 mes |
| Pruebas trimestrales de restauración | Administrativa | Bajo | Trimestral |

**Riesgo residual estimado:** Bajo-Medio (5-7).

### 3.5. R-19 — Suplantación en cloud (Crítico, riesgo 16)

**Estrategia:** Mitigar.

| Salvaguarda | Tipo | Coste estimado | Plazo |
|---|---|---|---|
| MFA obligatoria en M365, gestor de citas y software de contabilidad | Técnica | Bajo | 1 semana |
| Política de contraseñas (mínimo 14 caracteres, gestor de contraseñas corporativo) | Administrativa | Bajo | 2 semanas |
| Acceso condicional por geolocalización en M365 | Técnica | Bajo | 1 semana |
| Revisión trimestral de cuentas activas y permisos | Administrativa | Bajo | Trimestral |

**Riesgo residual estimado:** Bajo (3-5).

### 3.6. Riesgos altos (10-15)

Para los riesgos de nivel alto se aplican salvaguardas adicionales o las mismas que cubren los críticos:

| Riesgo | Salvaguardas principales |
|---|---|
| R-04 — Acceso no autorizado a historiales | Matriz de roles, MFA, segmentación, registro de accesos |
| R-05 — Suplantación de identidad | Cubierto por R-19 (MFA + política de contraseñas) |
| R-06 — Destrucción accidental | Cubierto por R-01 (backups 3-2-1) + formación |
| R-07 — Alteración accidental | Permisos restringidos, registro de cambios, formación |
| R-11 — Backups corruptos no detectados | Verificación mensual de restauración + alertas |
| R-26 — Interceptación en Wi-Fi | VLANs separadas, WPA3, certificados |
| R-30 — Errores de monitorización | Implantar SIEM (recomendado: Wazuh) |
| R-31 — Indisponibilidad del proveedor TI | Contrato con segundo proveedor / formación a personal interno |
| R-32 — Deficiencias organizativas | Definir roles formales, designar responsable de seguridad |

---

## 4. Plan de implantación

### 4.1. Fase 1 — Quick wins (mes 1)

Acciones de bajo coste y alto impacto que se pueden implantar de inmediato:

- ✅ MFA obligatoria en M365 y servicios cloud.
- ✅ Política de contraseñas robustas + gestor de contraseñas corporativo.
- ✅ Política de copias de seguridad 3-2-1 documentada.
- ✅ Plan de respuesta a incidentes básico documentado.
- ✅ Inventario formal de activos (este proyecto).
- ✅ Análisis de riesgos formal (este proyecto).
- ✅ Designación de un responsable de seguridad de la información (puede ser una función adicional del director clínico inicialmente).

### 4.2. Fase 2 — Salvaguardas técnicas (mes 2-3)

Acciones que requieren inversión y configuración:

- ✅ Implantar EDR en servidor y puestos.
- ✅ Configurar snapshots inmutables en NAS.
- ✅ Segmentar red (VLANs).
- ✅ Implantar SIEM (Wazuh).
- ✅ Backups offline mensuales con custodia externa.
- ✅ Filtrado avanzado de correo.
- ✅ Hardening del servidor.

### 4.3. Fase 3 — Cultura y procesos (mes 4-6)

Acciones que requieren cambio organizativo:

- ✅ Plan de formación en ciberseguridad para todo el personal.
- ✅ Simulaciones de phishing trimestrales.
- ✅ Procedimientos formales de gestión de cambios y de incidentes.
- ✅ Auditoría interna de cumplimiento.
- ✅ Plan de continuidad documentado y probado.

### 4.4. Fase 4 — Mejora continua (a partir del mes 6)

- ✅ Auditoría externa anual.
- ✅ Revisión y actualización del análisis de riesgos.
- ✅ KPIs de seguridad operativos (apartado 08).

---

## 5. Estimación económica

| Concepto | Inversión inicial | Coste anual recurrente |
|---|---|---|
| EDR (15 licencias) | 1.500 € | 1.500 € |
| Filtrado avanzado de correo (Defender for O365) | — | 1.000 € |
| MFA (incluido en M365 Business) | — | — |
| Switch gestionable con VLANs (si fuera necesario sustituir) | 600 € | — |
| SIEM (Wazuh open source) | 2.000 € (despliegue) | 500 € (mantenimiento) |
| Disco extraíble cifrado para backups offline | 200 € | — |
| Formación inicial al personal | 800 € | 600 € (anual) |
| Consultoría externa (auditoría inicial + seguimiento) | 3.500 € | 1.500 € (anual) |
| **Total aproximado** | **8.600 €** | **5.100 €** |

> Estimación orientativa para una clínica del tamaño de DentaCare. Los precios reales dependen de proveedores y volumen.

---

## 6. Riesgos aceptados y justificación

Algunos riesgos de nivel bajo o medio se aceptan formalmente sin tratamiento adicional:

| Riesgo | Justificación |
|---|---|
| R-13 — Fuego en sala técnica | Probabilidad muy baja. Mitigado parcialmente por backups offline (R-01). Asumible. |
| R-29 — Manipulación de logs | Probabilidad muy baja. Riesgo residual bajo. Trazabilidad ya cubierta por logs centralizados (futuro SIEM). |
| R-22 — Caída del proveedor SaaS de citas | Probabilidad baja. Existe respaldo manual (gestión telefónica de citas). |

La aceptación se documenta y se revisa anualmente.

---

## 7. Riesgos transferidos

Algunos riesgos pueden transferirse mediante contratación de seguros o externalización:

| Riesgo | Mecanismo de transferencia |
|---|---|
| R-01, R-02, R-10 — Ciberataques | Ciberseguro con cobertura de respuesta a incidentes y rescate |
| R-13, R-15 — Daños físicos | Seguro multirriesgo de empresa |

---

## 8. Próximos pasos

1. Aprobación del plan por dirección.
2. Designación del responsable de seguridad.
3. Implantación de la **Fase 1** en el primer mes.
4. Seguimiento mensual del avance del plan.
5. Revisión global a los 6 meses con los KPIs definidos en el [apartado 08](../08-kpis/).

---

## 9. Observaciones

> Las salvaguardas propuestas son las mínimas razonables para una organización del perfil de DentaCare. En cada caso real conviene priorizar por riesgo, capacidad económica y plazos contractuales (por ejemplo, los del convenio con la mutua).

> El plan se considera vivo: se actualiza con cada análisis de riesgos posterior, con cada incidente y con cada cambio relevante en la infraestructura.
