# BIA — Análisis de impacto en el negocio

Análisis de impacto en el negocio (Business Impact Analysis) de DentaCare. Identifica los servicios críticos, el impacto de su interrupción y los tiempos máximos asumibles.

---

## 1. Objetivo del BIA

El BIA tiene tres finalidades:

1. **Identificar los procesos críticos** del negocio.
2. **Cuantificar el impacto** de su interrupción a lo largo del tiempo.
3. **Definir los objetivos de recuperación** (RTO, RPO, MTD, WRT) que servirán de entrada al plan de continuidad.

---

## 2. Definiciones

| Término | Definición |
|---|---|
| **RTO** (Recovery Time Objective) | Tiempo máximo aceptable de inactividad de un servicio antes de que el impacto sea inasumible |
| **RPO** (Recovery Point Objective) | Pérdida máxima aceptable de datos, medida en tiempo desde la última copia disponible |
| **MTD** (Maximum Tolerable Downtime) | Tiempo máximo total que el negocio puede sobrevivir sin el servicio |
| **WRT** (Work Recovery Time) | Tiempo necesario para verificar que los sistemas restaurados son operativos |
| **MTPD** (Maximum Tolerable Period of Disruption) | Equivalente a MTD; periodo máximo tolerable de interrupción |

Relación entre conceptos:

```
                 ┌──── RTO ────┬──── WRT ────┐
                 │  recuperar  │  verificar  │
  Incidente ────►│   técnica   │   sistemas  │────► Servicio normal
                 └─────────────┴─────────────┘
                 └─────────── MTD ───────────┘
```

---

## 3. Procesos críticos del negocio

| Proceso | Descripción | Servicio asociado | Impacto si se interrumpe |
|---|---|---|---|
| Atención clínica | Consulta, diagnóstico, tratamiento de pacientes | S-01 (gestión clínica) | Crítico |
| Gestión de citas | Asignación y modificación de citas | S-02 (citas online) | Medio |
| Facturación a mutua | Emisión de facturas y envío al cliente público | S-04 (facturación) | Alto |
| Comunicación interna y externa | Email con personal, mutua, proveedores | S-03 (correo) | Medio |
| Diagnóstico por imagen | Captura y consulta de radiografías digitales | HW-03 + D-02 | Crítico |

---

## 4. Análisis de impacto por proceso

### 4.1. Atención clínica (S-01)

**Descripción:** acceso al historial clínico, registro de la consulta, prescripción.

**Impacto en el tiempo:**

| Tiempo de caída | Impacto |
|---|---|
| 0 - 1 h | Bajo. Se puede improvisar con notas en papel. |
| 1 - 4 h | Medio. Se reprograman pacientes del día. Pérdida económica acotada. |
| 4 - 24 h | Alto. Cancelación de jornada completa. Pacientes derivados. Reputación afectada. |
| > 24 h | Muy alto. Imposibilidad de cumplir con la mutua pública. Riesgo de incumplimiento del convenio. |

**Objetivos:**

- **RTO:** 4 horas
- **RPO:** 24 horas (pérdida máxima admisible: la actividad de un día)
- **MTD:** 48 horas

### 4.2. Gestión de citas (S-02)

**Descripción:** plataforma web para que pacientes pidan, modifiquen o cancelen citas.

**Impacto en el tiempo:**

| Tiempo de caída | Impacto |
|---|---|
| 0 - 24 h | Bajo. Las citas se gestionan por teléfono como respaldo. |
| 24 - 72 h | Medio. Acumulación de llamadas, sobrecarga de recepción. |
| > 72 h | Alto. Pérdida de citas no registradas. Confusión con pacientes. |

**Objetivos:**

- **RTO:** 24 horas
- **RPO:** 1 hora
- **MTD:** 5 días

### 4.3. Facturación a mutua (S-04)

**Descripción:** emisión y envío electrónico de facturación al cliente público.

**Impacto en el tiempo:**

| Tiempo de caída | Impacto |
|---|---|
| 0 - 24 h | Bajo. La facturación es periódica, no diaria. |
| 24 - 72 h | Medio. Posible retraso en cobros. |
| 3 - 7 días | Alto. Incumplimiento de plazos contractuales. Penalizaciones. |
| > 7 días | Muy alto. Riesgo de pérdida del convenio. |

**Objetivos:**

- **RTO:** 48 horas
- **RPO:** 24 horas
- **MTD:** 7 días

### 4.4. Diagnóstico por imagen (HW-03 + D-02)

**Descripción:** captura, almacenamiento y consulta de radiografías digitales.

**Impacto en el tiempo:**

| Tiempo de caída | Impacto |
|---|---|
| 0 - 4 h | Medio. Se reprograman procedimientos que requieran imagen. |
| 4 - 24 h | Alto. Imposibilidad de tratamientos de implantología y endodoncia. |
| > 24 h | Muy alto. Cancelación masiva de tratamientos especializados. |

**Objetivos:**

- **RTO:** 4 horas
- **RPO:** 24 horas
- **MTD:** 48 horas

### 4.5. Comunicación (S-03)

**Descripción:** correo corporativo y comunicación con mutua y proveedores.

**Impacto en el tiempo:**

| Tiempo de caída | Impacto |
|---|---|
| 0 - 24 h | Bajo. Se puede comunicar por teléfono. |
| 24 - 72 h | Medio. Retrasos en respuestas a la mutua, pérdida de mensajes. |
| > 72 h | Alto. Riesgo reputacional, pérdida de información. |

**Objetivos:**

- **RTO:** 24 horas
- **RPO:** 4 horas
- **MTD:** 5 días

---

## 5. Resumen de objetivos de recuperación

| Proceso | RTO | RPO | MTD |
|---|---|---|---|
| Atención clínica | 4 h | 24 h | 48 h |
| Diagnóstico por imagen | 4 h | 24 h | 48 h |
| Gestión de citas | 24 h | 1 h | 5 días |
| Facturación a mutua | 48 h | 24 h | 7 días |
| Comunicación | 24 h | 4 h | 5 días |

---

## 6. Implicaciones para la estrategia de continuidad

A partir de los objetivos definidos, las decisiones derivadas son:

### 6.1. Copias de seguridad

El RPO más exigente es el de **gestión de citas (1 hora)**. Para cumplirlo:

- Backup continuo o cada hora de la base de datos del gestor de citas (SaaS, normalmente cubierto por el proveedor).
- Backup **diario** de Klinikare (cumple RPO de 24 h para atención clínica).
- Verificación de restauración **mensual** (actualmente no se hace).

### 6.2. Recuperación técnica

El RTO más exigente es **4 horas para atención clínica y diagnóstico**. Para cumplirlo:

- Procedimiento documentado de restauración del servidor.
- Hardware de repuesto disponible en menos de 4 h (acuerdo con el proveedor de TI).
- Plan de contingencia: posibilidad de operar manualmente (papel) las primeras horas.

### 6.3. Continuidad de negocio

- **Plan de continuidad documentado** indicando responsables, procedimientos y contactos.
- **Personal alternativo formado** para sustituir al proveedor de TI único (riesgo R-31).
- **Comunicación a pacientes** en caso de interrupción prolongada (canal definido).

### 6.4. Pruebas

- Prueba **anual** completa de restauración desde backup.
- Prueba **trimestral** de procedimiento de contingencia (operativa manual).

---

## 7. Observaciones

> Los valores de RTO/RPO se proponen a partir de un análisis estimado del impacto. En un proyecto real estos valores se validan con la dirección y los responsables de cada proceso, y se contrastan con la capacidad técnica y económica de la organización.

> El BIA debe revisarse al menos **anualmente** o cuando se produzcan cambios significativos en los procesos o servicios.
