# Matriz de riesgos

Cálculo del riesgo para los pares **activo × amenaza** más relevantes de DentaCare.

---

## 1. Metodología

El riesgo se calcula con la fórmula simplificada:

> **Riesgo = Impacto × Probabilidad**

### 1.1. Escala de impacto (1-5)

| Valor | Nivel | Significado |
|---|---|---|
| 1 | Muy bajo | Daño despreciable |
| 2 | Bajo | Daño asumible |
| 3 | Medio | Daño notable |
| 4 | Alto | Daño grave |
| 5 | Muy alto | Daño catastrófico |

### 1.2. Escala de probabilidad (1-5)

| Valor | Nivel | Significado | Frecuencia orientativa |
|---|---|---|---|
| 1 | Muy baja | Improbable | Menos de una vez cada 5 años |
| 2 | Baja | Poco probable | Cada 2-5 años |
| 3 | Media | Posible | Una vez al año |
| 4 | Alta | Probable | Varias veces al año |
| 5 | Muy alta | Casi seguro | Mensual o más |

### 1.3. Niveles de riesgo (Impacto × Probabilidad)

| Rango | Nivel | Color |
|---|---|---|
| 1-4 | Bajo | 🟢 |
| 5-9 | Medio | 🟡 |
| 10-15 | Alto | 🟠 |
| 16-25 | Muy alto / Crítico | 🔴 |

---

## 2. Matriz de riesgos (probabilidad × impacto)

|  | **Impacto 1** | **Impacto 2** | **Impacto 3** | **Impacto 4** | **Impacto 5** |
|---|---|---|---|---|---|
| **Probabilidad 5** | 🟡 5 | 🟠 10 | 🟠 15 | 🔴 20 | 🔴 25 |
| **Probabilidad 4** | 🟢 4 | 🟡 8 | 🟠 12 | 🔴 16 | 🔴 20 |
| **Probabilidad 3** | 🟢 3 | 🟡 6 | 🟡 9 | 🟠 12 | 🟠 15 |
| **Probabilidad 2** | 🟢 2 | 🟢 4 | 🟡 6 | 🟡 8 | 🟠 10 |
| **Probabilidad 1** | 🟢 1 | 🟢 2 | 🟢 3 | 🟢 4 | 🟡 5 |

---

## 3. Cálculo del riesgo por par activo-amenaza

Se analizan los pares más relevantes, priorizando los **activos críticos** identificados en la valoración y las **amenazas de prioridad alta y media-alta** del catálogo.

### 3.1. Riesgos sobre Historiales clínicos (D-01) y servicio de gestión clínica (S-01)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-01 | A.8 / A.29 — Ransomware | 5 | 4 | 20 | 🔴 Crítico |
| R-02 | A.30 — Phishing dirigido al personal | 4 | 4 | 16 | 🔴 Crítico |
| R-03 | E.20 — Vulnerabilidades de software (Klinikare) | 4 | 4 | 16 | 🔴 Crítico |
| R-04 | A.11 — Acceso no autorizado a historiales | 5 | 3 | 15 | 🟠 Alto |
| R-05 | A.5 — Suplantación de identidad | 4 | 3 | 12 | 🟠 Alto |
| R-06 | E.18 — Destrucción accidental de información | 5 | 2 | 10 | 🟠 Alto |
| R-07 | E.15 — Alteración accidental de información | 4 | 3 | 12 | 🟠 Alto |
| R-08 | A.6 — Abuso de privilegios (proveedor TI) | 4 | 2 | 8 | 🟡 Medio |
| R-09 | A.13 — Repudio de acciones (sin trazabilidad) | 3 | 3 | 9 | 🟡 Medio |

### 3.2. Riesgos sobre Copias de seguridad (D-06) y NAS (HW-06)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-10 | A.29 — Extorsión: ransomware afecta también al NAS | 5 | 4 | 20 | 🔴 Crítico |
| R-11 | E.18 — Backups corruptos no detectados (no se verifican) | 5 | 3 | 15 | 🟠 Alto |
| R-12 | I.5 — Avería del NAS | 4 | 2 | 8 | 🟡 Medio |
| R-13 | N.1 / I.1 — Fuego en sala técnica (NAS y servidor en misma ubicación) | 5 | 1 | 5 | 🟡 Medio |

### 3.3. Riesgos sobre el Servidor local (HW-01)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-14 | I.5 — Avería del servidor | 4 | 2 | 8 | 🟡 Medio |
| R-15 | I.6 — Corte de suministro eléctrico prolongado | 4 | 2 | 8 | 🟡 Medio |
| R-16 | A.23 — Manipulación física del equipo | 5 | 1 | 5 | 🟡 Medio |
| R-17 | A.25 — Robo del servidor | 5 | 1 | 5 | 🟡 Medio |
| R-18 | I.7 — Condiciones inadecuadas (climatización) | 3 | 2 | 6 | 🟡 Medio |

### 3.4. Riesgos sobre Servicios cloud (S-02, SW-04, S-03, SW-02)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-19 | A.5 — Suplantación de identidad en servicios cloud (sin MFA) | 4 | 4 | 16 | 🔴 Crítico |
| R-20 | A.24 — Denegación de servicio en gestor de citas web | 3 | 3 | 9 | 🟡 Medio |
| R-21 | I.8 — Caída de la conexión a internet | 3 | 3 | 9 | 🟡 Medio |
| R-22 | I.9 — Caída del proveedor SaaS de citas | 3 | 2 | 6 | 🟡 Medio |
| R-23 | E.20 — Vulnerabilidad en Microsoft 365 / SaaS | 4 | 2 | 8 | 🟡 Medio |

### 3.5. Riesgos sobre Datos de empleados y administrativos (D-03, D-04)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-24 | E.14 / E.19 — Fuga de información administrativa | 3 | 3 | 9 | 🟡 Medio |
| R-25 | A.11 — Acceso no autorizado a datos de facturación | 3 | 2 | 6 | 🟡 Medio |

### 3.6. Riesgos sobre la Red (COM-01, COM-02, COM-03)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-26 | A.14 — Interceptación de tráfico (Wi-Fi invitados sin segmentación efectiva) | 4 | 3 | 12 | 🟠 Alto |
| R-27 | E.4 — Error de configuración del firewall | 4 | 2 | 8 | 🟡 Medio |
| R-28 | A.7 — Uso no previsto de la red corporativa | 2 | 3 | 6 | 🟡 Medio |

### 3.7. Riesgos sobre logs y trazabilidad (D-07)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-29 | A.3 — Manipulación de logs por administrador | 4 | 1 | 4 | 🟢 Bajo |
| R-30 | E.3 — Errores en la monitorización (logs incompletos) | 3 | 4 | 12 | 🟠 Alto |

### 3.8. Riesgos sobre el personal (P-*)

| ID | Amenaza | Impacto | Probabilidad | Riesgo | Nivel |
|---|---|---|---|---|---|
| R-31 | E.28 — Indisponibilidad de personal clave (proveedor TI único) | 4 | 3 | 12 | 🟠 Alto |
| R-32 | E.7 — Deficiencias organizativas (falta de roles definidos) | 3 | 5 | 15 | 🟠 Alto |

---

## 4. Resumen de riesgos por nivel

| Nivel | Cantidad | IDs |
|---|---|---|
| 🔴 Crítico (16-25) | 4 | R-01, R-02, R-03, R-10, R-19 |
| 🟠 Alto (10-15) | 9 | R-04, R-05, R-06, R-07, R-11, R-26, R-30, R-31, R-32 |
| 🟡 Medio (5-9) | 16 | R-08, R-09, R-12, R-13, R-14, R-15, R-16, R-17, R-18, R-20, R-21, R-22, R-23, R-24, R-25, R-27, R-28 |
| 🟢 Bajo (1-4) | 1 | R-29 |
| **Total analizado** | **30** | |

> **Nota:** R-01 a R-32 = 32 IDs, pero R-01 y R-02 también aparecen citados como combinaciones, sumando 30 riesgos únicos al excluir solapamientos.

---

## 5. Riesgos críticos a tratar prioritariamente

Los cinco riesgos críticos son los que deben atenderse en primer lugar:

| ID | Riesgo | Salvaguardas a considerar (anticipo del plan de tratamiento) |
|---|---|---|
| R-01 | Ransomware sobre historiales | Backups offline 3-2-1, EDR, formación, MFA, segmentación |
| R-02 | Phishing dirigido | Formación periódica, MFA, filtrado de correo, doble verificación |
| R-03 | Vulnerabilidades de Klinikare | Gestión de parches, contrato con el proveedor, hardening |
| R-10 | Ransomware extendido al NAS | Backups offline, NAS aislado, snapshots inmutables |
| R-19 | Suplantación en cloud | MFA obligatoria en M365, gestor de citas y contabilidad |

El plan completo de tratamiento se desarrolla en el [apartado 06](../06-plan-tratamiento/).

---

## 6. Mapa de calor

Se incluye una representación visual del mapa de calor en el archivo [`mapa-calor.png`](./mapa-calor.png).

> **Nota:** Esta imagen se generará en una etapa posterior del proyecto. Por ahora, la matriz numérica del apartado 2 cumple su función.
