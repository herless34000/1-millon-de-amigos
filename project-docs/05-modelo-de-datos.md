# 05 - Modelo de Datos

## 1. Objetivo

Este documento define el modelo conceptual de datos de la plataforma **1 Millón de Amigos**.

Su objetivo es identificar las principales entidades que necesita el sistema, la información que almacenarán y la relación existente entre ellas.

Este documento servirá como base para el posterior diseño de la base de datos en Supabase utilizando PostgreSQL.

---

# 2. Visión general

La plataforma estará formada por diferentes entidades relacionadas entre sí.

Las principales son:

- Usuarios.
- Perfiles.
- Publicaciones o proyectos.
- Categorías.
- Comentarios.
- Reacciones.
- Seguimientos.
- Ayudas.
- Conversaciones.
- Mensajes.
- Notificaciones.
- Denuncias.
- Reconocimientos.
- Actividad de usuarios.
- Administración y moderación.

La relación general puede representarse de la siguiente manera:

USUARIO

↓

PERFIL

↓

PUEDE CREAR

↓

PUBLICACIONES / PROYECTOS

↓

PUEDE RECIBIR

- Comentarios.
- Me gusta.
- Alientos.
- Seguidores.
- Ayudas.
- Denuncias.

Los usuarios también pueden:

↓

SEGUIR

↓

OTROS USUARIOS

↓

INICIAR

↓

CONVERSACIONES

↓

ENVIAR

↓

MENSAJES

↓

RECIBIR

↓

NOTIFICACIONES

---

# 3. Usuarios

## 3.1 Propósito

La entidad **Usuario** representa una cuenta autenticada dentro de la plataforma.

La autenticación será gestionada inicialmente mediante Supabase Auth.

Los usuarios podrán registrarse utilizando:

- Correo electrónico y contraseña.
- Google.
- Apple.

---

## 3.2 Información principal

Cada usuario tendrá una identidad única dentro del sistema.

Información relacionada:

- ID único.
- Correo electrónico.
- Método de autenticación.
- Fecha de creación.
- Estado de la cuenta.

El estado de una cuenta podrá incluir:

- Activa.
- Bloqueada temporalmente.
- Eliminada.

---

## 3.3 Relación con el perfil

La información pública y personal adicional del usuario será almacenada en la entidad **Perfil**.

Relación:

USUARIO

1

↓

1

PERFIL

Cada usuario tendrá un único perfil.

---

# 4. Perfiles

## 4.1 Propósito

La entidad **Perfil** almacenará la información relacionada con la identidad y presencia del usuario dentro de la plataforma.

---

## 4.2 Información del perfil

El perfil podrá contener:

- ID del usuario.
- Nombre.
- Apellido.
- Nombre de usuario.
- Fecha de nacimiento.
- Fotografía de perfil.
- Biografía o descripción.
- País.
- Ciudad.
- Fecha de creación.
- Fecha de actualización.

---

## 4.3 Nombre de usuario

El nombre de usuario deberá ser único dentro de la plataforma.

Ejemplo:

@juanperez

No podrán existir dos perfiles con el mismo nombre de usuario.

---

## 4.4 Relaciones

Un perfil puede:

- Crear múltiples publicaciones.
- Realizar comentarios.
- Dar me gusta.
- Dar aliento.
- Seguir usuarios.
- Seguir publicaciones.
- Ofrecer ayuda.
- Iniciar conversaciones.
- Enviar mensajes.
- Recibir notificaciones.
- Realizar denuncias.
- Recibir reconocimientos.

---

# 5. Publicaciones o proyectos

## 5.1 Propósito

La entidad **Publicación** representa el contenido creado por un usuario dentro de la plataforma.

Dentro de 1 Millón de Amigos, una publicación también puede representar un proyecto, necesidad, solicitud de ayuda, idea, causa, actividad o pregunta.

---

## 5.2 Información principal

Cada publicación podrá contener:

- ID único.
- Usuario creador.
- Título.
- Descripción.
- Estado.
- Ubicación opcional.
- Fecha de creación.
- Fecha de actualización.
- Fecha de publicación.

---

## 5.3 Estados

Inicialmente, una publicación podrá tener los siguientes estados:

- Borrador.
- Publicado.
- Bloqueado.
- Eliminado.

---

## 5.4 Relaciones

Una publicación pertenece a un usuario.

Relación:

USUARIO

1

↓

N

PUBLICACIONES

Un usuario puede crear múltiples publicaciones.

Cada publicación puede tener:

- Una o varias categorías.
- Comentarios.
- Me gusta.
- Alientos.
- Seguidores.
- Ayudas.
- Denuncias.

---

# 6. Categorías

## 6.1 Propósito

Las categorías permiten clasificar las publicaciones.

Una publicación podrá tener:

- Ninguna categoría.
- Una categoría.
- Varias categorías.

Por esta razón, la relación entre publicaciones y categorías será de muchos a muchos.

---

## 6.2 Información de una categoría

Cada categoría podrá contener:

- ID.
- Nombre.
- Descripción opcional.
- Estado.
- Fecha de creación.

Ejemplos:

- Salud.
- Educación.
- Deportes.
- Ciencia.
- Vivienda.
- Emprendimiento.
- Animales.
- Arte.
- Fotografía.
- Entretenimiento.
- Tecnología.
- Libre.

---

## 6.3 Relación

PUBLICACIÓN

N

↕

N

CATEGORÍA

Para representar esta relación será necesaria una entidad intermedia:

PUBLICACION_CATEGORIA

---

# 7. Comentarios

## 7.1 Propósito

La entidad **Comentario** almacenará los comentarios realizados por los usuarios en las publicaciones.

---

## 7.2 Información principal

Cada comentario tendrá:

- ID.
- Publicación.
- Usuario autor.
- Contenido.
- Fecha de creación.
- Fecha de actualización.
- Estado.

---

## 7.3 Relaciones

PUBLICACIÓN

1

↓

N

COMENTARIOS

Un usuario puede realizar múltiples comentarios.

---

# 8. Me gusta

## 8.1 Propósito

La entidad **Me gusta** registrará cuando un usuario indique que una publicación le gusta.

---

## 8.2 Información

Cada registro tendrá:

- Usuario.
- Publicación.
- Fecha.

---

## 8.3 Regla

Un usuario podrá indicar "Me gusta" una sola vez por publicación.

Relación:

USUARIO

N

↕

N

PUBLICACIÓN

---

# 9. Alientos

## 9.1 Propósito

La entidad **Aliento** registrará una muestra de apoyo de un usuario hacia una publicación.

El aliento representa una forma de ayuda diferente al aporte económico.

---

## 9.2 Información

Cada aliento tendrá:

- Usuario.
- Publicación.
- Fecha.

---

## 9.3 Regla

Un usuario podrá dar aliento a una publicación según las reglas que se definan para esta interacción.

La estructura inicial deberá permitir registrar quién realizó el aliento y a qué publicación corresponde.

---

# 10. Seguimiento de usuarios

## 10.1 Propósito

La entidad **Seguimiento de usuarios** permitirá registrar cuándo un usuario sigue a otro usuario.

---

## 10.2 Información

Cada seguimiento tendrá:

- Usuario que sigue.
- Usuario seguido.
- Fecha.

---

## 10.3 Relación

USUARIO

N

↕

N

USUARIO

Un usuario puede seguir a múltiples usuarios y puede ser seguido por múltiples usuarios.

---

# 11. Seguimiento de publicaciones

## 11.1 Propósito

La entidad **Seguimiento de publicaciones** permitirá que un usuario siga una publicación o proyecto.

---

## 11.2 Información

Cada seguimiento tendrá:

- Usuario.
- Publicación.
- Fecha.

Un usuario podrá seguir múltiples publicaciones.

Una publicación podrá tener múltiples seguidores.

---

# 12. Ayudas

## 12.1 Propósito

La entidad **Ayuda** registrará las diferentes formas mediante las cuales un usuario puede apoyar una publicación.

---

## 12.2 Tipos de ayuda

Inicialmente se contemplan:

- Aliento.
- Dinero.
- Bien.
- Servicio.
- Tiempo.
- Conocimiento.
- Difusión.

---

## 12.3 Información principal

Cada ayuda podrá contener:

- ID.
- Usuario que ayuda.
- Publicación relacionada.
- Tipo de ayuda.
- Estado.
- Fecha de creación.
- Fecha de actualización.
- Información adicional según el tipo de ayuda.

---

## 12.4 Estados de ayuda

Dependiendo del tipo de ayuda, una ayuda podrá tener estados como:

- Ofrecida.
- En coordinación.
- Confirmada.
- Completada.
- Cancelada.

---

## 12.5 Relación

USUARIO

1

↓

N

AYUDAS

PUBLICACIÓN

1

↓

N

AYUDAS

Un usuario puede realizar múltiples ayudas.

Una publicación puede recibir múltiples ayudas.

---

# 13. Ayuda económica

## 13.1 Propósito

La ayuda económica representa un tipo especial de ayuda.

Durante la primera fase, los aportes económicos utilizarán un flujo de simulación.

---

## 13.2 Información

La información relacionada podrá incluir:

- Ayuda asociada.
- Monto.
- Moneda.
- Estado.
- Fecha.
- Tipo de operación.

---

## 13.3 Evolución futura

La estructura deberá permitir incorporar posteriormente:

- Procesador de pagos.
- Identificador de transacción.
- Confirmación del pago.
- Comisiones.
- Reembolsos.
- Retiro o transferencia.

---

# 14. Conversaciones

## 14.1 Propósito

La entidad **Conversación** representa un espacio de comunicación entre usuarios.

Las conversaciones podrán utilizarse para:

- Comunicación general.
- Coordinación de ayuda.
- Coordinación relacionada con una publicación.

---

## 14.2 Información principal

Cada conversación podrá contener:

- ID.
- Fecha de creación.
- Fecha de última actividad.
- Publicación relacionada, si corresponde.

---

# 15. Participantes de conversación

Una conversación puede tener uno o varios participantes.

Para permitir esta relación se utilizará una entidad intermedia:

CONVERSACION_PARTICIPANTE

Información:

- Conversación.
- Usuario.
- Fecha de incorporación.

Relación:

USUARIO

N

↕

N

CONVERSACIÓN

---

# 16. Mensajes

## 16.1 Propósito

La entidad **Mensaje** almacenará los mensajes enviados dentro de una conversación.

---

## 16.2 Información

Cada mensaje tendrá:

- ID.
- Conversación.
- Usuario remitente.
- Contenido.
- Fecha de envío.
- Estado.

El estado podrá incluir:

- Enviado.
- Leído.
- Eliminado.

---

# 17. Notificaciones

## 17.1 Propósito

La entidad **Notificación** permitirá informar a los usuarios sobre actividades relacionadas con su cuenta o participación dentro de la plataforma.

---

## 17.2 Ejemplos

Una notificación puede generarse cuando ocurre:

- Un nuevo comentario.
- Un nuevo seguidor.
- Una nueva ayuda.
- Un nuevo mensaje.
- Una actividad en una publicación seguida.
- Una acción administrativa.

---

## 17.3 Información

Cada notificación tendrá:

- ID.
- Usuario destinatario.
- Tipo.
- Información relacionada.
- Estado de lectura.
- Fecha de creación.

---

# 18. Denuncias

## 18.1 Propósito

La entidad **Denuncia** permitirá registrar contenido o usuarios denunciados.

---

## 18.2 Información

Cada denuncia podrá contener:

- ID.
- Usuario que realiza la denuncia.
- Tipo de contenido denunciado.
- Identificador del contenido.
- Motivo.
- Descripción adicional.
- Estado.
- Fecha de creación.

---

## 18.3 Estados

Una denuncia podrá encontrarse en estados como:

- Pendiente.
- En revisión.
- Resuelta.
- Rechazada.

---

# 19. Reconocimientos

## 19.1 Propósito

La entidad **Reconocimiento** almacenará los diferentes reconocimientos disponibles dentro de la plataforma.

Ejemplos:

- Proyecto del mes.
- Proyecto más inspirador.
- Proyecto con mayor impacto.
- Proyecto más colaborativo.
- Proyecto más innovador.
- Amigo del mes.
- Salón de los Amigos.
- Top 10.
- Top 50.
- Top 100.
- Yo fui parte.

---

## 19.2 Información

Cada reconocimiento podrá contener:

- ID.
- Nombre.
- Descripción.
- Tipo.
- Condiciones o criterios.
- Fecha de creación.

---

# 20. Reconocimientos otorgados

Para registrar qué reconocimiento ha recibido cada usuario será necesaria una entidad:

USUARIO_RECONOCIMIENTO

Información:

- Usuario.
- Reconocimiento.
- Publicación o proyecto relacionado, si corresponde.
- Fecha de otorgamiento.

Relación:

USUARIO

N

↕

N

RECONOCIMIENTO

---

# 21. Actividad del usuario

## 21.1 Propósito

La entidad **Actividad** permitirá registrar eventos relevantes realizados por los usuarios.

Ejemplos:

- Creó una publicación.
- Comentó.
- Dio aliento.
- Ayudó a un proyecto.
- Siguió a un usuario.
- Completó una participación.

---

## 21.2 Información

Cada actividad podrá contener:

- ID.
- Usuario.
- Tipo de actividad.
- Información relacionada.
- Fecha.

---

# 22. Administración y moderación

La administración requerirá información relacionada con las acciones realizadas sobre usuarios y publicaciones.

El sistema deberá permitir registrar acciones como:

- Bloqueo temporal de cuenta.
- Desbloqueo de cuenta.
- Eliminación de cuenta.
- Bloqueo de publicación.
- Desbloqueo de publicación.
- Eliminación de publicación.

---

# 23. Acciones administrativas

Se recomienda contar con una entidad para registrar las acciones realizadas por los administradores.

Entidad:

ACCION_ADMINISTRATIVA

Información:

- ID.
- Administrador.
- Tipo de acción.
- Usuario afectado, si corresponde.
- Publicación afectada, si corresponde.
- Motivo.
- Fecha.

Esta información permitirá mantener un historial de las acciones administrativas realizadas.

---

# 24. Relación general del modelo

La estructura general puede representarse de la siguiente manera:

USUARIO
│
├── PERFIL
│
├── PUBLICACIONES
│   │
│   ├── PUBLICACION_CATEGORIA
│   ├── COMENTARIOS
│   ├── ME_GUSTA
│   ├── ALIENTOS
│   ├── SEGUIMIENTO_PUBLICACION
│   ├── AYUDAS
│   └── DENUNCIAS
│
├── SEGUIMIENTO_USUARIO
│
├── CONVERSACIONES
│   │
│   ├── CONVERSACION_PARTICIPANTE
│   └── MENSAJES
│
├── NOTIFICACIONES
│
├── ACTIVIDAD
│
├── USUARIO_RECONOCIMIENTO
│
└── ACCIONES ADMINISTRATIVAS

CATEGORIA
│
└── PUBLICACION_CATEGORIA

RECONOCIMIENTO
│
└── USUARIO_RECONOCIMIENTO

---

# 25. Entidades principales

Para la primera implementación, las entidades principales identificadas son:

1. Usuarios.
2. Perfiles.
3. Publicaciones.
4. Categorías.
5. Publicación - Categoría.
6. Comentarios.
7. Me gusta.
8. Alientos.
9. Seguimiento de usuarios.
10. Seguimiento de publicaciones.
11. Ayudas.
12. Ayudas económicas.
13. Conversaciones.
14. Participantes de conversación.
15. Mensajes.
16. Notificaciones.
17. Denuncias.
18. Reconocimientos.
19. Reconocimientos de usuarios.
20. Actividad.
21. Acciones administrativas.

---

# 26. Principios para el diseño posterior de la base de datos

Cuando este modelo sea implementado en PostgreSQL mediante Supabase, deberán considerarse los siguientes principios:

- Cada entidad tendrá un identificador único.
- Las relaciones deberán utilizar claves foráneas.
- La información deberá mantener integridad referencial.
- Los usuarios solo podrán modificar la información para la cual tengan permiso.
- Las reglas de acceso deberán implementarse mediante políticas de seguridad.
- La autenticación será gestionada mediante Supabase Auth.
- La información pública y el perfil del usuario estarán separados de la información de autenticación.
- Las acciones administrativas deberán estar restringidas a usuarios autorizados.
- Las publicaciones públicas deberán poder visualizarse sin necesidad de iniciar sesión.