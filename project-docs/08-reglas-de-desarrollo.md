# 08 - Reglas de Desarrollo

## 1. Objetivo

Este documento define las reglas generales que deberán seguirse durante el desarrollo de la plataforma **1 Millón de Amigos**.

El objetivo es mantener:

- Orden.
- Consistencia.
- Seguridad.
- Facilidad de mantenimiento.
- Control de cambios.
- Coherencia con los documentos funcionales y técnicos del proyecto.

Estas reglas deberán ser respetadas tanto por desarrolladores humanos como por herramientas de inteligencia artificial utilizadas durante el desarrollo.

---

# 2. Principio principal

Antes de desarrollar una nueva funcionalidad se deberá revisar la documentación existente del proyecto.

Los cambios deberán respetar:

- La visión del producto.
- Los roles de usuario.
- Los requisitos funcionales.
- Los flujos de usuario.
- El modelo de datos.
- La arquitectura y servicios definidos.
- Las reglas de interfaz.
- Las presentes reglas de desarrollo.

No se deberán implementar funcionalidades basándose únicamente en suposiciones.

---

# 3. No inventar requisitos

La inteligencia artificial o cualquier desarrollador no deberá inventar funcionalidades que no hayan sido definidas.

Si una funcionalidad no está suficientemente clara, deberá identificarse como una decisión pendiente antes de implementarla.

No se deberá asumir:

- Nuevos tipos de usuarios.
- Nuevos permisos.
- Nuevas funcionalidades.
- Nuevos campos en la base de datos.
- Nuevos flujos.
- Nuevos métodos de pago.
- Nuevos colores o estilos.

sin revisar primero la documentación existente.

---

# 4. Desarrollo por etapas

El proyecto deberá desarrollarse por etapas.

No se deberá intentar construir toda la plataforma simultáneamente.

El proceso general será:

DOCUMENTAR

↓

DEFINIR

↓

DISEÑAR

↓

IMPLEMENTAR

↓

PROBAR

↓

CORREGIR

↓

GUARDAR CAMBIOS

↓

CONTINUAR

Cada funcionalidad deberá ser completada y verificada antes de avanzar a la siguiente.

---

# 5. Desarrollo incremental

Las funcionalidades deberán construirse en partes pequeñas y controlables.

Ejemplo:

Incorrecto:

"Construye toda la red social."

Correcto:

"Implementa el registro de usuarios."

↓

Probar

↓

"Implementa la creación del perfil."

↓

Probar

↓

"Implementa la creación de publicaciones."

↓

Probar

Este principio será especialmente importante durante el desarrollo mediante inteligencia artificial.

---

# 6. No modificar funcionalidades existentes sin necesidad

Una nueva funcionalidad no deberá modificar código existente innecesariamente.

Antes de realizar cambios se deberá identificar:

- Qué archivo será modificado.
- Por qué necesita ser modificado.
- Qué funcionalidad puede verse afectada.

No se deberá realizar una reestructuración completa del proyecto para agregar una funcionalidad pequeña.

---

# 7. Reutilización de componentes

Antes de crear un nuevo componente se deberá verificar si ya existe uno que pueda reutilizarse.

Ejemplos:

- Botones.
- Campos de formulario.
- Tarjetas.
- Modales.
- Navegación.
- Avatares.
- Mensajes de error.
- Indicadores de carga.

No deberán crearse múltiples versiones del mismo componente sin una razón clara.

---

# 8. Estructura clara del proyecto

El código deberá mantener una estructura organizada.

La estructura inicial podrá evolucionar, pero deberá mantener una separación clara entre:

- Páginas.
- Componentes.
- Funcionalidades.
- Servicios.
- Tipos.
- Utilidades.
- Configuración.

Ejemplo conceptual:

```text
src/

├── app/
│
├── components/
│
├── features/
│
├── services/
│
├── types/
│
├── lib/
│
└── utils/