# TIF — Presentación y cierre del Encuentro E3 (09/11/2026)

> Es un guion para la exposición grupal de unos 3 minutos. Se basa en la ficha del 26/10 y el complemento del 02/11 (errores en producción que se detectan tarde). Lo que depende de la clase o de la prueba en desarrollo está marcado para completar.

## Grupo / integrantes

`[completar]`

## 1. ¿Qué problema abordamos?

Un desarrollador que mantiene varios sistemas web se entera tarde de las fallas, por aviso del cliente, y sin información para reconstruirlas.

## 2. ¿Qué alternativas aparecieron y con qué criterio las comparamos?

Comparamos tres alternativas: **A** (captura automática de errores), **B** (verificaciones periódicas externas) y **C** (formulario de reporte para el cliente). Usamos estos criterios: rapidez de detección, información para reconstruir, costo mensual, tiempo de revisión y privacidad.

## 3. ¿Qué decidimos y qué verificamos o quedó pendiente?

Decidimos un **piloto de la A** en un solo sistema, sin registrar datos de formularios y con una regla de corte por tiempo de revisión. La B queda como complemento y la C se descartó porque no adelanta el aviso.

- **Verificado:** `[resultado de la prueba en desarrollo: qué registró, cuánto tardó el aviso, si apareció algún dato personal]`.
- **Pendiente:** los límites del plan gratuito y la cantidad real de fallas por tipo.

## 4. ¿Qué aportó la IA y qué aprendimos?

La IA aportó la alternativa B y señaló el límite de la C. El problema, los criterios, la elección y la prueba fueron decisiones nuestras. Aprendimos que una prueba chica y real responde más que otra ronda de preguntas a la IA.

## Guion de 3 minutos

> “Partimos de un problema real de uno de nosotros, que es desarrollador: las fallas de los sistemas que mantiene le llegan tarde, por el cliente, y sin datos para saber qué pasó.
>
> Antes de consultar a la IA ya teníamos dos ideas: capturar los errores automáticamente y darle al cliente un formulario de reporte. La IA sumó una tercera, probar periódicamente desde afuera que el sistema funcione, y nos hizo ver que el formulario mejora el aviso pero no lo adelanta.
>
> Comparamos con cinco criterios. El que nos cambió la decisión fue la privacidad: capturar errores puede guardar datos de usuarios sin querer. Por eso elegimos un piloto en un solo sistema, probado antes en desarrollo con un error provocado a propósito. En esa prueba vimos [resultado].
>
> Queda pendiente confirmar el costo y contar las fallas reales por tipo. La IA nos dio opciones; la decisión y el control de los riesgos son nuestros.”

## Observación recibida y corrección que hacemos

`[completar en clase: qué observó el docente o el otro grupo]` → `[qué cambiamos]`.

Si no hay observación, una autocorrección posible: agregar a la ficha el resultado de la prueba en desarrollo y pasar el criterio 2 de supuesto a verificado (o a refutado).

## Reflexión individual

**Jonatan Harbertz** *(revisá y ajustá con tus palabras)*:

- *Antes pensaba que* la solución a mi problema era instalar una herramienta de monitoreo, y que la IA me iba a decir cuál.
- *Ahora sé que debo* delimitar el problema y definir criterios antes de elegir, y probar lo que se pueda en lugar de suponerlo.
- *La próxima vez mejoraré* juntando los datos reales (cuántas fallas, de qué tipo) antes de comparar alternativas.

`[cada integrante agrega sus tres frases]`

**Entrega final:** ficha del 26/10 + complemento del 02/11 + la corrección de arriba + las reflexiones individuales.
