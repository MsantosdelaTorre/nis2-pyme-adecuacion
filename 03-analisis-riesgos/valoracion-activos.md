# Valoración de activos

Valoración de los activos identificados en el [inventario](./inventario-activos.md) en las cinco dimensiones de seguridad de **MAGERIT**: Confidencialidad (C), Integridad (I), Disponibilidad (D), Autenticidad (A) y Trazabilidad (T).

---

## 1. Escala de valoración

Se utiliza una escala de **0 a 10** según el impacto que tendría la pérdida de la dimensión correspondiente.

| Valor | Nivel | Significado |
|---|---|---|
| 0 | Despreciable | Sin impacto relevante |
| 1-2 | Bajo | Impacto menor, asumible |
| 3-4 | Medio-bajo | Impacto perceptible pero limitado |
| 5-6 | Medio | Impacto notable sobre la organización |
| 7-8 | Alto | Impacto grave |
| 9-10 | Muy alto | Impacto muy grave o catastrófico |

---

## 2. Criterios de valoración por dimensión

| Dimensión | Pregunta clave |
|---|---|
| **Confidencialidad (C)** | ¿Qué impacto tendría que esta información llegue a quien no debe? |
| **Integridad (I)** | ¿Qué impacto tendría que esta información se altere sin autorización? |
| **Disponibilidad (D)** | ¿Qué impacto tendría no poder acceder a este activo cuando se necesita? |
| **Autenticidad (A)** | ¿Qué impacto tendría no poder verificar el origen o autoría? |
| **Trazabilidad (T)** | ¿Qué impacto tendría no poder reconstruir quién hizo qué y cuándo? |

---

## 3. Valoración de activos esenciales

Solo se valoran los activos **esenciales** (datos y servicios). Los activos de soporte (hardware, software, comunicaciones) heredan su valor de los esenciales que sostienen.

### 3.1. Datos / Información [D]

| ID | Activo | C | I | D | A | T | Justificación |
|---|---|---|---|---|---|---|---|
| D-01 | Historiales clínicos | 8 | 9 | 7 | 9 | 9 | Datos de salud (categoría especial RGPD). Su alteración afecta a la salud del paciente. Trazabilidad obligatoria por Ley 41/2002. |
| D-02 | Radiografías digitales | 8 | 9 | 7 | 8 | 8 | Asociadas a historial clínico. Su alteración puede llevar a diagnósticos erróneos. |
| D-03 | Datos de facturación | 6 | 7 | 5 | 6 | 6 | Datos económicos y bancarios. Impacto medio si se filtran o alteran. |
| D-04 | Datos de empleados | 6 | 6 | 4 | 5 | 5 | Datos personales del personal. Impacto medio. |
| D-05 | Consentimientos informados | 7 | 9 | 5 | 9 | 8 | Documento legal. Su alteración o falsificación tiene implicaciones legales graves. |
| D-06 | Copias de seguridad | 8 | 9 | 8 | - | 6 | Heredan criticidad de los datos respaldados. La disponibilidad de los backups es crítica para la recuperación. |
| D-07 | Logs del sistema | 5 | 8 | 6 | - | 9 | La trazabilidad es la dimensión clave: deben ser íntegros y conservarse. |

### 3.2. Servicios [S]

| ID | Activo | C | I | D | A | T | Justificación |
|---|---|---|---|---|---|---|---|
| S-01 | Servicio de gestión clínica | 8 | 9 | 8 | 9 | 9 | Servicio nuclear de la actividad. Sin él no se puede atender a pacientes. |
| S-02 | Servicio de citas online | 4 | 5 | 6 | 5 | 4 | Importante operativamente, pero las citas pueden gestionarse manualmente como respaldo. |
| S-03 | Servicio de correo corporativo | 6 | 6 | 6 | 7 | 5 | Canal de comunicación con mutua y proveedores. Impacto medio. |
| S-04 | Servicio de facturación a mutua | 6 | 8 | 5 | 8 | 7 | La integridad de la facturación es crítica para el cobro y el cumplimiento del convenio. |

---

## 4. Valoración de activos de soporte (heredada)

Los activos de soporte adoptan el **valor más alto** de los activos esenciales que sostienen, en cada dimensión.

### 4.1. Software [SW]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| SW-01 | Klinikare | D-01, D-02, S-01 | 8 | 9 | 8 | 9 | 9 |
| SW-02 | Microsoft 365 Business | S-03 | 6 | 6 | 6 | 7 | 5 |
| SW-03 | Software de contabilidad | D-03, S-04 | 6 | 8 | 5 | 8 | 7 |
| SW-04 | Gestor de citas web | S-02 | 4 | 5 | 6 | 5 | 4 |
| SW-05 | Windows Server 2019 | SW-01 | 8 | 9 | 8 | 9 | 9 |
| SW-06 | Windows 10/11 (puestos) | Acceso a S-01, S-03 | 8 | 9 | 8 | 9 | 9 |
| SW-07 | Windows Defender | Protección de SW-05, SW-06 | - | 7 | 7 | - | - |

### 4.2. Hardware [HW]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| HW-01 | Servidor local | SW-01, SW-05, D-01, D-02 | 8 | 9 | 8 | 9 | 9 |
| HW-02 | Puestos de trabajo | SW-06, acceso a S-01 | 7 | 8 | 7 | 8 | 8 |
| HW-03 | Equipos de radiografía digital | D-02 | 8 | 9 | 7 | 8 | 8 |
| HW-04 | Firewall hardware | Protege COM-01, COM-03 | - | 8 | 8 | - | - |
| HW-05 | Switch gestionable | COM-01 | - | 7 | 8 | - | - |
| HW-06 | NAS de backups | D-06 | 8 | 9 | 8 | - | 6 |
| HW-07 | Router ISP | COM-03 | - | 6 | 7 | - | - |

### 4.3. Comunicaciones [COM]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| COM-01 | Red LAN cableada | Conecta HW-01 con HW-02, HW-03 | 7 | 8 | 8 | - | - |
| COM-02 | Red Wi-Fi de invitados | Servicio a pacientes | 3 | 3 | 3 | - | - |
| COM-03 | Conexión a internet | S-02, S-03, SW-04 | 6 | 6 | 7 | - | - |

### 4.4. Soportes y auxiliar [Media], [AUX]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| Media-01 | Discos del servidor | D-01, D-02, D-03 | 8 | 9 | 8 | - | - |
| Media-02 | Discos del NAS | D-06 | 8 | 9 | 8 | - | - |
| Media-03 | Documentación en papel | D-05 | 7 | 9 | 5 | 9 | 8 |
| AUX-01 | UPS del servidor | HW-01 | - | - | 8 | - | - |
| AUX-02 | Cableado estructurado | COM-01 | - | - | 7 | - | - |
| AUX-03 | Climatización sala servidor | HW-01 | - | - | 7 | - | - |

### 4.5. Instalaciones [L]

| ID | Activo | C | I | D | A | T |
|---|---|---|---|---|---|---|
| L-01 | Sala técnica | 8 | - | 8 | - | - |
| L-02 | Consultas | 7 | - | 6 | - | - |
| L-03 | Recepción y administración | 6 | - | 6 | - | - |

---

## 5. Resumen de los activos más críticos

Los activos con valoración igual o superior a **8** en cualquier dimensión:

| Activo | Tipo | Dimensiones críticas (≥8) |
|---|---|---|
| Historiales clínicos (D-01) | Datos | C, I, A, T |
| Radiografías digitales (D-02) | Datos | C, I, A, T |
| Consentimientos informados (D-05) | Datos | I, A, T |
| Copias de seguridad (D-06) | Datos | C, I, D |
| Logs del sistema (D-07) | Datos | I, T |
| Servicio de gestión clínica (S-01) | Servicio | C, I, D, A, T |
| Servicio de facturación a mutua (S-04) | Servicio | I, A |
| Klinikare (SW-01) | Software | C, I, D, A, T |
| Windows Server 2019 (SW-05) | Software | C, I, D, A, T |
| Servidor local (HW-01) | Hardware | C, I, D, A, T |
| Equipos de radiografía digital (HW-03) | Hardware | C, I, A, T |
| NAS de backups (HW-06) | Hardware | C, I, D |
| Discos del servidor (Media-01) | Soporte | C, I, D |

Estos activos serán el foco prioritario del [análisis de amenazas](./amenazas.md) y del posterior cálculo de riesgo.

---

## 6. Observaciones

> Las dimensiones marcadas con `-` no aplican al activo. Por ejemplo, no tiene sentido valorar la "Confidencialidad" de un sistema de alimentación ininterrumpida (UPS), ya que no contiene información.# Valoración de activos

Valoración de los activos identificados en el [inventario](./inventario-activos.md) en las cinco dimensiones de seguridad de **MAGERIT**: Confidencialidad (C), Integridad (I), Disponibilidad (D), Autenticidad (A) y Trazabilidad (T).

---

## 1. Escala de valoración

Se utiliza una escala de **0 a 10** según el impacto que tendría la pérdida de la dimensión correspondiente.

| Valor | Nivel | Significado |
|---|---|---|
| 0 | Despreciable | Sin impacto relevante |
| 1-2 | Bajo | Impacto menor, asumible |
| 3-4 | Medio-bajo | Impacto perceptible pero limitado |
| 5-6 | Medio | Impacto notable sobre la organización |
| 7-8 | Alto | Impacto grave |
| 9-10 | Muy alto | Impacto muy grave o catastrófico |

---

## 2. Criterios de valoración por dimensión

| Dimensión | Pregunta clave |
|---|---|
| **Confidencialidad (C)** | ¿Qué impacto tendría que esta información llegue a quien no debe? |
| **Integridad (I)** | ¿Qué impacto tendría que esta información se altere sin autorización? |
| **Disponibilidad (D)** | ¿Qué impacto tendría no poder acceder a este activo cuando se necesita? |
| **Autenticidad (A)** | ¿Qué impacto tendría no poder verificar el origen o autoría? |
| **Trazabilidad (T)** | ¿Qué impacto tendría no poder reconstruir quién hizo qué y cuándo? |

---

## 3. Valoración de activos esenciales

Solo se valoran los activos **esenciales** (datos y servicios). Los activos de soporte (hardware, software, comunicaciones) heredan su valor de los esenciales que sostienen.

### 3.1. Datos / Información [D]

| ID | Activo | C | I | D | A | T | Justificación |
|---|---|---|---|---|---|---|---|
| D-01 | Historiales clínicos | 8 | 9 | 7 | 9 | 9 | Datos de salud (categoría especial RGPD). Su alteración afecta a la salud del paciente. Trazabilidad obligatoria por Ley 41/2002. |
| D-02 | Radiografías digitales | 8 | 9 | 7 | 8 | 8 | Asociadas a historial clínico. Su alteración puede llevar a diagnósticos erróneos. |
| D-03 | Datos de facturación | 6 | 7 | 5 | 6 | 6 | Datos económicos y bancarios. Impacto medio si se filtran o alteran. |
| D-04 | Datos de empleados | 6 | 6 | 4 | 5 | 5 | Datos personales del personal. Impacto medio. |
| D-05 | Consentimientos informados | 7 | 9 | 5 | 9 | 8 | Documento legal. Su alteración o falsificación tiene implicaciones legales graves. |
| D-06 | Copias de seguridad | 8 | 9 | 8 | - | 6 | Heredan criticidad de los datos respaldados. La disponibilidad de los backups es crítica para la recuperación. |
| D-07 | Logs del sistema | 5 | 8 | 6 | - | 9 | La trazabilidad es la dimensión clave: deben ser íntegros y conservarse. |

### 3.2. Servicios [S]

| ID | Activo | C | I | D | A | T | Justificación |
|---|---|---|---|---|---|---|---|
| S-01 | Servicio de gestión clínica | 8 | 9 | 8 | 9 | 9 | Servicio nuclear de la actividad. Sin él no se puede atender a pacientes. |
| S-02 | Servicio de citas online | 4 | 5 | 6 | 5 | 4 | Importante operativamente, pero las citas pueden gestionarse manualmente como respaldo. |
| S-03 | Servicio de correo corporativo | 6 | 6 | 6 | 7 | 5 | Canal de comunicación con mutua y proveedores. Impacto medio. |
| S-04 | Servicio de facturación a mutua | 6 | 8 | 5 | 8 | 7 | La integridad de la facturación es crítica para el cobro y el cumplimiento del convenio. |

---

## 4. Valoración de activos de soporte (heredada)

Los activos de soporte adoptan el **valor más alto** de los activos esenciales que sostienen, en cada dimensión.

### 4.1. Software [SW]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| SW-01 | Klinikare | D-01, D-02, S-01 | 8 | 9 | 8 | 9 | 9 |
| SW-02 | Microsoft 365 Business | S-03 | 6 | 6 | 6 | 7 | 5 |
| SW-03 | Software de contabilidad | D-03, S-04 | 6 | 8 | 5 | 8 | 7 |
| SW-04 | Gestor de citas web | S-02 | 4 | 5 | 6 | 5 | 4 |
| SW-05 | Windows Server 2019 | SW-01 | 8 | 9 | 8 | 9 | 9 |
| SW-06 | Windows 10/11 (puestos) | Acceso a S-01, S-03 | 8 | 9 | 8 | 9 | 9 |
| SW-07 | Windows Defender | Protección de SW-05, SW-06 | - | 7 | 7 | - | - |

### 4.2. Hardware [HW]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| HW-01 | Servidor local | SW-01, SW-05, D-01, D-02 | 8 | 9 | 8 | 9 | 9 |
| HW-02 | Puestos de trabajo | SW-06, acceso a S-01 | 7 | 8 | 7 | 8 | 8 |
| HW-03 | Equipos de radiografía digital | D-02 | 8 | 9 | 7 | 8 | 8 |
| HW-04 | Firewall hardware | Protege COM-01, COM-03 | - | 8 | 8 | - | - |
| HW-05 | Switch gestionable | COM-01 | - | 7 | 8 | - | - |
| HW-06 | NAS de backups | D-06 | 8 | 9 | 8 | - | 6 |
| HW-07 | Router ISP | COM-03 | - | 6 | 7 | - | - |

### 4.3. Comunicaciones [COM]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| COM-01 | Red LAN cableada | Conecta HW-01 con HW-02, HW-03 | 7 | 8 | 8 | - | - |
| COM-02 | Red Wi-Fi de invitados | Servicio a pacientes | 3 | 3 | 3 | - | - |
| COM-03 | Conexión a internet | S-02, S-03, SW-04 | 6 | 6 | 7 | - | - |

### 4.4. Soportes y auxiliar [Media], [AUX]

| ID | Activo | Sostiene | C | I | D | A | T |
|---|---|---|---|---|---|---|---|
| Media-01 | Discos del servidor | D-01, D-02, D-03 | 8 | 9 | 8 | - | - |
| Media-02 | Discos del NAS | D-06 | 8 | 9 | 8 | - | - |
| Media-03 | Documentación en papel | D-05 | 7 | 9 | 5 | 9 | 8 |
| AUX-01 | UPS del servidor | HW-01 | - | - | 8 | - | - |
| AUX-02 | Cableado estructurado | COM-01 | - | - | 7 | - | - |
| AUX-03 | Climatización sala servidor | HW-01 | - | - | 7 | - | - |

### 4.5. Instalaciones [L]

| ID | Activo | C | I | D | A | T |
|---|---|---|---|---|---|---|
| L-01 | Sala técnica | 8 | - | 8 | - | - |
| L-02 | Consultas | 7 | - | 6 | - | - |
| L-03 | Recepción y administración | 6 | - | 6 | - | - |

---

## 5. Resumen de los activos más críticos

Los activos con valoración igual o superior a **8** en cualquier dimensión:

| Activo | Tipo | Dimensiones críticas (≥8) |
|---|---|---|
| Historiales clínicos (D-01) | Datos | C, I, A, T |
| Radiografías digitales (D-02) | Datos | C, I, A, T |
| Consentimientos informados (D-05) | Datos | I, A, T |
| Copias de seguridad (D-06) | Datos | C, I, D |
| Logs del sistema (D-07) | Datos | I, T |
| Servicio de gestión clínica (S-01) | Servicio | C, I, D, A, T |
| Servicio de facturación a mutua (S-04) | Servicio | I, A |
| Klinikare (SW-01) | Software | C, I, D, A, T |
| Windows Server 2019 (SW-05) | Software | C, I, D, A, T |
| Servidor local (HW-01) | Hardware | C, I, D, A, T |
| Equipos de radiografía digital (HW-03) | Hardware | C, I, A, T |
| NAS de backups (HW-06) | Hardware | C, I, D |
| Discos del servidor (Media-01) | Soporte | C, I, D |

Estos activos serán el foco prioritario del [análisis de amenazas](./amenazas.md) y del posterior cálculo de riesgo.

---

## 6. Observaciones

> Las dimensiones marcadas con `-` no aplican al activo. Por ejemplo, no tiene sentido valorar la "Confidencialidad" de un sistema de alimentación ininterrumpida (UPS), ya que no contiene información.
