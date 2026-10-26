# Ficha TP3 reducido / inicio del TIF — Encuentro E1 (26/10/2026)

> **Problema reutilizado:** el del TP1 de Jonatan Harbertz, *errores en producción que se detectan tarde*, llevado al trabajo en grupo, como recomienda la guía. La estructura sigue los ejemplos resueltos del docente: alternativas con mecanismos distintos, variantes separadas, preferencia provisoria y verificación pendiente.
>
> La consulta del punto 3 se hizo de verdad a Claude el 26/10/2026, y el fragmento registrado es su respuesta.

## Grupo / integrantes

`[completar]` — Herramienta de IA: Claude (Anthropic).

## 1. Problema en una oración

Un desarrollador independiente que mantiene varios sistemas web en producción se entera tarde, y en general por aviso del cliente, de las fallas que afectan el uso, y con poca información para reconstruir qué pasó.

## 2. Tres criterios para comparar

1. **Rapidez de detección:** cuánto se reduce el tiempo entre la falla y el momento en que el desarrollador se entera.
2. **Información para reconstruir:** si al detectar la falla se sabe cuándo ocurrió, dónde y qué estaba haciendo el usuario.
3. **Esfuerzo y costo sostenibles:** que una sola persona lo pueda mantener, con poco o ningún costo mensual.

## 3. Consulta realizada a la IA

> Un desarrollador independiente mantiene varios sistemas web en producción para distintos clientes. Se entera tarde de las fallas, en general porque el cliente avisa, y sin datos para reconstruirlas. Trabaja solo, con poco presupuesto, y no puede registrar datos personales de los usuarios sin autorización. Proponé tres alternativas que resuelvan el problema con mecanismos realmente distintos (no variantes de la misma idea). Para cada una indicá una ventaja y un límite posibles. No elijas la mejor ni recomiendes marcas; marcá los supuestos.

**Fragmento de la respuesta (Claude, 26/10/2026):**

> A) Captura automática de errores: la aplicación registra cada error con fecha, pantalla y mensaje, y avisa al desarrollador. Ventaja: detección casi inmediata y con contexto. Límite: hay que integrarla en cada sistema y cuidar que no registre datos personales. B) Verificaciones periódicas externas: un proceso prueba cada cierto tiempo que las funciones clave respondan (ingresar, guardar, exportar). Ventaja: detecta caídas sin tocar el código. Límite: solo ve lo que se prueba; no detecta errores de datos. C) Canal de reporte para el cliente: un formulario breve con campos fijos (qué hacía, cuándo, captura). Ventaja: mejora la información del aviso, a bajo costo. Límite: sigue dependiendo de que el cliente avise. Supuesto: no conozco cuántas fallas ocurren ni de qué tipo.

## 4. Tres alternativas

| Alternativa | Ventaja posible | Límite posible |
|---|---|---|
| A. Captura automática de errores en cada sistema, con aviso al desarrollador | Detección inmediata, con fecha y contexto | Integración en cada sistema; riesgo de registrar datos personales |
| B. Verificaciones periódicas externas de las funciones clave | No requiere tocar el código; detecta caídas | Solo ve lo que se prueba; no detecta datos incorrectos |
| C. Canal de reporte estructurado para el cliente | Bajo costo; mejora la información de cada aviso | Sigue dependiendo del aviso del cliente: no acorta la demora |

*Origen:* A y C ya aparecían como “soluciones anticipadas” en el TP1, antes de consultar. La IA aportó la B y señaló el límite de la C. Las alertas por correo y el panel de salud son **variantes** de A o B, no alternativas nuevas.

## 5. ¿Qué alternativa elegimos y por qué?

Elegimos, **en forma provisoria**, la **A (captura automática de errores)**, empezando por un solo sistema como piloto. Es la única que mejora a la vez el criterio 1 (detección) y el criterio 2 (información para reconstruir). En el TP1 se vio que los cuatro datos que faltaban se generan en el momento de la falla, y solo la A los captura ahí.

La B queda como complemento para las caídas completas. Descartamos la C como solución principal: mejora el aviso, pero no lo adelanta.

## 6. ¿Qué riesgo o dato debemos verificar fuera de la IA?

- **Dato:** cuántas fallas hay por mes y de qué tipo, con la tabla real de reclamos anonimizados del TP1. Si la mayoría son caídas completas, la B pesa más.
- **Riesgo:** que la captura registre datos personales de los usuarios (formularios, correos). Hay que revisar en una prueba qué guarda exactamente cada error.
- **Dato:** el costo y los límites del plan gratuito de la herramienta de captura que se use, según la documentación oficial del proveedor.

**Entrega:** conservamos la consulta y la herramienta utilizada. No hay datos de clientes. Nada está verificado todavía: el 02/11 completamos la comprobación sobre esta misma ficha.
