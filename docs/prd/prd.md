# PRD — USFQ Reserva COCOA

**Estado:** borrador v0.2 (incluye las correcciones de [revision.md](revision.md))
**Fuentes:** resúmenes 1–5 de la entrevista con el cliente (Zoom) y documento *Web 3 – Contexto* (análisis del equipo y notas de la visita al cliente del 11 de noviembre de 2026).
**Regla de conflicto:** cuando las fuentes se contradicen, prevalece lo que respondió el cliente en la visita del 11 de noviembre.
**Aprobadores:** Santiago (administrador) y Luis Daniel (su jefe).

---

## 1. Problema y objetivo

### Problema
La plataforma actual de reservas del COCOA no permite que los estudiantes reserven equipos y espacios por su cuenta:

- El carrito se borra solo, así que no se puede reservar más de un artículo a la vez. El cliente no sabe por qué desaparecen los artículos.
- Iniciar sesión falla y recuperar la contraseña es difícil.
- Los estudiantes no reciben confirmación ni notificación de ningún tipo.
- Entrar y trabajar como administrador es complicado, y no hay un flujo claro para aprobar o rechazar reservas.
- Se permiten correos personales (p. ej. Gmail), así que no se puede comprobar si el usuario pertenece a la universidad.
- Los horarios causan confusión entre AM y PM.
- Por todo esto, el administrador atiende a mano hasta **10 estudiantes por hora**.
- La plataforma actual cuesta **USD 3.000 al año**.

### Objetivo
Construir desde cero una plataforma web, pensada primero para el celular, en la que los estudiantes de la USFQ reserven **varios equipos y espacios en una sola solicitud** sin ayuda del administrador. El administrador debe poder aprobar las reservas, gestionar el inventario y controlar los préstamos desde la misma herramienta.

---

## 2. Usuarios

| Perfil | Quién es | Lo que necesita hacer |
|---|---|---|
| **Estudiante** | Alumno de las carreras de cine, periodismo y comunicación, con una cuenta creada por el administrador. Usa sobre todo el celular. | Entrar con su correo y contraseña de la universidad. Buscar lo que está disponible por fecha y hora. Armar un carrito con varios equipos, kits o espacios. Enviar una sola solicitud. Ver si está pendiente, aprobada o rechazada. Cancelar. Consultar su historial. Recibir avisos y recordatorios por correo. |
| **Administrador** | Santiago y Luis Daniel (2 administradores). También usan el celular. | Crear, dar de baja y bloquear estudiantes. Aprobar o rechazar solicitudes. Modificar cualquier carrito o solicitud. Dar de alta, editar y dar de baja equipos, unidades, kits y espacios. Cambiar el estado de los equipos. Configurar horarios. Dejar notas en las reservas. Ver su panel del día. Exportar reportes. |
| **Bodega COCOA** | Personal de la bodega donde se entregan y reciben los equipos. Mencionado en la visita ("2 administradores + bodega COCOA"). Sus permisos no están definidos (ver P-03). | Entregar y recibir equipos, y dejar constancia de retiros y devoluciones. |

Los profesores **no son usuarios** de la plataforma.

---

## 3. Alcance del MVP

Falta que el cliente diga qué entra en la entrega del 2 de diciembre (ver P-28).

1. **Inicio de sesión institucional:** solo con correo de la USFQ y la misma contraseña de la universidad, sin opción de registro propio (ver P-05).
2. **Gestión de cuentas:** el administrador crea, da de baja, bloquea y desbloquea a los estudiantes.
3. **Ficha del estudiante:** el administrador ve el estado de bloqueo de cada estudiante. Semestre, materias y puntuación quedan pendientes (ver P-40).
4. **Búsqueda por fecha:** el estudiante elige primero la fecha y el horario, y después ve solo lo que está disponible, como en Airbnb (qué cuenta como disponible: ver RN-25 y P-31).
5. **Buscador y filtros:** se puede buscar por nombre de producto y fecha, y filtrar por kits o productos sueltos.
6. **Catálogo:** cada equipo y espacio muestra su nombre, sus datos y una o dos fotos.
7. **Selección de unidad:** cuando un producto tiene unidades numeradas, el estudiante elige una (como si fuera una talla de ropa).
8. **Kits:** el administrador arma conjuntos de productos que se reservan como un solo artículo.
9. **Carrito persistente:** guarda varios artículos y no se borra solo (ver RN-08).
10. **Solicitud única:** todo el carrito se envía como una sola solicitud, con una nota opcional del estudiante.
11. **Estado tras el envío:** al enviar, la página muestra "En espera de aprobación".
12. **Aprobación y rechazo:** el administrador aprueba o rechaza cada solicitud, sin tener que dar un motivo.
13. **Edición por el administrador:** el administrador puede modificar cualquier carrito o solicitud.
14. **Notas internas:** el administrador deja notas en la reserva que el estudiante no ve.
15. **Cancelación:** el estudiante cancela sus reservas desde su cuenta.
16. **Historial:** el estudiante consulta sus reservas pasadas y las aprobadas.
17. **Comprobante electrónico:** *provisionalmente fuera del MVP.* El comprobante en PDF pasa a después de diciembre (ver P-39); mientras tanto, la reserva aprobada se ve en el historial.
18. **Gestión de inventario:** el administrador da de alta, edita y da de baja equipos, unidades, kits y espacios, y lleva un contador de existencias.
19. **Estados de equipo:** cada unidad está en uno de tres estados: libre, ocupado o en mantenimiento.
20. **Carga inicial desde Excel:** el inventario se importa del archivo Excel del cliente, con las fotos.
21. **Horarios por artículo:** cada equipo o espacio tiene su propia franja de disponibilidad, que se reserva en bloques de 30 minutos.
22. **Retiros y devoluciones:** se registra cuándo se retiró y cuándo se devolvió cada reserva.
23. **Penalizaciones:** el sistema bloquea al estudiante que devuelve tarde o daña un equipo.
24. **Panel diario del administrador:** muestra las reservas agendadas para el día y los productos en mantenimiento.
25. **Avisos por correo:** se envían correos al solicitar, aprobar, rechazar y cancelar, y como recordatorio de la reserva y de la devolución.
26. **Reportes en Excel:** se exportan las reservas por estudiante y los equipos más usados.
27. **Idioma:** la interfaz está en español y tiene un botón para cambiar a inglés.
28. **Diseño adaptable:** la parte del estudiante y la del administrador funcionan bien en el celular.
29. **Identidad visual:** se usan los colores, logos y estética de la USFQ y del COCOA.
30. **Chatbot de preguntas frecuentes (deseable):** asistente dentro de la web. El cliente lo pidió "de preferencia", así que va al final de la prioridad (ver P-17).

---

## 4. Reglas de negocio

**Acceso**

- **RN-01.** Solo pueden iniciar sesión correos del dominio institucional de la USFQ (dominio exacto: ver P-30). Cualquier otro dominio (Gmail, Outlook personal, etc.) se rechaza.
- **RN-02.** La pantalla de inicio de sesión no tiene botón de "crear cuenta". Solo pueden entrar los correos que un administrador registró antes.
- **RN-03.** La contraseña es la misma de la universidad. La plataforma no guarda contraseñas propias. Para eso hace falta que TI de la USFQ dé acceso (ver P-05).
- **RN-04.** Un estudiante dado de baja no puede iniciar sesión.

**Carrito y solicitudes**

- **RN-05.** Todos los artículos del carrito se envían en **una sola solicitud**. No hay un tope de artículos por solicitud, y el sistema debe aceptar al menos **25** (ver P-06).
- **RN-06.** No hay límite de reservas por estudiante.
- **RN-07.** No hay duración mínima ni máxima de reserva.
- **RN-08.** Si el carrito pasa **1 hora** sin enviarse, se cierra la sesión, pero el carrito queda guardado (provisional, ver P-33).
- **RN-09.** Las solicitudes se pueden enviar a cualquier hora del día, cualquier día.
- **RN-10.** Una solicitud pendiente **no bloquea** la disponibilidad: el artículo sigue apareciendo como disponible para otros estudiantes y puede recibir varias solicitudes en el mismo horario. Qué pasa con una reserva aprobada: ver P-31.
- **RN-11.** Si dos solicitudes se superponen, tiene prioridad la que se envió primero. Si el sistema impide o solo avisa al aprobar la posterior: ver P-32.
- **RN-12.** En los productos con unidades numeradas (p. ej. Oculus #1 a #6), el estudiante debe elegir una unidad concreta. En los productos sin numerar (p. ej. trípodes), solo elige la cantidad.

**Horarios**

- **RN-13.** Los horarios se reservan en bloques de **30 minutos**.
- **RN-14.** Los horarios se muestran en formato de **24 horas** para evitar confusiones entre AM y PM (ver P-08).
- **RN-15.** Los equipos se entregan y se reciben **solo en horario laboral, de 08:30 a 17:00**. Fuera de esa franja no se puede elegir hora de retiro ni de devolución. Qué días son laborables: ver P-35.
- **RN-16.** Las computadoras son la excepción: se pueden reservar fuera del horario laboral, incluso de madrugada. Cómo se usan y quién da acceso fuera de horario: ver P-34.
- **RN-17.** El espacio de computadoras y cada computadora individual los reservan los estudiantes, igual que cualquier otro artículo. No hay restricción por rol.

**Aprobación, cancelación y retiro**

- **RN-18.** El administrador puede aprobar o rechazar sin indicar un motivo.
- **RN-19.** El estudiante puede cancelar una reserva hasta **1 hora antes** de que empiece.
- **RN-20.** Si el estudiante no viene a retirar el equipo dentro de los **30 minutos** de tolerancia, la reserva se libera automáticamente.
- **RN-21.** El administrador puede modificar cualquier carrito o solicitud, aunque esté pendiente o aprobada.

**Penalizaciones e inventario**

- **RN-22.** Si un estudiante devuelve un equipo después de la hora acordada, queda **bloqueado 14 días** y no puede enviar solicitudes durante ese tiempo. Margen para devolver y quién registra la hora: ver P-36. Qué pasa con sus reservas futuras: ver P-37.
- **RN-23.** Si el administrador registra que un estudiante dañó un equipo, el estudiante queda **bloqueado 14 días** de forma automática. Esta regla sale de una nota confusa de la visita (ver P-38).
- **RN-24.** Una unidad marcada como dañada o extraviada sale del catálogo y no se puede reservar.
- **RN-25.** Cada unidad está siempre en uno de estos estados: **libre**, **ocupado** o **en mantenimiento**. Las que están en mantenimiento no se pueden reservar. El estado dice cómo está la unidad ahora; que esté disponible para una fecha y hora depende de las reservas de esa franja (ver P-31).
- **RN-26.** Cada equipo tiene **una o dos fotos**, nunca más de dos.

**Notificaciones y comprobantes**

- **RN-27.** Al enviar la solicitud, el estudiante ve en la página el mensaje "En espera de aprobación" y no recibe correo. Los administradores sí reciben un correo.
- **RN-28.** Cuando se aprueba la solicitud, el estudiante recibe un correo de aprobación y el administrador recibe una confirmación. Adjuntar el comprobante queda provisionalmente para después de diciembre (ver P-39).
- **RN-29.** Cuando se rechaza la solicitud, el estudiante recibe un correo.
- **RN-30.** Cuando se cancela una reserva, se envía un correo (a quién exactamente, ver P-14).
- **RN-31.** El estudiante recibe un recordatorio por correo antes de que empiece la reserva y otro antes de la hora de devolución (cuánto antes, ver P-13).
- **RN-32.** Todos los correos salen al correo institucional y solo a él.
- **RN-33.** Las reservas aprobadas se ven en el historial del estudiante. Cuando haya comprobantes (provisionalmente después de diciembre, ver P-39), serán solo electrónicos.

**Interfaz**

- **RN-34.** La interfaz se abre en español por defecto y cambia a inglés con un botón.

---

## 5. Fuera de alcance

| Elemento | Motivo |
|---|---|
| Bot de WhatsApp | En la entrevista quedó como un requerimiento aparte, fuera de esta primera versión. |
| Registro propio de estudiantes | Lo decidió el cliente: solo el administrador crea cuentas, para controlar el acceso y dar de baja a quienes ya no pertenecen a la universidad. |
| Inicio de sesión con correos personales | Lo decidió el cliente: los correos personales impiden identificar a los estudiantes. |
| Contraseñas propias y su recuperación | Se usa la contraseña de la universidad, así que la plataforma no las administra. |
| Integración con el *workflow* institucional y comprobantes de pago | El cliente lo dejó para "después de diciembre". |
| Comprobante en PDF y su envío por correo (provisional) | La nota de la visita lo pone en el mismo bloque que el *workflow*, "después de diciembre". Falta que el cliente lo confirme (P-39). |
| Motivo obligatorio al rechazar | El cliente dijo que no hace falta. |
| Límites de reservas por estudiante y de duración | El cliente dijo que no los hay. |
| Migrar o rediseñar la plataforma actual | Se parte de cero ("ningún problema desde cero"). La plataforma actual solo sirve como referencia de lo que no hay que repetir. |

---

## 6. Decisiones del cliente

Las decisiones de la entrevista no tienen fecha porque los resúmenes no la registran (ver P-20).

| # | Decisión | Fecha |
|---|---|---|
| D-01 | Hay dos roles base: estudiante y administrador. | Entrevista (sin fecha) |
| D-02 | Solo se entra con correo institucional, nunca con correos personales. | Entrevista (sin fecha) |
| D-03 | Solo el administrador crea y da de baja usuarios. | Entrevista; confirmado el 11/11/2026 |
| D-04 | La plataforma permite reservar tanto equipos (cine, periodismo, comunicación) como espacios (p. ej. el estudio de TV). | Entrevista (sin fecha) |
| D-05 | El inventario inicial se carga desde el Excel del cliente, con una o dos fotos por equipo. | Entrevista (sin fecha) |
| D-06 | Debe haber reportes de uso en Excel. | Entrevista (sin fecha) |
| D-07 | El bot de WhatsApp queda fuera de esta versión. | Entrevista (sin fecha) |
| D-08 | Los aprobadores y *testers* son Santiago y Luis Daniel, que asistirán a la presentación final. | Entrevista (sin fecha) |
| D-09 | Todos los artículos van en una sola solicitud, con la cantidad que el estudiante quiera ("25 ítems si quieren"). | 11/11/2026 |
| D-10 | Una solicitud pendiente no bloquea la disponibilidad, así que puede haber solicitudes dobles. | 11/11/2026 |
| D-11 | Si hay conflicto, tiene prioridad quien reservó primero. | 11/11/2026 |
| D-12 | No hay límite de reservas por estudiante. | 11/11/2026 |
| D-13 | No hay duración mínima ni máxima de reserva. | 11/11/2026 |
| D-14 | Hay que añadir una casilla para una nota corta, "externa e interna". | 11/11/2026 |
| D-15 | El estudiante puede tener artículos en el carrito 1 hora antes de que la sesión se cierre sola. | 11/11/2026 |
| D-16 | En los productos con unidades, se elige una unidad concreta, como una talla de ropa. Los trípodes no llevan número. | 11/11/2026 |
| D-17 | Quien devuelve tarde queda bloqueado dos semanas. Quien daña un equipo, también dos semanas, de forma automática. | 11/11/2026 |
| D-18 | Un equipo dañado o extraviado sale del sistema. | 11/11/2026 |
| D-19 | Los estados de un equipo son libre, ocupado y en mantenimiento. | 11/11/2026 |
| D-20 | La contraseña es la misma de la universidad. | 11/11/2026 |
| D-21 | Se puede cancelar hasta 1 hora antes. Si el estudiante no llega a retirar dentro de los 30 minutos de margen, el equipo se libera. | 11/11/2026 |
| D-22 | Los reportes incluyen las reservas por estudiante (exportables como PDF a modo de comprobante) y los equipos más usados. | 11/11/2026 |
| D-23 | Solo hay disponibilidad en horario laboral, salvo las computadoras. El retiro y la devolución son de 08:30 a 17:00. Las solicitudes se pueden enviar a cualquier hora. | 11/11/2026 |
| D-24 | Los horarios se manejan en bloques de media hora, en formato de 24 h. | 11/11/2026 |
| D-25 | No hace falta indicar el motivo de un rechazo. | 11/11/2026 |
| D-26 | El estudiante puede ver el historial de sus reservas. | 11/11/2026 |
| D-27 | Se envían correos al solicitar, al aprobar (al alumno y al administrador) y al cancelar, más recordatorios de la reserva y de la devolución. | 11/11/2026 |
| D-28 | Al enviar la solicitud, la espera de aprobación se muestra solo en la página. Al aprobarse, llega el comprobante por correo (el comprobante queda provisionalmente para después de diciembre, P-39). | 11/11/2026 |
| D-29 | El administrador puede modificar todos los carritos y dejar notas en las reservas. | 11/11/2026 |
| D-30 | La búsqueda funciona como Airbnb: primero la fecha y después los productos disponibles. | 11/11/2026 |
| D-31 | Debe haber kits, con filtro por kits o por productos, y un contador de existencias. | 11/11/2026 |
| D-32 | Se desarrolla desde cero, con la identidad visual de la USFQ y del COCOA. | 11/11/2026 |
| D-33 | La interfaz está en español por defecto, con botón para pasar a inglés. | 11/11/2026 |
| D-34 | Se prioriza el celular, también para el administrador. | 11/11/2026 |
| D-35 | El administrador tiene un panel diario con las reservas del día y los productos en mantenimiento. | 11/11/2026 |
| D-36 | Indicadores, según la nota literal: "Que semestre que materias. 5 estrellas en uber. Score. Fue bloqueado. Todo correcto. Nivel de semestre." Qué significa está pendiente (P-40). | 11/11/2026 |
| D-37 | Los términos y condiciones son opcionales. | 11/11/2026 |
| D-38 | El chatbot se incluye "de preferencia". | 11/11/2026 |
| D-39 | El cliente entrega el Excel de productos en la semana 15. | 11/11/2026 |
| D-40 | La tecnología será Supabase y el nombre del producto, "USFQ Reserva COCOA". | 11/11/2026 |

---

## 7. Supuestos y preguntas abiertas

| # | Pregunta abierta | Supuesto provisional |
|---|---|---|
| P-01 | ¿Cuál es el presupuesto mensual real? Los resúmenes dicen USD 150 en cuatro casos y USD 1,50 en uno, y la visita no dio una cifra. | **USD 150 al mes** para *hosting*, base de datos y correo. |
| P-02 | ¿Qué se entrega exactamente en diciembre: un prototipo o un sistema listo para usar? | Un **prototipo funcional**, que se presenta al cliente. Qué funcionalidades entran depende de P-28. El cliente elige una propuesta y se implementa después. |
| P-03 | ¿Qué permisos tiene la bodega COCOA? ¿Es un perfil aparte o un lugar? | La bodega usa una **cuenta de administrador**. No se crea un tercer rol en el MVP. |
| P-04 | ~~¿Los profesores son un perfil con cuenta propia?~~ | **Resuelta.** Los profesores no son usuarios. Las computadoras y su espacio los reservan los estudiantes, sin restricción por rol (RN-17). |
| P-05 | "¿Puede conseguir que TI de la USFQ nos dé acceso para conectar el inicio de sesión institucional? ¿Con qué sistema? Si no llega a tiempo, ¿acepta que en la presentación se entre con un enlace enviado al correo institucional?" | Se pide el acceso a TI. Ninguna fuente dice qué sistema usa la universidad, así que no se da por hecho que sea Microsoft. Si el acceso no llega a tiempo, en la presentación se entra con un **enlace enviado al correo institucional**, solo para los correos que el administrador registró antes. |
| P-06 | ¿El "25 ítems" es un máximo por solicitud o solo un ejemplo? | Es un ejemplo: no hay tope, y se prueba con 25. |
| P-07 | ¿El plazo de 1 hora del carrito cuenta desde el último cambio o desde que se añade el primer artículo? ¿El carrito aparta los artículos durante ese tiempo? | Cuenta desde el **último cambio**, y el carrito **no aparta** artículos (coherente con RN-10). |
| P-08 | ¿"24H" significa formato de 24 horas o que se puede solicitar las 24 horas? | Las dos cosas: los horarios se muestran en formato de 24 h y las solicitudes se aceptan a cualquier hora. |
| P-09 | ~~¿El retiro y la devolución terminan a las 17:20 o a las 17:00 ("hasta las 5 PM")?~~ | **Resuelta.** La franja es **08:30–17:00**, y la configura el administrador. |
| P-10 | ~~¿El margen para retirar el equipo es de 15 o de 30 minutos? ¿Depende del tipo de artículo?~~ | **Resuelta.** El margen es de **30 minutos** para todo, y el administrador puede cambiarlo. |
| P-11 | Cuando se aprueba una solicitud, ¿qué pasa con las demás pendientes que se superponen? | Se aprueba primero la más antigua. Las que chocan con ella se marcan como conflicto y el administrador las rechaza o modifica a mano. |
| P-12 | ¿Qué es la nota "externa e interna"? | La nota **externa** la escribe el estudiante y la ve el administrador. La **interna** la escribe el administrador y el estudiante no la ve. |
| P-13 | ¿Con cuánta anticipación se envían los recordatorios? ¿Qué significa "notificaciones cada cierto tiempo"? | Un recordatorio **24 h antes** de que empiece la reserva y otro **1 h antes** de la devolución. No hay más avisos periódicos. |
| P-14 | ¿Quién recibe el correo cuando se cancela una reserva? | El **estudiante y los administradores**. |
| P-15 | ¿Cómo se calcula la puntuación "5 estrellas" del estudiante? | Depende de P-40. Mientras no se resuelva, **no se calcula ninguna puntuación**. |
| P-16 | ¿De dónde salen el semestre y las materias del estudiante? | Depende de P-40. Mientras no se resuelva, **no se cargan esos datos**. |
| P-17 | ¿El chatbot debe estar en el MVP, en qué canal y con qué contenido? | Es un chatbot web de preguntas frecuentes, con **prioridad más baja**. Si no da tiempo, sale del MVP. |
| P-18 | ¿Qué incluye cada kit y si se reserva entero o por partes? | El administrador define qué contiene cada kit, que se reserva entero. Un kit está disponible solo si lo están todas sus piezas. |
| P-19 | ¿Cuáles son las políticas de uso, dónde están escritas y hay que guardar prueba de que se aceptaron? | Los términos son opcionales. Si el administrador los carga, se muestran antes de enviar la solicitud y se guarda la aceptación (usuario y fecha). |
| P-20 | ¿En qué fecha fue la entrevista por Zoom? | No consta en las fuentes. Se registra como anterior al 11/11/2026. |
| P-21 | ¿El Excel identifica cada unidad por separado? ¿Quién lo mantiene actualizado después? | Se completa la numeración de unidades al importarlo. Después, el administrador mantiene el inventario desde la plataforma. |
| P-22 | ¿Las reservas tienen costo para el estudiante? (El Excel trae costos y se habla de "comprobante de compra"). | En el MVP **no se cobra**. El costo solo se guarda como dato del inventario y el comprobante es de la reserva. |
| P-23 | ¿Qué incluye el reporte de "reservas por estudiante" y cómo es el PDF con "sello físico"? | El reporte trae el estudiante, los artículos, las fechas y el estado. El PDF es el comprobante imprimible de la reserva, con un espacio para el sello, y queda provisionalmente para después de diciembre (P-39). |
| P-24 | ¿Un estudiante bloqueado puede entrar a la plataforma? | Sí: entra y ve su historial, pero no puede enviar solicitudes. |
| P-25 | ¿Por qué es difícil hoy entrar como administrador? | No se sabe. Hay que revisar el enlace de la plataforma actual, que el cliente todavía no envió. |
| P-26 | ¿Desde cuándo cuenta la hora límite para cancelar en una reserva de varios artículos? | Desde el inicio del **primer** artículo de la solicitud. |
| P-27 | Supuesto del equipo que la visita contradice: "la entrega y la devolución se gestionan fuera del sistema". | **Se descarta.** El sistema registra retiros y devoluciones (necesario para RN-22). |
| P-28 | "Si el 2 de diciembre solo pudieran funcionar 5 cosas, ¿cuáles serían?" El MVP tiene 30 funcionalidades y quedan 9 días desde el 23/11. | Se prioriza lo que pide el criterio de éxito principal del cliente: buscar, armar un carrito con varios artículos, enviar la solicitud, aprobarla o rechazarla, y gestionar el inventario. El chatbot es lo primero que sale (P-17). |
| P-29 | "¿Puede enviarnos el Excel de productos esta semana, aunque esté incompleto?" Si llega en la semana 15, no hay tiempo de probar la carga real. | Mientras no llegue el Excel, se desarrolla y se prueba con datos de ejemplo. |
| P-30 | "¿Cuál es el dominio exacto de los correos de los estudiantes?" | El dominio queda como un dato configurable y no se fija hasta que el cliente lo confirme. |
| P-31 | "Una vez aprobada una reserva, ¿el artículo debe desaparecer de la búsqueda para ese horario?" | **Sí.** Una reserva aprobada ocupa esa unidad en esa franja y la saca de la búsqueda. Las pendientes no la ocupan (RN-10). |
| P-32 | "Si hay dos solicitudes que chocan, ¿puede usted aprobar la segunda antes que la primera, o el sistema debe impedirlo?" | El sistema **no lo impide, pero avisa**: muestra que hay una solicitud anterior con prioridad (RN-11). El administrador decide, porque puede modificar cualquier solicitud (RN-21). |
| P-33 | "Pasada la hora, ¿se cierra la sesión pero el carrito sigue guardado, o el carrito se vacía?" La fuente solo dice "1 hora", en respuesta a cuándo se cierra la sesión. | **Se cierra la sesión y el carrito queda guardado**, para no repetir la queja principal (el carrito que se borra solo). |
| P-34 | "¿Las computadoras se usan en el espacio o se llevan? ¿Quién da acceso fuera de horario?" | Se usan **en el espacio de computadoras** (la visita las describe como "espacio de computadora", con cada computadora como subsección), sin pasar por la bodega. Quién da acceso fuera de horario sigue pendiente. |
| P-35 | "¿Qué días cuentan como laborables? ¿Qué pasa con los fines de semana y los feriados?" | Los días laborables los configura el administrador. Una reserva puede abarcar días no laborables (RN-07), pero el retiro y la devolución tienen que caer en la franja laboral (RN-15). |
| P-36 | "¿Hay un margen para devolver antes de bloquear?" También falta saber quién registra la hora real de devolución. | **Sin margen**, como dijo el cliente: cuenta cualquier retraso. Si fija un margen, se configura. La hora de devolución la registra quien recibe el equipo, con la cuenta de administrador (P-03). |
| P-37 | "¿Las reservas futuras de un estudiante bloqueado se cancelan?" | **Se mantienen.** El administrador puede cancelarlas o modificarlas (RN-21). |
| P-38 | "¿El bloqueo es automático? ¿Se puede quitar antes de que se cumplan las dos semanas?" RN-23 sale de una nota confusa de la visita. | Es **automático** al registrar la devolución tardía o el daño, y el administrador puede quitarlo antes (ítem 2 del alcance). |
| P-39 | "¿Para diciembre basta con que la reserva aprobada se vea en el historial, y el comprobante en PDF llega después?" La nota dice "después de diciembre" junto a los comprobantes y el *workflow*. | **Sí.** El comprobante en PDF y su envío por correo pasan a después de diciembre. En el MVP la reserva aprobada se ve en el historial y se avisa por correo. |
| P-40 | "Cuando habló de 'indicadores' (semestre, materias, 5 estrellas), ¿se refería a calificar a cada estudiante o a datos para los reportes? ¿Quién calificaría?" | En el MVP **no hay calificación de estudiantes**. La ficha solo muestra el estado de bloqueo ("Fue bloqueado"). |

---

## 8. Épicas del MVP

1. **E1 — Acceso y cuentas:** inicio de sesión con las credenciales de la USFQ, cuentas que crea el administrador, bajas, bloqueos y ficha del estudiante con su estado de bloqueo.
2. **E2 — Catálogo e inventario:** equipos, unidades numeradas, kits, espacios, fotos, estados, horarios por artículo, contador de existencias e importación desde Excel.
3. **E3 — Reserva del estudiante:** búsqueda por fecha, carrito persistente, solicitud única con nota, cancelación e historial.
4. **E4 — Operación administrativa:** aprobación y conflictos, edición de solicitudes, notas internas, retiros y devoluciones, penalizaciones, panel diario y reportes en Excel.
5. **E5 — Notificaciones y experiencia:** correos y recordatorios, interfaz en español e inglés, diseño para celular, identidad visual de la USFQ y el COCOA, y chatbot opcional.

---

## 9. Criterios de éxito y restricciones

### Criterios de éxito
- **Principal (cliente):** los estudiantes añaden varios artículos al carrito y completan su reserva **sin errores y sin ayuda del administrador**.
- Ya no hacen falta las solicitudes manuales, que hoy llegan a **10 por hora**.
- Ningún carrito se borra solo: solo se vacía si el estudiante lo envía o lo vacía (RN-08).
- Todos los correos de RN-27 a RN-31 llegan al destinatario que corresponde.
- Santiago y Luis Daniel aprueban la experiencia de uso como *testers* y en la presentación final.

### Restricciones
- **Plazo:** el prototipo funcional se presenta el 2 de diciembre de 2026, como proyecto final del semestre. Se compartirán avances intermedios con los aprobadores. No cabe todo el alcance de la sección 3 (ver P-28).
- **Insumos del cliente:** el Excel de productos llega en la semana 15 (se pidió adelantarlo, ver P-29). El enlace de la plataforma actual todavía no se ha enviado.
- **Tecnología:** Supabase, desarrollado desde cero, sin infraestructura previa. Se permiten herramientas de IA en el desarrollo.
- **Costo:** unos USD 150 al mes de operación (pendiente de confirmar, P-01), frente a los USD 3.000 al año que cuesta hoy.
- **Acceso:** solo con el correo y las credenciales institucionales de la USFQ. Depende de que TI de la USFQ dé acceso (ver P-05).
- **Plataforma:** pensada primero para el celular, en estudiante y administrador. Español por defecto, con inglés.
- **Marca:** colores, logos y estética de la USFQ y del COCOA.
