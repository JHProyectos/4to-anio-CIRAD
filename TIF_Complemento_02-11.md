# TIF — Complemento del Encuentro E2 (02/11/2026)

> Esta hoja continúa la ficha del 26/10 ([TIF_Ficha_26-10.md](TIF_Ficha_26-10.md)), sobre los errores en producción que se detectan tarde; no es un trabajo nuevo. Las comprobaciones que todavía no se hicieron figuran como **PENDIENTE**, con el modo de hacerlas. Cuando estén hechas, se reemplaza por la fuente y el resultado.

## Grupo / integrantes

`[completar]`

## 1. Revisamos la ficha: ¿qué mejoramos del problema o de los criterios?

- **Problema:** acotamos el alcance a **errores de la aplicación**. Las caídas completas del proveedor de hosting quedan fuera, igual que en el TP1: no dependen del desarrollador y el proveedor ya las informa.
- **Criterio 3:** “esfuerzo y costo” mezclaba dos cosas. Lo dividimos en *costo mensual* y *tiempo semanal de revisión*. Una herramienta gratis que genera cien avisos por día no es sostenible para una persona sola.
- **Nuevo criterio:** **privacidad**. En el TP1 era una restricción, pero al elegir la A pasó a ser lo que más puede salir mal, así que la usamos también para comparar.

## 2. Una comprobación externa: ¿qué verificamos o qué falta verificar?

| Qué hay que comprobar | Fuente / prueba | Resultado |
|---|---|---|
| Qué registra la captura de errores cuando ocurre una falla | **Prueba en un sistema de desarrollo:** integrar la captura, provocar a propósito un error en un formulario con datos ficticios y revisar el registro generado | `[completar]`. Hay que anotar: si quedan fecha, pantalla y mensaje (criterio 2), cuánto tarda en llegar el aviso (criterio 1) y si aparece algún dato cargado en el formulario (privacidad). |
| Costo y límites del plan gratuito | Documentación oficial de precios del proveedor elegido, con fecha de consulta | **PENDIENTE.** Lo haríamos registrando el enlace, la fecha y los límites (eventos por mes, días de retención). |
| Cantidad y tipo de fallas reales | Tabla de reclamos anonimizados del TP1, reconstruida con mensajes y correos de los últimos meses | **PENDIENTE.** Lo haríamos contando las fallas por tipo (error visible, falla silenciosa, datos incorrectos, caída). |

Volver a preguntarle a la IA no cuenta como verificación, así que no lo incluimos.

## 3. Decisión revisada: ¿qué haríamos, por qué y con qué precaución?

Mantenemos la **A como piloto en un solo sistema**, durante un mes.

- **Por qué:** es la única alternativa que captura la información en el momento de la falla. La prueba de desarrollo nos dice, antes de llevarla a producción, si realmente lo hace.
- **Precauciones:**
  - Configurar la captura para que **no guarde el contenido de formularios ni datos de usuarios**, y comprobarlo en la prueba antes de pasar a producción.
  - Avisar al cliente que se registran errores técnicos.
  - Definir una regla de corte: si los avisos llevan más de 30 minutos semanales de revisión, filtrar por gravedad antes de sumar más sistemas.

## 4. ¿Qué aportó la IA y qué decidió el grupo?

- **Aportó la IA:** la alternativa B, el límite de la C (no adelanta el aviso) y una redacción ordenada de ventajas y límites.
- **Decidió el grupo:** el problema y su recorte (vienen del TP1), los criterios, sumar la privacidad como criterio, elegir la A como piloto, el diseño de la prueba de desarrollo y la regla de corte.

## 5. Reflexión breve: ¿qué mejoraríamos al resolver otro problema?

Haríamos antes la prueba en desarrollo. Con una hora de prueba se responden dudas que en la ficha quedaron como supuestos (qué se registra, cuánto tarda). Probar barato antes de comparar en abstracto.

## Reflexión personal

**Jonatan Harbertz:** `[completar en una o dos frases propias]`. Por ejemplo: al ser un problema mío, me costó no saltar directo a la herramienta que ya tenía en mente; los criterios me obligaron a justificar por qué la A y no la C.

`[cada integrante agrega la suya]`
