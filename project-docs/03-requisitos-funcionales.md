# 03 - Requisitos Funcionales

## 1. Objetivo

Este documento define los requisitos funcionales de la plataforma **1 Millón de Amigos**.

Los requisitos funcionales describen las acciones, procesos y comportamientos que el sistema debe permitir.

Cada requisito tendrá un identificador único para facilitar su referencia durante el diseño, desarrollo, pruebas y mantenimiento del proyecto.

---

# 2. Registro y autenticación

## RF-001 - Registro con correo electrónico

El sistema debe permitir que un usuario cree una cuenta utilizando:

- Nombre.
- Apellido.
- Fecha de nacimiento.
- Correo electrónico.
- Contraseña.
- Nombre de usuario.

---

## RF-002 - Nombre de usuario único

El sistema debe garantizar que cada nombre de usuario sea único dentro de la plataforma.

No podrán existir dos usuarios con el mismo nombre de usuario.

---

## RF-003 - Correo electrónico único

El sistema debe garantizar que una dirección de correo electrónico solo pueda estar asociada a una cuenta.

---

## RF-004 - Verificación de correo electrónico

El sistema debe solicitar la verificación del correo electrónico del usuario.

---

## RF-005 - Registro con Google

El sistema debe permitir el registro e inicio de sesión mediante una cuenta de Google.

---

## RF-006 - Registro con Apple

El sistema debe permitir el registro e inicio de sesión mediante una cuenta de Apple.

---

## RF-007 - Inicio de sesión

El sistema debe permitir que los usuarios registrados inicien sesión.

---

## RF-008 - Recuperación de contraseña

El sistema debe permitir que un usuario solicite la recuperación de su contraseña.

---

## RF-009 - Cierre de sesión

El sistema debe permitir que un usuario cierre sesión de forma segura.

---

# 3. Perfil de usuario

## RF-010 - Perfil de usuario

El sistema debe crear un perfil para cada usuario registrado.

El perfil deberá permitir mostrar información relacionada con:

- Nombre de usuario.
- Información pública.
- Publicaciones creadas.
- Proyectos apoyados.
- Actividad.
- Reconocimientos.
- Reputación.
- Participación en ayudas.

---

## RF-011 - Visualización de perfiles

El sistema debe permitir visualizar perfiles públicos de usuarios.

---

## RF-012 - Edición de perfil

El sistema debe permitir que un usuario edite la información permitida de su propio perfil.

---

# 4. Publicaciones y proyectos

## RF-013 - Creación de publicaciones

El sistema debe permitir que cualquier usuario registrado cree una publicación o proyecto.

Una publicación puede representar:

- Una necesidad personal.
- Una necesidad colectiva.
- Una solicitud de ayuda.
- Una causa.
- Una actividad.
- Una idea.
- Una pregunta simple.

---

## RF-014 - Múltiples publicaciones

El sistema debe permitir que un usuario registrado cree múltiples publicaciones.

---

## RF-015 - Borrador

El sistema debe permitir guardar una publicación como borrador antes de publicarla.

---

## RF-016 - Publicación automática

Las publicaciones deberán publicarse automáticamente sin requerir aprobación previa de un administrador.

---

## RF-017 - Edición de publicaciones

El sistema debe permitir que el creador de una publicación edite su contenido después de haber sido publicado.

---

## RF-018 - Eliminación de publicaciones

El sistema debe permitir que el creador de una publicación elimine su propio contenido.

Cuando una publicación haya sido eliminada, su contenido no deberá estar disponible públicamente.

---

## RF-019 - Estados de publicaciones

El sistema deberá manejar los siguientes estados:

- Borrador.
- Publicado.
- Bloqueado.
- Eliminado.

---

## RF-020 - Enlace de publicación eliminada

Cuando una publicación haya sido eliminada, su enlace podrá continuar existiendo.

Al acceder al enlace, el sistema deberá informar que el contenido ya no está disponible.

---

## RF-021 - Categorías

El sistema debe permitir asociar una publicación con:

- Una categoría.
- Varias categorías.
- Ninguna categoría.

---

## RF-022 - Gestión de categorías

El administrador deberá poder crear nuevas categorías para la plataforma.

---

## RF-023 - Ubicación

El sistema debe permitir que un usuario agregue una ubicación a una publicación de manera opcional.

El usuario deberá poder decidir si desea mostrar o no la ubicación públicamente.

---

## RF-024 - Contenido de publicaciones

La plataforma deberá estar preparada para permitir publicaciones con:

- Texto.
- Imágenes.
- Videos.
- Enlaces.

La implementación inicial podrá habilitar únicamente el contenido definido para la primera versión del producto.

---

# 5. Feed y exploración

## RF-025 - Feed principal

El sistema debe mostrar un feed principal con publicaciones disponibles.

---

## RF-026 - Visualización pública

Las publicaciones deberán poder ser visualizadas por visitantes que no hayan iniciado sesión.

---

## RF-027 - Explorar publicaciones

El sistema debe permitir explorar publicaciones.

---

## RF-028 - Búsqueda

El sistema debe proporcionar una funcionalidad de búsqueda de publicaciones.

---

## RF-029 - Filtro por categorías

El sistema debe permitir filtrar publicaciones por categorías.

---

## RF-030 - Página individual

Cada publicación deberá contar con una página individual accesible mediante una dirección única.

---

# 6. Interacciones sociales

## RF-031 - Me gusta

Los usuarios registrados deberán poder indicar que les gusta una publicación.

---

## RF-032 - Comentarios

Los usuarios registrados deberán poder comentar publicaciones.

---

## RF-033 - Compartir

El sistema deberá permitir compartir publicaciones.

---

## RF-034 - Seguir usuarios

Los usuarios registrados deberán poder seguir a otros usuarios.

---

## RF-035 - Seguir publicaciones

Los usuarios registrados deberán poder seguir publicaciones o proyectos.

---

## RF-036 - Dar aliento

Los usuarios registrados deberán poder expresar aliento o apoyo a una publicación.

El sistema deberá registrar esta interacción.

---

# 7. Sistema de ayuda

## RF-037 - Formas de ayuda

El sistema deberá permitir las siguientes formas de ayuda:

- Aliento.
- Dinero.
- Bienes.
- Servicios.
- Tiempo.
- Conocimiento.
- Difusión.

---

## RF-038 - Ofrecer ayuda

El sistema deberá permitir que un usuario registrado indique que desea ayudar a una publicación.

---

## RF-039 - Ayuda mediante dinero

El sistema deberá proporcionar un flujo para realizar aportes económicos.

Durante la primera fase, el sistema utilizará un mecanismo de simulación de donaciones.

---

## RF-040 - Ayuda mediante bienes

El sistema deberá permitir que un usuario ofrezca un bien para apoyar una publicación.

La coordinación de la ayuda podrá realizarse mediante el sistema de comunicación de la plataforma.

---

## RF-041 - Ayuda mediante servicios

El sistema deberá permitir que un usuario ofrezca un servicio para apoyar una publicación.

---

## RF-042 - Ayuda mediante tiempo

El sistema deberá permitir que un usuario ofrezca su tiempo como voluntario para apoyar una publicación.

---

## RF-043 - Ayuda mediante conocimiento

El sistema deberá permitir que un usuario ofrezca conocimientos o experiencia para apoyar una publicación.

---

## RF-044 - Ayuda mediante difusión

El sistema deberá permitir que un usuario ayude a difundir una publicación.

---

## RF-045 - Registro de ayudas

El sistema deberá registrar las ayudas realizadas por los usuarios.

---

## RF-046 - Confirmación de ayuda

El sistema deberá permitir registrar la confirmación de una ayuda cuando corresponda.

---

# 8. Chat y comunicación

## RF-047 - Sistema de chat

La plataforma deberá contar con un sistema de comunicación mediante chat entre usuarios registrados.

---

## RF-048 - Inicio de conversaciones

El sistema deberá permitir iniciar conversaciones entre usuarios de acuerdo con las reglas de acceso definidas para la plataforma.

---

## RF-049 - Coordinación de ayuda

El sistema de chat deberá permitir la coordinación entre usuarios relacionada con:

- Bienes.
- Servicios.
- Tiempo.
- Conocimiento.
- Otras formas de ayuda.

---

# 9. Seguimiento y notificaciones

## RF-050 - Notificaciones

El sistema deberá informar a los usuarios sobre actividades relacionadas con su participación dentro de la plataforma.

---

## RF-051 - Actividad

El sistema deberá registrar actividades relevantes de los usuarios dentro de la plataforma.

---

# 10. Reputación y reconocimientos

## RF-052 - Registro de participación

El sistema deberá registrar la participación de los usuarios en las diferentes formas de ayuda.

---

## RF-053 - Sistema de reputación

La plataforma deberá contar con un sistema de reputación basado en la participación de los usuarios.

La reputación no deberá depender únicamente de las contribuciones económicas.

---

## RF-054 - Puntos

El sistema podrá asignar puntos a los usuarios de acuerdo con las acciones realizadas dentro de la plataforma.

---

## RF-055 - Reconocimientos

El sistema deberá permitir otorgar reconocimientos relacionados con la participación y contribución de los usuarios.

Los reconocimientos podrán incluir:

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

---

## RF-056 - Participación en proyectos completados

Cuando un proyecto sea completado, el sistema deberá permitir reconocer a los usuarios que participaron en él.

La plataforma podrá mostrar un reconocimiento asociado a su participación.

Ejemplo:

> Yo fui parte.

---

# 11. Administración y moderación

## RF-057 - Panel administrativo

El sistema deberá proporcionar un panel administrativo para usuarios con permisos de administrador.

---

## RF-058 - Gestión de usuarios

El administrador deberá poder:

- Visualizar usuarios.
- Bloquear temporalmente cuentas.
- Desbloquear cuentas.
- Eliminar permanentemente cuentas.

---

## RF-059 - Gestión de publicaciones

El administrador deberá poder:

- Visualizar publicaciones.
- Bloquear temporalmente publicaciones.
- Desbloquear publicaciones.
- Eliminar permanentemente publicaciones.

---

## RF-060 - Denuncias

El sistema deberá permitir que los usuarios denuncien contenido.

---

## RF-061 - Gestión de denuncias

El administrador deberá poder:

- Visualizar denuncias.
- Revisar contenido denunciado.
- Revisar usuarios involucrados.
- Aplicar medidas de moderación.

---

# 12. Pagos y donaciones

## RF-062 - Simulación de donaciones

Durante la primera fase, el sistema deberá permitir simular aportes económicos.

La simulación deberá registrar la actividad dentro de la plataforma.

---

## RF-063 - Historial de aportes

El sistema deberá registrar los aportes económicos realizados durante la simulación.

---

## RF-064 - Integración futura de pagos

La arquitectura del sistema deberá permitir incorporar posteriormente una pasarela de pagos real.

---

# 13. Restricciones generales

## RF-065 - Acciones que requieren autenticación

Las siguientes acciones deberán requerir que el usuario haya iniciado sesión:

- Crear publicaciones.
- Editar publicaciones.
- Comentar.
- Dar me gusta.
- Seguir usuarios.
- Seguir publicaciones.
- Dar aliento.
- Ofrecer ayuda.
- Utilizar el chat.
- Realizar aportes.

---

## RF-066 - Acceso público

Los visitantes no registrados deberán poder visualizar el contenido público de la plataforma.

---

# 14. Resumen funcional

La primera versión de 1 Millón de Amigos deberá permitir el siguiente flujo general:

Visitante

↓

Visualiza publicaciones públicas

↓

Se registra o inicia sesión

↓

Usuario registrado

↓

Puede:

- Crear publicaciones.
- Publicar necesidades, ideas o preguntas.
- Interactuar con publicaciones.
- Seguir usuarios y proyectos.
- Dar aliento.
- Ofrecer diferentes formas de ayuda.
- Comunicarse mediante chat.
- Participar en la comunidad.
- Recibir reputación y reconocimientos.

↓

Administrador

↓

Gestiona:

- Usuarios.
- Publicaciones.
- Denuncias.
- Moderación.