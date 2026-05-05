# Catálogo de amenazas

Identificación de las amenazas aplicables a los activos de DentaCare según el catálogo de **MAGERIT**.

---

## 1. Tipología de amenazas (MAGERIT)

MAGERIT clasifica las amenazas en cuatro grupos:

| Código | Grupo | Descripción |
|---|---|---|
| **[N]** | Desastres naturales | Eventos naturales que pueden afectar a los activos |
| **[I]** | Origen industrial | Fallos de origen humano no intencionado o industrial |
| **[E]** | Errores y fallos no intencionados | Errores de personas o software |
| **[A]** | Ataques intencionados | Acciones deliberadas de personas |

---

## 2. Amenazas aplicables a DentaCare

### 2.1. Desastres naturales [N]

| ID | Amenaza | Activos afectados | Dimensiones |
|---|---|---|---|
| N.1 | Fuego | L-01 (sala técnica), HW-01, HW-06 | D |
| N.2 | Daños por agua | L-01, HW-01, HW-06 | D |
| N.* | Otros desastres naturales (terremoto, tormenta) | L-01, AUX-* | D |

### 2.2. Origen industrial [I]

| ID | Amenaza | Activos afectados | Dimensiones |
|---|---|---|---|
| I.1 | Fuego (origen industrial) | L-01, HW-01 | D |
| I.2 | Daños por agua (origen industrial: fugas) | L-01, HW-01 | D |
| I.3 | Contaminación mecánica (polvo, suciedad) | HW-01, HW-02, HW-03 | D |
| I.4 | Contaminación electromagnética | HW-*, COM-01 | D |
| I.5 | Avería de origen físico o lógico | HW-01, HW-02, HW-03, SW-* | D |
| I.6 | Corte del suministro eléctrico | HW-01, AUX-01 (UPS limita el impacto) | D |
| I.7 | Condiciones inadecuadas de temperatura/humedad | HW-01, AUX-03 | D |
| I.8 | Fallo de servicios de comunicaciones | COM-03, S-02, S-03 | D |
| I.9 | Interrupción de otros servicios esenciales | SW-04 (gestor de citas SaaS) | D |
| I.10 | Degradación de los soportes de almacenamiento | Media-01, Media-02 | I, D |

### 2.3. Errores y fallos no intencionados [E]

| ID | Amenaza | Activos afectados | Dimensiones |
|---|---|---|---|
| E.1 | Errores de los usuarios | D-01, D-03, S-01 | I, C, D |
| E.2 | Errores del administrador del sistema | HW-01, SW-*, configuraciones | I, C, D |
| E.3 | Errores de monitorización (logs) | D-07 | T |
| E.4 | Errores de configuración | HW-04 (firewall), SW-* | C, I, D |
| E.7 | Deficiencias en la organización | Todos | C, I, D, A, T |
| E.8 | Difusión de software dañino | SW-*, HW-* | C, I, D |
| E.14 | Escapes de información | D-01, D-02, D-03 | C |
| E.15 | Alteración accidental de la información | D-01, D-05, D-07 | I |
| E.18 | Destrucción de información | D-01, D-06 | D |
| E.19 | Fugas de información | D-01, D-02, D-03 | C |
| E.20 | Vulnerabilidades de los programas (software) | SW-01, SW-02, SW-04, SW-05, SW-06 | C, I, D |
| E.21 | Errores de mantenimiento / actualización de programas | SW-* | I, D |
| E.23 | Errores de mantenimiento / actualización de hardware | HW-* | D |
| E.24 | Caída del sistema por agotamiento de recursos | HW-01, SW-01 | D |
| E.25 | Pérdida de equipos | HW-02 (puestos), portátiles | C, D |
| E.28 | Indisponibilidad del personal | P-01, P-02, P-04 | D |

### 2.4. Ataques intencionados [A]

| ID | Amenaza | Activos afectados | Dimensiones |
|---|---|---|---|
| A.3 | Manipulación de los registros de actividad (logs) | D-07 | I, T |
| A.4 | Manipulación de la configuración | HW-04, SW-* | C, I, D |
| A.5 | Suplantación de la identidad del usuario | S-01, D-01 | C, I, A |
| A.6 | Abuso de privilegios de acceso | D-01, S-01, P-04 | C, I |
| A.7 | Uso no previsto | HW-02, COM-02 | C, D |
| A.8 | Difusión de software dañino (malware, ransomware) | SW-*, HW-*, D-01, D-06 | C, I, D |
| A.11 | Acceso no autorizado | D-01, D-02, S-01 | C |
| A.13 | Repudio (negar haber hecho algo) | D-01, D-05, D-07 | T, A |
| A.14 | Interceptación de información (escucha) | COM-01, COM-03 | C |
| A.15 | Modificación deliberada de información | D-01, D-05 | I |
| A.18 | Destrucción de información | D-01, D-06 | D |
| A.19 | Divulgación de información | D-01, D-02 | C |
| A.22 | Manipulación de programas | SW-01, SW-05 | C, I, D |
| A.23 | Manipulación de equipos | HW-01, HW-02 | C, I, D |
| A.24 | Denegación de servicio (DoS / DDoS) | S-02, COM-03, SW-04 | D |
| A.25 | Robo (físico) | HW-02, Media-03 | C, D |
| A.26 | Ataque destructivo (vandalismo, sabotaje) | HW-*, L-* | D |
| A.28 | Indisponibilidad del personal (chantaje, baja por causa externa) | P-01, P-04 | D |
| A.29 | Extorsión (incluye ransomware con doble extorsión) | D-01, D-06 | C, D |
| A.30 | Ingeniería social (phishing dirigido) | P-* | C, I |

---

## 3. Amenazas más relevantes para DentaCare

A partir del catálogo aplicado y considerando la actividad de la clínica, las amenazas más probables y de mayor impacto son:

| Prioridad | Amenaza | Por qué es relevante para DentaCare |
|---|---|---|
| 🔴 Alta | A.8 / A.29 — Ransomware | Sector salud entre los más atacados. Caso reciente en clínica del entorno. Backups no verificados. |
| 🔴 Alta | A.30 — Phishing dirigido | Personal sin formación específica en ciberseguridad. Punto de entrada habitual. |
| 🔴 Alta | E.20 — Vulnerabilidades de software | Klinikare instalado on-premise sin gestión de parches formal. |
| 🟠 Media-Alta | A.11 — Acceso no autorizado | Sin MFA en servicios cloud, sin segmentación de red. |
| 🟠 Media-Alta | E.18 / A.18 — Destrucción de información | Backups sin verificación. Pérdida de historiales clínicos sería crítica. |
| 🟠 Media-Alta | A.5 — Suplantación de usuario | Sin política de contraseñas. Sin doble factor. |
| 🟠 Media-Alta | E.1 / E.15 — Error humano | Personal no formado, accesos no segregados. |
| 🟡 Media | I.6 — Corte de suministro eléctrico | UPS existe pero sin pruebas periódicas. |
| 🟡 Media | I.5 — Avería de hardware | Servidor único sin redundancia. |
| 🟡 Media | A.14 — Interceptación de comunicaciones | Wi-Fi de invitados sin segmentación efectiva de la red corporativa. |

---

## 4. Próximo paso

Estas amenazas, cruzadas con los activos valorados en el [apartado anterior](./valoracion-activos.md), permiten construir la [matriz de riesgos](./matriz-riesgos.md) para calcular el riesgo (impacto × probabilidad) de cada combinación relevante.
