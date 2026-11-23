# Revisión del PRD — USFQ Reserva COCOA

**Documento revisado:** [prd.md](prd.md) (borrador v0.1)

Correcciones aplicadas al PRD en la versión v0.2.

---

## 1. Sección 2 — Usuarios

**Corrección:** los profesores no son usuarios de la plataforma. Se descarta ese perfil.

**Cambio:** eliminar la fila **Profesor** de la tabla de usuarios y añadir debajo de la tabla:

> Los profesores **no son usuarios** de la plataforma.

**Antes:**

| Perfil | Quién es | Lo que necesita hacer |
|---|---|---|
| **Profesor** | Mencionado en la visita solo para el espacio de computadoras ("solo profes/admin"). No es un perfil confirmado (ver P-04). | Reservar el espacio de computadoras y las computadoras individuales. |

**Después:** la fila se elimina.

**Aplicado en el PRD:** se eliminó la fila **Profesor** y se añadió la frase debajo de la tabla de la sección 2.

---

## 2. Sección 4 — Reglas de negocio (RN-17)

**Corrección:** las computadoras las reservan los estudiantes. No hay restricción a administradores ni a profesores.

**Antes:**

> **RN-17.** El espacio de computadoras y cada computadora individual solo los pueden reservar administradores o profesores (ver P-04).

**Después:**

> **RN-17.** El espacio de computadoras y cada computadora individual los reservan los estudiantes, igual que cualquier otro artículo. No hay restricción por rol.

**Aplicado en el PRD:** RN-17 se reemplazó por el texto de "Después".

---

## 3. Sección 7 — Supuestos y preguntas abiertas (P-04)

**Corrección:** como consecuencia de los dos puntos anteriores, la pregunta P-04 queda resuelta.

**Antes:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-04 | ¿Los profesores son un perfil con cuenta propia? | No en el MVP. Las computadoras y su espacio se marcan como "solo administradores", y el administrador las reserva en nombre de los profesores. |

**Después:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-04 | ~~¿Los profesores son un perfil con cuenta propia?~~ | **Resuelta.** Los profesores no son usuarios. Las computadoras y su espacio los reservan los estudiantes, sin restricción por rol (RN-17). |

**Aplicado en el PRD:** P-04 se marcó como resuelta con el texto de "Después".

---

## 4. Sección 7 — Horario de retiro y devolución (P-09)

**Corrección:** el retiro y la devolución son hasta las **17:00**.

**Antes:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-09 | ¿El retiro y la devolución terminan a las 17:20 o a las 17:00 ("hasta las 5 PM")? | La franja es **08:30–17:20**, y la configura el administrador. |

**Después:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-09 | ~~¿El retiro y la devolución terminan a las 17:20 o a las 17:00 ("hasta las 5 PM")?~~ | **Resuelta.** La franja es **08:30–17:00**, y la configura el administrador. |

**Cambio relacionado en la sección 4 (RN-15):**

> **Antes:** **RN-15.** Los equipos se entregan y se reciben **solo en horario laboral, de 08:30 a 17:20** (ver P-09). Fuera de esa franja no se puede elegir hora de retiro ni de devolución.

> **Después:** **RN-15.** Los equipos se entregan y se reciben **solo en horario laboral, de 08:30 a 17:00**. Fuera de esa franja no se puede elegir hora de retiro ni de devolución.

**Aplicado en el PRD:** P-09 se marcó como resuelta y RN-15 se cambió a 17:00. Por coherencia, D-23 también pasa de 17:20 a 17:00.

---

## 5. Sección 7 — Margen de retiro (P-10)

**Corrección:** el margen para retirar el equipo es de **30 minutos**.

**Antes:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-10 | ¿El margen para retirar el equipo es de 15 o de 30 minutos? ¿Depende del tipo de artículo? | **15 minutos** para todo, y el administrador puede cambiarlo. |

**Después:**

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-10 | ~~¿El margen para retirar el equipo es de 15 o de 30 minutos? ¿Depende del tipo de artículo?~~ | **Resuelta.** El margen es de **30 minutos** para todo, y el administrador puede cambiarlo. |

**Cambio relacionado en la sección 4 (RN-20):**

> **Antes:** **RN-20.** Si el estudiante no viene a retirar el equipo dentro del margen de tolerancia, la reserva se libera automáticamente (el margen está pendiente: 15 o 30 minutos, ver P-10).

> **Después:** **RN-20.** Si el estudiante no viene a retirar el equipo dentro de los **30 minutos** de tolerancia, la reserva se libera automáticamente.

**Aplicado en el PRD:** P-10 se marcó como resuelta y RN-20 se cambió a 30 minutos. Por coherencia, D-21 también pasa de "15/30 min" a 30 minutos.

---

# Problemas detectados por la IA

Los puntos 6 a 13 los encontró una IA (Claude, de Anthropic) al revisar el PRD como un socio de producto escéptico y compararlo con los archivos de `docs/fuentes/`. **No son correcciones confirmadas por el cliente.** Son riesgos y preguntas que hay que validar con él antes de cambiar el PRD.

| # | Problema | Sección | Gravedad | Corrección |
|---|---|---|---|---|
| 6 | El alcance no cabe en el 2 de diciembre | 3 y 9 | Alta | Nueva **P-28** (qué 5 cosas entran el 2/12; provisional: lo que exige el criterio de éxito principal, y el chatbot es lo primero que sale) y **P-29** (adelantar el Excel; provisional: datos de ejemplo mientras tanto). Nota al inicio de la sección 3. En la sección 9, el plazo queda en el "2 de diciembre de 2026" y se enlaza a P-28 y P-29. P-02 ya no dice "todo el alcance del MVP". |
| 7 | Inicio de sesión con la contraseña de la universidad | 4 (RN-03) | Alta | **P-05** reescrita: se pide acceso a TI, ya no se da por hecho Microsoft, y el plan B provisional es entrar con un enlace enviado al correo institucional. Nueva **P-30** (dominio exacto; provisional: configurable). Se añadieron enlaces en el ítem 1, RN-01, RN-03 y la restricción "Acceso" de la sección 9. |
| 8 | No está definido qué significa "disponible" | 3 (ítem 4) y 4 (RN-10, RN-11, RN-25) | Alta | Nueva **P-31** (provisional: una reserva aprobada ocupa la unidad en su franja y la saca de la búsqueda) y **P-32** (provisional: el sistema avisa, pero no impide aprobar la posterior). RN-25 ahora separa el estado actual de la unidad de su disponibilidad por franja. Enlaces añadidos en el ítem 4, RN-10 y RN-11. |
| 9 | El carrito que caduca repite la queja principal | 4 (RN-08) | Media | RN-08 cambia de "se vacía y se cierra la sesión" a "se cierra la sesión, pero el carrito queda guardado" (provisional, nueva **P-33**). D-15 reescrita como dijo el cliente. Ajustados el ítem 9 y el criterio de éxito del carrito. |
| 10 | Computadoras de madrugada con la bodega cerrada | 4 (RN-16) | Media | Nueva **P-34** (provisional: se usan en el espacio de computadoras, sin pasar por la bodega; sigue pendiente quién da acceso) y **P-35** (provisional: días laborables configurables; una reserva puede abarcar días no laborables, pero el retiro y la devolución caen en la franja laboral). Enlaces añadidos en RN-15 y RN-16. |
| 11 | Penalización sin margen ni efecto sobre reservas futuras | 4 (RN-22, RN-23) | Media | Nueva **P-36** (margen para devolver y quién registra la hora; provisional: sin margen y la registra quien recibe el equipo), **P-37** (provisional: las reservas futuras se mantienen y el administrador puede cancelarlas) y **P-38** (provisional: bloqueo automático que el administrador puede quitar antes). RN-23 ahora dice que sale de una nota confusa. |
| 12 | El comprobante en PDF entra al MVP aunque el cliente dijo "después de diciembre" | 3 (ítem 17) y 4 (RN-28) | Media | Nueva **P-39** (provisional: el PDF y su correo pasan a después de diciembre). El ítem 17 queda marcado como fuera del MVP de forma provisional. Se reescribieron RN-28 y RN-33, y se añadió una fila en la sección 5. Se quitaron los comprobantes del ítem 16, de la tabla de usuarios y de la épica E3. Enlaces añadidos en D-28 y P-23. |
| 13 | Ficha del estudiante con una "puntuación" inventada | 3 (ítem 3) y 6 (D-36) | Media | Nueva **P-40** (provisional: no hay calificación y la ficha solo muestra el estado de bloqueo). El ítem 3 y la épica E1 se reducen al estado de bloqueo. D-36 ahora cita la nota literal. P-15 y P-16 pasan a depender de P-40. |

---

## 6. Secciones 3 y 9 — El alcance no cabe en el 2 de diciembre

**Detectado por:** IA · **Gravedad:** alta

**Frase del PRD:**

> **Plazo:** el prototipo funcional se presenta a principios de diciembre de 2026 […]

> **Insumos del cliente:** el Excel de productos llega en la semana 15.

**Por qué es un problema:**
- El 23 de noviembre quedan 9 días, y el MVP tiene 30 funcionalidades.
- Varias son casi proyectos completos: el inicio de sesión con la cuenta de la universidad, importar y exportar Excel, el PDF, los recordatorios programados, las penalizaciones automáticas, los kits, los dos idiomas y el chatbot.
- Si la semana 15 cae cerca de la entrega, no habrá tiempo de probar la carga real del inventario.
- El PRD no prioriza nada, salvo el chatbot.

**Preguntas al cliente:**
- "Si el 2 de diciembre solo pudieran funcionar 5 cosas, ¿cuáles serían?"
- "¿Puede enviarnos el Excel esta semana, aunque esté incompleto?"

---

## 7. Sección 4 — Inicio de sesión con la contraseña de la universidad (RN-03)

**Detectado por:** IA · **Gravedad:** alta

**Frase del PRD:**

> **RN-03.** La contraseña es la misma de la universidad. La plataforma no guarda contraseñas propias.

**Por qué es un problema:**
- Hace falta que TI de la USFQ registre la aplicación en su sistema de inicio de sesión. Eso no depende del equipo y difícilmente se consigue en 9 días.
- Que ese sistema sea Microsoft (P-05) es un supuesto nuestro; ninguna fuente lo dice.
- Tampoco se conoce el dominio exacto de los correos que exige RN-01.
- No hay plan B, y que falle el inicio de sesión es justamente una de las quejas actuales.

**Preguntas al cliente:**
- "¿Puede conseguir que TI nos dé ese acceso? Si no llega a tiempo, ¿acepta que en la presentación se entre con un enlace enviado al correo institucional?"
- "¿Cuál es el dominio exacto de los correos de los estudiantes?"

---

## 8. Secciones 3 y 4 — No está definido qué significa "disponible" (RN-10, RN-11, RN-25)

**Detectado por:** IA · **Gravedad:** alta

**Frase del PRD:**

> **RN-10.** Una solicitud pendiente **no bloquea** la disponibilidad: el artículo sigue apareciendo como disponible para otros estudiantes y puede recibir varias solicitudes en el mismo horario.

**Por qué es un problema:**
- La búsqueda "como Airbnb" (ítem 4) promete mostrar "solo lo que está disponible", pero el PRD nunca dice qué cuenta como disponible.
- RN-25 mezcla el estado actual de la unidad (libre u ocupado) con reservas que son por franjas de tiempo.
- RN-11 no aclara si el sistema impide aprobar una solicitud posterior o solo la marca.
- Es la base de todo el sistema, y el cliente dijo que hoy la disponibilidad "es un lío".

**Preguntas al cliente:**
- "Una vez aprobada una reserva, ¿el artículo debe desaparecer de la búsqueda para ese horario?"
- "Si hay dos solicitudes que chocan, ¿puede usted aprobar la segunda antes que la primera, o el sistema debe impedirlo?"

---

## 9. Sección 4 — El carrito que caduca repite la queja principal (RN-08)

**Detectado por:** IA · **Gravedad:** media

**Frase del PRD:**

> **RN-08.** Si el carrito pasa **1 hora** sin enviarse, se vacía y se cierra la sesión.

**Por qué es un problema:**
- La queja número uno del cliente es que el carrito se borra solo, y RN-08 programa justo eso.
- Como el carrito no aparta artículos (RN-10), vaciarlo no protege a nadie.
- La fuente solo responde "1 hora" a la pregunta de cuándo se cierra la sesión. Lo de "se vacía" se agregó en el PRD.

**Pregunta al cliente:** "Pasada la hora, ¿se cierra la sesión pero el carrito sigue guardado, o el carrito se vacía?"

---

## 10. Sección 4 — Computadoras de madrugada con la bodega cerrada (RN-16)

**Detectado por:** IA · **Gravedad:** media

**Frase del PRD:**

> **RN-16.** Las computadoras son la excepción: se pueden reservar fuera del horario laboral, incluso de madrugada.

**Por qué es un problema:**
- RN-15 solo permite retirar y devolver equipos en horario laboral, así que a las 2:00 nadie entrega ni recibe.
- No se sabe si las computadoras se prestan para llevar o se usan en el espacio, ni quién abre ese espacio.
- El PRD no dice qué días son laborables.
- Como no hay duración máxima (RN-07), una reserva podría ir de viernes a lunes y no hay regla para eso.

**Preguntas al cliente:**
- "¿Las computadoras se usan en el espacio o se llevan?"
- "¿Quién da acceso fuera de horario?"
- "¿Qué pasa con los fines de semana y los feriados?"

---

## 11. Sección 4 — Penalización sin margen ni efecto sobre reservas futuras (RN-22, RN-23)

**Detectado por:** IA · **Gravedad:** media

**Frase del PRD:**

> **RN-22.** Si un estudiante devuelve un equipo después de la hora acordada, queda **bloqueado 14 días** y no puede enviar solicitudes durante ese tiempo.

**Por qué es un problema:**
- Tal como está escrita, un minuto de retraso bloquea 14 días. Para retirar hay 30 minutos de margen, pero para devolver ninguno.
- No dice qué pasa con las reservas que el estudiante ya tiene aprobadas.
- Tampoco dice quién registra la hora real de devolución, ni si el bloqueo es automático o lo confirma el administrador.
- RN-23 sale de una nota confusa de la visita ("Bloquea el sistema si hay una pagina del administrador por algun usuario dañado…"), pero el PRD la presenta como una regla firme.

**Preguntas al cliente:**
- "¿Hay un margen para devolver?"
- "¿Las reservas futuras de un estudiante bloqueado se cancelan?"
- "¿El bloqueo es automático y se puede quitar antes de tiempo?"

---

## 12. Secciones 3 y 4 — El comprobante en PDF entra al MVP aunque el cliente dijo "después de diciembre" (ítem 17, RN-28)

**Detectado por:** IA · **Gravedad:** media

**Frase del PRD:**

> **Comprobante electrónico:** cada reserva aprobada genera un comprobante en PDF.

**Por qué es un problema:**
- La nota de la visita dice: "Solo comprobantes electronicos, en el historial, ya sale la solicitud, conectar con el workflow. **Después de diciembre.** Un correo. Con el comprobante de pago."
- El PRD saca del MVP solo la conexión con el workflow y el pago (sección 5), pero deja el PDF y el correo que lo envía (RN-28). Es probable que todo ese bloque sea para después de diciembre.
- "Comprobante de compra" (D-22) además da a entender que hay cobros, algo que nadie aclaró (P-22).

**Pregunta al cliente:** "¿Para diciembre basta con que la reserva aprobada se vea en el historial, y el comprobante en PDF llega después?"

---

## 13. Secciones 3 y 6 — Ficha del estudiante con una "puntuación" inventada (ítem 3, D-36)

**Detectado por:** IA · **Gravedad:** media

**Frase del PRD:**

> **Ficha del estudiante:** el administrador ve el semestre, las materias, la puntuación y el estado de bloqueo de cada estudiante.

**Por qué es un problema:**
- La fuente solo dice, bajo el título "Indicadores": "Que semestre que materias. 5 estrellas en uber. Score. Fue bloqueado. Todo correcto. Nivel de semestre."
- Eso también puede referirse a los indicadores de los reportes (qué semestres o materias usan más los equipos).
- El PRD lo convirtió en una calificación de 1 a 5, y la forma de calcularla (P-15) y de cargar los datos (P-16) son inventadas.
- Además, obliga al administrador a escribir a mano el semestre y las materias de cada estudiante.

**Pregunta al cliente:** "Cuando habló de 'indicadores', ¿se refería a calificar a cada estudiante o a datos para los reportes? ¿Quién calificaría?"