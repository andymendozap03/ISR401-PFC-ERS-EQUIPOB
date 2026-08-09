# Changelog

Todos los cambios relevantes del ERS/SRS de **MundiPets** se documentan en este archivo.
El formato sigue el esquema `[Versión] - [Fecha] / Añadido / Cambiado / Eliminado`, tal
como exige la guía de la PE4 (Unidad IV).

> Nota de versionado: la versión declarada en este archivo (`[1.0]`, `[1.1]`) corresponde
> al nombre del archivo del ERS dentro del repositorio (`ERS_SRS_2A_v1.0` → `v1.1`). La
> versión interna del propio documento, registrada en su portada e historial de
> revisiones, es `3.0` → `3.1` (continuación de las Entregas 1A=1.0, 1B=2.0, 2A=3.0).

## [1.1] - 09/08/2026

> Versión resultante de la inspección formal Fagan y de la aprobación del CCB en la PE4
> (Unidad IV). Corresponde a la versión interna **3.1** del documento.

### Añadido
- **RF-26 — Eliminar cuenta y datos personales.** Nuevo requisito funcional aprobado por
  RFC-01, que implementa el mecanismo de eliminación exigido por RD-06 y el derecho de
  supresión reconocido en RL-04 (Art. 15 LOPDP).
- **Criterio de verificación** en las 9 restricciones de diseño (RD-01 a RD-09), que
  antes carecían de este campo a diferencia de los requisitos funcionales y no
  funcionales (defecto de completitud detectado en la inspección).

### Cambiado
- **RNF-02 (Disponibilidad del sistema)** — acotado al entorno de producción con backend
  desplegado; se aclara explícitamente que no es exigible ni medible sobre el MVP local
  (`localStorage`, sin servidor). Aprobado por RFC-02.
- **RF-10 (Gestionar recordatorios de controles preventivos)** — se formaliza como
  comportamiento obligatorio el canal de respaldo *in-app* ante la indisponibilidad del
  proveedor externo de mensajería (WhatsApp Business API), antes solo mencionado en el
  campo "Impacto" de RD-08. Aprobado por RFC-03.
- **RF-24 (Trazabilidad de cepa, lote y aplicador de cada vacuna)** — prioridad MoSCoW
  elevada de *Should* a *Must*, por ser una dependencia bloqueante del paso 4 de CU-02
  (*Must*). Se actualizaron 4 tablas relacionadas (análisis INVEST, priorización MoSCoW,
  cobertura del MVP y matriz de trazabilidad extendida) para mantener consistencia.
- **RF-12 (Verificar la identidad de los usuarios)** — se agrega el actor "Veterinaria" y
  la exigencia de validar el número de registro profesional ante el ente regulador
  competente.
- **RF-05 (Gestionar solicitudes de adopción)** — se agrega el actor "Refugio de
  animales", alineando el requisito con la Tabla 5 (clases y características de
  usuarios).
- **RF-02 (Gestionar historial médico de la mascota)** — se agrega "fecha de aplicación"
  a las Entradas del registro de vacunas.
- **RF-01 (Registrar mascota)** — se incorpora "descripción" a la narrativa, ya
  presente en el campo Entradas pero ausente de la descripción del requisito.
- **RF-18 (Gestionar el flujo de solicitud de adopción por etapas)** — se unifica la
  terminología de "resultado de visita" a "resultado de visita al hogar", consistente
  con HU-13.
- **RNF-04, RNF-13, RNF-14, RNF-15** — se define el tamaño y perfil de la muestra de
  usuarios de prueba (mínimo 15: 10 no técnicos, 5 técnicos) en el criterio de
  verificación, antes no especificado.
- **RNF-11 (Portabilidad entre navegadores y dispositivos)** — se agrega Microsoft Edge
  a los navegadores soportados (de 3 a 4), consistente con la Sección 2.5 (Entorno
  operativo).
- **RNF-16 (Confidencialidad de datos de ubicación y contacto)** — se acota el radio de
  ocultamiento de "≥ 1 km" (sin techo) a un rango configurable "entre 1 km y 5 km".
- **Definición de "titular" (Sección 2, requisitos legales)** — se reformula para
  eliminar la contradicción con RL-07 sobre la protección indirecta del historial
  médico de la mascota.
- **Matriz de trazabilidad extendida (Sección 5.5)** — corregida la inconsistencia
  numérica "40 filas" vs. "50 elementos"; la matriz ahora declara y cubre
  consistentemente **59 filas (TR-01 a TR-59)**, incorporando los 9 requisitos legales
  (RL-01 a RL-09) que antes quedaban fuera de su cobertura declarada.
- **Priorización MoSCoW de RF-04** — se añade la justificación explícita de por qué se
  mantiene la prioridad *Should* pese al bajo porcentaje de calificación máxima (42,1 %)
  obtenido en la encuesta de importancia declarada.
- **CA-14 (escenario de aceptación de HU-14)** — se agrega el mensaje de feedback visual
  mostrado al usuario en el escenario de rechazo, antes ausente.
- **Portada e historial de revisiones del ERS** — versión interna del documento
  actualizada de `3.0` a `3.1`, con la fila correspondiente agregada a la tabla de
  historial.

### Eliminado
- N/A

---

## [1.0] - 2026-08-02

> Versión base del ERS/SRS, correspondiente a la Entrega 2A del PFC.

### Añadido
- Versión completa del ERS/SRS de MundiPets según IEEE/ISO/IEC 29148:2018, importada al
  repositorio `ISR401-PFC-ERS-EquipoB`.
- Fuentes LaTeX del ERS (`01_ERS/fuentes_tex/ERS_SRS_2A_v1.0/`), figuras y referencias
  bibliográficas.
- Estructura inicial de carpetas para la PE4 (Unidad IV): `02_Inspeccion/`, `03_CCB/`,
  `04_Trazabilidad/`, `05_Informe/`, `06_Evidencias/`, `07_Borradores/`.

### Cambiado
- N/A

### Eliminado
- N/A
