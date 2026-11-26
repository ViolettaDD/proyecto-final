# DESIGN.md de USFQ Reserva COCOA

Este es nuestro sistema de diseño. Es lo mismo que está en el [brand board](docs/diseno/brand-board.html) y en nuestro layout ([docs/diseno/pantallas.png](docs/diseno/pantallas.png)), pero escrito para que lo podamos seguir nosotras y el agente cuando programemos. Si algo está en uno, tiene que estar en el otro. Las reglas que citamos (RN-xx) y las preguntas abiertas (P-xx) están en el [PRD](docs/prd/prd.md).

Nota para el agente: usa solo las variables de la última sección. No inventes colores, tamaños ni nombres de estados. Si algo no está aquí, pregunta antes de improvisar.


## 1. Concepto

Se llama USFQ Reserva COCOA y el subtítulo es "Equipos y espacios audiovisuales". La idea que elegimos se llama "Directo al set": reservar tiene que ser tan simple como elegir la fecha, escoger el equipo y mandar la solicitud. Nada más.

Nuestras tres palabras clave: claro, rápido y confiable.

El cliente nos pidió "colores de la u, estética, logos", así que la página se ve como la USFQ: fondo blanco, el rojo del logo, texto negro y grises claros. Lo que la hace del COCOA son las fotos reales de los equipos (cámaras, lentes, luces), que son las protagonistas de cada pantalla.

### Las direcciones que probamos

Antes de elegir probamos tres estilos:

- A. Institucional USFQ (la que elegimos). Blanco, rojo y negro, el logo de la U arriba, fotos grandes de los equipos y tarjetas limpias. Es lo que pidió el cliente, se lee bien al sol en el celular y se siente oficial, que es importante porque el acceso es solo con correo institucional.
- B. Claqueta. Tinta negra sobre fondo color papel, franjas de claqueta de cine y el rojo solo como acento. Nos gustaba por lo cinematográfico, pero se alejaba de la imagen de la U que pidió el cliente y tanto negro pesaba mucho en una pantalla chica.
- C. Estudio nocturno. Todo oscuro, como una sala de edición. La descartamos porque se lee mal afuera entre clases, los colores de los estados pierden contraste y el administrador trabaja en una oficina con luz.


## 2. Quién la usa y dónde

Los estudiantes de cine, periodismo y comunicación entran casi siempre desde el celular, entre clases, caminando o en el pasillo, con poco tiempo y a cualquier hora (RN-09). Les importa ver rápido qué hay disponible en su fecha, armar el carrito con una sola mano y saber siempre en qué va su reserva.

Los administradores (Santiago y Luis Daniel) y la bodega COCOA usan el celular y también la compu de la bodega, mientras atienden estudiantes en persona. Les importa ver el día de un vistazo, aprobar en uno o dos toques y darse cuenta de los choques y los atrasos sin tener que buscarlos.


## 3. Principios

1. Primero la fecha. En el inicio lo primero que se ve es "Selecciona la fecha", y el catálogo muestra lo disponible para esa fecha (RN-13, D-30).
2. El rojo guía. El rojo es para la acción principal de cada pantalla ("Iniciar sesión", "Agregar al carrito", "Continuar solicitud") y para marcar dónde estás (pestaña activa, ícono activo del menú). No lo usamos para decorar.
3. El estado siempre se ve. Cada reserva y cada unidad muestra su estado con texto, color y, en las reservas, un ícono. Nunca solo con color.
4. Nada se borra solo. El carrito se guarda (RN-08) y cualquier cosa que borre algo pide confirmación.
5. Los datos se escriben siempre igual. Fechas, horas y unidades siguen la sección 8, en 24 horas.
6. Pensado para el pulgar. Diseñamos para pantallas de 360 px de ancho, el menú va abajo, los botones importantes van abajo y de lado a lado, y todo lo que se toca mide por lo menos 48 px.


## 4. Colores

Sacamos la paleta del logo de la USFQ. Falta confirmarla con el manual de marca de la U (P-42); si cambia, solo hay que editar las variables.

Ojo con el rojo: el rojo del logo (#ED1C24) con texto blanco encima da 4.38:1, y nos pedimos 4.5:1 como mínimo. Por eso los botones y todo lo que lleva texto blanco sobre rojo usa el rojo oscuro (#C41B1E), que da 5.96:1. El rojo del logo queda para el logo, los íconos y los títulos grandes.

### Marca y neutros

| Variable | Nombre | Hex | Para qué | Contraste |
|---|---|---|---|---|
| --color-rojo-usfq | Rojo USFQ | #ED1C24 | Logo, íconos activos, raya debajo del nombre, títulos de 24 px o más | Sobre blanco 4.38:1 (solo para texto grande o íconos) |
| --color-rojo | Rojo botón | #C41B1E | Botón principal, pestaña activa, contador del carrito, enlaces | Blanco encima 5.96:1, sobre gris claro 5.14:1 |
| --color-rojo-oscuro | Rojo presionado | #9E1418 | Botón principal al pasar el mouse o al tocarlo | Blanco encima 8.18:1 |
| --color-negro | Negro | #000000 | Títulos grandes ("RESERVA COCOA", "¿Qué necesitas reservar?") | Sobre gris claro 18.1:1 |
| --color-texto | Casi negro | #1A1A1A | Texto normal, nombres de equipos, íconos del menú | Sobre blanco 17.4:1 |
| --color-gris | Gris | #757575 | Texto secundario sobre blanco ("Unidad: 1", fechas en listas, ayudas) y el estado Mantenimiento. Nunca como texto sobre gris claro | Sobre blanco 4.61:1, blanco encima 4.61:1 |
| --color-gris-claro | Gris claro | #EEEEEE | Pestañas sin elegir, chips de categoría, cajas de información, fondo de campos | No lleva texto claro encima |
| --color-borde | Borde | #E0E0E0 | Bordes de tarjetas y campos, divisiones. Nunca para texto | No aplica |
| --color-blanco | Blanco | #FFFFFF | Fondo de la página, tarjetas, texto sobre rojo | No aplica |

### Estados de una reserva

Cada estado tiene un color para el texto y otro para el fondo de la etiqueta. Todos pasan de 4.5:1.

| Estado (RN-35) | Ícono | Texto | Fondo | Contraste |
|---|---|---|---|---|
| En espera | reloj de arena | #7A4500 | #FFF0D1 | 6.96:1 |
| Aprobada | check | #1E6B3A | #E2F2E7 | 5.62:1 |
| Rechazada | equis | #9B1C1C | #FBE3E3 | 6.68:1 |
| Cancelada | círculo tachado | #4A4744 | #ECE9E4 | 7.62:1 |
| No retirada | reloj tachado | #5A5650 | #F1EEE9 | 6.30:1 |
| En curso | flecha saliendo | #1D4E89 | #E1EBF7 | 6.96:1 |
| Atrasada | alerta | #9A3412 | #FDE6D8 | 6.08:1 |
| Finalizada | flecha entrando | #2E5266 | #E3ECF1 | 6.97:1 |
| Conflicto (marca, RN-36) | dos rectángulos encimados | #6B2C91 | #F0E5F7 | 7.21:1 |

### Estados de una unidad

Son los tres estados que nos dio el cliente (RN-25), con los colores de nuestro layout:

| Estado | Hex | Variable | Contraste |
|---|---|---|---|
| Disponible | #16803D | --unidad-disponible | Blanco encima 5.01:1, sobre blanco 5.01:1 |
| Ocupado | #C41B1E | --unidad-ocupado | Blanco encima 5.96:1, sobre blanco 5.96:1 |
| Mantenimiento | #757575 | --unidad-mantenimiento | Blanco encima 4.61:1, sobre blanco 4.61:1 |

Cómo se usan para que siempre pasen de 4.5:1:

- En la etiqueta de las tarjetas del catálogo, el color va de fondo sólido con el texto en blanco ("● Disponible").
- En los cuadros para elegir unidad, el fondo es blanco y el borde de 2 px, el número y la palabra van del color del estado.
- Nunca ponemos el texto de estos colores sobre un fondo verde, rosado o gris claro: el verde y el gris bajan de 4.5:1.
- Mantenimiento y Ocupado no se pueden elegir (RN-25).

### Estados de cuentas y otros

No tienen colores propios, reutilizan los de arriba:

- Dañado o Extraviado: el rojo de Ocupado. Solo lo ve el administrador, porque sale del catálogo (RN-38).
- Cuenta activa: los de Aprobada.
- Cuenta bloqueada: los de Atrasada, y siempre con la fecha, por ejemplo "Bloqueada hasta el 9 dic".
- Cuenta dada de baja: los de Cancelada.

### Mensajes del sistema

- Éxito: texto #1E6B3A sobre #E2F2E7, con un check verde en círculo (como "Reserva aprobada" en el detalle).
- Error: texto #9B1C1C sobre #FBE3E3.
- Aviso: texto #7A4500 sobre #FFF0D1.
- Información: texto #1A1A1A sobre #EEEEEE, con un ícono de "i" (como "Una sola solicitud" en el carrito).


## 5. Tipografía

Usamos dos letras:

- Nexa para títulos, en negrita y casi siempre en mayúsculas para la marca ("RESERVA COCOA"). Es geométrica y firme, y combina con el logo. Ojo: Nexa no es gratis para web. Si no conseguimos la licencia (o la U no la tiene), usamos Montserrat, que es gratis en Google Fonts y se ve muy parecida. En el brand board ya usamos Montserrat en su lugar.
- Roboto para todo lo demás. Es gratis en Google Fonts, se lee muy bien en tamaños chicos y es la letra de Android, así que se siente natural en el celular.

Las horas, fechas, cantidades y códigos van con font-variant-numeric: tabular-nums, para que no "bailen" en las listas.

### Tamaños (base de 16 px, pensando primero en el celular)

| Variable | Tamaño / interlineado | Peso | Letra | Dónde se usa |
|---|---|---|---|---|
| --texto-marca | 32 / 34 px | 800, mayúsculas | Nexa | "RESERVA COCOA" en el login y en el brand board |
| --texto-h1 | 24 / 30 px | 700 | Nexa | Título de la pantalla ("¿Qué necesitas reservar?", "Mis reservas", "Tu reserva está en espera de aprobación") |
| --texto-h2 | 20 / 26 px | 700 | Nexa | Nombre del equipo en el detalle ("Cámara Sony FX6"), secciones ("Explora por categoría") |
| --texto-h3 | 16 / 22 px | 700 | Roboto | Nombre del equipo en las tarjetas, código de reserva |
| --texto-cuerpo | 16 / 24 px | 400 | Roboto | Texto normal y campos. En los campos nunca menos de 16 px, para que el iPhone no haga zoom |
| --texto-pequeno | 14 / 20 px | 500 | Roboto | Botones de pestañas, etiquetas, "Unidad: 1", fechas en listas |
| --texto-mini | 12 / 16 px | 500 | Roboto | Etiquetas de estado chiquitas, nombres del menú de abajo, "Acceso exclusivo con correo institucional". Nunca para algo que haya que leer con cuidado |


## 6. Espaciado, radios y sombras

### Espaciado

| Variable | Valor | Dónde se usa |
|---|---|---|
| --esp-1 | 4 px | Entre un ícono y su texto |
| --esp-2 | 8 px | Entre chips, entre la etiqueta y el campo |
| --esp-3 | 12 px | Entre tarjetas del catálogo, relleno de chips |
| --esp-4 | 16 px | Margen a los lados en el celular y relleno de las tarjetas |
| --esp-5 | 24 px | Entre bloques dentro de una pantalla |
| --esp-6 | 32 px | Entre secciones |
| --esp-7 | 48 px | Espacios grandes en la compu |

### Radios

| Variable | Valor | Dónde se usa |
|---|---|---|
| --radio-s | 8 px | Cuadros de unidad (1, 2, 3, 4) y miniaturas de fotos |
| --radio-m | 12 px | Botones, campos, cajas de información |
| --radio-l | 16 px | Tarjetas de equipo, de reserva y el banner del inicio |
| --radio-pill | 999 px | Pestañas (Productos / Kits, Futuras / En curso / Pasadas), chips de categoría, etiquetas de estado, contador del carrito, botón ES / EN |

### Sombras y medidas

- --sombra-1 es una sombra muy suave para las tarjetas, y --sombra-2 una más marcada para el botón del chatbot y los menús.
- --tactil-min es 48 px, lo mínimo que mide cualquier cosa que se toca.
- --ancho-max es 1120 px, el ancho máximo del contenido en la compu.

Cómo cambia según la pantalla: hasta 599 px (celular) el catálogo va en dos columnas de tarjetas y el resto en una; de 600 a 1023 px (tablet) el catálogo va en tres columnas; desde 1024 px (compu) va en cuatro, el menú de abajo pasa a ser una barra arriba, y el administrador ve la lista y el detalle lado a lado.


## 7. Componentes

### Barra de arriba y menú de abajo

- Arriba: flecha para volver (si no es una pantalla principal), el título al centro o a la izquierda, y a la derecha la campana y el carrito con el número de cosas en un círculo rojo.
- La campana abre la lista de avisos de la reserva (los mismos que llegan por correo, más "en espera de aprobación", que solo se ve en la página, RN-27). No manda notificaciones push.
- Abajo, para el estudiante: Inicio, Explorar, Reservas y Perfil. El que está activo va en rojo, con el ícono relleno.
- Abajo, para el administrador: Hoy, Solicitudes, Inventario y Estudiantes.
- El botón ES / EN es una pastilla con dos partes; la que está activa va en rojo con texto blanco (RN-34).

### Botones

Tenemos cuatro tipos:

- Principal: fondo rojo botón (#C41B1E), texto blanco de 16 px en negrita, 48 px de alto, de lado a lado en el celular. Para la acción más importante de la pantalla ("Iniciar sesión", "Agregar al carrito", "Continuar solicitud"). Uno por pantalla.
- Secundario: fondo blanco con borde y texto rojo. Para la otra opción ("Ver mis reservas", "Descargar comprobante").
- De texto: sin fondo ni borde. Para cosas menores ("Vaciar carrito", "Ver detalle").
- De peligro: fondo blanco con borde y texto rojo oscuro (#9B1C1C), con ícono de basurero o de equis. Para "Rechazar", "Cancelar reserva", "Dar de baja" o quitar algo del carrito, y siempre pide confirmar.

Cómo se ven según lo que pasa:

- Al pasar el mouse o al tocar, el principal se pone rojo presionado (#9E1418) y el secundario toma un fondo rosado muy claro.
- Con foco (por ejemplo con el teclado), aparece un anillo negro de 2 px separado del botón.
- Si está desactivado, se ve gris claro con texto gris y decimos por qué, por ejemplo "Selecciona una unidad".
- Mientras carga, aparece un circulito girando y el texto cambia ("Enviando..."). El botón no cambia de tamaño y no deja tocar dos veces.

### Campos

- En el login los campos tienen un ícono a la izquierda (sobre para el correo, candado para la contraseña) y un ojito a la derecha para ver la contraseña. Debajo del botón va "Acceso exclusivo con correo institucional".
- Fuera del login, la etiqueta siempre está arriba y se ve todo el tiempo. Nunca usamos el texto de ejemplo de adentro como única etiqueta.
- El campo mide 48 px de alto, con texto de 16 px, borde gris (#E0E0E0) y fondo blanco.
- Cuando estás escribiendo, el borde se pone casi negro.
- Si hay un error, el borde se pone rojo oscuro y abajo aparece un mensaje con un ícono que dice qué hacer, por ejemplo "Usa tu correo de la USFQ." o "Elige una hora entre 08:30 y 17:00."
- El buscador es una pastilla gris claro con lupa ("Buscar equipo...").
- "Selecciona la fecha" es una fila blanca con ícono de calendario rojo y una flecha. Al tocarla se abre un calendario y una lista de horas cada 30 minutos (RN-13). Para retirar y devolver no aparecen las horas fuera de 08:30 a 17:00 (RN-15), salvo en las computadoras (RN-16).
- La nota para el administrador (la nota externa, P-12) es opcional, va en el carrito, tiene 3 líneas y un contador de hasta 280 caracteres.

### Inicio del estudiante

Arriba "Hola, [nombre]" y el título "¿Qué necesitas reservar?". Después la fila "Selecciona la fecha", un banner rojo con foto ("Reserva equipos, kits y espacios del COCOA") que puede rotar, y "Explora por categoría" con tres botones grandes: Equipos, Kits y Espacios.

### Tarjeta de equipo (catálogo)

- Va en una cuadrícula de dos columnas en el celular, sobre fondo blanco con borde gris y radio de 16 px.
- Arriba la foto del equipo sobre fondo blanco; abajo la etiqueta de estado (Disponible, Ocupado o Mantenimiento, sólida con texto blanco) y el nombre en negrita, en dos líneas como máximo.
- Arriba del catálogo están las pestañas Productos / Kits, el buscador y los chips de categoría (Todo, Cámaras, Lentes, Audio...). El chip elegido va en rojo con texto blanco.
- Los kits muestran "Incluye 5 piezas" y están disponibles solo si todas sus piezas lo están (P-18).
- Los espacios muestran la capacidad en vez de las unidades.

### Detalle del equipo y elección de unidad

- Foto grande con puntitos abajo para pasar a la segunda foto (máximo dos fotos, RN-26).
- Nombre, etiqueta de estado y una descripción corta.
- "Selecciona una unidad" con cuadros de 72 por 56 px, uno por unidad (RN-12), como tallas de ropa. Cada cuadro es blanco, con el número grande y el estado chiquito abajo, y el borde y el texto del color del estado: Disponible en verde (#16803D), Ocupado en rojo (#C41B1E) o Mantenimiento en gris (#757575). Los ocupados y en mantenimiento no se pueden tocar. La unidad elegida se rellena de verde con el texto en blanco y lleva un check.
- Los equipos sin número, como los trípodes, en vez de cuadros tienen un contador de menos y más que no pasa de las unidades libres.
- Abajo, el botón principal "Agregar al carrito" con ícono de carrito. Se desactiva hasta que eliges una unidad.

### Carrito

- Título "Carrito (3)". Arriba, la fecha y la hora elegidas, con opción de cambiarlas.
- Cada fila tiene la miniatura, el nombre, "Unidad: 1" en gris y un basurero para quitarla (pide confirmar).
- Una caja gris con ícono de información: "Una sola solicitud. Todos los artículos se enviarán en una única reserva." (RN-05).
- La nota opcional para el administrador.
- Botón principal "Continuar solicitud". Debajo: "El carrito se guarda aunque cierres la sesión." (RN-08).

### Pantalla de en espera

Después de mandar la solicitud aparece el logo, un círculo rosado con un reloj de arena rojo, el título "Tu reserva está en espera de aprobación" y el texto "Hemos recibido tu solicitud. Te notificaremos por correo institucional cuando sea aprobada o rechazada." (RN-27, RN-28, RN-29). Debajo, una caja con el código de solicitud, la fecha de uso y cuántos equipos son, y el botón secundario "Ver mis reservas".

### Mis reservas

- Pestañas Futuras, En curso y Pasadas.
  - Futuras: En espera y Aprobada.
  - En curso: En curso y Atrasada.
  - Pasadas: Rechazada, Cancelada, No retirada y Finalizada.
- Cada fila tiene el código en negrita ("#R-10458"), la etiqueta de estado a la derecha, las fechas y cuántos artículos son ("15 – 17 nov 2026 · 3 artículos"), y una flecha para abrir el detalle.

### Detalle de la reserva

- Arriba, el mensaje del estado (por ejemplo, la caja verde "Reserva aprobada. Tu solicitud ha sido aprobada.").
- Código de reserva, fecha de uso y la lista de artículos, que se abre y se cierra ("Artículos (5)").
- Según el estado, un botón: "Cancelar reserva" si está En espera o Aprobada y falta más de una hora (RN-19); "Reservar de nuevo" si ya terminó.
- La fila "Comprobante electrónico" y el botón "Descargar comprobante" están en nuestro diseño, pero solo se muestran cuando haya comprobante en PDF. Por ahora eso quedó para después de diciembre (P-39), así que en el MVP no aparecen.
- El administrador además ve la nota interna (caja gris con el rótulo "Solo administradores") y, si aplica, la marca de Conflicto con un enlace a la solicitud que se mandó antes.

### Etiqueta de estado

Es una pastilla de 24 px de alto con un punto o ícono y el nombre del estado en 12 a 14 px. Usa los colores de la sección 4. El texto es siempre el nombre exacto del estado: no se abrevia ni se cambia por otra palabra.

### Chatbot

Un botón redondo rojo con un globito de chat, abajo a la derecha. Al lado puede aparecer una vez el mensaje "¿Necesitas ayuda? Estoy aquí para resolver tus dudas sobre reservas.", que se cierra con una equis. Es lo de menor prioridad (P-17): si no alcanzamos, no aparece y nada más cambia. Nunca tapa el botón principal de la pantalla.

### Carga, vacío, error y éxito

- Cargando: mostramos la forma gris de las tarjetas mientras llegan los datos, no una ruedita en toda la pantalla. Si tarda más de 5 segundos, agregamos "Sigue cargando...".
- Vacío: un ícono, una frase que explica qué pasa y un botón. Por ejemplo: "No hay equipos disponibles el mié 2 dic de 10:00 a 12:00. Prueba con otra hora." con el botón "Cambiar fecha". En Mis reservas: "Todavía no tienes reservas." con el botón "Explorar equipos".
- Error: el mensaje va donde iba el contenido, dice qué pasó y qué hacer, y tiene un botón para reintentar. Nunca mostramos códigos técnicos. Por ejemplo: "No pudimos cargar el catálogo. Revisa tu conexión e inténtalo otra vez."
- Éxito: la pantalla de en espera después de mandar la solicitud, y la caja verde en el detalle cuando se aprueba. Para cosas chiquitas, como agregar al carrito, basta un aviso abajo que dura 4 segundos: "Agregado al carrito".


## 8. Cómo escribimos los datos

Usamos siempre la hora de Ecuador (America/Guayaquil), y no la mostramos.

- Fecha en listas: día corto, número y mes corto, como "mié 2 dic". Nunca "02/12/2026" ni "12/2".
- Rango de fechas: "15 – 17 nov 2026", con espacios alrededor del guion. Si cambia el mes: "30 nov – 2 dic 2026".
- Fecha completa: "miércoles 2 de diciembre de 2026".
- Si es hoy o mañana, lo decimos con la palabra: "Hoy, 10:00–12:00".
- Hora: en 24 horas y con dos dígitos, como "08:30" o "17:00" (RN-14). Nunca "8:30 AM" ni "5pm".
- Rango de horas: con un guion corto y sin espacios, como "10:00–12:30".
- Duración: "2 h 30 min", no "2.5 horas".
- Cantidades: con la palabra que concuerda, como "1 artículo", "3 artículos", "Carrito (3)" o "Artículos (5)". Nunca "3 artículo(s)".
- Unidad: "Unidad: 2" en el carrito y en el detalle, y solo el número en los cuadros para elegir.
- Código de reserva: numeral, R- y cinco números, como "#R-10458".
- Tiempo relativo: solo si falta o pasó menos de un día, como "en 45 min" o "hace 2 h".
- Bloqueo: siempre con la fecha en que termina, como "Bloqueada hasta el mié 9 dic", no "Bloqueada 14 días".

En inglés (RN-34) las fechas quedan como "Wed, Dec 2" o "Nov 15 – 17, 2026", la hora sigue en 24 horas y el código no cambia.

### Estados de una reserva

El nombre del estado es igual para el estudiante y para el administrador. Lo que cambia es la frase de ayuda del detalle:

- En espera (en inglés, Pending). El estudiante ve: "Tu reserva está en espera de aprobación. Te notificaremos por correo institucional." El administrador ve: "Revisa y aprueba o rechaza."
- Aprobada (Approved). El estudiante ve: "Tu solicitud ha sido aprobada. Retira en bodega COCOA el mié 2 dic desde las 10:00; tienes 30 min de margen." El administrador ve: "Lista para entregar."
- Rechazada (Declined). El estudiante ve: "Tu solicitud no fue aprobada. Puedes buscar otra fecha o equipo." El administrador ve: "Rechazada."
- Cancelada (Cancelled). El estudiante ve "Cancelaste esta reserva." o "La bodega canceló esta reserva." El administrador ve "Cancelada por el estudiante." o "Cancelada por administración."
- No retirada (Not picked up). El estudiante ve: "No se retiró a tiempo y los equipos se liberaron." El administrador ve: "Liberada: pasaron 30 min sin retiro."
- En curso (In progress). El estudiante ve: "Devuélvelo hasta las 17:00 de hoy." El administrador ve: "Debe volver hoy a las 17:00."
- Atrasada (Overdue). El estudiante ve: "Ya pasó la hora de devolución. Devuélvelo cuanto antes; tu cuenta quedará bloqueada 14 días." El administrador ve: "Atrasada 45 min. Al registrar la devolución se bloquea la cuenta 14 días."
- Finalizada (Completed). El estudiante ve: "Devuelto el mié 2 dic a las 16:40. ¡Gracias!" El administrador ve: "Devuelto a las 16:40."
- Conflicto (Conflict). El estudiante no lo ve. El administrador ve: "Choca con #R-10439, enviada antes. Tiene prioridad la anterior."


## 9. Cómo hablamos

Somos directas, cercanas y útiles. Al estudiante lo tuteamos ("¿Qué necesitas reservar?", "Selecciona una unidad"), le decimos qué pasó y qué puede hacer, en frases cortas. Con el administrador somos igual de directas.

Algunos ejemplos de así sí y así no:

- Así sí: "Hemos recibido tu solicitud. Te notificaremos por correo institucional cuando sea aprobada o rechazada." Así no: "¡Su solicitud ha sido procesada exitosamente!" Decimos qué sigue, sin frases de robot.
- Así sí: "Esta unidad está en mantenimiento. Elige otra." Así no: "Error: ítem no disponible (code 409)." Explicamos y damos una salida, sin códigos.
- Así sí: "Puedes cancelar hasta las 09:00 (1 h antes)." Así no: "Las cancelaciones están sujetas a la política vigente." Damos la hora exacta en vez de mandar a leer una norma.
- Así sí: "Tu cuenta está bloqueada hasta el mié 9 dic por una devolución atrasada." Así no: "Usted ha sido penalizado." Decimos hasta cuándo y por qué, sin regañar.
- Así sí: "Selecciona la fecha." Así no: "Por favor, seleccione la fecha deseada a continuación." Corto y amable.

Palabras que usamos siempre igual: reserva (no "pedido" ni "orden", como dice hoy la plataforma actual), solicitud (lo que se manda), equipo, kit y espacio, artículos (para contar lo que hay en una reserva), unidad, retirar y devolver, y bodega COCOA. Y todo en español o todo en inglés, nada de "Rent" ni "Add to Cart" mezclados.


## 10. Accesibilidad

- Todo el texto tiene un contraste de 4.5:1 o más (lo revisamos color por color en la sección 4). Por eso el texto blanco nunca va sobre el rojo del logo, sino sobre el rojo botón.
- El estado nunca se muestra solo con color: siempre va con su nombre escrito.
- Todo lo que se toca mide por lo menos 48 por 48 px, con 8 px de separación. Los íconos del menú de abajo y de la barra de arriba tienen un área táctil de 48 px aunque el dibujo sea más chico.
- Todo lo que se puede usar con teclado muestra el anillo de foco, y se recorre en el mismo orden en que se ve.
- Todos los campos tienen su etiqueta (en el login, aunque no se vea, el lector de pantalla la lee), y los errores se conectan al campo.
- Las fotos tienen texto alternativo con el nombre y la unidad, por ejemplo "Cámara Sony FX6, unidad 1". Los íconos que solo decoran se esconden del lector de pantalla; los que son botones (campana, carrito, basurero) tienen nombre ("Notificaciones", "Carrito, 3 artículos", "Quitar del carrito").
- La página funciona con zoom al 200 % y con la letra agrandada del celular, sin que haya que moverse de lado.
- Si la persona tiene activado reducir movimiento, el banner del inicio no rota solo.
- La página dice en qué idioma está (español o inglés) según lo que se eligió.


## 11. Lo que no hacemos

- No ponemos texto blanco sobre el rojo del logo (#ED1C24): no llega a 4.5:1.
- No usamos el rojo para decorar.
- No mostramos horas con AM o PM (RN-14).
- No usamos solo el color para mostrar un estado.
- No vaciamos el carrito si el estudiante no lo pide (RN-08).
- No ponemos botón de "Crear cuenta" ni "Entrar con Google" (RN-02, RN-03).
- No mostramos códigos de error técnicos.
- No usamos texto de menos de 12 px.
- No ponemos texto gris (#757575) sobre el gris claro (#EEEEEE): da 3.97:1. Sobre gris claro, el texto va en #1A1A1A.
- No inventamos otros nombres para los estados: usamos los de RN-35 tal cual.
- No mezclamos español e inglés en la misma pantalla.
- No hacemos modo oscuro en el MVP (P-43).
- No ponemos favoritos (el corazón de las tarjetas) en el MVP, porque no está en el PRD. Si el cliente lo pide, lo agregamos.
- No usamos fotos de internet: solo las fotos reales del inventario. Si un equipo no tiene foto, va el ícono de su categoría.
- No deformamos ni cambiamos de color el logo de la USFQ, y siempre va sobre fondo blanco o sobre rojo con su versión en negativo.


## Variables CSS

Esto se copia tal cual a tokens.css.

```css
:root {
  /* Marca y neutros (sacados del logo USFQ, falta confirmar con el manual, P-42) */
  --color-rojo-usfq: #ED1C24;   /* solo logo, íconos y títulos grandes */
  --color-rojo: #C41B1E;        /* botones y todo texto blanco sobre rojo */
  --color-rojo-oscuro: #9E1418;
  --color-rojo-suave: #FDE8E8;
  --color-negro: #000000;
  --color-texto: #1A1A1A;
  --color-gris: #757575;        /* solo sobre blanco */
  --color-gris-claro: #EEEEEE;
  --color-borde: #E0E0E0;
  --color-blanco: #FFFFFF;

  /* Estados de una reserva (RN-35, RN-36) */
  --estado-espera-texto: #7A4500;      --estado-espera-fondo: #FFF0D1;
  --estado-aprobada-texto: #1E6B3A;    --estado-aprobada-fondo: #E2F2E7;
  --estado-rechazada-texto: #9B1C1C;   --estado-rechazada-fondo: #FBE3E3;
  --estado-cancelada-texto: #4A4744;   --estado-cancelada-fondo: #ECE9E4;
  --estado-noretirada-texto: #5A5650;  --estado-noretirada-fondo: #F1EEE9;
  --estado-encurso-texto: #1D4E89;     --estado-encurso-fondo: #E1EBF7;
  --estado-atrasada-texto: #9A3412;    --estado-atrasada-fondo: #FDE6D8;
  --estado-finalizada-texto: #2E5266;  --estado-finalizada-fondo: #E3ECF1;
  --estado-conflicto-texto: #6B2C91;   --estado-conflicto-fondo: #F0E5F7;

  /* Estados de unidad (RN-25): sólidos con texto blanco, o texto y borde sobre blanco */
  --unidad-disponible: #16803D;
  --unidad-ocupado: #C41B1E;
  --unidad-mantenimiento: #757575;

  /* Mensajes */
  --msg-exito: var(--estado-aprobada-texto);
  --msg-exito-fondo: var(--estado-aprobada-fondo);
  --msg-error: var(--estado-rechazada-texto);
  --msg-error-fondo: var(--estado-rechazada-fondo);
  --msg-aviso: var(--estado-espera-texto);
  --msg-aviso-fondo: var(--estado-espera-fondo);
  --msg-info: var(--color-texto);
  --msg-info-fondo: var(--color-gris-claro);

  /* Tipografía (Nexa necesita licencia; si no hay, Montserrat) */
  --fuente-titulos: "Nexa", "Montserrat", system-ui, sans-serif;
  --fuente-texto: "Roboto", system-ui, -apple-system, "Segoe UI", sans-serif;
  --texto-marca: 800 2rem/2.125rem var(--fuente-titulos);
  --texto-h1: 700 1.5rem/1.875rem var(--fuente-titulos);
  --texto-h2: 700 1.25rem/1.625rem var(--fuente-titulos);
  --texto-h3: 700 1rem/1.375rem var(--fuente-texto);
  --texto-cuerpo: 400 1rem/1.5rem var(--fuente-texto);
  --texto-pequeno: 500 0.875rem/1.25rem var(--fuente-texto);
  --texto-mini: 500 0.75rem/1rem var(--fuente-texto);

  /* Espaciado */
  --esp-1: 4px;  --esp-2: 8px;  --esp-3: 12px; --esp-4: 16px;
  --esp-5: 24px; --esp-6: 32px; --esp-7: 48px;

  /* Radios */
  --radio-s: 8px; --radio-m: 12px; --radio-l: 16px; --radio-pill: 999px;

  /* Sombras y medidas */
  --sombra-1: 0 1px 3px rgb(0 0 0 / 0.08);
  --sombra-2: 0 6px 20px rgb(0 0 0 / 0.16);
  --tactil-min: 48px;
  --ancho-max: 1120px;
  --anillo-foco: 0 0 0 2px var(--color-blanco), 0 0 0 4px var(--color-texto);
}
```
