# 04 - Flujos de Usuario

## 1. Objetivo

Este documento describe los principales recorridos que realizan los usuarios dentro de la plataforma 1 Millón de Amigos.

Cada flujo define la secuencia general de acciones desde el inicio de una actividad hasta su resultado.

Los flujos servirán como referencia para:

- Diseño de pantallas.
- Desarrollo de funcionalidades.
- Diseño de la base de datos.
- Definición de permisos.
- Pruebas del sistema.

---

# 2. Flujo de acceso a la plataforma

Una persona puede acceder a la plataforma sin tener una cuenta.

Flujo:

Visitante

↓

Accede a 1 Millón de Amigos

↓

Visualiza contenido público

↓

Puede:

- Ver publicaciones.
- Explorar proyectos.
- Buscar contenido.
- Ver perfiles públicos.
- Ver categorías.

↓

Intenta realizar una acción que requiere autenticación

↓

El sistema solicita:

- Iniciar sesión.
- Crear una cuenta.

---

# 3. Flujo de registro tradicional

Usuario

↓

Selecciona "Crear cuenta"

↓

Selecciona registro mediante correo electrónico

↓

Completa:

- Nombre.
- Apellido.
- Fecha de nacimiento.
- Correo electrónico.
- Contraseña.
- Nombre de usuario.

↓

El sistema valida la información

↓

Se crea la cuenta

↓

El sistema solicita verificar el correo electrónico

↓

Usuario verifica su correo

↓

Cuenta verificada

↓

Usuario inicia sesión

↓

Accede a la plataforma como usuario registrado.

---

# 4. Flujo de registro con Google

Usuario

↓

Selecciona "Continuar con Google"

↓

Es dirigido al proceso de autenticación de Google

↓

Autoriza el acceso

↓

El sistema recibe la información autorizada

↓

Se crea o vincula la cuenta

↓

Usuario accede a la plataforma.

---

# 5. Flujo de registro con Apple

Usuario

↓

Selecciona "Continuar con Apple"

↓

Es dirigido al proceso de autenticación de Apple

↓

Autoriza el acceso

↓

El sistema recibe la información autorizada

↓

Se crea o vincula la cuenta

↓

Usuario accede a la plataforma.

---

# 6. Flujo de inicio de sesión

Usuario registrado

↓

Accede a "Iniciar sesión"

↓

Selecciona una opción:

- Correo electrónico y contraseña.
- Google.
- Apple.

↓

El sistema valida la autenticación

↓

Autenticación correcta

↓

Usuario accede a la plataforma.

---

# 7. Flujo de recuperación de contraseña

Usuario

↓

Selecciona "¿Olvidaste tu contraseña?"

↓

Ingresa su correo electrónico

↓

El sistema valida la existencia de la cuenta

↓

El sistema envía un enlace o mecanismo de recuperación

↓

Usuario establece una nueva contraseña

↓

Contraseña actualizada

↓

Usuario inicia sesión.

---

# 8. Flujo de creación de una publicación

Usuario registrado

↓

Selecciona "Crear publicación"

↓

El sistema muestra el formulario de creación

↓

Usuario ingresa la información de su publicación

↓

Puede incluir:

- Título.
- Descripción.
- Categorías.
- Ubicación opcional.
- Tipo o tipos de ayuda que necesita.
- Información adicional relacionada con su necesidad.

↓

Usuario selecciona una acción:

- Guardar borrador.
- Publicar.

---

## 8.1 Guardar como borrador

Usuario

↓

Selecciona "Guardar borrador"

↓

El sistema guarda la publicación

↓

Estado:

BORRADOR

↓

El usuario puede continuar editándola posteriormente.

---

## 8.2 Publicar

Usuario

↓

Selecciona "Publicar"

↓

El sistema valida la información requerida

↓

Publicación creada

↓

Estado:

PUBLICADO

↓

La publicación aparece automáticamente dentro de la plataforma.

No requiere aprobación previa de un administrador.

---

# 9. Flujo de edición de una publicación

Usuario registrado

↓

Accede a una publicación creada por él

↓

Selecciona "Editar"

↓

Modifica la información permitida

↓

Selecciona "Guardar cambios"

↓

El sistema actualiza la publicación

↓

Los cambios quedan visibles.

---

# 10. Flujo de eliminación de una publicación

Usuario registrado

↓

Accede a una publicación creada por él

↓

Selecciona "Eliminar"

↓

El sistema solicita confirmación

↓

Usuario confirma la eliminación

↓

Estado:

ELIMINADO

↓

La publicación deja de estar disponible públicamente.

↓

Si una persona accede posteriormente al enlace:

↓

El sistema informa:

"Esta publicación ya no está disponible."

---

# 11. Flujo de exploración de publicaciones

Visitante o usuario registrado

↓

Accede al inicio o sección de exploración

↓

Visualiza publicaciones

↓

Puede:

- Buscar.
- Explorar categorías.
- Abrir una publicación.
- Visitar un perfil.

↓

Selecciona una publicación

↓

Accede al detalle de la publicación.

---

# 12. Flujo de interacción social

Usuario registrado

↓

Visualiza una publicación

↓

Puede realizar una o varias acciones:

- Dar "me gusta".
- Comentar.
- Compartir.
- Seguir la publicación.
- Dar aliento.
- Seleccionar "¿Cómo puedo ayudar?"

↓

El sistema registra la acción realizada.

↓

La actividad podrá generar:

- Actualización de contadores.
- Notificaciones.
- Registro de actividad.
- Actualización de reputación cuando corresponda.

---

# 13. Flujo de seguimiento de usuarios

Usuario registrado

↓

Visita el perfil de otro usuario

↓

Selecciona "Seguir"

↓

El sistema registra el seguimiento

↓

El usuario comienza a seguir a la persona seleccionada.

↓

Posteriormente podrá dejar de seguirla.

---

# 14. Flujo de seguimiento de publicaciones

Usuario registrado

↓

Visualiza una publicación

↓

Selecciona "Seguir"

↓

El sistema registra el seguimiento

↓

El usuario podrá recibir información o notificaciones relacionadas con la publicación.

---

# 15. Flujo principal de ayuda

Usuario registrado

↓

Visualiza una publicación

↓

Selecciona:

"¿Cómo puedo ayudar?"

↓

El sistema muestra las formas de ayuda disponibles.

El usuario puede seleccionar:

- Dar aliento.
- Dar dinero.
- Dar un bien.
- Ofrecer un servicio.
- Dar tiempo.
- Compartir conocimiento.
- Ayudar a difundir.

↓

El sistema inicia el flujo correspondiente al tipo de ayuda seleccionado.

---

# 16. Flujo de ayuda mediante aliento

Usuario registrado

↓

Selecciona:

"Dar aliento"

↓

El sistema registra la muestra de apoyo

↓

Se actualiza la información de apoyo de la publicación

↓

La participación queda registrada.

---

# 17. Flujo de ayuda mediante dinero

Usuario registrado

↓

Selecciona:

"Dar dinero"

↓

El sistema muestra el flujo de aporte económico

↓

Primera fase:

Simulación de donación

↓

Usuario selecciona o ingresa un monto

↓

Confirma la operación simulada

↓

El sistema registra el aporte

↓

Se actualiza la información relacionada con los aportes del proyecto

↓

La actividad queda registrada en el perfil o historial correspondiente.

---

# 18. Flujo futuro de ayuda mediante dinero real

Usuario registrado

↓

Selecciona:

"Dar dinero"

↓

Selecciona el monto

↓

Accede al procesador de pagos

↓

Realiza el pago

↓

El sistema recibe la confirmación de la operación

↓

El aporte queda registrado

↓

Se actualiza la información del proyecto.

La integración de pagos reales será implementada en una fase posterior.

---

# 19. Flujo de ayuda mediante bienes

Usuario registrado

↓

Selecciona:

"Dar un bien"

↓

El sistema inicia el proceso de oferta de ayuda

↓

El usuario indica el bien que desea ofrecer

↓

La oferta queda registrada

↓

Se inicia o habilita la comunicación entre las personas involucradas

↓

Los usuarios coordinan mediante chat

↓

Se realiza la entrega

↓

La ayuda puede ser confirmada

↓

La participación queda registrada.

---

# 20. Flujo de ayuda mediante servicio

Usuario registrado

↓

Selecciona:

"Ofrecer un servicio"

↓

El usuario indica el servicio que desea ofrecer

↓

La oferta queda registrada

↓

Se habilita la comunicación mediante chat

↓

Los usuarios coordinan la ayuda

↓

El servicio es realizado

↓

La ayuda puede ser confirmada

↓

La participación queda registrada.

---

# 21. Flujo de ayuda mediante tiempo

Usuario registrado

↓

Selecciona:

"Dar tiempo"

↓

El usuario indica su disposición para participar

↓

La participación queda registrada

↓

Se habilita la comunicación correspondiente

↓

Los usuarios coordinan:

- Fecha.
- Horario.
- Lugar.
- Duración.

↓

Se realiza la actividad

↓

La participación puede ser confirmada

↓

La ayuda queda registrada.

---

# 22. Flujo de ayuda mediante conocimiento

Usuario registrado

↓

Selecciona:

"Compartir conocimiento"

↓

El usuario indica que desea aportar sus conocimientos o experiencia

↓

La oferta queda registrada

↓

Se habilita la comunicación entre los usuarios

↓

Se coordina la forma de colaboración

↓

La ayuda puede ser confirmada

↓

La participación queda registrada.

---

# 23. Flujo de ayuda mediante difusión

Usuario registrado

↓

Selecciona:

"Compartir" o "Ayudar a difundir"

↓

El sistema muestra las opciones disponibles para compartir

↓

El usuario selecciona el medio de difusión

↓

La publicación es compartida

↓

El sistema registra la actividad cuando sea técnicamente posible.

---

# 24. Flujo de inicio de conversación

Usuario registrado

↓

Desea comunicarse con otro usuario

↓

Selecciona una opción que permite iniciar comunicación

↓

El sistema abre o crea una conversación

↓

Usuario envía un mensaje

↓

El destinatario recibe una notificación

↓

Puede acceder al chat

↓

Ambos usuarios pueden continuar la conversación.

---

# 25. Flujo de coordinación de ayuda mediante chat

Usuario A ofrece ayuda

↓

Usuario B recibe la oferta

↓

Se inicia o utiliza una conversación

↓

Ambos usuarios coordinan los detalles

↓

Se realiza la ayuda

↓

La ayuda puede ser confirmada

↓

La actividad queda registrada.

---

# 26. Flujo de denuncia

Usuario registrado

↓

Visualiza una publicación o contenido

↓

Selecciona "Denunciar"

↓

El sistema muestra las opciones de denuncia

↓

Usuario selecciona un motivo

↓

Envía la denuncia

↓

La denuncia queda registrada

↓

El administrador puede revisarla.

---

# 27. Flujo de moderación de una publicación

Administrador

↓

Accede al panel administrativo

↓

Visualiza publicaciones o denuncias

↓

Revisa el contenido

↓

Selecciona una acción:

- No realizar ninguna acción.
- Bloquear temporalmente.
- Desbloquear.
- Eliminar permanentemente.

↓

El sistema actualiza el estado correspondiente.

---

# 28. Flujo de moderación de una cuenta

Administrador

↓

Accede al panel administrativo

↓

Selecciona un usuario

↓

Revisa la información correspondiente

↓

Selecciona una acción:

- No realizar ninguna acción.
- Bloquear temporalmente.
- Desbloquear.
- Eliminar permanentemente.

↓

El sistema actualiza el estado de la cuenta.

---

# 29. Flujo de notificaciones

Una acción ocurre dentro de la plataforma.

Ejemplos:

- Nuevo comentario.
- Nuevo seguidor.
- Nueva ayuda.
- Nuevo mensaje.
- Actividad relacionada con una publicación seguida.
- Acción administrativa relevante.

↓

El sistema registra el evento

↓

El usuario correspondiente recibe una notificación dentro de la plataforma.

↓

El usuario accede a la notificación

↓

El sistema lo dirige al contenido relacionado.

---

# 30. Flujo de reputación y reconocimientos

Usuario realiza una acción dentro de la plataforma

↓

La acción es registrada

↓

Cuando corresponda, el sistema actualiza:

- Participación.
- Puntos.
- Reputación.
- Reconocimientos.

↓

La información puede ser mostrada en el perfil del usuario.

---

# 31. Flujo de finalización de un proyecto

Un proyecto alcanza su objetivo o el creador considera que la necesidad ha sido resuelta.

↓

El proyecto puede ser marcado como finalizado de acuerdo con las reglas definidas para esta funcionalidad.

↓

El sistema registra la finalización

↓

Los usuarios que participaron pueden recibir reconocimiento por su contribución.

Ejemplo:

"Yo fui parte."

---

# 32. Resumen del flujo principal de la plataforma

VISITANTE

↓

EXPLORA CONTENIDO

↓

SE INTERESA EN PARTICIPAR

↓

SE REGISTRA / INICIA SESIÓN

↓

USUARIO REGISTRADO

↓

PUEDE:

- Crear una publicación.
- Solicitar ayuda.
- Interactuar con otros usuarios.
- Seguir personas y publicaciones.
- Dar aliento.
- Ofrecer ayuda.
- Comunicarse mediante chat.
- Participar en proyectos.
- Recibir reputación y reconocimientos.

↓

CREA IMPACTO DENTRO DE LA COMUNIDAD