# PRD de USFQ Reserva COCOA

Versión 0.3, para el avance 2. Ya incluye los cambios que anotamos en [revision.md](revision.md).

De dónde sacamos todo: los cinco resúmenes de la entrevista por Zoom, nuestro documento del avance 1 (con lo que el cliente nos respondió en clase y en la visita del 11 de noviembre) y lo que vimos nosotras mismas en la plataforma que usan hoy, https://cocoausfq.ezrentalstore.com, que revisamos el 25 de noviembre.

Cuando dos fuentes dicen cosas distintas, nos quedamos con lo que dijo el cliente en la visita del 11 de noviembre.

Quienes aprueban son Santiago (el administrador) y Luis Daniel (su jefe).


## 1. Problema y objetivo

### Qué pasa hoy

Hoy el COCOA usa una tienda de alquiler de EZRentOut (cocoausfq.ezrentalstore.com) que está pensada para alquilar cosas, no para que los estudiantes de la universidad pidan equipos prestados. Según el cliente, y por lo que pudimos ver nosotras, los problemas son estos:

- El carrito se borra solo, entonces no se puede reservar más de una cosa a la vez. Ni el cliente sabe por qué desaparecen los artículos.
- Iniciar sesión falla y recuperar la contraseña es complicado.
- Los estudiantes no reciben ninguna confirmación ni aviso.
- Entrar como administrador es difícil y no hay un flujo claro para aprobar o rechazar reservas.
- Se puede entrar con correos personales. De hecho, la pantalla de inicio de sesión ofrece entrar con Google o con Microsoft, así que cualquiera con Gmail entra y no hay forma de saber si es de la universidad.
- Hay confusión con las horas (AM y PM).
- Primero se elige el producto y después la fecha, en cada tarjeta. El cliente quiere justo lo contrario: primero la fecha y después ver qué hay libre.
- La página está medio en español y medio en inglés: el menú dice "Catálogo" y "Mis órdenes", pero los botones dicen "Rent", "Add to Cart", "Check Availability" y el login dice "Welcome Back!".
- El catálogo es enorme y desordenado: 270 artículos en 45 páginas y 75 kits en 13 páginas. Las categorías mezclan marcas (MOJO, Matthews), salas (Sala MS-204, Salas de Proyección) y tipos de equipo, y hay una que se llama "Uncategorized" y otra repetida ("Interactividad").
- Los artículos sueltos dicen "Available: 2" y los kits dicen "In Stock" u "Out of Stock", y no queda claro para qué fechas.
- Los espacios (Estudio de TV, Estudio Podcast, la sala H104) están metidos como si fueran kits.
- Por todo esto, el administrador termina atendiendo a mano hasta 10 estudiantes por hora.
- La plataforma cuesta 3.000 dólares al año.

### Qué queremos lograr

Vamos a hacer desde cero una página web, pensada primero para el celular, donde los estudiantes de la USFQ puedan reservar varios equipos y espacios en una sola solicitud sin tener que pedirle ayuda al administrador. Y que el administrador, desde la misma herramienta, pueda aprobar reservas, manejar el inventario y llevar el control de los préstamos.


## 2. Usuarios

Estudiantes. Son de cine, periodismo y comunicación, y su cuenta la crea el administrador. Casi siempre entran desde el celular, entre clases. Necesitan entrar con su correo y contraseña de la U, buscar qué hay libre para una fecha y hora, armar un carrito con varios equipos, kits o espacios, mandar todo en una sola solicitud, ver si está pendiente, aprobada o rechazada, cancelar si hace falta, revisar su historial y recibir avisos y recordatorios por correo.

Administradores. Son dos: Santiago y Luis Daniel. También usan mucho el celular. Necesitan crear, dar de baja y bloquear estudiantes, aprobar o rechazar solicitudes, cambiar cualquier carrito o solicitud, agregar, editar y quitar equipos, unidades, kits y espacios, cambiar el estado de los equipos, configurar horarios, dejar notas en las reservas, ver su panel del día y sacar reportes.

Bodega COCOA. Es la gente de la bodega donde se entregan y se reciben los equipos. El cliente la mencionó en la visita ("2 administradores + bodega COCOA"), pero no sabemos qué permisos tendría (P-03). Lo que necesitan es entregar y recibir equipos y dejar registrado cuándo salió y cuándo volvió cada cosa.

Los profesores no son usuarios de la plataforma.


## 3. Alcance del MVP

Todavía falta que el cliente nos diga qué tiene que funcionar sí o sí el 2 de diciembre (P-28). Mientras tanto, vamos a trabajar en este orden:

- Primero (el núcleo): 1, 2, 4, 6, 7, 9, 10, 11, 12, 15, 16, 18, 19, 21 y 28.
- Después: 3, 5, 8, 13, 14, 20, 22, 23, 24, 25, 27 y 29.
- Si nos da el tiempo: 26 y 30. El chatbot (30) es lo primero que sacamos si no alcanzamos.

Lo que va a tener:

1. Inicio de sesión institucional: solo con el correo de la USFQ y la misma contraseña de la U, sin opción de registrarse (P-05).
2. Manejo de cuentas: el administrador crea, da de baja, bloquea y desbloquea estudiantes.
3. Ficha del estudiante: el administrador ve si un estudiante está bloqueado. Lo del semestre, las materias y la puntuación queda pendiente (P-40).
4. Búsqueda por fecha: el estudiante elige primero la fecha y la hora, y solo después ve lo que está libre, como en Airbnb (qué cuenta como libre está en RN-25 y P-31).
5. Buscador y filtros: se puede buscar por nombre y fecha, y filtrar por kits, equipos sueltos o espacios.
6. Catálogo: cada equipo o espacio aparece con su nombre, sus datos y una o dos fotos.
7. Elegir la unidad: si un equipo tiene unidades numeradas, el estudiante escoge cuál quiere, como cuando eliges una talla de ropa.
8. Kits: el administrador arma grupos de equipos que se reservan como si fueran uno solo.
9. Carrito que no se borra: guarda varias cosas y no se vacía solo (RN-08).
10. Una sola solicitud: todo el carrito se manda junto, con una nota opcional del estudiante.
11. Qué pasa después de enviar: la página muestra "En espera de aprobación".
12. Aprobar y rechazar: el administrador aprueba o rechaza cada solicitud, sin tener que explicar por qué.
13. El administrador puede editar: puede cambiar cualquier carrito o solicitud.
14. Notas internas: el administrador puede dejar notas en una reserva que el estudiante no ve.
15. Cancelar: el estudiante puede cancelar sus reservas desde su cuenta.
16. Historial: el estudiante ve sus reservas pasadas y las que tiene aprobadas.
17. Comprobante electrónico: por ahora queda fuera del MVP. El comprobante en PDF pasa para después de diciembre (P-39); mientras tanto, la reserva aprobada se ve en el historial.
18. Inventario: el administrador agrega, edita y quita equipos, unidades, kits y espacios, y tiene un contador de cuántos hay.
19. Estados de los equipos: cada unidad está libre, ocupada o en mantenimiento.
20. Carga desde Excel: el inventario inicial se sube desde el Excel del cliente, con las fotos.
21. Horario por artículo: cada equipo o espacio tiene su propio horario, y se reserva en bloques de 30 minutos.
22. Retiros y devoluciones: queda guardado cuándo se retiró y cuándo se devolvió cada reserva.
23. Bloqueos: el sistema bloquea al estudiante que devuelve tarde o daña un equipo.
24. Panel del día del administrador: muestra las reservas de hoy y los equipos que están en mantenimiento.
25. Correos: se mandan al solicitar, aprobar, rechazar y cancelar, más recordatorios antes de la reserva y antes de la devolución.
26. Reportes en Excel: reservas por estudiante y equipos más usados.
27. Idioma: todo en español, con un botón para pasar a inglés.
28. Que funcione bien en el celular, tanto para estudiantes como para administradores.
29. Identidad visual: colores, logos y estilo de la USFQ y del COCOA.
30. Chatbot de preguntas frecuentes, si alcanza: el cliente lo pidió "de preferencia", así que va al final (P-17).


## 4. Reglas de negocio

Las numeramos para poder citarlas después en las historias de usuario y en el código.

### Acceso

- RN-01. Solo se puede entrar con correos del dominio de la USFQ (el dominio exacto está pendiente, P-30). Gmail, Outlook personal o cualquier otro se rechaza.
- RN-02. En el inicio de sesión no hay botón de "crear cuenta". Solo entran los correos que el administrador registró antes.
- RN-03. La contraseña es la misma de la universidad, así que nosotras no guardamos contraseñas. Para eso necesitamos que TI de la USFQ nos dé acceso (P-05).
- RN-04. Un estudiante dado de baja ya no puede entrar.

### Carrito y solicitudes

- RN-05. Todo lo que está en el carrito se manda en una sola solicitud. No hay un máximo de artículos, y el sistema tiene que aguantar por lo menos 25 (P-06).
- RN-06. No hay límite de reservas por estudiante.
- RN-07. No hay duración mínima ni máxima para una reserva.
- RN-08. Si el carrito pasa 1 hora sin enviarse, se cierra la sesión, pero el carrito se queda guardado (provisional, P-33).
- RN-09. Las solicitudes se pueden mandar a cualquier hora y cualquier día.
- RN-10. Una solicitud pendiente no aparta nada: el artículo sigue apareciendo libre para los demás y puede recibir varias solicitudes para el mismo horario. Lo que pasa con una reserva ya aprobada está en P-31.
- RN-11. Si dos solicitudes chocan, gana la que se mandó primero. Si el sistema impide aprobar la segunda o solo avisa, está en P-32.
- RN-12. En los equipos con unidades numeradas (por ejemplo, Oculus #1 a #6) el estudiante elige una unidad. En los que no tienen número (como los trípodes) solo pone cuántos quiere.

### Horarios

- RN-13. Se reserva en bloques de 30 minutos.
- RN-14. Las horas se muestran en formato de 24 horas, para que nadie se confunda con AM y PM (P-08).
- RN-15. Los equipos se entregan y se reciben solo en horario laboral, de 08:30 a 17:00. Fuera de ese horario no se puede elegir hora de retiro ni de devolución. Qué días cuentan como laborables está en P-35.
- RN-16. Las computadoras son la excepción: se pueden reservar fuera de horario, incluso de madrugada. Cómo se usan y quién abre fuera de horario está en P-34.
- RN-17. El espacio de computadoras y cada computadora los reservan los estudiantes, igual que cualquier otra cosa. No hay restricción por rol.

### Aprobación, cancelación y retiro

- RN-18. El administrador puede aprobar o rechazar sin dar un motivo.
- RN-19. El estudiante puede cancelar hasta 1 hora antes de que empiece la reserva.
- RN-20. Si el estudiante no llega a retirar dentro de los 30 minutos de tolerancia, la reserva se libera sola.
- RN-21. El administrador puede cambiar cualquier carrito o solicitud, aunque ya esté pendiente o aprobada.

### Bloqueos e inventario

- RN-22. Si un estudiante devuelve un equipo después de la hora acordada, queda bloqueado 14 días y no puede mandar solicitudes en ese tiempo. El margen para devolver y quién registra la hora están en P-36; qué pasa con sus reservas futuras, en P-37.
- RN-23. Si el administrador registra que un estudiante dañó un equipo, el estudiante queda bloqueado 14 días automáticamente. Esta regla sale de una nota medio confusa de la visita (P-38).
- RN-24. Si una unidad se marca como dañada o extraviada, sale del catálogo y ya no se puede reservar.
- RN-25. Cada unidad está siempre libre, ocupada o en mantenimiento, y las que están en mantenimiento no se pueden reservar. En pantalla se muestran como Disponible, Ocupado y Mantenimiento. Ojo: el estado dice cómo está la unidad ahorita; si está libre para una fecha y hora depende de las reservas de esa franja (P-31).
- RN-26. Cada equipo tiene una o dos fotos, nunca más.

### Correos y comprobantes

- RN-27. Cuando el estudiante manda la solicitud, ve en la página "En espera de aprobación" y no le llega correo. A los administradores sí les llega uno.
- RN-28. Cuando se aprueba, al estudiante le llega un correo de aprobación y al administrador una confirmación. Adjuntar el comprobante queda para después de diciembre (P-39).
- RN-29. Cuando se rechaza, al estudiante le llega un correo. Esto lo supusimos nosotras porque el cliente no lo nombró en su lista de correos (P-41).
- RN-30. Cuando se cancela una reserva, se manda un correo (a quién exactamente, P-14).
- RN-31. El estudiante recibe un recordatorio antes de que empiece la reserva y otro antes de la hora de devolución (cuánto antes, P-13).
- RN-32. Todos los correos van solo al correo institucional.
- RN-33. Las reservas aprobadas se ven en el historial del estudiante. Cuando haya comprobantes (después de diciembre, P-39), serán solo electrónicos.

### Interfaz

- RN-34. La página se abre en español y tiene un botón para pasar a inglés. Todo el texto cambia de idioma, no solo una parte (hoy la plataforma actual mezcla los dos).

### Estados

- RN-35. Una reserva siempre está en uno de estos 8 estados. Los colores y textos de cada uno están en el [DESIGN.md](../../DESIGN.md).
  - En espera: el estudiante mandó la solicitud y espera la aprobación. Puede pasar a Aprobada, Rechazada o Cancelada.
  - Aprobada: el administrador la aprobó. Puede pasar a En curso, Cancelada o No retirada.
  - Rechazada: el administrador la rechazó, sin motivo (RN-18). Ahí termina.
  - Cancelada: la canceló el estudiante hasta 1 hora antes (RN-19) o la canceló el administrador (RN-21). Ahí termina.
  - No retirada: pasaron 30 minutos desde la hora de inicio y nadie la retiró (RN-20). Ahí termina.
  - En curso: se registró que el equipo salió o que empezó el uso del espacio. Puede pasar a Finalizada o Atrasada.
  - Atrasada: llegó la hora de devolución y todavía no se registra la devolución. Pasa a Finalizada cuando vuelve, y ahí se bloquea la cuenta (RN-22).
  - Finalizada: se registró la devolución o terminó el uso del espacio. Ahí termina.
- RN-36. "Conflicto" no es un estado, es una marca que le aparece a una solicitud En espera cuando choca con otra que se mandó antes para la misma unidad y horario (RN-11, P-11, P-32). Se quita cuando la otra se rechaza o se cancela.
- RN-37. La cuenta de un estudiante puede estar Activa, Bloqueada (hasta una fecha, RN-22 y RN-23) o Dada de baja (RN-04).
- RN-38. Aparte de los estados de RN-25, el administrador puede marcar una unidad como Dañada o Extraviada, y en ese caso sale del catálogo (RN-24).


## 5. Lo que queda fuera

- Bot de WhatsApp. En la entrevista quedó como algo aparte, no para esta primera versión.
- Que los estudiantes se registren solos. El cliente decidió que solo el administrador crea cuentas, para controlar quién entra y poder dar de baja a quien ya no está en la U.
- Entrar con correos personales o con "Login with Google". El cliente no quiere correos personales porque no se sabe quién es quién.
- Contraseñas propias y cómo recuperarlas. Se usa la contraseña de la U, así que no nos toca manejarlas.
- Conectar con el workflow de la universidad y los comprobantes de pago. El cliente lo dejó para "después de diciembre".
- El comprobante en PDF y mandarlo por correo (por ahora). En la nota de la visita está en el mismo grupo que el workflow, "después de diciembre". Falta que el cliente lo confirme (P-39).
- Pedir un motivo al rechazar. El cliente dijo que no hace falta.
- Límites de reservas por estudiante o de duración. El cliente dijo que no hay.
- Migrar o arreglar la plataforma actual de EZRentOut. Empezamos de cero ("ningún problema desde cero", nos dijo). La plataforma actual solo nos sirve para ver qué no repetir.
- Precios y cobros. La plataforma actual es una tienda de alquiler, pero el cliente no nos habló de cobrarle a los estudiantes (P-22).


## 6. Decisiones del cliente

De la entrevista por Zoom no tenemos fecha porque los resúmenes no la dicen (P-20). Todo lo demás es de la visita del 11 de noviembre de 2026.

De la entrevista (sin fecha):

- D-01. Hay dos roles: estudiante y administrador.
- D-02. Solo se entra con correo institucional, nunca con correos personales.
- D-03. Solo el administrador crea y da de baja usuarios. Lo volvió a confirmar el 11 de noviembre.
- D-04. Se pueden reservar equipos (de cine, periodismo y comunicación) y también espacios, como el estudio de TV.
- D-05. El inventario inicial se sube desde el Excel del cliente, con una o dos fotos por equipo.
- D-06. Tiene que haber reportes de uso en Excel.
- D-07. El bot de WhatsApp queda fuera de esta versión.
- D-08. Santiago y Luis Daniel son quienes aprueban y prueban, y van a estar en la presentación final.

Del 11 de noviembre de 2026:

- D-09. Todo va en una sola solicitud, con todas las cosas que el estudiante quiera ("25 ítems si quieren").
- D-10. Una solicitud pendiente no aparta nada, así que puede haber solicitudes dobles.
- D-11. Si hay choque, gana el que reservó primero.
- D-12. No hay límite de reservas por estudiante.
- D-13. No hay duración mínima ni máxima.
- D-14. Hay que poner una casilla para una notita, "externa e interna".
- D-15. El estudiante puede tener cosas en el carrito 1 hora antes de que se cierre la sesión.
- D-16. En los equipos con unidades se elige una en concreto, como una talla de ropa. Los trípodes no llevan número.
- D-17. El que devuelve tarde queda bloqueado dos semanas. El que daña un equipo, también dos semanas, automático.
- D-18. Un equipo dañado o perdido sale del sistema.
- D-19. Los estados de un equipo son libre, ocupado y en mantenimiento.
- D-20. La contraseña es la misma de la universidad.
- D-21. Se puede cancelar hasta 1 hora antes. Si el estudiante no llega a retirar en los 30 minutos de margen, el equipo se libera.
- D-22. Los reportes tienen las reservas por estudiante (que se pueden sacar en PDF como comprobante) y los equipos más usados.
- D-23. Solo hay disponibilidad en horario laboral, menos las computadoras. Se retira y se devuelve de 08:30 a 17:00. Las solicitudes se pueden mandar a cualquier hora.
- D-24. Las horas van en bloques de media hora y en formato de 24 horas.
- D-25. No hace falta decir por qué se rechaza.
- D-26. El estudiante puede ver su historial.
- D-27. Se mandan correos al solicitar, al aprobar (uno al estudiante y otro al administrador) y al cancelar, y además recordatorios de la reserva y de la devolución.
- D-28. Al mandar la solicitud, lo de "en espera de aprobación" se ve solo en la página. Cuando se aprueba, llega el comprobante por correo (el comprobante queda para después de diciembre, P-39).
- D-29. El administrador puede cambiar todos los carritos y dejar notas en las reservas.
- D-30. La búsqueda funciona como Airbnb: primero la fecha y después lo que está libre.
- D-31. Tiene que haber kits, un filtro para ver kits o productos, y un contador de existencias.
- D-32. Se hace desde cero, con la identidad de la USFQ y del COCOA.
- D-33. Todo en español, con un botón para pasar a inglés.
- D-34. Primero el celular, también para el administrador.
- D-35. El administrador tiene un panel del día con las reservas de hoy y los equipos en mantenimiento.
- D-36. Indicadores. La nota que tomamos dice tal cual: "Que semestre que materias. 5 estrellas en uber. Score. Fue bloqueado. Todo correcto. Nivel de semestre." Todavía no sabemos bien qué quiso decir (P-40).
- D-37. Los términos y condiciones son opcionales.
- D-38. El chatbot va "de preferencia".
- D-39. El cliente nos manda el Excel de productos en la semana 15.
- D-40. Se usa Supabase y el producto se llama "USFQ Reserva COCOA".


## 7. Supuestos y preguntas abiertas

Para cada duda ponemos la pregunta y lo que vamos a hacer mientras no nos respondan.

- P-01. ¿Cuál es el presupuesto real al mes? Cuatro resúmenes dicen 150 dólares y uno dice 1,50, y en la visita no nos dieron una cifra. Mientras tanto: 150 dólares al mes para hosting, base de datos y correos.
- P-02. ¿Qué entregamos en diciembre, un prototipo o algo listo para usar? Mientras tanto: un prototipo que funcione y que le presentamos al cliente. Qué entra depende de P-28. El cliente elige una propuesta y se implementa después.
- P-03. ¿Qué permisos tiene la bodega COCOA? ¿Es un perfil aparte o solo el lugar? Mientras tanto: la bodega usa una cuenta de administrador y no hacemos un tercer rol.
- P-04. ¿Los profesores tienen cuenta propia? Ya está resuelta: no son usuarios, y las computadoras y su espacio los reservan los estudiantes sin restricción (RN-17).
- P-05. ¿Puede conseguir que TI de la USFQ nos dé acceso para conectar el inicio de sesión de la U? ¿Con qué sistema? Si no llega a tiempo, ¿le parece que en la presentación se entre con un enlace que llega al correo institucional? Mientras tanto: le pedimos el acceso a TI. Hoy la plataforma actual ofrece "Login with Microsoft", pero eso no prueba que la U use Microsoft para todo, así que no lo damos por hecho. Si no llega a tiempo, en la presentación se entra con un enlace al correo institucional, solo para correos que el administrador ya registró.
- P-06. ¿Lo de "25 ítems" es el máximo o solo un ejemplo? Mientras tanto: es un ejemplo, no hay tope, y lo probamos con 25.
- P-07. ¿La hora del carrito cuenta desde el último cambio o desde que se pone la primera cosa? ¿El carrito aparta las cosas mientras tanto? Mientras tanto: cuenta desde el último cambio y no aparta nada (va con RN-10).
- P-08. ¿"24H" quiere decir formato de 24 horas o que se puede pedir a cualquier hora? Mientras tanto: las dos cosas.
- P-09. ¿El retiro y la devolución son hasta las 17:20 o hasta las 17:00? Ya está resuelta: de 08:30 a 17:00, y lo puede cambiar el administrador.
- P-10. ¿El margen para retirar es de 15 o de 30 minutos? Ya está resuelta: 30 minutos para todo, y lo puede cambiar el administrador.
- P-11. Cuando se aprueba una solicitud, ¿qué pasa con las otras pendientes que chocan? Mientras tanto: se aprueba primero la más antigua, las que chocan quedan marcadas como conflicto y el administrador las rechaza o las cambia.
- P-12. ¿Qué es la nota "externa e interna"? Mientras tanto: la externa la escribe el estudiante y la lee el administrador; la interna la escribe el administrador y el estudiante no la ve.
- P-13. ¿Con cuánto tiempo se mandan los recordatorios? ¿Qué es "notificaciones cada cierto tiempo"? Mientras tanto: uno 24 horas antes de que empiece la reserva y otro 1 hora antes de la devolución, y nada más.
- P-14. ¿A quién le llega el correo cuando se cancela? Mientras tanto: al estudiante y a los administradores.
- P-15. ¿Cómo se calcula lo de "5 estrellas"? Depende de P-40. Mientras tanto: no calculamos ninguna puntuación.
- P-16. ¿De dónde sacamos el semestre y las materias? Depende de P-40. Mientras tanto: no guardamos esos datos.
- P-17. ¿El chatbot va en el MVP, dónde y qué responde? Mientras tanto: es un chatbot dentro de la web para preguntas frecuentes, con la prioridad más baja. Si no alcanzamos, sale.
- P-18. ¿Qué tiene cada kit y se reserva entero o por partes? Mientras tanto: el administrador define qué tiene cada kit y se reserva entero. Un kit está libre solo si todas sus piezas lo están. En la plataforma actual vimos que los kits ya tienen su lista de piezas (por ejemplo, "KIT FS7 #1" con maleta de cámara, lente, etc.), así que podemos partir de ahí.
- P-19. ¿Cuáles son las políticas de uso, dónde están y hay que guardar que el estudiante las aceptó? Mientras tanto: los términos son opcionales; si el administrador los sube, se muestran antes de mandar la solicitud y guardamos quién aceptó y cuándo. En la plataforma actual no encontramos políticas escritas.
- P-20. ¿Qué día fue la entrevista por Zoom? No lo dicen las fuentes. Mientras tanto: la ponemos como antes del 11 de noviembre.
- P-21. ¿El Excel tiene cada unidad por separado? ¿Quién lo actualiza después? Mientras tanto: completamos la numeración al subirlo y después el administrador lo actualiza desde la plataforma. En la plataforma actual cada unidad tiene su propio número ("Item # 1459") y hay equipos con nombre numerado ("1-Editora 01", "10-Editora 10"), así que probablemente el Excel ya viene así.
- P-22. ¿Las reservas le cuestan algo al estudiante? El Excel trae costos y se habló de "comprobante de compra". Mientras tanto: no se cobra nada. El costo solo se guarda como dato del inventario y el comprobante es de la reserva, no de un pago.
- P-23. ¿Qué tiene el reporte de "reservas por estudiante" y cómo es el PDF con "sello físico"? Mientras tanto: el reporte tiene estudiante, artículos, fechas y estado. El PDF es el comprobante para imprimir, con espacio para el sello, y queda para después de diciembre (P-39).
- P-24. ¿Un estudiante bloqueado puede entrar? Mientras tanto: sí, entra y ve su historial, pero no puede mandar solicitudes.
- P-25. ¿Por qué es tan difícil entrar como administrador hoy? Ya vimos la parte pública de la plataforma, pero no la del administrador. Lo que sí vimos: el login está en inglés y ofrece tres formas de entrar (Google, Microsoft y correo con contraseña), lo que puede confundir. Mientras tanto: hacemos un solo botón de entrada, el mismo para estudiantes y administradores, y el sistema sabe qué rol tiene cada uno.
- P-26. En una reserva con varias cosas, ¿desde cuándo cuenta la hora límite para cancelar? Mientras tanto: desde que empieza la primera cosa de la solicitud.
- P-27. En el avance 1 supusimos que la entrega y la devolución se manejaban fuera del sistema, pero la visita dice otra cosa. Lo descartamos: el sistema registra retiros y devoluciones (lo necesitamos para RN-22).
- P-28. Si el 2 de diciembre solo pudieran funcionar 5 cosas, ¿cuáles serían? Son 30 funcionalidades y quedan muy pocos días. Mientras tanto: priorizamos lo que pide el criterio de éxito del cliente: buscar, armar un carrito con varias cosas, mandar la solicitud, aprobarla o rechazarla, y manejar el inventario. Lo primero que sale es el chatbot.
- P-29. ¿Nos puede mandar el Excel de productos esta semana, aunque no esté completo? Si llega en la semana 15 no nos da tiempo de probar la carga de verdad. Mientras tanto: trabajamos con datos de ejemplo sacados de lo que se ve en la plataforma actual (nombres, categorías y kits reales).
- P-30. ¿Cuál es exactamente el dominio de los correos de los estudiantes? Mientras tanto: el dominio es un dato que se puede configurar y no lo fijamos hasta que nos confirmen.
- P-31. Cuando se aprueba una reserva, ¿el artículo desaparece de la búsqueda para ese horario? Mientras tanto: sí. Una reserva aprobada ocupa esa unidad en ese horario y la saca de la búsqueda. Las pendientes no (RN-10).
- P-32. Si dos solicitudes chocan, ¿usted puede aprobar la segunda antes que la primera, o el sistema no debería dejar? Mientras tanto: el sistema deja, pero avisa que hay una anterior con prioridad (RN-11). Decide el administrador, porque puede cambiar cualquier solicitud (RN-21).
- P-33. Pasada la hora, ¿se cierra la sesión y el carrito sigue guardado, o el carrito se vacía? La respuesta del cliente fue solo "1 hora". Mientras tanto: se cierra la sesión y el carrito se queda, para no repetir justo la queja principal.
- P-34. ¿Las computadoras se usan ahí mismo o se las llevan? ¿Quién abre fuera de horario? Mientras tanto: se usan en el espacio de computadoras (en la visita se habló de "espacio de computadora" con cada computadora adentro), sin pasar por la bodega. Quién abre fuera de horario sigue pendiente. En la plataforma actual las computadoras aparecen como "Editora 01", "Editora 10", etc.
- P-35. ¿Qué días son laborables? ¿Qué pasa con fines de semana y feriados? Mientras tanto: los días los configura el administrador. Una reserva puede pasar por días no laborables (RN-07), pero el retiro y la devolución tienen que ser en horario laboral (RN-15).
- P-36. ¿Hay algún margen para devolver antes de bloquear? ¿Quién registra la hora real de devolución? Mientras tanto: sin margen, como dijo el cliente; cualquier retraso cuenta. Si después pone un margen, se configura. La hora la registra quien recibe el equipo, con la cuenta de administrador (P-03).
- P-37. ¿Se cancelan las reservas futuras de un estudiante bloqueado? Mientras tanto: no, se mantienen, y el administrador las puede cancelar o cambiar (RN-21).
- P-38. ¿El bloqueo es automático? ¿Se puede quitar antes de las dos semanas? RN-23 sale de una nota confusa. Mientras tanto: es automático al registrar el atraso o el daño, y el administrador lo puede quitar antes.
- P-39. ¿Para diciembre basta con que la reserva aprobada aparezca en el historial y el PDF llega después? La nota dice "después de diciembre" junto a los comprobantes y el workflow. Mientras tanto: sí. El PDF y su correo pasan para después de diciembre. En nuestro layout ya dejamos diseñado el "Comprobante electrónico" en el detalle de la reserva, pero en el MVP no se muestra hasta que el cliente lo confirme.
- P-40. Cuando habló de "indicadores" (semestre, materias, 5 estrellas), ¿se refería a calificar a cada estudiante o a datos para los reportes? ¿Quién calificaría? Mientras tanto: no hay calificación de estudiantes en el MVP. La ficha solo dice si fue bloqueado.
- P-41. ¿Al estudiante le tiene que llegar un correo cuando le rechazan la solicitud? El cliente nombró correos al solicitar, aprobar y cancelar, pero no al rechazar. Mientras tanto: sí se manda (RN-29), porque si no, el estudiante no sabe que tiene que buscar otra cosa. Si el cliente dice que no, basta con que se vea en el historial.
- P-42. ¿Nos pueden pasar el manual de marca de la USFQ y del COCOA (logos, colores, tipografías)? El cliente pidió "colores de la u, estética, logos", pero no nos dio el manual. Mientras tanto: sacamos la paleta del logo de la USFQ (rojo #ED1C24 y #C41B1E, negro, #1A1A1A, gris claro #EEEEEE y blanco) y usamos Nexa para títulos y Roboto para textos, todo guardado como variables en el [DESIGN.md](../../DESIGN.md). Nexa necesita licencia para web; si no la conseguimos, usamos Montserrat. Cuando llegue el manual, solo cambiamos los valores.
- P-43. ¿Quieren modo oscuro? Nadie lo mencionó. Mientras tanto: no lo hacemos en el MVP.
- P-44. En nuestro layout pusimos un corazón para guardar favoritos y una campana de avisos. ¿Le sirven al cliente? Mientras tanto: los favoritos quedan fuera del MVP, y la campana solo muestra los mismos avisos que llegan por correo, más el de "en espera de aprobación" (RN-27).


## 8. Épicas del MVP

1. E1, Acceso y cuentas: entrar con la cuenta de la USFQ, cuentas que crea el administrador, bajas, bloqueos y la ficha del estudiante.
2. E2, Catálogo e inventario: equipos, unidades numeradas, kits, espacios, fotos, estados, horarios por artículo, contador y carga desde Excel.
3. E3, Reserva del estudiante: buscar por fecha, carrito que no se borra, una sola solicitud con nota, cancelar e historial.
4. E4, Trabajo del administrador: aprobar y ver conflictos, editar solicitudes, notas internas, retiros y devoluciones, bloqueos, panel del día y reportes en Excel.
5. E5, Avisos y experiencia: correos y recordatorios, español e inglés, diseño para celular, identidad de la USFQ y el COCOA, y el chatbot si alcanza.


## 9. Cómo sabremos que funciona, y nuestros límites

### Criterios de éxito

- El principal, según el cliente: los estudiantes pueden poner varias cosas en el carrito y terminar su reserva sin errores y sin pedirle ayuda al administrador.
- El administrador ya no tiene que atender solicitudes a mano (hoy son hasta 10 por hora).
- Ningún carrito se borra solo: solo se vacía si el estudiante lo manda o lo vacía él mismo (RN-08).
- Todos los correos de RN-27 a RN-31 le llegan a quien tienen que llegar.
- Santiago y Luis Daniel prueban la página y les parece fácil de usar, en las pruebas y en la presentación final.

### Restricciones

- Fecha: presentamos el prototipo el 2 de diciembre de 2026, como proyecto final del semestre. Vamos a ir mostrando avances a quienes aprueban. No nos alcanza el tiempo para todo lo de la sección 3 (P-28).
- Lo que nos tiene que dar el cliente: el Excel de productos llega en la semana 15 (pedimos que lo adelante, P-29). El enlace de la plataforma actual ya lo tenemos y lo revisamos.
- Tecnología: Supabase, desde cero y sin nada heredado. Podemos usar IA para desarrollar.
- Costo: alrededor de 150 dólares al mes (falta confirmar, P-01), contra los 3.000 al año que cuesta hoy.
- Acceso: solo con correo y contraseña de la USFQ, y para eso dependemos de TI (P-05).
- Celular primero, para estudiantes y administradores. En español, con opción de inglés.
- Marca: colores, logos y estilo de la USFQ y del COCOA. Los valores exactos dependen del manual de marca (P-42). Todo lo visual está en el [DESIGN.md](../../DESIGN.md) y en el [brand board](../diseno/brand-board.html).


## 10. Cómo usamos la IA

- En el avance 1 usamos ChatGPT para comparar los cinco resúmenes de la entrevista, encontrar contradicciones y ordenar por temas las preguntas que cada una propuso para el cliente.
- Para revisar el primer borrador del PRD le pedimos a Claude que lo cuestionara como si fuera alguien muy escéptico, comparándolo con las fuentes. Encontró los problemas que están en [revision.md](revision.md). Nosotras los convertimos en preguntas abiertas (P-28 a P-40) con lo que vamos a hacer mientras tanto; ninguno lo tomamos como si lo hubiera decidido el cliente.
- Para esta versión, el brand board y el DESIGN.md, Claude comparó el PRD con las respuestas del cliente del avance 1, revisó la plataforma actual, propuso los estados de reserva (RN-35 a RN-38) y las preguntas P-41 a P-43, nos ayudó a pasar nuestro layout al brand board y al DESIGN.md, y calculó el contraste de cada color. Así nos dimos cuenta de que el texto blanco sobre el rojo del logo (#ED1C24) no llega a 4.5:1, y por eso los botones usan #C41B1E.
- Lo que decidimos nosotras: el layout de las pantallas, la paleta, las tipografías, qué supuestos mantenemos y en qué orden se construye todo. Cuando la IA y el cliente no coincidían, le hicimos caso al cliente.
