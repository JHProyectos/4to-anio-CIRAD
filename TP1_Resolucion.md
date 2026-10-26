# TP1 — Formulación e interacción: errores en producción que se detectan tarde

[TOC]

> **Cómo usar este borrador.** Están resueltas las partes del TP1 sobre la situación propia (Clases 03 a 06). Los ejercicios guiados del caso común no están incluidos. Antes de pasarlo a las guías tenés que revisar tres cosas:
>
> - Los datos entre corchetes `[...]` son tuyos: cantidad de clientes, reclamos, tiempos. **No los inventes.** Si no los tenés, dejalos como *faltante*, que la guía lo acepta.
> - La guía exige que la **primera formulación (Clase 03, 5.G) y la caracterización (Clase 04, secciones 5 y 6) sean sin IA**. Acá están como borrador: leelas, cambiá lo que no coincida con tu experiencia y escribilas con tus palabras.
> - Las respuestas de IA registradas son reales: son las de Claude en esta sesión, con fecha del 26/10/2026. Si tu docente pide capturas, repetí las consultas y adjuntá lo que obtengas.

---

## Avance 1 — Clase 03: de la situación al problema

### 1. Datos

| Campo | Registro |
|---|---|
| Apellido y nombre | Harbertz, Jonatan |
| Carrera / comisión | Ing. en Sistemas de Información |
| Área de la situación | Profesional / tecnológica |
| Herramienta de IA | Claude (Anthropic) |

### 4. Situación propia

**Título provisorio:** errores en sistemas en producción que se detectan tarde.

**¿Por qué la elegí?** Desarrollo y mantengo sistemas web para clientes como trabajo independiente (JH Proyectos). Muchas fallas me llegan cuando el cliente ya las sufrió, y eso afecta mi tiempo y la confianza del cliente.

**Descripción:** mantengo varios sistemas web en producción para distintos clientes. Cuando ocurre una falla (un error en una pantalla, un proceso que no termina, datos que no se guardan), en general me entero porque el cliente me escribe. Entre el momento de la falla y el aviso puede pasar tiempo. A veces el cliente no avisa y el error se repite. Cuando llega el reclamo tengo que reconstruir qué pasó, con poca información sobre el momento exacto y las condiciones del error. Esto se suma al trabajo en curso y desordena la planificación.

| Hechos que conozco | Interpretaciones / suposiciones |
|---|---|
| Mantengo `[N]` sistemas en producción para `[N]` clientes. | Que la mayoría de las fallas no se reportan. |
| La vía principal por la que me entero de una falla es el aviso del cliente. | Que las fallas se repiten porque no las veo a tiempo. |
| Algunos reclamos llegan días después de la falla. | Que los clientes pierden confianza por la demora. |
| Reconstruir un error sin registro lleva más tiempo que con registro. | Que el problema es técnico y no de comunicación con el cliente. |

**Soluciones que aparecieron demasiado pronto:** instalar una herramienta de monitoreo de errores; mandar alertas por correo; hacer un panel de salud de cada sistema; pedirles a los clientes que reporten con un formulario.

### 5. Primera delimitación — sin IA

**A. Problema central:** me entero tarde, y de forma incompleta, de las fallas que ocurren en los sistemas que mantengo.

| B. Causas probables (hipótesis) | C. Consecuencias |
|---|---|
| No hay un registro sistemático de errores en todos los sistemas *(a verificar por sistema)*. | Demora en corregir. |
| Dependo del aviso del cliente como canal principal. | Retrabajo para reconstruir el error. |
| Cuando hay registro, nadie lo revisa en forma periódica *(hipótesis)*. | Planificación desordenada por urgencias. |
| | Posible pérdida de confianza del cliente *(hipótesis)*. |

**D. Incluye:** las fallas técnicas de los sistemas web que mantengo en producción: errores de la aplicación y procesos que fallan.

**E. Queda fuera:** errores de uso del cliente, pedidos de cambios o mejoras, caídas del proveedor de hosting y aspectos comerciales (contratos, cobro del mantenimiento).

**F. Propósito:** en este TP1 pretendo **comprender** por qué las fallas me llegan tarde y qué información me falta en ese momento, para después poder **priorizar** qué conviene empezar a registrar.

**G. Primera formulación:**

> Las fallas que ocurren en los sistemas web que mantengo en producción llegan a mi conocimiento tarde, en general por aviso del cliente y con poca información sobre cuándo y cómo ocurrieron. Esto demora su corrección y me obliga a reconstruir los hechos. Necesito comprender qué parte del problema se debe a la falta de registro y cuál a la dependencia del aviso del cliente.

### 6. IA como contraparte crítica

**Consulta exacta:**

> Soy desarrollador independiente y mantengo sistemas web para clientes. Te paso mi primera formulación de un problema. No me propongas soluciones ni herramientas. Señalame: términos ambiguos, si confundo problema con causa, consecuencia o solución, si el alcance es muy amplio o muy estrecho, qué información falta y qué preguntas me ayudarían a precisar el propósito.
>
> Formulación: "Las fallas que ocurren en los sistemas web que mantengo en producción llegan a mi conocimiento tarde, en general por aviso del cliente y con poca información sobre cuándo y cómo ocurrieron. Esto demora su corrección y me obliga a reconstruir los hechos. Necesito comprender qué parte del problema se debe a la falta de registro y cuál a la dependencia del aviso del cliente."

**Respuesta (fragmento principal, Claude, 26/10/2026):**

> “Tarde” y “poca información” son términos sin referencia: ¿tarde respecto de qué? Convendría expresarlo como el tiempo entre la falla y tu conocimiento de ella. “Falla” abarca cosas muy distintas, como un error visible, un proceso silencioso o datos incorrectos; no todas se detectan igual. La última oración ya presupone dos causas (falta de registro y dependencia del cliente) y las convierte en el marco del problema: podría haber otras. Falta saber cuántos sistemas, con qué frecuencia ocurren fallas y si alguno ya tiene registro. Preguntas: ¿qué decisión querés poder tomar al final? ¿Te importan todas las fallas o las que afectan al cliente? ¿Cómo sabrías que el problema mejoró?

### 7. Registro de observaciones

| Tipo | Qué señaló la IA |
|---|---|
| Ambigüedad | “Tarde” y “poca información” sin referencia. |
| Información faltante | Cantidad de sistemas, frecuencia de fallas, registro existente. |
| Confusión problema / causa | La formulación ya incluye dos causas como marco. |
| Alcance | “Falla” es demasiado amplio: distintos tipos se detectan distinto. |
| Propósito | ¿Qué decisión quiero poder tomar? ¿Cómo sabría que mejoró? |

### 8. Decisión humana

| Observación | Decisión | Justificación | Cambio |
|---|---|---|---|
| Definir “tarde” como tiempo de detección | Acepto | Lo vuelve medible. | Uso “tiempo entre la falla y mi conocimiento de ella”. |
| Causas presupuestas en la formulación | Modifico | Son mis hipótesis principales, pero no deben ser el problema. | Las saco del enunciado y las dejo como hipótesis. |
| Distinguir tipos de falla | Modifico | Es útil, pero no quiero achicar tanto el alcance. | Me centro en las fallas que afectan al uso del cliente. |
| “¿Qué decisión querés tomar?” | Acepto | Aclara el propósito. | Agrego: priorizar qué información registrar primero. |

### 9. Reformulación

> En los sistemas web que mantengo en producción, el tiempo entre que ocurre una falla que afecta el uso del cliente y el momento en que me entero es variable y a veces de días, y cuando me entero cuento con poca información sobre cuándo y en qué condiciones ocurrió. Quiero comprender de qué depende ese tiempo y qué información me falta, para priorizar qué empezar a registrar.

**¿Qué cambió?** Defino la demora de forma medible, acoto el alcance a las fallas que afectan al cliente y saco las causas del enunciado. Las tres decisiones son mías a partir de las observaciones de la IA. No acepté reducir el problema a un solo tipo de falla.

**Pendientes para la Clase 04:** cuántos sistemas y clientes; qué sistemas ya tienen algún registro; frecuencia aproximada de reclamos; quién más interviene (clientes, usuarios finales, proveedor de hosting).

### 11. Cierre

**Pregunta de cierre:** formular bien el problema evita que la IA me devuelva una lista de herramientas de monitoreo, que era justamente la solución que yo había anticipado.

**Ticket:** 1) Hoy advertí que mi primera formulación ya traía las causas adentro. 2) Antes de consultar a una IA debería poder decir qué decisión quiero tomar. 3) Una observación que no aceptaría automáticamente es achicar el problema a un único tipo de falla.

---

## Avance 2 — Clase 04: caracterización

### 5. Recuperar el avance 1

**A. Formulación de la Clase 03:** la reformulación de la sección 9 del Avance 1.

**B. Propósito:** se mantiene: comprender de qué depende el tiempo de detección y qué información falta, para priorizar qué registrar.

**C. Contexto relevante:** trabajo solo, sin guardias ni horario de soporte fijo. Los sistemas están en distintas tecnologías y servidores, `[completar: p. ej. Supabase, hosting propio]`. Desarrollo proyectos nuevos al mismo tiempo que mantengo los existentes.

**D. Actores:**

| Actor | Papel | Información que posee | Decide / influye / afectado |
|---|---|---|---|
| Yo (desarrollador) | Mantiene y corrige | Código, servidores, registros existentes | Decide qué se registra y cómo |
| Cliente (responsable) | Contrata el mantenimiento y reporta | Cuándo notó el problema, impacto en su negocio | Influye (prioridades, presupuesto); afectado |
| Usuarios finales del cliente | Usan el sistema | Qué hicieron cuando falló | Afectados; rara vez reportan directo |
| Proveedor de infraestructura | Aloja base de datos y servidores | Métricas y registros de la plataforma | Influye (límites, qué registra) |

### 6. Variables, restricciones e información

**E. Variables:**

- *Cantidad de sistemas en producción:* a más sistemas, menos posible revisar cada uno a mano.
- *Frecuencia de fallas:* cambia la urgencia de registrar.
- *Tiempo de detección:* es la variable central del problema.
- *Información disponible al detectar:* determina el tiempo de reconstrucción.
- *Gravedad de la falla para el cliente:* no todas requieren la misma rapidez.

**F. Restricciones:**

- Trabajo solo: el tiempo que puedo dedicar a revisar es limitado.
- Presupuesto bajo para herramientas pagas.
- No puedo registrar datos personales de los usuarios finales sin autorización del cliente.
- Los planes de algunos proveedores limitan cuánto tiempo se conservan sus registros.

| G. Información disponible | H. Supuestos | I. Información faltante |
|---|---|---|
| Lista de sistemas en producción `[N]`. | Que la mayoría de las fallas no se reportan. | Cuántas fallas hubo en los últimos meses. |
| Historial de reclamos en mensajes y correo. | Que el cliente avisa tarde por falta de canal. | Tiempo promedio entre falla y aviso. |
| Qué sistemas tienen algún registro de errores `[completar]`. | Que con registro reconstruiría más rápido. | Qué conserva hoy cada proveedor y por cuánto tiempo. |
| | | Qué fallas fueron graves para el cliente. |

**J. Criterios iniciales:**

| Criterio | Justificación | Indicador posible |
|---|---|---|
| Rapidez de detección | Es el centro del problema. | Tiempo entre falla y conocimiento. |
| Información para reconstruir | Reduce el retrabajo. | ¿Sé cuándo, dónde y con qué datos falló? |
| Esfuerzo de mantenimiento | Trabajo solo. | Horas por semana dedicadas a revisar. |
| Respeto de la privacidad | Restricción legal y de confianza. | Sin datos personales en los registros. |
| Costo | Presupuesto bajo. | Costo mensual por sistema. |

### 7. Revisión crítica con IA

**A. Consulta:**

> Te paso la caracterización de mi problema (propósito, contexto, actores, variables, restricciones, información disponible, supuestos, faltantes y criterios). No me propongas soluciones ni completes datos que faltan. Señalame actores, variables o restricciones omitidos, afirmaciones que parezcan supuestos, criterios que falten y contradicciones entre las partes. `[se pegó la caracterización de las secciones 5 y 6]`

**Respuesta (fragmento, Claude, 26/10/2026):**

> Falta un actor: si el cliente tiene a alguien interno que recibe las quejas de los usuarios, ese intermediario influye en cuándo te llega el aviso. “Gravedad” aparece como variable, pero no hay un criterio para definirla; sin eso no vas a poder priorizar. “Historial de reclamos en mensajes y correo” está como información disponible, pero no está organizado: es más un dato a reconstruir que un dato disponible. Falta una restricción: el acceso a producción de cada cliente puede estar limitado por contrato. Los criterios son coherentes con el propósito; “costo” y “esfuerzo” podrían solaparse.

**B. Decisión humana:**

| Aporte | Decisión | Justificación |
|---|---|---|
| Intermediario del cliente | Acepto | En al menos un cliente pasa así. Lo agrego como actor. |
| Criterio para la gravedad | Acepto | Sin él la variable no sirve. Agrego el criterio “impacto en la operación del cliente”. |
| El historial no está organizado | Modifico | Es real que está disperso. Lo dejo como disponible, pero con estado *a reconstruir*. |
| Acceso limitado por contrato | Descarto | En mis casos yo administro el acceso. No aplica hoy. |
| Solapamiento costo/esfuerzo | Descarto | Son distintos: uno es dinero y el otro mi tiempo. |

### 8. Ajuste final

**A. Formulación:** se mantiene la de la Clase 03 sin cambios en el enunciado.

**B. Qué cambió:** agregué el actor intermediario y el criterio de impacto en la operación del cliente. Cambié el estado del historial de reclamos a *a reconstruir*.

---

## Avance 3 — Clase 05: herramienta e información

### 1. Datos

| Campo | Registro |
|---|---|
| Propósito vigente | Comprender de qué depende el tiempo de detección y priorizar qué registrar. |
| Tarea con IA | Organizar mis reclamos pasados (anonimizados) por tipo de falla, demora y gravedad, y señalar qué información faltaba en cada caso. |

### 7 y 8. Herramienta seleccionada

| Herramienta / tipo | Por qué podría servir | Limitación relevante |
|---|---|---|
| Asistente conversacional (Claude) | Clasifica texto desordenado y señala patrones; se puede pedir que no invente. | Puede clasificar con seguridad casos ambiguos; no verifica datos. |
| Planilla de cálculo | Control total; fácil de recalcular tiempos. | Clasificar a mano lleva tiempo; no sugiere categorías. |
| Asistente con búsqueda web | Accede a información actual. | No aporta nada: la tarea es sobre mis datos, no sobre la web. |

**A. Elección:** Claude para clasificar y detectar faltantes, y la planilla para guardar el resultado y calcular. Pesaron la adecuación a la tarea (texto desordenado) y la trazabilidad (la planilla queda como registro).

**B. Inventario:**

| Información | Fuente | Estado | Acción |
|---|---|---|---|
| Lista de sistemas en producción | Propia | Verificado | Incluir (con nombres genéricos) |
| Reclamos de los últimos `[N]` meses | Mensajes y correo | A reconstruir | Incluir, anonimizados |
| Fecha de la falla vs. fecha del aviso | Reclamos y registros | Parcial / faltante | Incluir lo que haya, marcar faltantes |
| Registros técnicos existentes | Proveedor | A verificar | Excluir por ahora |
| Gravedad para el cliente | Mi juicio | Supuesto | Incluir, marcado como supuesto |

**C. Lo que no incorporo:** nombres de clientes y de sus usuarios, datos de los sistemas (correos, DNI, montos), credenciales, direcciones de servidores y capturas con datos reales. Reemplazo los nombres por “Cliente A, B, C” y resumo cada reclamo en una línea sin datos personales.

### 9. Borrador de consulta para la Clase 06

> Te paso una tabla de reclamos anonimizados de sistemas que mantengo (fecha del aviso, fecha estimada de la falla si la sé, descripción breve, gravedad estimada por mí). Clasificalos por tipo de falla y marcá en cada uno qué información me faltaba para reconstruirlo. No inventes fechas ni causas: si no está, decí “sin dato”.

**Decisiones:** herramienta mixta; solo datos anonimizados; la gravedad, marcada como supuesto. **Pendiente para la Clase 06:** reconstruir la tabla de reclamos `[tarea tuya]`.

### 11. Cierre

**Ticket:** 1) Hoy advertí que mis datos estaban más desordenados de lo que creía. 2) Antes de compartir información con una IA debería anonimizar y quitar lo que no hace falta. 3) El criterio que más pesó fue la adecuación a la tarea.

---

## Cierre — Clase 06: interacción iterativa

> Para esta parte hace falta tu tabla de reclamos real, anonimizada. Abajo usé una **tabla de ejemplo con 6 reclamos ficticios**, marcada como tal, para mostrar la secuencia. Reemplazala por la tuya y repetí las tres consultas: las respuestas van a cambiar.

### 4. Punto de partida

| Componente | Registro |
|---|---|
| Problema y propósito | Los de la Clase 03, sin cambios desde la Clase 04. |
| Herramienta | Claude + planilla. |
| Función de la IA | Clasificar los reclamos y señalar faltantes; no decide qué registrar. |
| No comparto | Nombres, datos personales, credenciales, servidores. |
| Criterios | Los cinco de la Clase 04 + impacto en la operación del cliente. |

**Tabla de ejemplo (ficticia):**

| # | Cliente | Aviso | Falla estimada | Descripción | Gravedad (supuesto) |
|---|---|---|---|---|---|
| 1 | A | lunes | sin dato | “no se guardan los pedidos” | Alta |
| 2 | A | jueves | martes | pantalla en blanco al ingresar | Alta |
| 3 | B | miércoles | mismo día | error al exportar un informe | Media |
| 4 | C | viernes | sin dato | correo de aviso que no llega | Media |
| 5 | B | martes | semana anterior | totales mal calculados | Alta |
| 6 | C | lunes | mismo día | lentitud general | Baja |

### 5. Interacción 1

**Consulta 1:** el borrador de la Clase 05 con la tabla pegada.

**Resultado 1 (fragmento):**

> Clasificación: errores visibles (2, 3), fallas silenciosas de proceso (1, 4), datos incorrectos (5), rendimiento (6). Faltantes: en 1 y 4 no hay fecha de falla; en ninguno hay un mensaje de error ni se sabe qué acción hizo el usuario. Observación: las fallas silenciosas y los datos incorrectos son las de mayor demora entre la falla y el aviso.

**Me sirve:** la categoría “falla silenciosa” y que las demoras mayores coinciden con ella. **Problema:** la observación final se apoya en solo dos casos con fecha (2 y 5) y la presenta como patrón.

**Decisión:** pedir que separe lo que surge de los datos de lo que infiere, y que diga con cuántos casos sostiene cada afirmación.

### 6. Interacciones 2 y 3

**Consulta 2 (ajuste: corregir / aclarar):**

> En tu última observación sacaste un patrón de pocos casos. Rehacé el análisis separando en dos columnas: “surge de los datos” (con los números de caso) e “inferencia a verificar”. Si un caso no tiene fecha de falla, no lo uses para hablar de demoras.

**Resultado 2 (fragmento):**

> Surge de los datos: los casos 2 y 5 tienen demora de 2 o más días; los casos 3 y 6, de 0 días. A verificar: que las fallas silenciosas tarden más en detectarse (1 y 4 no tienen fecha). Con 4 casos fechados no se puede afirmar un patrón.

**Qué mejoró:** queda claro qué está respaldado. **Qué sigue problemático:** no me dice qué registrar para cerrar esos faltantes, que es el propósito.

**Consulta 3 (ajuste: acotar / reorganizar):**

> Con esa separación, armá una tabla: para cada faltante detectado, qué dato habría necesitado y en qué momento se genera ese dato. No recomiendes herramientas ni decidas prioridades: sólo vinculá faltante, dato y momento.

**Resultado 3 (fragmento):**

| Faltante | Dato necesario | Momento en que se genera |
|---|---|---|
| Fecha de la falla | Fecha y hora del error | Al ocurrir el error, en el servidor |
| Mensaje de error | Texto técnico del error | Al ocurrir, en la aplicación |
| Acción del usuario | Pantalla u operación en curso | Al ocurrir, en el navegador o la aplicación |
| Falla silenciosa | Resultado de cada proceso automático | Al terminar (o no) el proceso |

**Resultado utilizable:** los cuatro datos que me faltan se generan en el momento de la falla y no en el aviso. Eso sostiene que la dependencia del aviso del cliente es parte central del problema. **Limitaciones:** la tabla es de ejemplo; falta repetirla con datos reales, y la gravedad sigue siendo un supuesto mío.

### 7. Decisiones humanas

| Aporte de la IA | Decisión | Justificación | Qué haré |
|---|---|---|---|
| Categoría “falla silenciosa” | Acepto | Describe casos que reconozco. | La uso en la clasificación. |
| Patrón de demora por tipo | Rechazo | Pocos casos. | Lo dejo como hipótesis. |
| Separar datos de inferencias | Acepto | Mejora la trazabilidad. | Lo aplico en todo el TP. |
| Tabla faltante–dato–momento | Modifico | Útil, pero la priorización es mía. | Ordeno por impacto en el cliente. |

### 8. Primera vs. última interacción

La primera pedía clasificar y marcar faltantes, sin pedir separar evidencia de inferencia. La última acota la tarea a vincular faltantes con datos y momentos, prohíbe recomendar herramientas y exige no usar casos sin fecha. La mejora vino de dos decisiones mías: exigir el respaldo de cada afirmación y volver al propósito (qué registrar) en lugar de pedir más análisis.

### 9. Reflexión final

| Pregunta | Respuesta |
|---|---|
| 1. ¿Qué aportó la IA? | Una clasificación inicial y la estructura faltante–dato–momento. |
| 2. ¿Qué dependió de mi criterio? | El alcance, qué datos compartir, qué rechazar y cómo priorizar. |
| 3. ¿Qué cambió entre la primera y la última consulta? | Pasé de “analizá” a pedir una tarea acotada con restricciones explícitas. |
| 4. ¿Qué sugerencia no usé? | El patrón de demora por tipo de falla: se apoyaba en dos casos. |
| 5. ¿Qué limitaciones mostró? | Generaliza con pocos datos y presenta inferencias con tono de hecho. |
| 6. ¿Qué mejoraría? | Reconstruir primero una tabla real con más casos fechados. |
