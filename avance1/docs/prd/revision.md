# Revisión del PRD de USFQ Reserva COCOA

Aquí anotamos lo que cambiamos del primer borrador del [PRD](prd.md) y por qué. Todo esto ya está aplicado en el PRD.


## Primero, lo que corregimos nosotras

1. Profesores. En el borrador habíamos puesto a los profesores como un tipo de usuario, por la nota de la visita que decía "solo profes/admin". Lo corregimos: los profesores no usan la plataforma. Sacamos ese perfil de la sección 2 y agregamos la frase "Los profesores no son usuarios de la plataforma".

2. Computadoras (RN-17). Antes decía que el espacio de computadoras y cada computadora solo los podían reservar administradores o profesores. Ahora dice que los reservan los estudiantes, igual que cualquier otra cosa, sin restricción por rol.

3. Pregunta P-04. Como consecuencia de los dos puntos anteriores, la pregunta de si los profesores tenían cuenta propia quedó resuelta.

4. Horario de retiro y devolución (P-09 y RN-15). Teníamos la duda de si era hasta las 17:20 o hasta las 17:00, porque la nota decía "8:30 AM a 5:20 PM hasta las 5PM". Quedó en 17:00. Cambiamos RN-15 y también D-23 para que coincidan.

5. Margen para retirar (P-10 y RN-20). La nota decía "15 y 30 minutos". Quedó en 30 minutos para todo, y el administrador lo puede cambiar. Cambiamos RN-20 y D-21.


## Después, lo que encontró la IA

Le pedimos a Claude que revisara el PRD como si fuera alguien muy escéptico y lo comparara con nuestras fuentes. Lo que encontró no lo tomamos como decisiones del cliente: son riesgos y dudas que tenemos que confirmar con él. Para cada uno pusimos una pregunta abierta en el PRD, con lo que vamos a hacer mientras tanto.

6. No nos alcanza el tiempo para todo (secciones 3 y 9, importancia alta). Son 30 funcionalidades y el 23 de noviembre nos quedaban 9 días. Varias son casi proyectos enteros: el login con la cuenta de la U, subir y bajar Excel, el PDF, los recordatorios automáticos, los bloqueos, los kits, los dos idiomas y el chatbot. Además, si el Excel llega en la semana 15, no hay tiempo de probarlo. Agregamos P-28 (qué 5 cosas tienen que funcionar el 2 de diciembre) y P-29 (que nos manden el Excel antes), y pusimos un orden de prioridad en la sección 3.

7. Entrar con la contraseña de la U (RN-03, importancia alta). Para eso TI de la USFQ tiene que registrar nuestra app en su sistema, y eso no depende de nosotras. Tampoco sabíamos si usan Microsoft ni cuál es el dominio exacto de los correos. Y no teníamos plan B, cuando justo el login es una de las quejas. Reescribimos P-05 con un plan B (entrar con un enlace que llega al correo institucional) y agregamos P-30 para el dominio.

8. No estaba claro qué significa "disponible" (RN-10, RN-11 y RN-25, importancia alta). La búsqueda tipo Airbnb promete mostrar solo lo que está libre, pero nunca decíamos qué es estar libre. RN-25 mezclaba cómo está la unidad ahora con las reservas por horario. Y RN-11 no decía si el sistema impide aprobar una solicitud que llegó después o solo avisa. El cliente mismo dijo que hoy la disponibilidad "es un lío". Agregamos P-31 (una reserva aprobada saca la unidad de la búsqueda en ese horario) y P-32 (el sistema avisa pero no impide), y separamos las dos cosas en RN-25.

9. El carrito que se vacía repetía la queja principal (RN-08, importancia media). La queja número uno es que el carrito se borra solo, y nosotras habíamos escrito una regla que hacía justo eso. Como el carrito no aparta nada, vaciarlo no ayudaba a nadie. Además, el cliente solo dijo "1 hora" cuando le preguntamos cuándo se cierra la sesión; lo de vaciar lo agregamos nosotras. Ahora RN-08 dice que se cierra la sesión pero el carrito se queda (P-33).

10. Computadoras de madrugada con la bodega cerrada (RN-16, importancia media). Si solo se retira y se devuelve en horario laboral, a las 2 de la mañana nadie entrega nada. No sabíamos si las computadoras se llevan o se usan ahí, ni quién abre el espacio, ni qué días son laborables. Agregamos P-34 y P-35.

11. Bloqueo sin margen y sin decir qué pasa con las reservas futuras (RN-22 y RN-23, importancia media). Como estaba escrito, un minuto de atraso bloqueaba 14 días. Tampoco decía qué pasa con las reservas que el estudiante ya tiene, quién registra la hora de devolución ni si el bloqueo es automático. Y RN-23 sale de una nota bastante confusa de la visita. Agregamos P-36, P-37 y P-38.

12. El comprobante en PDF estaba en el MVP aunque el cliente dijo "después de diciembre" (alcance 17 y RN-28, importancia media). La nota dice: "Solo comprobantes electronicos, en el historial, ya sale la solicitud, conectar con el workflow. Después de diciembre. Un correo. Con el comprobante de pago." Nosotras habíamos sacado solo el workflow y el pago, pero dejamos el PDF. Agregamos P-39 y pasamos el PDF para después de diciembre por ahora.

13. Una "puntuación" del estudiante que nadie pidió así (alcance 3 y D-36, importancia media). La nota solo dice, bajo "Indicadores": "Que semestre que materias. 5 estrellas en uber. Score. Fue bloqueado. Todo correcto. Nivel de semestre." Eso también puede referirse a datos para los reportes. Nosotras lo habíamos convertido en una calificación de 1 a 5 y nos inventamos cómo calcularla. Agregamos P-40 y, por ahora, la ficha solo muestra si el estudiante fue bloqueado.


## Por último, para el avance 2

14. Faltaban los estados de una reserva. El PRD no decía en qué estados puede estar una reserva, y el DESIGN.md los necesita para darles color y texto. Agregamos RN-35 a RN-38.

15. El correo al rechazar no lo pidió el cliente. Lo dejamos como supuesto nuestro y lo preguntamos en P-41.

16. Revisamos la plataforma actual (cocoausfq.ezrentalstore.com) y agregamos al problema lo que vimos: es una tienda de alquiler de EZRentOut, deja entrar con Google, mezcla español e inglés, primero se elige el producto y después la fecha, y el catálogo tiene categorías desordenadas. Con eso también actualizamos P-21, P-25, P-29 y P-34.

17. Agregamos la sección de cómo usamos la IA y las preguntas P-42 (manual de marca) y P-43 (modo oscuro).

18. Pasamos nuestro layout de pantallas al brand board y al DESIGN.md. Con eso el estado "Pendiente" pasó a llamarse "En espera", como en las pantallas, y los estados de las unidades se muestran como Disponible (#16803D), Ocupado (#C41B1E) y Mantenimiento (#757575). Al revisar el contraste vimos que el texto blanco sobre el rojo del logo (#ED1C24) da 4.38:1, así que los botones usan #C41B1E. El corazón de favoritos y la campana no estaban en el PRD, así que agregamos P-44.
