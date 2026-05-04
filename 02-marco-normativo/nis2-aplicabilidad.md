# Aplicabilidad de la Directiva NIS2 a DentaCare

Análisis de la aplicabilidad de la Directiva (UE) 2022/2555 (NIS2) a DentaCare y de las obligaciones derivadas.

> ⚠️ **Nota sobre el caso de estudio**
> 
> DentaCare, tal como está dimensionada en este proyecto (15 empleados, 850.000 € de facturación), **no superaría los umbrales generales de aplicabilidad de NIS2**. La inclusión bajo NIS2 se justifica en este caso a través de la excepción de proveedor de servicios al sector público (apartado 3.3), pero se trata de una **interpretación amplia para este caso práctico**
> 
> El objetivo del proyecto no es determinar con rigor jurídico si NIS2 aplica, sino **demostrar cómo se realizaría un proceso completo de adecuación** si aplicase. Por eso el caso se desarrolla como si DentaCare estuviera plenamente sujeta a la Directiva.
> 
> En un proyecto real, la determinación de aplicabilidad requeriría análisis jurídico formal.

---

## 1. Marco normativo

La **Directiva (UE) 2022/2555** (Network and Information Security 2, NIS2) es la norma europea que establece medidas para un nivel común elevado de ciberseguridad en la Unión Europea. Sustituye a la Directiva NIS original de 2016 y entró en aplicación efectiva en octubre de 2024, con plazo de transposición a los Estados miembros.

En España, la transposición se realiza mediante la **Ley de Coordinación y Gobernanza de la Ciberseguridad** (en proceso de tramitación).

---

## 2. Criterios de aplicabilidad

NIS2 aplica a entidades que cumplan **dos condiciones**:

1. Pertenecer a un **sector regulado** (Anexo I — esenciales, o Anexo II — importantes).
2. Superar el **umbral de tamaño**:
   - **Mediana empresa:** entre 50 y 249 empleados, o facturación entre 10 y 50 M€.
   - **Gran empresa:** más de 250 empleados, o facturación superior a 50 M€.

Las microempresas y pequeñas empresas (menos de 50 empleados y facturación inferior a 10 M€) **quedan generalmente excluidas**, salvo excepciones específicas (proveedores de servicios de comunicaciones electrónicas, registros de nombres de dominio, entidades únicas en su sector, entre otras).

---

## 3. Análisis para DentaCare

### 3.1. Sector

DentaCare presta servicios de **asistencia sanitaria** (odontología). El sector salud está incluido en el **Anexo I** de NIS2 como sector de **alta criticidad**, dentro de la categoría "Sanidad — Prestadores de asistencia sanitaria".

### 3.2. Tamaño

| Criterio | Valor DentaCare | Umbral NIS2 |
|---|---|---|
| Empleados | 15 | ≥ 50 |
| Facturación anual | 850.000 € | ≥ 10 M€ |

DentaCare se sitúa **por debajo** de los umbrales generales de tamaño. En principio, esto la dejaría fuera del ámbito directo de NIS2.

### 3.3. Excepciones a considerar

Aunque DentaCare no supere los umbrales generales, NIS2 contempla supuestos en los que entidades más pequeñas pueden quedar incluidas:

- Si presta servicios a una entidad esencial bajo NIS2 como **proveedor crítico**.
- Si una **interrupción de su servicio podría tener un impacto significativo en la salud pública** o en otros servicios esenciales.
- Si así lo determina el Estado miembro mediante criterios adicionales.

DentaCare presta servicios a una mutua del sector público mediante convenio. Esto puede situar a la clínica en la categoría de **proveedor de un servicio esencial**, lo que activaría su inclusión bajo NIS2 incluso por debajo de los umbrales generales.

### 3.4. Conclusión sobre aplicabilidad

A efectos de este caso práctico se asume que **NIS2 le aplica a DentaCare como entidad importante** por su condición de proveedor de servicios sanitarios al sector público. Esta interpretación es conservadora y permite trabajar con el conjunto completo de obligaciones de la Directiva.

> **Nota didáctica:** En un proyecto real, esta determinación requeriría un análisis jurídico formal por parte de un especialista. Aquí se asume la aplicabilidad para desarrollar el caso de forma completa.

---

## 4. Obligaciones derivadas

Como entidad importante bajo NIS2, DentaCare debe cumplir con las siguientes obligaciones principales:

### 4.1. Gobernanza y responsabilidad de la dirección

- La dirección **es directamente responsable** del cumplimiento de las medidas de gestión de riesgos.
- Los órganos de dirección deben **aprobar** las medidas adoptadas y **supervisar** su aplicación.
- La dirección debe **recibir formación** específica en ciberseguridad.

### 4.2. Medidas técnicas y organizativas (Art. 21)

NIS2 exige adoptar medidas adecuadas y proporcionadas en, al menos, los siguientes ámbitos:

| Ámbito | Aplicación a DentaCare |
|---|---|
| Políticas de análisis de riesgos y seguridad de los sistemas | Apartado 03 (análisis de riesgos) y 07 (políticas) |
| Gestión de incidentes | Política y procedimiento de respuesta a incidentes |
| Continuidad de negocio (backups, recuperación, gestión de crisis) | Apartado 04 (BIA) y plan de continuidad |
| Seguridad de la cadena de suministro | Análisis de proveedores: Klinikare, alojamiento web, proveedor de TI |
| Seguridad en la adquisición, desarrollo y mantenimiento de sistemas | Procedimientos de gestión de cambios |
| Políticas y procedimientos para evaluar la eficacia de las medidas | Apartado 08 (KPIs) |
| Formación y concienciación en ciberseguridad | Plan de formación al personal |
| Criptografía y, cuando proceda, cifrado | Cifrado de copias de seguridad y comunicaciones |
| Seguridad de los recursos humanos, control de accesos y gestión de activos | Política de control de accesos |
| Autenticación multifactor (MFA) cuando proceda | MFA en servicios cloud y acceso al servidor |

### 4.3. Notificación de incidentes

DentaCare debe notificar al CSIRT competente (en España, **INCIBE-CERT** para entidades del sector privado) los incidentes con **impacto significativo**, en los siguientes plazos:

| Hito | Plazo | Contenido |
|---|---|---|
| **Aviso temprano** (early warning) | 24 horas desde la detección | Sospecha de incidente, posible carácter malicioso, posible impacto transfronterizo |
| **Notificación oficial** | 72 horas desde la detección | Evaluación inicial de gravedad, indicadores de compromiso |
| **Informe intermedio** | A petición de la autoridad | Estado del incidente |
| **Informe final** | 1 mes desde la notificación | Descripción detallada, causa raíz, medidas adoptadas, impacto transfronterizo |

### 4.4. Otras obligaciones

- **Registro** ante la autoridad competente (en España, el INCIBE).
- **Cooperación** con la autoridad nacional y con el CSIRT en caso de incidente.
- **Seguridad de la cadena de suministro:** evaluar la postura de seguridad de los proveedores críticos.

---

## 5. Sanciones por incumplimiento

NIS2 introduce un régimen sancionador armonizado en toda la UE.

| Tipo de entidad | Sanción máxima |
|---|---|
| Entidades **esenciales** | Hasta **10 millones de euros** o el **2 % de la facturación mundial anual**, lo que sea mayor |
| Entidades **importantes** (caso de DentaCare) | Hasta **7 millones de euros** o el **1,4 % de la facturación mundial anual**, lo que sea mayor |

Adicionalmente, los miembros del órgano de dirección pueden ser **considerados personalmente responsables** si se demuestra negligencia grave, pudiendo serles impuestas:

- Inhabilitación temporal para el ejercicio de funciones directivas.
- Publicación pública del incumplimiento.

---

## 6. Roadmap de cumplimiento

A partir de este análisis, el resto del proyecto desarrolla los pasos necesarios para que DentaCare cumpla con las exigencias de NIS2:

| Apartado | Contribución al cumplimiento NIS2 |
|---|---|
| [03 — Análisis de riesgos](../03-analisis-riesgos/) | Cumple Art. 21.2.a (políticas de análisis de riesgos) |
| [04 — BIA](../04-bia/) | Cumple Art. 21.2.c (continuidad del negocio) |
| [05 — GAP analysis](../05-gap-analysis/) | Identifica brechas frente a las medidas exigidas |
| [06 — Plan de tratamiento](../06-plan-tratamiento/) | Plan de implantación de medidas |
| [07 — Políticas](../07-politicas/) | Cumple obligación de políticas documentadas |
| [08 — KPIs](../08-kpis/) | Cumple Art. 21.2.f (evaluación de eficacia) |

---

## Referencias

- **Directiva (UE) 2022/2555** del Parlamento Europeo y del Consejo, de 14 de diciembre de 2022 (NIS2).
- **INCIBE-CERT** — Centro de Respuesta a Incidentes de Seguridad de referencia para entidades del sector privado en España.
- **Guías CCN-CERT** sobre gestión de incidentes y notificación.
