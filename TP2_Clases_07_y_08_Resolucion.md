# TP2 — Clases 07 y 08: validación crítica de una respuesta de IA

[TOC]

> Borrador para pasar a las guías. Los datos personales quedan en blanco. La **valoración inicial** (Clase 07, 3.B y 3.C) tiene que ser *tu* primera impresión: la de abajo es un ejemplo y conviene ajustarla a lo que pensaste vos al leerla. Todas las fuentes son las del dossier simulado de la Clase 07 (A, B, C): no hay referencias externas inventadas.

---

## Clase 07 — Primer avance

### 1. Datos

| Campo | Registro |
|---|---|
| Apellido y nombre | |
| Carrera / comisión | |
| Fecha | |
| Título del TP2 | Validación crítica de una respuesta sobre mantenimiento |
| IA adicional | Claude (Anthropic), 19/10/2026, como apoyo para organizar el registro. Las clasificaciones y decisiones se revisaron contra el dossier. |
| Archivo | TP2_Avance1_Apellido_Nombre_CIRAD.pdf |

### 3. Leer y detectar hallazgos

**A. Respuesta original (se conserva íntegra):**

> “Conviene comenzar por la climatización, que afecta al 80 % de los usuarios. Las filtraciones son superficiales y pueden esperar; las fallas eléctricas se deben a sobrecargas por mal uso. Como los laboratorios tienen pocos usuarios, sus equipos deben quedar al final. Un mantenimiento mensual reducirá los costos un 30 %. La opinión de la administración es suficiente para fijar el orden. Este plan puede aplicarse de inmediato sin inspecciones adicionales”.

**B. Valoración inicial:** Requiere revisión. Está bien escrita y propone un orden concreto, pero da cifras sin decir de dónde salen y afirma causas sin diagnóstico.

**C. Qué resultó convincente:** el “80 % de los usuarios” y el “30 % de ahorro”: los números precisos le dan apariencia de respaldo técnico.

**D. Primeros hallazgos:**

| ID | Fragmento | Categoría | Justificación provisional |
|---|---|---|---|
| 1 | “la climatización, que afecta al 80 % de los usuarios” | Supuesto / dato sin fuente | La cifra no tiene origen. Usa la cantidad de afectados como único criterio. |
| 2 | “Las filtraciones son superficiales y pueden esperar; las fallas eléctricas se deben a sobrecargas por mal uso” | Supuesto (posible error) | Da por hecho la gravedad y la causa sin inspección. Omite el riesgo de seguridad de agua cerca de instalaciones eléctricas. |
| 3 | “Como los laboratorios tienen pocos usuarios, sus equipos deben quedar al final” | Sesgo + omisión | Privilegia el número de usuarios y omite la continuidad de actividades académicas. |
| 4 | “Un mantenimiento mensual reducirá los costos un 30 %” | Supuesto / dato sin fuente | Cifra precisa sin estimación que la respalde. |
| 5 | “La opinión de la administración es suficiente para fijar el orden” | Sesgo | Excluye a usuarios de aulas y laboratorios y al criterio técnico. |
| 6 | “puede aplicarse de inmediato sin inspecciones adicionales” | Omisión / posible error | Saltea la revisión técnica previa. |

**E. Impacto en la decisión:** se postergaría un riesgo eléctrico (agua + tablero), se dejaría sin resolver un equipo que impide una práctica obligatoria y se asignaría presupuesto con cifras no comprobadas.

**F. Información necesaria:** parte de incidencias, pauta de priorización, relevamiento de usuarios afectados, diagnóstico técnico de cortes y filtraciones, estimación de costos y ahorro.

**G. Primera prioridad — ID 2.** Si es incorrecta, se posterga un riesgo para la seguridad de las personas: es la de mayor impacto.

**H. Segunda prioridad — ID 3.** Define qué queda último. Si el criterio está sesgado, se interrumpe una actividad académica obligatoria.

### 4. Dossier de fuentes

**E. Qué permiten comprobar:** ID 1 y 4 (C1, C2 muestran que no hay datos), ID 2 (A1, A2), ID 3 (A3, B1), ID 5 (C3, B1), ID 6 (B2).

**F. Límites:** el material es simulado y sin fecha. No permite saber la gravedad real de cada problema, ni los costos, ni la causa de los cortes. Para una decisión real harían falta inspección técnica, relevamiento de usuarios y presupuestos.

**G. Fuentes adicionales:** no consulté otras. Pendientes: informe técnico eléctrico, relevamiento de usuarios afectados por climatización, presupuesto por intervención.

### 5. Registro individual

| Componente | Mi registro |
|---|---|
| Hallazgo 1 | Afirma que la climatización afecta al 80 %. Cifra sin fuente: C1 dice que no hay relevamiento. |
| Hallazgo 2 | Afirma que las filtraciones son superficiales y los cortes se deben al mal uso. A1 y A2 lo cuestionan: hay filtración junto a un tablero y la causa no está diagnosticada. |
| Hallazgo 3 | Afirma que los laboratorios van al final por tener pocos usuarios. A3: un equipo impide una práctica obligatoria; B1 incluye la continuidad de actividades. |
| Hallazgo 4 | Afirma un ahorro del 30 %. C2: no hay estimación de ahorro. |
| Prioridades | ID 2 (seguridad) e ID 3 (continuidad académica): son los que más cambian el orden propuesto. |
| Límites | No se puede afirmar la gravedad real ni la causa de las fallas, ni cuántos usuarios se ven afectados. |

**Afirmación y evidencia:** “Las filtraciones son superficiales y pueden esperar” ↔ A1: “Se registra una filtración junto a un tablero eléctrico”. *La fuente dice* que la filtración está junto a un tablero. *Mi interpretación* es que eso implica riesgo eléctrico y no puede tratarse como superficial.

**Alcance:** A1 no informa la magnitud de la filtración. Respalda que existe un riesgo, no su gravedad exacta.

**¿Qué puedo sostener?** Que no corresponde postergar la filtración junto al tablero sin inspección (A1, B2). **Pendiente:** la causa de los cortes; hace falta un diagnóstico eléctrico.

**Decisión provisional:** rechazo los ID 2 y 6. Modifico el ID 3. Dejo los ID 1 y 4 pendientes (no verificados, no demostrados falsos).

### 6. Dos contrastes

**Contraste 1 — ID 2**

- **A.** “Las filtraciones son superficiales y pueden esperar; las fallas eléctricas se deben a sobrecargas por mal uso”.
- **B.** Fuente A (parte de incidencias), A1: filtración junto a un tablero eléctrico; A2: cortes cuya causa no fue diagnosticada. Contradice que la filtración pueda esperar y deja sin respaldo la causa atribuida. **Estado:** la parte de la filtración queda *contradicha* en este contexto; la causa de los cortes queda *no verificada*.
- **C. Decisión:** rechazo. La reemplazo por “la filtración junto al tablero y los cortes requieren inspección técnica prioritaria”.
- **D. Pendientes:** la gravedad de la filtración y la causa de los cortes. Hace falta una inspección eléctrica y edilicia.

**Contraste 2 — ID 3**

- **E.** “Como los laboratorios tienen pocos usuarios, sus equipos deben quedar al final”.
- **F.** Fuente A, A3: un equipo fuera de servicio es necesario para una práctica obligatoria. Fuente B (pauta), B1: valorar seguridad, continuidad de actividades, urgencia y costo. **Estado:** contradicha. El criterio de la pauta no es la cantidad de usuarios, y A3 muestra que hay una actividad interrumpida.
- **G. Decisión:** modifico. El equipo de A3 pasa a ser prioritario por continuidad. Los demás equipos se evalúan con los criterios de B1.
- **H. Pendientes:** fecha de la práctica, costo de la reparación y existencia de alternativas (otro equipo, reprogramación). Se resuelve consultando a la cátedra y al área técnica.

### 7. Decisiones humanas

| ID | Decisión | Evidencia y razón | Cambio concreto |
|---|---|---|---|
| 1 | Pendiente | C1: no hay relevamiento. No se demuestra que sea falsa, pero tampoco tiene respaldo. | Elimino el 80 %. La climatización se evalúa con un relevamiento. |
| 2 | Rechazo | A1, A2, B2 | Pasa a ser prioridad de inspección por seguridad. |
| 3 | Modifico | A3, B1 | El equipo para la práctica obligatoria es prioritario. |
| 4 | Pendiente | C2: no hay estimación. | Elimino el 30 %. |

### 8. Comparación y respuesta ajustada

**Original:** sostenía un orden cerrado (climatización primero, laboratorios al final) con certeza alta, cifras sin fuente y sin inspección.

**Revisada:** el orden depende de la seguridad y la continuidad (B1). Las cifras se eliminan (C1, C2). Se explicitan pendientes y la necesidad de revisión técnica (B2).

**Respuesta ajustada (≈165 palabras):**

Con la información disponible no es posible fijar todavía un orden definitivo de mantenimiento. La pauta del ejercicio indica valorar seguridad, continuidad de actividades, urgencia y costo, y exige una revisión técnica previa al plan (B1, B2). Por eso conviene atender primero los riesgos de seguridad: hay una filtración junto a un tablero eléctrico (A1) y cortes eléctricos sin causa diagnosticada (A2). Ambos requieren inspección técnica inmediata, sin dar por sentado que la filtración sea superficial ni que los cortes se deban al mal uso. También es prioritario el equipo de laboratorio fuera de servicio, porque impide una práctica obligatoria (A3): el número de usuarios no es el único criterio. La climatización debe evaluarse, pero no hay relevamiento que respalde que afecta al 80 % de los usuarios (C1), ni estimación que sostenga un ahorro del 30 % (C2). Antes de decidir, falta consultar a usuarios de aulas y laboratorios (C3), contar con el diagnóstico técnico y estimar el costo de cada intervención.

### 9. Revisión entre pares y reflexión

| Pregunta | Respuesta |
|---|---|
| 1. ¿La evidencia sostiene los cambios? | *(completar con tu pareja)* Cada cambio cita un código del dossier. |
| 2. ¿Quedó algún supuesto como hecho? | Hay que cuidar no afirmar que la filtración “es grave”: A1 indica riesgo, no magnitud. |
| 3. ¿Qué cambio incorporo? | *(completar tras el intercambio)* |
| 4. ¿Qué cambió respecto de la valoración inicial? | Pasé de “requiere revisión” a no utilizable tal como está: el orden propuesto era el inverso al que sugiere la evidencia. |
| 5. ¿Qué afirmación revisaría antes de aceptar? | La causa de los cortes: atribuirla al mal uso desplaza la responsabilidad sin diagnóstico. |
| 6. ¿Qué falta comprobar? | Diagnóstico eléctrico, relevamiento de usuarios, costos. Pendiente para la Clase 08. |

---

## Clase 08 — Cierre del TP2

### 1. Datos

| Campo | Registro |
|---|---|
| Apellido y nombre | |
| Carrera / comisión | |
| Fecha | |
| Herramienta(s) de IA | Respuesta original: provista por la cátedra. Apoyo: Claude (Anthropic), 19/10/2026, para organizar el registro. |
| Caso | Priorización del mantenimiento de edificios y equipamientos |

### 3. Recuperación de la Clase 07

**A. Respuesta validada:** la respuesta de IA sobre cómo priorizar el mantenimiento de la Facultad (texto completo en el Avance 1, sección 3.A). Propósito: ordenar reparaciones con presupuesto limitado.

**B. Hallazgos principales:**

- Cifras sin fuente: 80 % de afectados y 30 % de ahorro.
- Supuestos sobre gravedad y causa: filtración “superficial”, cortes por “mal uso”.
- Sesgo por cantidad de usuarios contra los laboratorios.
- Sesgo de voz: sólo la administración decide.
- Omisión de la revisión técnica previa.

### 4. Afirmaciones a verificar

1. “Conviene comenzar por la climatización, que afecta al 80 % de los usuarios”.
2. “Las filtraciones son superficiales y pueden esperar; las fallas eléctricas se deben a sobrecargas por mal uso”.
3. “Como los laboratorios tienen pocos usuarios, sus equipos deben quedar al final”.
4. “Un mantenimiento mensual reducirá los costos un 30 %”.
5. “La opinión de la administración es suficiente para fijar el orden. Este plan puede aplicarse de inmediato sin inspecciones adicionales”.

### 5. Plan de contraste

| Nº | ¿Qué quiero comprobar? | Fuente o procedimiento | ¿Por qué es pertinente? |
|---|---|---|---|
| 1 | Si existe el dato del 80 % y si la cantidad de afectados es el criterio correcto | Nota administrativa (C1) y pauta (B1) | C dice qué datos existen; B fija los criterios. |
| 2 | La gravedad de la filtración y la causa de los cortes | Parte de incidencias (A1, A2) y, en un caso real, inspección técnica | Es el registro directo de los problemas. |
| 3 | Si los laboratorios pueden ir al final | Parte de incidencias (A3) y pauta (B1) | Muestran el impacto académico y el criterio de continuidad. |
| 4 | Si hay base para el 30 % | Nota administrativa (C2) y, en un caso real, estimación de costos del área técnica | Una cifra de ahorro requiere un cálculo documentado. |
| 5 | Quién debe decidir y si hace falta inspección | Pauta (B2) y nota administrativa (C3) | B2 regula el procedimiento; C3 muestra a quién no se consultó. |

### 6. Control de calidad de las fuentes

| Criterio | Evaluación del dossier |
|---|---|
| Autoridad / origen | Material preparado por la cátedra para el ejercicio. Válido dentro del caso simulado, no para la Facultad real. |
| Actualidad | Sin fecha consignada: es un límite. No se puede saber si las incidencias siguen vigentes. |
| Pertinencia | Alta: cada fragmento se refiere directamente a afirmaciones de la respuesta. |
| Independencia | Las fuentes A, B y C son distintas entre sí y distintas de la respuesta de IA. No usé otra IA para “verificar”. |
| Método / trazabilidad | Se cita por código (A1…C3). No se conoce cómo se relevaron las incidencias. |

### 7 y 8. Matriz de validación

**Afirmación 1** — “Conviene comenzar por la climatización, que afecta al 80 % de los usuarios”.

- **Fuente y evidencia:** C1: “No hay relevamiento de usuarios afectados”. B1: los criterios son seguridad, continuidad, urgencia y costo.
- **Resultado:** No verificable (el dato no existe en las fuentes).
- **Decisión:** Reformular.
- **Justificación:** sin relevamiento, el 80 % no puede sostenerse. La climatización se mantiene como problema a evaluar, pero no encabeza el orden por una cifra sin respaldo.

**Afirmación 2** — “Las filtraciones son superficiales y pueden esperar; las fallas eléctricas se deben a sobrecargas por mal uso”.

- **Fuente y evidencia:** A1: filtración junto a un tablero eléctrico. A2: cortes sin causa diagnosticada.
- **Resultado:** No confirmada. La primera parte queda contradicha en este contexto; la causa, no verificable.
- **Decisión:** Corregir.
- **Justificación:** agua junto a un tablero es un riesgo de seguridad, primer criterio de B1. Atribuir los cortes al mal uso es un supuesto sin diagnóstico.

**Afirmación 3** — “Como los laboratorios tienen pocos usuarios, sus equipos deben quedar al final”.

- **Fuente y evidencia:** A3: un equipo fuera de servicio es necesario para una práctica obligatoria. B1: incluye la continuidad de actividades.
- **Resultado:** No confirmada (contradicha por A3 y B1).
- **Decisión:** Corregir.
- **Justificación:** el criterio de cantidad de usuarios no está en la pauta, y hay una actividad obligatoria interrumpida.

**Afirmación 4** — “Un mantenimiento mensual reducirá los costos un 30 %”.

- **Fuente y evidencia:** C2: “No hay estimación de ahorro”.
- **Resultado:** No verificable.
- **Decisión:** Descartar.
- **Justificación:** es una cifra precisa sin cálculo que la respalde. Podría incluirse un mantenimiento preventivo como propuesta, pero sin prometer un ahorro.

**Afirmación 5** — “La opinión de la administración es suficiente para fijar el orden. Este plan puede aplicarse de inmediato sin inspecciones adicionales”.

- **Fuente y evidencia:** B2: “Se requiere revisión técnica previa al plan”. C3: “No se consultó a usuarios de aulas y laboratorios”.
- **Resultado:** No confirmada (contradicha por B2).
- **Decisión:** Corregir.
- **Justificación:** el procedimiento exige revisión técnica, y faltan las voces de quienes usan los espacios.

### 9. Registro de fuentes

| Fuente | Autor / institución | Fecha / versión | Referencia |
|---|---|---|---|
| A. Parte de incidencias del ejercicio | Cátedra CIRAD (material simulado) | No consignada | Dossier Clase 07, A1–A3 |
| B. Pauta de priorización del ejercicio | Cátedra CIRAD (material simulado) | No consignada | Dossier Clase 07, B1–B2 |
| C. Nota administrativa del ejercicio | Cátedra CIRAD (material simulado) | No consignada | Dossier Clase 07, C1–C3 |
| Avance 1 del TP2 | Estudiante | Clase 07 | TP2_Avance1_Apellido_Nombre_CIRAD.pdf |

### 10. Ajuste y decisión humana

**A. Respuesta ajustada** (entre corchetes, el tipo de cambio):

Con la información disponible no puede fijarse aún un orden definitivo; antes debe hacerse la revisión técnica que exige la pauta (B2) **[corregido]**. El orden se define por seguridad, continuidad de actividades, urgencia y costo (B1) **[reformulado: deja de ser la cantidad de usuarios]**.

1. **Seguridad:** inspección inmediata de la filtración junto al tablero eléctrico (A1) y diagnóstico de los cortes, cuya causa se desconoce (A2) **[corregido]**.
2. **Continuidad:** reparación del equipo de laboratorio necesario para una práctica obligatoria (A3) **[corregido]**.
3. **Climatización:** se evalúa tras relevar a cuántos usuarios afecta (C1) **[reformulado: se elimina el 80 %]**.

Un mantenimiento preventivo puede considerarse, pero no hay estimación de ahorro (C2) **[descartado el 30 %]**. El orden final debe acordarse con el área técnica y consultando a usuarios de aulas y laboratorios, no sólo a la administración (C3) **[ampliado]**.

**B. Qué cambió:** no se mantuvo ninguna afirmación tal cual. Se corrigieron la gravedad de la filtración y la causa de los cortes (A1, A2), la posición de los laboratorios (A3, B1) y la aplicación inmediata (B2). Se reformuló el lugar de la climatización (C1). Se descartó el 30 % (C2) y se amplió la consulta a usuarios (C3).

**C. Conclusión:** la respuesta original no es confiable ni utilizable: invertía las prioridades que surgen de la evidencia. La versión ajustada es utilizable como **criterio de priorización**, no como plan. Lo verificado es que existen un riesgo de seguridad y una actividad obligatoria interrumpida. Lo condicionado es el orden entre climatización y otros equipos, que depende del relevamiento y los costos. Lo pendiente antes de una decisión real es el diagnóstico técnico, la gravedad de la filtración, los costos y la fecha de las incidencias (el dossier no la consigna). Además, el dossier es simulado: en la Facultad real habría que repetir el contraste con documentación auténtica.

### 11. Declaración de responsabilidad

- [ ] La selección de fuentes y la decisión final son propias
- [ ] Conservo registro de la evidencia
- [ ] No confundí coincidencia con verificación

*(Marcalas vos después de revisar el trabajo.)*

### 13. Cierre individual

**Pregunta de cierre:** al principio la respuesta me pareció razonable por las cifras y el tono seguro. Después de contrastarla, mi confianza en ella bajó mucho: ninguna afirmación sobrevivió sin cambios. En cambio, confío más en la versión ajustada, porque puedo mostrar de dónde sale cada parte y qué falta comprobar.

**Ticket de salida:**

1. Una afirmación que parecía confiable y cambió después de verificar fue “la climatización afecta al 80 % de los usuarios”: no había ningún relevamiento detrás (C1).
2. Una fuente es útil cuando se refiere exactamente a lo que afirmo, tiene un origen identificable y es independiente de la respuesta que estoy revisando.
3. Para mí, trazabilidad significa que otra persona pueda seguir el camino de cada afirmación a su fuente y a mi decisión, y llegar a la misma conclusión.
