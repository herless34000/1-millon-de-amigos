# 06 - API y Servicios

## 1. Objetivo

Este documento define los principales servicios, integraciones y mecanismos de comunicación que utilizará la plataforma **1 Millón de Amigos**.

La arquitectura inicial del proyecto estará basada en:

- Next.js.
- Supabase.
- PostgreSQL.
- Supabase Auth.
- Supabase Storage.
- Supabase Realtime.

La aplicación utilizará inicialmente las capacidades proporcionadas por Supabase para reducir la complejidad de la primera implementación.

---

# 2. Arquitectura general

La estructura general de la aplicación será:

USUARIO

↓

NAVEGADOR WEB

↓

NEXT.JS

↓

SUPABASE

├── AUTENTICACIÓN
├── BASE DE DATOS
├── ALMACENAMIENTO
└── REALTIME

La plataforma será inicialmente una aplicación web responsive.

Esto permitirá utilizarla desde:

- Computadoras.
- Tablets.
- Teléfonos móviles.

---

# 3. Next.js

Next.js será utilizado para desarrollar la aplicación web.

Será responsable de:

- Mostrar las páginas.
- Gestionar la navegación.
- Mostrar formularios.
- Procesar las interacciones del usuario.
- Comunicarse con Supabase.
- Mostrar contenido público.
- Gestionar las áreas privadas de usuarios.
- Gestionar el panel administrativo.

Next.js será la capa principal de interacción entre el usuario y los servicios de la plataforma.

---

# 4. Supabase

Supabase será utilizado como plataforma principal de servicios backend.

Inicialmente proporcionará:

- Autenticación.
- Base de datos PostgreSQL.
- Almacenamiento de archivos.
- Funcionalidades en tiempo real.
- Gestión de permisos y seguridad.

La arquitectura inicial buscará aprovechar estos servicios antes de incorporar infraestructura adicional.

---

# 5. Autenticación

La autenticación será gestionada mediante Supabase Auth.

El sistema deberá permitir:

- Registro mediante correo electrónico y contraseña.
- Inicio de sesión.
- Cierre de sesión.
- Recuperación de contraseña.
- Verificación de correo electrónico.
- Inicio de sesión mediante Google.
- Inicio de sesión mediante Apple.

---

# 6. Flujo de autenticación

El flujo general será:

USUARIO

↓

REGISTRO O INICIO DE SESIÓN

↓

SUPABASE AUTH

↓

VALIDACIÓN DE CREDENCIALES

↓

AUTENTICACIÓN CORRECTA

↓

CREACIÓN O RECUPERACIÓN DE SESIÓN

↓

ACCESO A LA PLATAFORMA

Después de la autenticación, el sistema deberá identificar el tipo de usuario y aplicar los permisos correspondientes.

---

# 7. Perfiles y autenticación

La información de autenticación será gestionada mediante Supabase Auth.

La información relacionada con el perfil será almacenada separadamente dentro de la base de datos.

Relación:

SUPABASE AUTH

↓

USUARIO AUTENTICADO

↓

PERFIL

El perfil almacenará información como:

- Nombre.
- Apellido.
- Nombre de usuario.
- Fecha de nacimiento.
- Fotografía de perfil.
- Biografía.
- País.
- Ciudad.

---

# 8. Base de datos

La base de datos principal será PostgreSQL mediante Supabase.

Almacenará información relacionada con:

- Perfiles.
- Publicaciones.
- Categorías.
- Comentarios.
- Me gusta.
- Alientos.
- Seguimiento de usuarios.
- Seguimiento de publicaciones.
- Ayudas.
- Ayudas económicas.
- Conversaciones.
- Participantes.
- Mensajes.
- Notificaciones.
- Denuncias.
- Reconocimientos.
- Actividad.
- Acciones administrativas.

La estructura detallada será definida posteriormente mediante las tablas y relaciones correspondientes.

---

# 9. Seguridad y permisos

La seguridad de acceso será gestionada principalmente mediante:

- Autenticación.
- Identificación del usuario.
- Roles.
- Políticas de seguridad.

Supabase utilizará políticas de seguridad a nivel de filas para controlar el acceso a la información.

El sistema deberá garantizar que:

- Un usuario solo pueda editar su propio perfil.
- Un usuario solo pueda editar sus propias publicaciones.
- Un usuario solo pueda eliminar sus propias publicaciones.
- Un usuario solo pueda modificar sus propios comentarios cuando corresponda.
- Los usuarios solo puedan acceder a conversaciones en las que participan.
- Los administradores puedan realizar acciones de moderación.
- El contenido público pueda ser visualizado según las reglas definidas.

---

# 10. Servicio de almacenamiento

Supabase Storage será utilizado para almacenar archivos relacionados con la plataforma.

Inicialmente podrá utilizarse para:

- Fotografías de perfil.
- Imágenes de publicaciones.
- Documentos.
- Otros archivos permitidos por la plataforma.

Los archivos deberán estar organizados mediante una estructura definida.

Ejemplo conceptual:

avatars/

    user-id/

        profile-image.jpg


publications/

    publication-id/

        image-01.jpg

        image-02.jpg


documents/

    publication-id/

        document.pdf

La estructura definitiva será definida durante la implementación.

---

# 11. Publicaciones

La comunicación entre la aplicación y las publicaciones deberá permitir:

- Crear publicaciones.
- Guardar borradores.
- Publicar contenido.
- Editar publicaciones.
- Eliminar publicaciones.
- Obtener publicaciones.
- Buscar publicaciones.
- Filtrar por categorías.
- Visualizar publicaciones individuales.

Conceptualmente, las operaciones serán:

CREAR

↓

GUARDAR

↓

PUBLICAR

↓

CONSULTAR

↓

ACTUALIZAR

↓

ELIMINAR

Estas operaciones podrán realizarse utilizando los servicios y capacidades proporcionadas por Supabase y Next.js.

---

# 12. Interacciones sociales

La aplicación deberá permitir registrar interacciones como:

- Me gusta.
- Comentarios.
- Alientos.
- Seguimiento de usuarios.
- Seguimiento de publicaciones.
- Compartir.

Cada interacción deberá quedar asociada a:

- El usuario que realiza la acción.
- El contenido o usuario relacionado.
- La fecha de realización.

---

# 13. Sistema de ayuda

El sistema deberá permitir registrar diferentes tipos de ayuda.

La comunicación deberá permitir:

- Crear una ayuda.
- Consultar ayudas relacionadas con una publicación.
- Consultar ayudas realizadas por un usuario.
- Actualizar el estado de una ayuda.
- Confirmar una ayuda cuando corresponda.

Tipos de ayuda:

- Aliento.
- Dinero.
- Bien.
- Servicio.
- Tiempo.
- Conocimiento.
- Difusión.

---

# 14. Ayuda económica

## 14.1 Primera fase

Durante la primera fase, los aportes económicos funcionarán mediante un sistema de simulación.

El flujo será:

USUARIO

↓

SELECCIONA MONTO

↓

CONFIRMA APORTE SIMULADO

↓

SISTEMA REGISTRA EL APORTE

↓

SE ACTUALIZA EL PROYECTO

No se procesará dinero real durante esta fase.

---

## 14.2 Fase futura

Posteriormente podrá integrarse una pasarela de pagos.

El flujo general será:

USUARIO

↓

SELECCIONA MONTO

↓

SOLICITA REALIZAR EL PAGO

↓

PROCESADOR DE PAGOS

↓

CONFIRMACIÓN

↓

SISTEMA REGISTRA LA TRANSACCIÓN

↓

ACTUALIZACIÓN DEL PROYECTO

La integración específica del proveedor de pagos será definida cuando esta funcionalidad sea incorporada.

---

# 15. Chat

La plataforma contará con un sistema de comunicación entre usuarios.

El sistema deberá permitir:

- Crear conversaciones.
- Agregar participantes.
- Enviar mensajes.
- Recibir mensajes.
- Consultar conversaciones.
- Consultar historial de mensajes.
- Registrar mensajes leídos cuando corresponda.

El servicio de comunicación podrá utilizar Supabase Realtime para actualizar los mensajes en tiempo real.

Flujo:

USUARIO A

↓

ENVÍA MENSAJE

↓

SUPABASE

↓

REALTIME

↓

USUARIO B RECIBE EL MENSAJE

---

# 16. Notificaciones

El sistema deberá registrar notificaciones relacionadas con actividades importantes.

Ejemplos:

- Nuevo comentario.
- Nuevo seguidor.
- Nuevo mensaje.
- Nueva ayuda.
- Actividad relacionada con una publicación seguida.
- Acción administrativa.

Flujo:

EVENTO

↓

SISTEMA

↓

CREACIÓN DE NOTIFICACIÓN

↓

USUARIO

↓

VISUALIZACIÓN DE NOTIFICACIÓN

Las notificaciones iniciales serán internas dentro de la plataforma.

En fases posteriores podrán incorporarse:

- Notificaciones por correo electrónico.
- Notificaciones push.
- Otros canales.

---

# 17. Búsqueda y exploración

La aplicación deberá permitir consultar publicaciones mediante:

- Texto.
- Categorías.
- Información relacionada.

La implementación inicial podrá utilizar las capacidades de consulta de PostgreSQL y Supabase.

En una etapa posterior podrá incorporarse un sistema de búsqueda más avanzado si el crecimiento de la plataforma lo requiere.

---

# 18. Administración

El panel administrativo utilizará los mismos servicios principales de la plataforma, pero estará protegido mediante permisos especiales.

El administrador deberá poder gestionar:

- Usuarios.
- Publicaciones.
- Denuncias.
- Comentarios.
- Moderación.
- Categorías.
- Reconocimientos.

Las operaciones administrativas deberán quedar registradas cuando corresponda.

---

# 19. API conceptual

La aplicación utilizará operaciones relacionadas con las principales entidades del sistema.

Ejemplos conceptuales:

## Usuarios y perfiles

- Crear perfil.
- Obtener perfil.
- Actualizar perfil.
- Consultar perfil público.

## Publicaciones

- Crear publicación.
- Obtener publicaciones.
- Obtener publicación individual.
- Actualizar publicación.
- Eliminar publicación.
- Buscar publicaciones.

## Comentarios

- Crear comentario.
- Obtener comentarios.
- Actualizar comentario cuando corresponda.
- Eliminar comentario.

## Interacciones

- Dar me gusta.
- Quitar me gusta.
- Dar aliento.
- Seguir usuario.
- Dejar de seguir usuario.
- Seguir publicación.
- Dejar de seguir publicación.

## Ayudas

- Crear ayuda.
- Consultar ayudas.
- Actualizar estado de ayuda.
- Confirmar ayuda.

## Chat

- Crear conversación.
- Obtener conversaciones.
- Obtener mensajes.
- Enviar mensaje.
- Marcar mensajes como leídos.

## Administración

- Obtener denuncias.
- Revisar denuncias.
- Bloquear usuario.
- Desbloquear usuario.
- Eliminar usuario.
- Bloquear publicación.
- Desbloquear publicación.
- Eliminar publicación.

---

# 20. Principio de comunicación

La aplicación deberá mantener una separación clara entre:

INTERFAZ

↓

LÓGICA DE APLICACIÓN

↓

SERVICIOS Y DATOS

La interfaz no deberá contener directamente toda la lógica del negocio.

La estructura del proyecto deberá permitir organizar claramente:

- Componentes visuales.
- Servicios.
- Acceso a datos.
- Lógica de negocio.
- Tipos y modelos.
- Utilidades.

---

# 21. Servicios externos futuros

La arquitectura deberá permitir incorporar posteriormente servicios externos.

Posibles integraciones:

- Pasarela de pagos.
- Servicio de correo electrónico.
- Notificaciones push.
- Servicios de verificación.
- Sistemas de análisis.
- Herramientas de monitoreo.
- Otros servicios necesarios para el crecimiento de la plataforma.

La incorporación de estos servicios no deberá requerir una reconstrucción completa de la aplicación.

---

# 22. Resumen de arquitectura

La primera versión utilizará:

USUARIO

↓

NEXT.JS

↓

SUPABASE

├── AUTH
│
├── POSTGRESQL
│
├── STORAGE
│
└── REALTIME

Esta arquitectura permitirá desarrollar inicialmente:

- Registro e inicio de sesión.
- Perfiles.
- Publicaciones.
- Feed.
- Categorías.
- Comentarios.
- Interacciones.
- Ayudas.
- Chat.
- Notificaciones.
- Administración.

La arquitectura podrá evolucionar posteriormente mediante la incorporación de servicios adicionales según las necesidades del proyecto.

---

# 23. Principio de evolución

La arquitectura inicial debe buscar simplicidad.

La primera versión deberá aprovechar las capacidades proporcionadas por Next.js y Supabase antes de introducir infraestructura adicional.

A medida que la plataforma crezca, podrán incorporarse nuevos servicios sin modificar la visión principal del producto.

El principio será:

CONSTRUIR

↓

VALIDAR

↓

MEDIR

↓

MEJORAR

↓

ESCALAR