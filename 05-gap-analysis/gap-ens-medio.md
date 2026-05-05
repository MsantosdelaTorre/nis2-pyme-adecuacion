# GAP analysis frente al ENS

Análisis de la diferencia entre el estado actual de DentaCare y los requisitos del **Esquema Nacional de Seguridad** para un sistema de categoría **ALTA** (definida en el [apartado 02](../02-marco-normativo/ens-categorizacion.md)).

---

## 1. Metodología

### 1.1. Fuente de los requisitos

Las medidas evaluadas son las del **Anexo II del RD 311/2022**, agrupadas en tres marcos:

| Marco | Código | Contenido |
|---|---|---|
| Marco organizativo | **org** | Política, normativa, procedimientos, autorización |
| Marco operacional | **op** | Planificación, control de accesos, explotación, monitorización, continuidad |
| Medidas de protección | **mp** | Instalaciones, personal, equipos, comunicaciones, soportes, aplicaciones, información, servicios |

### 1.2. Escala de madurez (CMM)

Cada medida se valora en una escala 0-5:

| Nivel | Estado |
|---|---|
| **0** | Inexistente — no se realiza |
| **1** | Inicial — se hace de forma reactiva, sin documentar |
| **2** | Repetible — se hace de forma similar, sin estandarizar |
| **3** | Definido — documentado y estandarizado |
| **4** | Gestionado — se mide y supervisa |
| **5** | Optimizado — se mejora de forma continua |

Para una categoría **ALTA**, el ENS exige nivel **4 (gestionado)** como mínimo en la mayoría de medidas.

### 1.3. Cálculo del GAP

GAP = Nivel requerido − Nivel actual

Un GAP positivo indica que existe una brecha que cubrir.

---

## 2. Marco organizativo (org)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| org.1 | Política de seguridad | 4 | 0 | 4 | No existe política documentada |
| org.2 | Normativa de seguridad | 4 | 0 | 4 | No existe normativa interna |
| org.3 | Procedimientos de seguridad | 4 | 1 | 3 | Procedimientos informales, no documentados |
| org.4 | Proceso de autorización | 4 | 1 | 3 | Autorizaciones verbales, sin registro |

---

## 3. Marco operacional (op)

### 3.1. Planificación

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.pl.1 | Análisis de riesgos | 4 | 0 | 4 | Este proyecto es el primer análisis formal |
| op.pl.2 | Arquitectura de seguridad | 4 | 1 | 3 | Arquitectura básica (firewall + AV) sin diseño formal |
| op.pl.3 | Adquisición de nuevos componentes | 4 | 1 | 3 | Adquisiciones sin criterios de seguridad definidos |
| op.pl.4 | Dimensionamiento / capacidad | 4 | 2 | 2 | El proveedor de TI dimensiona, pero sin documentar |
| op.pl.5 | Componentes certificados | 4 | 1 | 3 | No se exige certificación a los componentes |

### 3.2. Control de accesos

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.acc.1 | Identificación | 4 | 2 | 2 | Cada usuario tiene cuenta nominal en Klinikare |
| op.acc.2 | Requisitos de acceso | 4 | 1 | 3 | No hay matriz de roles documentada |
| op.acc.3 | Segregación de funciones | 4 | 1 | 3 | El proveedor de TI tiene acceso total |
| op.acc.4 | Proceso de gestión de derechos | 4 | 1 | 3 | Altas y bajas sin procedimiento formal |
| op.acc.5 | Mecanismo de autenticación | 4 | 1 | 3 | Solo contraseña, sin MFA |
| op.acc.6 | Acceso local | 4 | 2 | 2 | Cuentas locales en puestos |
| op.acc.7 | Acceso remoto | 4 | 0 | 4 | El proveedor de TI accede sin VPN ni control |

### 3.3. Explotación

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.exp.1 | Inventario de activos | 4 | 1 | 3 | No existe inventario formal previo a este proyecto |
| op.exp.2 | Configuración de seguridad | 4 | 1 | 3 | Configuraciones por defecto en muchos casos |
| op.exp.3 | Gestión de la configuración | 4 | 1 | 3 | Sin control de cambios documentado |
| op.exp.4 | Mantenimiento y actualización | 4 | 2 | 2 | Updates automáticos en M365, no en Klinikare |
| op.exp.5 | Gestión de cambios | 4 | 0 | 4 | No hay procedimiento de gestión de cambios |
| op.exp.6 | Protección frente a código dañino | 4 | 2 | 2 | Windows Defender activo, sin EDR |
| op.exp.7 | Gestión de incidentes | 4 | 0 | 4 | No hay procedimiento de respuesta a incidentes |
| op.exp.8 | Registro de la actividad | 4 | 1 | 3 | Logs existen pero no se monitorizan |
| op.exp.9 | Registro de la gestión de incidentes | 4 | 0 | 4 | No se registran formalmente |
| op.exp.10 | Protección de los registros | 4 | 1 | 3 | Logs sin protección frente a manipulación |
| op.exp.11 | Protección de claves criptográficas | 4 | 1 | 3 | Sin gestión formal de claves |

### 3.4. Servicios externos

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.ext.1 | Contratación y acuerdos de nivel de servicio | 4 | 2 | 2 | Contratos básicos, sin SLA detallado |
| op.ext.2 | Gestión diaria | 4 | 1 | 3 | Sin seguimiento periódico de proveedores |
| op.ext.3 | Protección de la cadena de suministro | 4 | 0 | 4 | No se evalúa la postura de seguridad de proveedores |

### 3.5. Continuidad del servicio

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.cont.1 | Análisis de impacto (BIA) | 4 | 0 | 4 | Este proyecto es el primer BIA |
| op.cont.2 | Plan de continuidad | 4 | 0 | 4 | No existe |
| op.cont.3 | Pruebas periódicas | 4 | 0 | 4 | No se realizan |
| op.cont.4 | Medios alternativos | 4 | 1 | 3 | Sin acuerdos formales para alternativas |

### 3.6. Monitorización del sistema

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| op.mon.1 | Detección de intrusión | 4 | 0 | 4 | Sin IDS/IPS ni SIEM |
| op.mon.2 | Sistema de métricas | 4 | 0 | 4 | Sin KPIs ni cuadros de mando |
| op.mon.3 | Vigilancia | 4 | 1 | 3 | Vigilancia solo cuando ocurre algo, reactiva |

---

## 4. Medidas de protección (mp)

### 4.1. Protección de las instalaciones (mp.if)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.if.1 | Áreas separadas y con control de acceso | 4 | 2 | 2 | Sala técnica con cerradura, pero sin control de acceso registrado |
| mp.if.2 | Identificación de las personas | 4 | 1 | 3 | Sin registro de visitas a sala técnica |
| mp.if.3 | Acondicionamiento de los locales | 4 | 3 | 1 | Climatización y UPS existen |
| mp.if.4 | Energía eléctrica | 4 | 3 | 1 | UPS instalado, sin grupo electrógeno |
| mp.if.5 | Protección frente a incendios | 4 | 2 | 2 | Detector básico, sin sistema de extinción |
| mp.if.6 | Protección frente a inundaciones | 4 | 2 | 2 | Sala en planta baja sin elevación |
| mp.if.7 | Registro de entrada y salida de equipos | 4 | 0 | 4 | No se registra |

### 4.2. Gestión del personal (mp.per)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.per.1 | Caracterización del puesto | 4 | 1 | 3 | Sin descripción formal de funciones de seguridad |
| mp.per.2 | Deberes y obligaciones | 4 | 1 | 3 | Cláusulas básicas en contratos, sin acuerdos específicos |
| mp.per.3 | Concienciación | 4 | 0 | 4 | Sin formación en ciberseguridad al personal |
| mp.per.4 | Formación | 4 | 0 | 4 | Sin plan de formación |

### 4.3. Protección de los equipos (mp.eq)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.eq.1 | Puesto de trabajo despejado | 4 | 2 | 2 | Política informal de pantalla limpia |
| mp.eq.2 | Bloqueo de puesto de trabajo | 4 | 2 | 2 | Bloqueo automático configurado, sin política |
| mp.eq.3 | Protección de portátiles | 4 | 1 | 3 | Sin cifrado de disco en portátiles |
| mp.eq.4 | Otros dispositivos conectados a la red | 4 | 1 | 3 | Equipos rayos X conectados sin endurecer |

### 4.4. Protección de las comunicaciones (mp.com)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.com.1 | Perímetro seguro | 4 | 2 | 2 | Firewall hardware, sin reglas formales |
| mp.com.2 | Protección de la confidencialidad | 4 | 1 | 3 | Sin cifrado de tráfico interno |
| mp.com.3 | Protección de la integridad y autenticidad | 4 | 1 | 3 | Sin firmas en comunicaciones |
| mp.com.4 | Segregación de redes | 4 | 1 | 3 | Wi-Fi de invitados separado, pero sin VLANs internas |

### 4.5. Protección de los soportes (mp.si)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.si.1 | Etiquetado | 4 | 0 | 4 | No se etiquetan soportes |
| mp.si.2 | Criptografía | 4 | 0 | 4 | Backups sin cifrar |
| mp.si.3 | Custodia | 4 | 1 | 3 | NAS en sala técnica, sin custodia formal |
| mp.si.4 | Transporte | 4 | 1 | 3 | Sin procedimiento para soportes que salgan de la sede |
| mp.si.5 | Borrado y destrucción | 4 | 0 | 4 | Sin procedimiento de borrado seguro |

### 4.6. Protección de las aplicaciones (mp.sw)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.sw.1 | Desarrollo seguro | 4 | N/A | - | DentaCare no desarrolla, usa software de terceros |
| mp.sw.2 | Aceptación y puesta en servicio | 4 | 1 | 3 | Sin pruebas formales antes de poner en producción |

### 4.7. Protección de la información (mp.info)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.info.1 | Datos de carácter personal | 4 | 2 | 2 | Cumplimiento básico RGPD, sin documentación completa |
| mp.info.2 | Calificación de la información | 4 | 0 | 4 | Sin clasificación por niveles |
| mp.info.3 | Cifrado | 4 | 1 | 3 | Cifrado solo en tránsito (HTTPS), no en reposo |
| mp.info.4 | Firma electrónica | 4 | 2 | 2 | Firma digital en facturación a mutua |
| mp.info.5 | Sellos de tiempo | 4 | 0 | 4 | No se utilizan |
| mp.info.6 | Limpieza de documentos | 4 | 1 | 3 | Sin procedimiento formal |
| mp.info.7 | Copias de seguridad | 4 | 2 | 2 | Backups diarios, sin verificación ni offline |

### 4.8. Protección de los servicios (mp.s)

| Código | Medida | Requerido | Actual | GAP | Comentario |
|---|---|---|---|---|---|
| mp.s.1 | Protección del correo electrónico | 4 | 2 | 2 | Anti-spam básico de M365 |
| mp.s.2 | Protección de servicios y aplicaciones web | 4 | 1 | 3 | Sin WAF, sin pruebas de seguridad |
| mp.s.3 | Protección frente a denegación de servicio | 4 | 1 | 3 | Sin medidas específicas anti-DDoS |

---

## 5. Resumen del GAP

| Marco | Medidas evaluadas | GAP medio | Estado |
|---|---|---|---|
| Marco organizativo (org) | 4 | 3,5 | 🔴 Muy deficiente |
| Marco operacional — planificación (op.pl) | 5 | 3,0 | 🟠 Deficiente |
| Marco operacional — control de accesos (op.acc) | 7 | 2,9 | 🟠 Deficiente |
| Marco operacional — explotación (op.exp) | 11 | 3,0 | 🟠 Deficiente |
| Marco operacional — servicios externos (op.ext) | 3 | 3,0 | 🟠 Deficiente |
| Marco operacional — continuidad (op.cont) | 4 | 3,8 | 🔴 Muy deficiente |
| Marco operacional — monitorización (op.mon) | 3 | 3,7 | 🔴 Muy deficiente |
| Protección de instalaciones (mp.if) | 7 | 2,1 | 🟡 Mejorable |
| Gestión del personal (mp.per) | 4 | 3,5 | 🔴 Muy deficiente |
| Protección de equipos (mp.eq) | 4 | 2,5 | 🟠 Deficiente |
| Protección de comunicaciones (mp.com) | 4 | 2,8 | 🟠 Deficiente |
| Protección de soportes (mp.si) | 5 | 3,2 | 🟠 Deficiente |
| Protección de aplicaciones (mp.sw) | 2 | 3,0 | 🟠 Deficiente |
| Protección de la información (mp.info) | 7 | 2,7 | 🟠 Deficiente |
| Protección de servicios (mp.s) | 3 | 2,7 | 🟠 Deficiente |

---

## 6. Conclusiones

### 6.1. Áreas con mayor brecha

Los tres ámbitos con mayor GAP (≥ 3,5) son los que deben atenderse primero:

1. **Continuidad del servicio (op.cont)** — sin BIA, sin plan, sin pruebas.
2. **Monitorización (op.mon)** — sin SIEM, sin KPIs, sin detección.
3. **Gestión del personal (mp.per)** — sin formación ni concienciación.
4. **Marco organizativo (org)** — sin políticas ni procedimientos formales.

### 6.2. Áreas mejor posicionadas

Las áreas con menor GAP son las que dependen de medidas físicas y básicas:

- **Protección de instalaciones (mp.if)** — climatización, UPS y sala con cerradura existen.
- **Protección de la información — copias (mp.info.7)** — los backups existen, aunque sin verificación.

### 6.3. Estado global

DentaCare presenta un nivel de madurez medio inferior a **2** en la mayoría de las áreas, frente al nivel **4** exigido para un sistema de categoría ALTA. La brecha global es **alta** y requiere un plan de tratamiento estructurado.

El plan se desarrolla en el [apartado 06](../06-plan-tratamiento/).

---

## 7. Observaciones

> Las valoraciones del estado actual son orientativas. En un proyecto real cada medida se evaluaría con evidencias documentales, entrevistas y pruebas técnicas.

> El cumplimiento del 100 % de las medidas no es alcanzable en una primera iteración. La estrategia recomendada es priorizar por riesgo y avanzar de forma incremental.
