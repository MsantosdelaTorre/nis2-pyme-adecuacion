# Categorización del sistema según el ENS

Categorización del sistema de información de DentaCare según el **Real Decreto 311/2022** (Esquema Nacional de Seguridad).

---

## 1. Aplicabilidad del ENS

DentaCare presta servicios al sector público a través de un convenio con una mutua pública. El ENS aplica a los **sistemas de información que sostienen esa prestación**, conforme al artículo 2 del RD 311/2022.

> El alcance del ENS en DentaCare se limita al sistema que da soporte al servicio prestado a la mutua pública. El resto de sistemas internos (gestión administrativa propia, marketing, etc.) quedan fuera del ámbito del ENS, aunque sí están bajo RGPD.

---

## 2. Dimensiones de seguridad

El ENS valora cinco dimensiones para cada sistema:

| Dimensión | Definición |
|---|---|
| **Confidencialidad (C)** | Garantía de que la información solo es accesible a quien está autorizado |
| **Integridad (I)** | Garantía de que la información no se altera de forma no autorizada |
| **Disponibilidad (D)** | Garantía de que la información y servicios están accesibles cuando se necesitan |
| **Autenticidad (A)** | Garantía de la identidad de usuarios y origen de la información |
| **Trazabilidad (T)** | Garantía de que las acciones quedan registradas y son atribuibles |

---

## 3. Niveles de cada dimensión

Cada dimensión se valora en uno de tres niveles según el impacto que tendría su pérdida:

| Nivel | Impacto |
|---|---|
| **BAJO** | Perjuicio limitado sobre las funciones de la organización, sus activos o las personas afectadas |
| **MEDIO** | Perjuicio grave |
| **ALTO** | Perjuicio muy grave o catastrófico |

---

## 4. Valoración de las dimensiones para DentaCare

### 4.1. Confidencialidad — **MEDIO**

El sistema trata historiales clínicos (categoría especial RGPD: salud). Una pérdida de confidencialidad supondría:

- Vulneración de derechos fundamentales de los pacientes.
- Posibles sanciones bajo RGPD/LOPDGDD.
- Daño reputacional grave.

No se valora ALTO porque no se tratan datos de seguridad nacional ni de personas en situación especial de protección.

### 4.2. Integridad — **ALTO**

La integridad de los historiales clínicos es **crítica**. Una alteración no autorizada (intencional o accidental) podría:

- Provocar tratamientos erróneos basados en información manipulada.
- Tener consecuencias directas sobre la salud del paciente.
- Generar responsabilidad civil y penal.

### 4.3. Disponibilidad — **MEDIO**

La pérdida de disponibilidad afecta a la prestación del servicio:

- Imposibilidad de atender a pacientes citados.
- Retraso en tratamientos en curso.
- Impacto económico por interrupción.

No se valora ALTO porque la atención odontológica, salvo urgencias puntuales, admite reprogramación sin daño grave.

### 4.4. Autenticidad — **ALTO**

La autenticidad va asociada a la integridad en este caso:

- Es esencial saber **qué profesional** ha hecho cada anotación en la historia clínica.
- La firma de consentimientos informados requiere garantía de autenticidad.
- Los informes derivados a la mutua pública deben ser trazables a su autor.

### 4.5. Trazabilidad — **ALTO**

Por la naturaleza sanitaria del servicio:

- Es obligatorio poder reconstruir quién ha accedido a cada historia clínica y cuándo.
- La Ley 41/2002 (autonomía del paciente) y el RGPD exigen trazabilidad de accesos.
- Necesario para atender posibles auditorías de la mutua pública o de la AEPD.

---

## 5. Resumen de la valoración

| Dimensión | Nivel | Justificación resumida |
|---|---|---|
| Confidencialidad | MEDIO | Datos de salud (categoría especial RGPD) |
| Integridad | ALTO | Riesgo directo sobre la salud del paciente |
| Disponibilidad | MEDIO | Impacto operativo, admite reprogramación |
| Autenticidad | ALTO | Trazabilidad profesional obligatoria |
| Trazabilidad | ALTO | Exigencia legal de registro de accesos |

---

## 6. Determinación de la categoría del sistema

Según el Anexo I del RD 311/2022, la **categoría del sistema** se determina por la **dimensión de mayor nivel**:

> Si una dimensión está en nivel ALTO, el sistema es de **categoría ALTA**.

Tres dimensiones (Integridad, Autenticidad, Trazabilidad) están valoradas como ALTO, por lo que:

> **Categoría del sistema: ALTA**

---

## 7. Consecuencias de la categorización

La categoría ALTA implica que DentaCare debe aplicar el conjunto **completo** de medidas del Anexo II del RD 311/2022, incluyendo refuerzos específicos de nivel ALTO en:

- Marco organizativo (políticas, normativa, procedimientos).
- Marco operacional (planificación, control de accesos, explotación, monitorización).
- Medidas de protección (instalaciones, gestión de personal, equipos, comunicaciones, soportes, aplicaciones, información, servicios).

El detalle de medidas requeridas y el estado actual de cada una se desarrolla en el [GAP analysis](../05-gap-analysis/).

---

## 8. Observación didáctica

> **Nota sobre la categoría asignada**
> 
> En un caso real, una clínica dental podría discutir si el sistema es realmente de categoría ALTA o si bastaría con MEDIA, dado que el impacto sobre la salud, aunque posible, no es comparable al de un hospital. Este proyecto opta por la categoría ALTA porque permite trabajar con el conjunto más amplio de medidas y demostrar la metodología completa.
> 
> En la práctica profesional, la categorización siempre se valida con el responsable del sistema y, si procede, con la autoridad competente.

---

## Referencias

- **Real Decreto 311/2022**, de 3 de mayo, por el que se regula el Esquema Nacional de Seguridad.
- **Anexo I** del RD 311/2022 — Categorización de los sistemas de información.
- **Anexo II** del RD 311/2022 — Medidas de seguridad.
- **Guía CCN-STIC 803** — Valoración de sistemas en el ENS.
