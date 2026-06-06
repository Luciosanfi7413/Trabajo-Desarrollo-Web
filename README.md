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

---

### 📄 CU001: Registro de Incidencia

| Atributo | Detalle |
| :--- | :--- |
| **Descripción** | Permite a cualquier empleado de la organización reportar una falla o solicitud técnica mediante un formulario web estandarizado que asocia automáticamente su identidad al caso. |
| **Actores** | Solicitante (Empleado). |
| **Precondiciones** | El usuario debe estar autenticado en el sistema (RF01). |
| **Postcondiciones** | El ticket queda registrado con estado "Nuevo" y visible en la bandeja de entrada del equipo técnico (RF06). |

#### 🔁 Secuencia Normal
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **1** | El Solicitante ingresa a la opción "Nuevo Ticket". | El sistema visualiza el formulario web estandarizado y asocia automáticamente el ticket al nombre del usuario logueado (RF03, RF04). |
| **2** | El Solicitante selecciona la Categoría del incidente, ingresa la Descripción y selecciona el nivel de Urgencia (RF03). | No aplica. |
| **3** | El Solicitante opcionalmente adjunta archivos de evidencia como capturas de pantalla, imágenes o PDF (RF08). | No aplica. |
| **4** | El Solicitante opcionalmente enlaza un activo informático específico (hardware o software) al ticket (RF09). | No aplica. |
| **5** | El Solicitante hace clic en el botón "Añadir". | El sistema genera un número de ticket único y correlativo de forma automática al momento de confirmar el registro (RF05). |
| **6** | No aplica. | El sistema cambia y muestra el estado del ticket a "Nuevo" dentro del flujo definido (RF06). |
| **7** | No aplica. | El sistema envía un correo automático al empleado y al área de sistemas confirmando la creación del ticket con su número único (RF07). |

#### ⚠️ Excepciones
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **q** | El usuario intenta adjuntar archivos que superan el tamaño máximo configurable (RF08). | El sistema rechaza la carga del archivo y lanza un mensaje informativo. |

| Parámetro | Valor |
| :--- | :--- |
| **Importancia** | Vital. |
| **Urgencia** | Inmediatamente. |
| **Comentarios** | No aplica. |

---

### 📄 CU002: Asignación y Priorización de Ticket

| Atributo | Detalle |
| :--- | :--- |
| **Descripción** | Permite al Jefe de Sistemas evaluar los incidentes entrantes utilizando la matriz de prioridad calculada automáticamente, ordenando por defecto la bandeja de entrada para visualizar los casos críticos y delegarlos manualmente. |
| **Actores** | Jefe de Sistemas. |
| **Precondiciones** | Existen tickets en estado "Nuevo" en la bandeja de entrada (RF06). |
| **Postcondiciones** | El ticket cambia a estado "En curso" dentro del flujo y queda asignado al técnico correspondiente (RF06, RF10). |

#### 🔁 Secuencia Normal
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **1** | El Jefe de Sistemas ingresa al panel de control de tickets. | El sistema muestra la pantalla de inicio con gráficos en tiempo real (RF24) y calcula de forma automática la Prioridad del ticket (Baja, Media, Alta, Crítica) cruzando la Urgencia cargada por el usuario y el Impacto técnico preliminar definido (RF07). |
| **2** | El Jefe de Sistemas visualiza la bandeja predeterminada. | El sistema ordena de forma automática y predeterminada la lista de tickets, mostrando los de prioridad "Crítica" y "Alta" en primer lugar para agilizar la gestión. |
| **3** | El Jefe de Sistemas aplica el motor de búsqueda con filtros avanzados si requiere segmentar por área o fecha (RF20). | No aplica. |
| **4** | El Jefe de Sistemas selecciona un técnico de la lista y le asigna el caso manualmente (RF10). | El sistema cambia el estado del ticket a "En curso" (RF06) e incluye la sección de chat o seguimiento para interactuar (RF11). |

#### ⚠️ Excepciones
*No aplica.*

| Parámetro | Valor |
| :--- | :--- |
| **Importancia** | Vital. |
| **Urgencia** | Inmediata. |
| **Comentarios** | No aplica. |

---

### 📄 CU003: Derivación a Soporte Externo

| Atributo | Detalle |
| :--- | :--- |
| **Descripción** | Permite a un técnico interno transferir la resolución de un incidente a un proveedor o especialista externo registrado, congelando los tiempos de resolución del sistema durante su intervención. |
| **Actores** | Técnico de Sistemas, Especialista Externo. |
| **Precondiciones** | El ticket se encuentra en estado "En curso" (RF06). |
| **Postcondiciones** | El ticket queda en estado "En espera" con el contador de tiempo de resolución pausado automáticamente (RF06, RF17). |

#### 🔁 Secuencia Normal
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **1** | El Técnico de Sistemas determina que el problema requiere la intervención de un proveedor externo. | No aplica. |
| **2** | El Técnico selecciona de la lista al proveedor de soporte externo correspondiente, registrando los datos de contacto y el motivo de la derivación (RF16). | El sistema cambia el estado del ticket a "En espera" dentro del flujo definido (RF06). |
| **3** | No aplica. | El sistema pausa automáticamente el contador de tiempo de resolución al pasar al estado "En espera" por derivación externa (RF17). |
| **4** | El Especialista Externo ingresa al ticket, intercambia mensajes en la sección de seguimiento (RF11) y documenta el tiempo exacto (horas/minutos) dedicado a la resolución de la tarea (RF12). | El sistema registra de forma inmutable qué especialista realizó los cambios, incluyendo fecha y hora (RF21). |

#### ⚠️ Excepciones
*No aplica.*

| Parámetro | Valor |
| :--- | :--- |
| **Importancia** | Importante. |
| **Urgencia** | Media. |
| **Comentarios** | No aplica. |

---

### 📄 CU004: Validación y Cierre de Ticket

| Atributo | Detalle |
| :--- | :--- |
| **Descripción** | Permite registrar la solución de un incidente en curso (validando la intervención externa si corresponde) y cambiar su estado para que el empleado evalúe la conformidad, habilitando también el cierre administrativo si el usuario no responde. |
| **Actores** | Técnico de Sistemas, Solicitante, Jefe de Sistemas. |
| **Precondiciones** | El ticket se encuentra originalmente en estado "En curso" o asignado para revisión en la bandeja (RF06). |
| **Postcondiciones** | El ticket cambia a estado "Cerrado" dentro del flujo de forma definitiva y la acción queda registrada en la auditoría inmutable del sistema (RF06, RF21). |

#### 🔁 Secuencia Normal
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **1** | El Técnico de Sistemas finaliza las tareas de soporte interno (o valida obligatoriamente la solución cargada por el especialista externo antes de permitir avanzar con el cierre, según RF18). | No aplica. |
| **2** | El Técnico registra la solución definitiva en el sistema y cambia manualmente el estado del ticket a "Resuelto" (RF14, RF06). | El sistema envía un correo al empleado solicitante cuando el ticket pasa a estado "Resuelto", detallando la solución aplicada (RF13). |
| **3** | El Solicitante recibe la notificación, ingresa al sistema y utiliza la opción habilitada para aprobar la solución y brindar su conformidad (RF14). | El sistema procesa la conformidad del usuario y cambia el estado del ticket a "Cerrado" de forma automática (RF14, RF06). |

#### ⚠️ Excepciones
| # | Acción (Actor) | Reacción (Sistema) |
| :-: | :--- | :--- |
| **p** | El ticket se encuentra en estado "Resuelto" y no se recibe respuesta por parte del solicitante para cerrarlo debido a la falta de compromiso interno técnico (RF15). | El Jefe de Sistemas cambia manualmente el estado del ticket para proceder a cerrarlo (RF15, RF06), registrándose la transacción con usuario, fecha y hora en el registro inmutable de auditoría (RF21). |

| Parámetro | Valor |
| :--- | :--- |
| **Importancia** | Importante. |
| **Urgencia** | Vital. |
| **Comentarios** | No aplica. |
## 8.0 Modelo de Datos (DER)

---

![Diagrama Entidad Relación](./TP%20DESARROLLO%20DIAGRAMA.png)

> 💡 **Nota de renderizado:** Para visualizar de forma interactiva el diagrama de arriba, podés importar el archivo correspondiente directamente en [Draw.io](https://app.diagrams.net/).

### 📝 Descripción Técnica del Modelo Entidad-Relación

Para garantizar la integridad de los datos y cumplir estrictamente con las reglas de negocio de la mesa de ayuda, el diagrama implementa las siguientes relaciones y cardinalidades:

| Entidad Origen | Relación (Rombo) | Entidad Destino | Cardinalidad | Explicación Técnica |
| :--- | :---: | :--- | :---: | :--- |
| **USUARIO** | Genera | **TICKET** | `1 : N` | Un usuario (Solicitante) puede reportar muchos tickets, pero cada ticket individual pertenece a un único usuario emisor. |
| **USUARIO** | Asigna | **TICKET** | `1 : N` | Un usuario (Técnico) puede tener asignados muchos tickets para resolver, pero un ticket en curso se delega a un solo técnico responsable. |
| **TICKET** | Pertenece | **CATEGORIA** | `N : 1` | Muchos tickets pueden clasificarse bajo la misma tipología, pero un ticket individual pertenece estrictamente a una única categoría técnica. |
| **TICKET** | Se asocia | **ACTIVO DE INVENTARIO** | `N : 1` | Muchos tickets de soporte pueden estar asociados a un mismo hardware o software defectuoso, pero cada ticket vincula un único activo por vez. |
| **TICKET** | Contiene | **ADJUNTO** | `1 : N` | Un ticket puede contener múltiples archivos de evidencia (capturas, imágenes, PDFs), pero cada archivo pertenece de forma exclusiva a un único ticket. |
| **TICKET** | Se deriva | **PROVEEDOR EXTERNO** | `N : 1` | Muchos tickets que excedan las capacidades internas pueden derivarse al mismo soporte tercerizado, pero un ticket específico solo se desvía a un único proveedor. |
