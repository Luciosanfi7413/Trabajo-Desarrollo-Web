# 🏢 Trabajo Práctico: Implementación y Configuración de Mesa de Ayuda (GLPI)

---

## 👥 Integrantes del Proyecto
* **[Arias, Matías]**
* **[Galli, Mariano]**
* **[Maldonado, Patricio]**
* **[Marcenaro, Lucía ]**
* **[Sanfilippo, Lucio ]**

**Asignatura:** [Desarrollo Web]  
**Año:** 2026  

---

## 📌 Índice del Documento
1. [1.0 Introducción y Objetivos](#10-introducción-y-objetivos)
2. [2.0 Alcance del Sistema](#20-alcance-del-sistema)
3. [3.0 Roles y Perfiles de Usuario](#30-roles-y-perfiles-de-usuario)
4. [4.0 Ciclo de Vida del Ticket](#40-ciclo-de-vida-del-ticket)
5. [5.0 Requisitos Funcionales y No Funcionales](#50-requisitos-funcionales-y-no-funcionales)
6. [6.0 Historias de Usuario](#60-historias-de-usuario)
7. [7.0 Casos de Uso](#70-casos-de-uso)
8. [8.0 Modelo de Datos (DER)](#80-modelo-de-datos-der)

---

## 1.0 Introducción y Objetivos
*[Copiar y pegar acá el texto de introducción que tenés en tu documento original]*

---

## 2.0 Alcance del Sistema
*[Copiar y pegar acá el alcance (dentro y fuera de alcance) de tu documento original]*

---

## 3.0 Roles y Perfiles de Usuario
*[Copiar y pegar acá la descripción de roles que armaron para el trabajo]*

---

## 4.0 Ciclo de Vida del Ticket
*[Copiar y pegar acá el texto o los pasos del ciclo de vida que definieron]*

---

## 5.0 Requisitos Funcionales y No Funcionales

### 5.1. Requerimientos Funcionales (RF)

#### Módulo 1 — Autenticación y Permisos
* **RF01:** El sistema debe permitir el inicio de sesión mediante usuario y contraseña únicos para cada empleado de la organización.
* **RF02:** El sistema debe restringir las funciones según cuatro perfiles: Administrador, Técnico de Sistemas, Especialista Externo y Solicitante (empleados de Compras, Ventas, Logística, etc.).

#### Módulo 2 — Gestión y Registro de Tickets
* **RF03:** El sistema debe proveer un formulario web estandarizado para que los empleados registren incidentes ingresando: categoría, descripción y urgencia.
* **RF04:** Al abrir un formulario, el sistema debe asociar el ticket al nombre del usuario logueado.
* **RF05:** El sistema debe generar un número de ticket único y correlativo de forma automática al momento de confirmar el registro.
* **RF06:** El sistema debe cambiar y mostrar el estado de los tickets a través de un flujo definido: Nuevo, En curso, En espera, Resuelto y Cerrado.
* **RF07:** El sistema debe enviar un correo automático al empleado y al área de sistemas confirmando la creación del ticket con su número único.
* **RF08:** El sistema debe permitir a los usuarios y técnicos adjuntar archivos (capturas de pantalla, imágenes, PDF) con un tamaño máximo configurable.
* **RF09:** El sistema debe permitir enlazar un activo informático específico (hardware o software) a un ticket.

#### Módulo 3 — Resolución y Seguimiento de Incidentes
* **RF10:** El sistema debe permitir al Jefe de Sistemas asignar tickets de forma manual a cualquier técnico del área.
* **RF11:** El sistema debe incluir un chat o sección de seguimiento dentro del ticket para que el técnico y el empleado intercambien mensajes sobre el avance del caso.
* **RF12:** El sistema debe permitir a los técnicos documentar el tiempo exacto (horas/minutos) dedicado a la resolución de cada tarea interna o externa.
* **RF13:** El sistema debe enviar un correo al empleado solicitante cuando el ticket pase a estado "Resuelto", detallando la solución aplicada.
* **RF14:** El sistema debe permitir al técnico cambiar el estado del ticket a "Resuelto". Asimismo, debe habilitar una opción para que el empleado solicitante apruebe la solución y brinde su conformidad, permitiendo el cierre definitivo del caso de forma automática o manual según su interacción.
* **RF15:** En caso de contar con un ticket en estado “Resuelto” y no recibir respuesta por parte del solicitante para cerrarlo, el sistema deberá permitir al jefe de sistema cambiar el estado del ticket a cerrarlo.

#### Módulo 4 — Integración y Soporte Externo
* **RF16:** El sistema debe permitir la asignación de tickets a proveedores de soporte externos, registrando los datos de contacto y el motivo de la derivación.
* **RF17:** El sistema debe pausar automáticamente el contador de tiempo de resolución cuando el ticket se cambie al estado "En espera" por derivación externa.
* **RF18:** El sistema debe exigir que un técnico interno valide la solución cargada por el especialista externo antes de permitir el cierre definitivo del ticket.

#### Módulo 5 — Administración, Auditoría y Reportes
* **RF19:** El sistema debe permitir a los técnicos transformar soluciones de tickets cerrados en artículos públicos o privados para agilizar problemas repetitivos.
* **RF20:** El sistema debe contar con un motor de búsqueda con filtros avanzados (por número, fecha, área, técnico o estado) para consultar el historial de tickets.
* **RF21:** El sistema debe registrar de forma inmutable qué usuario, técnico o especialista realizó cambios en los campos o estados del ticket, incluyendo fecha y hora.
* **RF22:** El sistema debe proveer una herramienta para importar datos masivos de hardware y usuarios a través de archivos estructurados (CSV o PDF).
* **RF23:** El sistema debe generar estadísticas de rendimiento.
* **RF24:** El sistema debe mostrar en la pantalla de inicio de los técnicos gráficos en tiempo real con la cantidad de tickets abiertos, cerrados, vencidos y derivados.

### 5.2. Requerimientos No Funcionales (RNF)

#### Seguridad y Respaldo
* **RNF01:** El sistema debe cifrar los accesos web mediante certificados SSL/TLS, obligando el uso de conexiones seguras mediante el protocolo HTTPS.
* **RNF02:** El sistema debe ejecutar una copia de seguridad automática de la base de datos y archivos adjuntos cada 24 horas, almacenándola en un volumen externo.

#### Usabilidad e Idioma
* **RNF03:** La interfaz gráfica de usuario, los mensajes de error y las notificaciones por correo deben configurarse nativamente en idioma español.
* **RNF04:** El sistema debe ser accesible de manera remota y local a través de navegadores web estándar (Chrome, Firefox, Edge, Safari) sin requerir instalaciones cliente.

#### Rendimiento y Capacidad
* **RNF05:** El tiempo de procesamiento y carga de la pantalla principal no debe superar los 3 segundos bajo una conectividad de red estándar.
* **RNF06:** El sistema debe soportar un mínimo de 50 usuarios conectados de forma simultánea sin experimentar degradación en los tiempos de respuesta del servidor.

#### Escalabilidad
* **RNF07:** La plataforma debe permitir activar o desactivar módulos nativos de GLPI (como la gestión de proyectos o contratos) en el futuro sin alterar la base de datos de tickets existente.

---

## 6.0 Historias de Usuario

### 🔹 HU-01: Asociar datos del usuario al crear un ticket
* **Como** usuario del sistema,
* **Quiero** que mi identidad se vincule automáticamente al abrir un ticket,
* **Para** ahorrar tiempo en la carga del formulario y evitar errores de tipeo.

> 📝 **Criterios de Aceptación:**
> * Al ingresar a la pantalla de "Nuevo Ticket", el formulario web estandarizado debe asociar de forma automática el caso al nombre del usuario logueado (**RF04**).
> * Las funciones disponibles en la pantalla deben estar estrictamente restringidas según el perfil correspondiente del empleado (**RF02**).
> * La interfaz gráfica de usuario y todo el formulario deben visualizarse nativamente en idioma español (**RNF03**).

---

### 🔹 HU-02: Adjuntar Capturas de Pantalla y Evidencias
* **Como** usuario del sistema,
* **Quiero** poder adjuntar imágenes o documentos a mi solicitud de asistencia,
* **Para** ofrecer detalles visuales del error exacto al técnico de sistemas.

> 📝 **Criterios de Aceptación:**
> * El formulario debe permitir a los usuarios (Solicitantes) y técnicos adjuntar archivos como capturas de pantalla, imágenes o PDF (**RF08**).
> * El sistema debe validar que los archivos cargados no superen el tamaño máximo configurable fijado en la plataforma (**RF08**).
> * El tiempo de carga y procesamiento de estos elementos no debe degradar la respuesta general de la pantalla (**RNF05**).

---

### 🔹 HU-03: Visualización de Indicadores Técnicos en Tiempo Real
* **Como** Técnico de Sistemas,
* **Quiero** ver gráficos actualizados en la pantalla de inicio sobre el estado de la bandeja de entrada,
* **Para** conocer instantáneamente el volumen de incidentes bajo mi responsabilidad sin realizar búsquedas manuales.

> 📝 **Criterios de Aceptación:**
> * La pantalla de inicio de los técnicos debe mostrar gráficos en tiempo real con la cantidad exacta de tickets abiertos, cerrados, vencidos y derivados (**RF24**).
> * El tiempo de procesamiento y carga de esta pantalla principal con sus gráficos no debe superar los 3 segundos bajo conectividad estándar (**RNF05**).
> * La carga de estos datos debe soportar al menos 50 usuarios técnicos o administrativos en simultáneo sin sufrir degradación (**RNF06**).

---

### 🔹 HU-04: Pausa de Tiempos por Soporte Externo
* **Como** Técnico de Sistemas,
* **Quiero** que el contador de resolución se suspenda cuando transfiero el caso a un proveedor de soporte externo,
* **Para** que los tiempos de demora del tercero no afecten mis métricas e indicadores de rendimiento interno.

> 📝 **Criterios de Aceptación:**
> * El sistema debe permitir asignar incidentes a proveedores de soporte externos, registrando de forma obligatoria sus datos de contacto y el motivo de la derivación (**RF16**).
> * Al cambiar el estado del ticket a "En espera" por motivo de derivación externa, el sistema debe pausar automáticamente el contador de tiempo de resolución (**RF17**).

---

### 🔹 HU-05: Validación de Conformidad y Cierre de Casos
* **Como** Técnico de Sistemas,
* **Quiero** que los empleados tengan un mecanismo formal para validar las soluciones que aplicamos,
* **Para** asegurar que el problem quedó resuelto operativamente antes de archivar el ticket.

> 📝 **Criterios de Aceptación:**
> * El sistema debe habilitar una opción en la plataforma para que el empleado solicitante apruebe la solución, brinde su conformidad y gatille el cierre definitivo del caso (**RF14**).
> * En caso de que el ticket esté en estado "Resuelto" y el solicitante no responda para cerrarlo, el sistema debe permitir al jefe de sistema cambiar manualmente el estado a cerrado (**RF15**).
> * Cualquier cambio de estado o validación debe registrarse de forma inmutable con usuario, fecha y hora (**RF21**).

---

## 7.0 Casos de Uso

```text
================================================================================
CU001: Registro de Incidente
================================================================================
Descripción:       Permite a cualquier empleado de la organización reportar una 
                   falla o solicitud técnica mediante un formulario web 
                   estandarizado que asocia automáticamente su identidad al caso.
Actores:           Solicitante (Empleado).
Precondiciones:    El usuario debe estar autenticado en el sistema (RF01) a 
                   través de un navegador compatible (RNF04) bajo HTTPS (RNF01).
Postcondiciones:   El ticket queda registrado con estado "Nuevo" dentro del 
                   flujo definido y visible en la bandeja técnica (RF06).
--------------------------------------------------------------------------------
Secuencia Normal:
  1. El Solicitante ingresa a la opción "Nuevo Ticket".
     -> El sistema visualiza el formulario web estandarizado en idioma español 
        y asocia automáticamente el caso al nombre del usuario logueado 
        (RF03, RF04, RNF03).
  2. El Solicitante selecciona la Categoría del incidente, ingresa la 
     Descripción y selecciona el nivel de Urgencia (RF03).
     -> No aplica.
  3. El Solicitante opcionalmente adjunta archivos de evidencia como capturas 
     de pantalla, imágenes o PDF (RF08).
     -> No aplica.
  4. El Solicitante opcionalmente enlaza un activo informático específico 
     (hardware o software) de la lista de su área (RF09).
     -> No aplica.
  5. El Solicitante hace clic en el botón "Añadir".
     -> El sistema genera un número de ticket único y correlativo de forma 
        automática al momento de confirmar el registro (RF05).
  6. No aplica.
     -> El sistema cambia y muestra el estado del ticket a "Nuevo" dentro 
        del flujo definido (RF06).
  7. No aplica.
     -> El sistema envía un correo automático al empleado y al área de sistemas 
        confirmando la creación del ticket con su número único (RF07).

Excepciones:
  q. El usuario intenta adjuntar archivos que superan el tamaño máximo.
     -> El sistema rechaza la carga por exceder el límite configurable (RF08) 
        y lanza un mensaje informativo en español (RNF03).
--------------------------------------------------------------------------------
Importancia: Vital | Urgencia: Inmediatamente | Comentarios: No aplica
================================================================================
