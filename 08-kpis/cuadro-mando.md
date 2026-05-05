# KPIs y cuadro de mando de seguridad

Definición de los indicadores que DentaCare utiliza para medir la eficacia del programa de seguridad y demostrar cumplimiento ante auditorías y la mutua pública.

---

## 1. Objetivo del cuadro de mando

- Medir la **eficacia** de las medidas de seguridad implantadas.
- Detectar **desviaciones** y áreas de mejora de forma temprana.
- Aportar evidencias **documentadas** ante auditorías internas y externas.
- Cumplir con la obligación NIS2 de **evaluar la eficacia** de las medidas (Art. 21.2.f).

---

## 2. Tipos de indicadores

| Tipo | Definición | Ejemplo |
|---|---|---|
| **KPI** (Key Performance Indicator) | Mide el rendimiento de un proceso de seguridad | % de personal formado |
| **KRI** (Key Risk Indicator) | Mide la exposición al riesgo | Número de intentos de phishing recibidos |
| **KCI** (Key Control Indicator) | Mide el funcionamiento de un control | % de copias de seguridad verificadas correctamente |

---

## 3. Indicadores definidos para DentaCare

### 3.1. Indicadores de gestión de incidentes

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-01 | Tiempo medio de detección (MTTD) | KPI | Suma del tiempo hasta detectar / nº de incidentes | < 4 horas | Mensual | Resp. seguridad |
| K-02 | Tiempo medio de respuesta (MTTR) | KPI | Suma del tiempo de respuesta / nº de incidentes | < 8 horas | Mensual | Resp. seguridad |
| K-03 | Número de incidentes críticos | KRI | Conteo de incidentes nivel "Crítico" | 0 al trimestre | Trimestral | Resp. seguridad |
| K-04 | % de incidentes notificados en plazo legal | KPI | Notificados en plazo / total que requerían notificación × 100 | 100 % | Trimestral | Dirección |
| K-05 | Número de brechas de datos personales | KRI | Conteo de brechas RGPD | 0 al año | Anual | Resp. seguridad |

### 3.2. Indicadores de copias de seguridad

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-06 | % de copias diarias completadas correctamente | KCI | Copias OK / copias programadas × 100 | ≥ 99 % | Mensual | Proveedor TI |
| K-07 | % de pruebas de restauración exitosas | KCI | Restauraciones OK / restauraciones probadas × 100 | 100 % | Trimestral | Proveedor TI |
| K-08 | Número de meses con backup offline realizado | KCI | Conteo | 12 al año | Anual | Resp. seguridad |
| K-09 | Tiempo de restauración real en simulacro | KPI | Duración del simulacro completo | ≤ RTO definido (4 h) | Anual | Proveedor TI |

### 3.3. Indicadores de control de accesos

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-10 | % de cuentas con MFA activada | KCI | Cuentas con MFA / total × 100 | 100 % en cuentas privilegiadas, ≥ 95 % en el resto | Mensual | Proveedor TI |
| K-11 | Número de cuentas inactivas > 60 días | KRI | Conteo | 0 | Mensual | Resp. seguridad |
| K-12 | % de altas/bajas gestionadas en plazo | KPI | Procesadas en plazo / total × 100 | ≥ 95 % | Trimestral | Resp. seguridad |
| K-13 | Número de revisiones trimestrales de permisos realizadas | KPI | Conteo | 4 al año | Anual | Resp. seguridad |
| K-14 | Número de accesos privilegiados al servidor | KRI | Conteo de eventos en logs | Tendencia estable | Mensual | Resp. seguridad |

### 3.4. Indicadores de formación y concienciación

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-15 | % de personal formado en ciberseguridad | KPI | Personal formado / plantilla × 100 | 100 % | Anual | Dirección |
| K-16 | Tasa de clic en simulacros de phishing | KRI | Personas que clican / total × 100 | < 10 % | Trimestral | Resp. seguridad |
| K-17 | Tasa de reporte de phishing simulado | KPI | Personas que reportan / total × 100 | ≥ 70 % | Trimestral | Resp. seguridad |

### 3.5. Indicadores de vulnerabilidades y parches

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-18 | % de equipos con SO actualizado | KCI | Equipos al día / total × 100 | ≥ 95 % | Mensual | Proveedor TI |
| K-19 | Tiempo medio de aplicación de parches críticos | KPI | Suma de días desde publicación hasta aplicación / nº de parches | ≤ 7 días | Mensual | Proveedor TI |
| K-20 | Número de vulnerabilidades críticas abiertas | KRI | Conteo de CVEs críticas sin remediar | 0 | Mensual | Resp. seguridad |

### 3.6. Indicadores de continuidad

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-21 | Número de simulacros de continuidad realizados | KPI | Conteo | 1 al año | Anual | Dirección |
| K-22 | Cumplimiento del RTO en el último simulacro | KPI | Sí/No (RTO real ≤ RTO objetivo) | Sí | Anual | Resp. seguridad |

### 3.7. Indicadores de proveedores

| ID | Indicador | Tipo | Fórmula | Objetivo | Frecuencia | Responsable |
|---|---|---|---|---|---|---|
| K-23 | % de proveedores críticos con cláusulas de seguridad en contrato | KCI | Proveedores con cláusulas / total críticos × 100 | 100 % | Anual | Dirección |
| K-24 | Número de incidentes causados por proveedores | KRI | Conteo | 0 | Anual | Resp. seguridad |

---

## 4. Umbrales y semáforos

Cada indicador se evalúa con tres umbrales:

| Color | Significado | Acción |
|---|---|---|
| 🟢 Verde | Cumple objetivo | Mantener y monitorizar |
| 🟡 Amarillo | Por debajo del objetivo, sin riesgo grave | Revisar causa, plan de mejora |
| 🔴 Rojo | Incumplimiento crítico | Acción correctiva inmediata |

### 4.1. Umbrales por indicador (ejemplos clave)

| Indicador | 🟢 Verde | 🟡 Amarillo | 🔴 Rojo |
|---|---|---|---|
| K-06 (% copias completas) | ≥ 99 % | 95-99 % | < 95 % |
| K-10 (% MFA) | ≥ 95 % | 85-94 % | < 85 % |
| K-15 (% personal formado) | 100 % | 80-99 % | < 80 % |
| K-16 (clic en phishing) | < 10 % | 10-25 % | > 25 % |
| K-19 (tiempo de parches) | ≤ 7 días | 7-14 días | > 14 días |
| K-20 (CVEs críticos abiertos) | 0 | 1-2 | ≥ 3 |

---

## 5. Cuadro de mando — vista mensual

Ejemplo de cómo se presenta el cuadro de mando a la dirección cada mes:

| Indicador | Objetivo | Mes anterior | Mes actual | Tendencia | Estado |
|---|---|---|---|---|---|
| K-01 — MTTD | < 4 h | 5,2 h | 3,1 h | ⬇️ | 🟢 |
| K-02 — MTTR | < 8 h | 9,8 h | 7,5 h | ⬇️ | 🟢 |
| K-06 — % copias OK | ≥ 99 % | 100 % | 99,5 % | ⬇️ | 🟢 |
| K-10 — % MFA | ≥ 95 % | 88 % | 96 % | ⬆️ | 🟢 |
| K-11 — Cuentas inactivas | 0 | 2 | 0 | ⬇️ | 🟢 |
| K-16 — Clic en phishing | < 10 % | — | 14 % | — | 🟡 |
| K-18 — % SO actualizado | ≥ 95 % | 92 % | 96 % | ⬆️ | 🟢 |
| K-19 — Tiempo parches | ≤ 7 días | 12 días | 8 días | ⬇️ | 🟡 |
| K-20 — CVEs críticos | 0 | 4 | 1 | ⬇️ | 🟡 |

> Los datos del ejemplo son ilustrativos y no corresponden a mediciones reales.

---

## 6. Periodicidad de revisión

| Frecuencia | Indicadores | Audiencia |
|---|---|---|
| **Mensual** | K-01, K-02, K-06, K-10, K-11, K-14, K-18, K-19, K-20 | Responsable de seguridad + proveedor TI |
| **Trimestral** | K-03, K-04, K-07, K-12, K-16, K-17 | Dirección |
| **Anual** | K-05, K-08, K-09, K-13, K-15, K-21, K-22, K-23, K-24 | Dirección + auditoría |

---

## 7. Recogida y origen de los datos

| Fuente | Indicadores que alimenta |
|---|---|
| Registro de incidentes (política de respuesta) | K-01 a K-05 |
| Logs del sistema y SIEM (cuando se implante) | K-01, K-02, K-14 |
| Sistema de copias de seguridad | K-06 a K-09 |
| Consola de M365 / directorio de usuarios | K-10 a K-13 |
| Plataforma de formación y simulacros | K-15 a K-17 |
| Herramienta de gestión de parches y escáner de vulnerabilidades | K-18 a K-20 |
| Documentación de simulacros de continuidad | K-21, K-22 |
| Inventario de proveedores y contratos | K-23, K-24 |

---

## 8. Comité de seguridad

Trimestralmente se celebra un **comité de seguridad** con los siguientes participantes:

- Dirección.
- Responsable de seguridad.
- Representante del proveedor de TI.
- Asesor legal (cuando proceda).

**Orden del día estándar:**

1. Revisión de los KPIs del trimestre.
2. Análisis de incidentes ocurridos.
3. Estado del plan de tratamiento de riesgos.
4. Decisiones sobre medidas correctivas.
5. Próximos pasos y compromisos.

Las actas se conservan como evidencia de cumplimiento.

---

## 9. Auditoría

- **Auditoría interna:** anual, basada en estos KPIs y en el GAP analysis.
- **Auditoría externa:** según se establezca en el convenio con la mutua pública (típicamente cada 2 años para cumplimiento ENS).

Los KPIs son la base evidencial de ambas auditorías.

---

## 10. Revisión de los propios indicadores

Los indicadores definidos también se revisan **anualmente** para:

- Comprobar que siguen siendo relevantes.
- Eliminar los que no aporten valor.
- Añadir nuevos indicadores que surjan a raíz de incidentes o cambios.
- Ajustar umbrales si la realidad de la organización ha cambiado.

---

## Referencias

- **Directiva (UE) 2022/2555 (NIS2)** — Art. 21.2.f sobre evaluación de la eficacia.
- **ISO/IEC 27004** — Information security management — Monitoring, measurement, analysis and evaluation.
- **CCN-STIC 815** — Métricas e indicadores en el ENS.
- **NIST SP 800-55** — Performance Measurement Guide for Information Security.
