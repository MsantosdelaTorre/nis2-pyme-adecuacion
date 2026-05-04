# DentaCare — Descripción de la organización

Este documento describe la organización ficticia sobre la que se construye el caso práctico.

---

## 1. Datos generales

| Campo | Valor |
|---|---|
| Nombre comercial | DentaCare |
| Razón social | DentaCare Salud Dental S.L. |
| Sector | Sanidad — Odontología |
| Ubicación | Sevilla, España |
| Sedes | 1 (sede única) |
| Empleados | 15 |
| Facturación anual aproximada | 850.000 € |
| Año de constitución | 2014 |

DentaCare es una clínica dental de tamaño medio que presta servicios odontológicos generales y especializados (ortodoncia, implantología, estética dental). Trabaja tanto con pacientes particulares como con pacientes derivados de mutuas privadas y de un convenio con una mutua del sector público.

---

## 2. Estructura organizativa

| Rol | Personas |
|---|---|
| Dirección / Gerencia | 1 |
| Odontólogos | 6 |
| Higienistas dentales | 3 |
| Auxiliares de clínica | 2 |
| Recepción / Administración | 2 |
| Responsable de TI (externo, a tiempo parcial) | 1 |

No existe un responsable de seguridad de la información dedicado. Las funciones de TI están externalizadas a un proveedor local que da soporte bajo demanda.

---

## 3. Servicios prestados

1. **Asistencia odontológica general:** revisiones, limpiezas, empastes, endodoncias.
2. **Ortodoncia:** brackets, alineadores invisibles.
3. **Implantología:** colocación de implantes y prótesis.
4. **Estética dental:** blanqueamientos, carillas.
5. **Servicio a mutua pública:** atención odontológica a beneficiarios de una mutua del sector público mediante convenio.

---

## 4. Activos de información (resumen)

Los activos se detallan en el inventario completo (apartado 03), pero a alto nivel:

- **Datos:** historiales clínicos, radiografías digitales, datos de facturación, datos personales de pacientes y empleados.
- **Aplicaciones:** software de gestión clínica (Klinikare), gestor de citas web, software de contabilidad, correo corporativo.
- **Infraestructura:** un servidor local con la base de datos clínica, 8 puestos de trabajo, 4 equipos de radiografía digital conectados en red, router/firewall del proveedor de internet, switch gestionable.
- **Servicios externos:** alojamiento de la web corporativa y el gestor de citas en un proveedor cloud español, copias de seguridad automatizadas a un NAS externo.

---

## 5. Infraestructura técnica
```
        Internet
            │
        [ Router ISP ]
            │
        [ Firewall hardware ]
            │
        [ Switch gestionable ]
        │     │       │
   [Puestos] [Servidor] [Equipos rayos X]
   (8 PCs)   (Klinikare  (4 unidades)
              + BBDD)
```
- **Servidor local:** Windows Server 2019, almacena la base de datos del software de gestión clínica.
- **Puestos de trabajo:** Windows 10/11, Microsoft 365 Business Basic.
- **Red:** LAN cableada en consultas, Wi-Fi separado para invitados.
- **Backups:** diarios al NAS externo, sin verificación periódica de restauración.
- **Antivirus:** Windows Defender en todos los equipos.

---

## 6. Datos tratados

DentaCare trata las siguientes categorías de datos personales:

- **Datos identificativos:** nombre, DNI, dirección, teléfono, email.
- **Datos de salud (categoría especial RGPD):** historial clínico, diagnósticos, tratamientos, radiografías.
- **Datos económicos:** información de facturación y, en algunos casos, datos bancarios.
- **Datos laborales** (de los empleados).

El volumen estimado es de **aproximadamente 4.500 pacientes activos** y un histórico de unos 12.000 expedientes.

---

## 7. Contexto regulatorio aplicable

| Norma | Aplicabilidad |
|---|---|
| **Directiva NIS2** (UE 2022/2555) | Aplicable como **entidad importante** (sector salud, mediana empresa). |
| **RGPD** (UE 2016/679) | Aplicable por tratamiento de datos personales, especialmente categoría especial (salud). |
| **LOPDGDD** (LO 3/2018) | Aplicable como adaptación nacional del RGPD. |
| **ENS** (RD 311/2022) | Aplicable parcialmente por la prestación de servicios al sector público (mutua pública). |
| **Ley 41/2002** (autonomía del paciente) | Aplicable por las obligaciones sobre historia clínica. |

El detalle de la aplicabilidad y la categorización ENS asignada se desarrolla en el apartado [02 — Marco normativo](../02-marco-normativo/).

---

## 8. Estado de seguridad inicial

A modo de fotografía de partida, la situación previa al proyecto de adecuación es la siguiente:

- ❌ No hay análisis de riesgos formal previo.
- ❌ No hay políticas de seguridad documentadas.
- ❌ No hay plan de respuesta a incidentes.
- ❌ Las copias de seguridad se realizan automáticamente pero no se verifica su restauración.
- ❌ No hay segmentación de red entre equipos clínicos y administrativos.
- ❌ No existe MFA en los servicios cloud.
- ⚠️ El acceso al software de gestión clínica usa contraseñas, pero no hay política de complejidad ni de caducidad.
- ✅ Existe firewall hardware perimetral.
- ✅ Existe antivirus en todos los puestos.
- ✅ El servidor está en una sala con cerradura.

Este estado inicial será el punto de partida del [GAP analysis](../05-gap-analysis/) frente a los requisitos del ENS.

---

## 9. Motivación del proyecto

DentaCare ha decidido iniciar un proceso de adecuación normativa por tres motivos:

1. **Obligación legal:** la entrada en vigor efectiva de NIS2 le aplica directamente.
2. **Renovación del convenio con la mutua pública:** la mutua exige a sus proveedores acreditar adecuación al ENS de categoría Media.
3. **Gestión del riesgo:** un incidente reciente en una clínica del entorno (cifrado de historiales por ransomware) ha hecho que la dirección priorice la seguridad.
