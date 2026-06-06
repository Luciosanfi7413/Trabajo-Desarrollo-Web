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
Introducción.
Somos una empresa que ofrece la implementación de GLPI, enfocada en clientes que todavía no utilizan herramientas formales de gestión de tickets, inventario ni soporte técnico. Para este trabajo se tomó como caso de estudio a Logística y Minería S.A., una empresa de transporte de carga con más de 20 años de experiencia, que actualmente enfrenta problemas de comunicación interna y de gestión de incidencias.
El presente proyecto busca analizar el proceso actual de soporte técnico de la empresa y proponer la implementación de GLPI como solución tecnológica. A lo largo del documento se realizará un relevamiento, un análisis de los procesos actuales y una propuesta de mejora, con su respectivo estudio de factibilidad.
Objetivo.
El objetivo principal de este proyecto es evaluar la viabilidad de implementar GLPI en Logística y Minería S.A. con el fin de mejorar la trazabilidad de incidencias, optimizar la comunicación entre áreas y aumentar la eficiencia en la resolución de problemas técnicos. Además, se busca estandarizar procesos actualmente dispersos y manuales, logrando un mayor control de los recursos informáticos de la empresa.


---

## 2.0 Historia y contexto de la empresa – Historia – Misión.
Historia y contexto.
Logística y Minería S.A. es una empresa de transporte de carga con más de 20 años de trayectoria. Comenzó como un emprendimiento familiar y, con el paso del tiempo, fue incorporando personal externo a medida que crecía. Hoy se compone de distintas áreas: sistemas, compras, mantenimiento, administración, ventas y logística.
La expansión de la empresa trajo aparejados problemas de comunicación interna y dificultades en la gestión de incidencias técnicas, lo que motivó la búsqueda de soluciones tecnológicas más formales.
Historia de la empresa.
Desde sus orígenes, la empresa se dedicó al transporte de carga para el sector minero e industrial. Con el crecimiento de la demanda, amplió su estructura organizativa y diversificar los servicios ofrecidos. La experiencia adquirida en dos décadas la posicionó como un actor confiable dentro del rubro.
Misión
Logística y Minería S.A. Tiene como misión ofrecer soluciones integrales y confiables de transporte de carga para el sector minero e industrial, asegurando eficiencia, seguridad y calidad en cada servicio. La empresa busca optimizar sus procesos internos mediante la innovación tecnológica, la estandarización de procedimientos y una comunicación efectiva entre áreas. A través de la mejora continua y la incorporación de herramientas que fortalezcan la gestión operativa, Logística y Minería S.A. trabaja para consolidarse como un referente del sector, promoviendo un crecimiento sostenible y una atención ágil y transparente hacia sus clientes.


Visión.
Logística y Minería S.A. aspira a consolidarse como la empresa líder en transporte de carga para el sector minero e industrial, destacándose por la confiabilidad de sus servicios, la innovación en la gestión tecnológica y la eficiencia en la comunicación interna, impulsando un crecimiento sostenible y aportando mayor valor a sus clientes.
Objetivos.
●	Optimizar la gestión de incidencias técnicas mediante la implementación de un sistema centralizado que garantice trazabilidad y eficiencia.
●	Mejorar la comunicación entre las diferentes áreas, evitando demoras y desorden en los procesos.
●	Estandarizar los procedimientos de soporte técnico, reemplazando prácticas informales por métodos formales y documentados.
●	Incrementar la eficiencia operativa a través de un control más preciso de los recursos tecnológicos e inventario.
●	Impulsar la innovación tecnológica como motor de crecimiento y competitividad en el sector.


Actualmente la empresa cuenta con las siguientes áreas:
●	Área de sistemas 
●	Área de compras
●	Área de mantenimiento
●	Área de administración
●	Área de ventas
●	Área de logística


---

## 3.0 Planeamiento del relevamiento – Entrevistas – Observaciones directas
Planeamiento del relevamiento.
Para obtener información precisa sobre la situación actual, se planificó un relevamiento que incluyó entrevistas a distintos niveles de la organización (mandos altos, medios y operativos) y observación directa de los procesos cotidianos en el área de sistemas. El objetivo fue identificar falencias, comprender los canales de comunicación y recolectar datos para el modelado de procesos y la propuesta de mejora.
Entrevistas.
Se entrevistó a representantes de mandos altos, medios y operativos, con el fin de obtener una visión completa de la problemática.
Para comprender a fondo el proceso actual de gestión de incidencias que utiliza la empresa realizamos el siguiente cuestionario:
Mandos altos.
¿Cómo gestionan actualmente los problemas técnicos que surgen en la empresa?
¿Cuál consideran que es la principal dificultad de este método?
¿Qué impacto creen que tiene esta situación en la empresa?
Respuestas.
Hoy en día no tenemos un sistema formal. Cada sector se comunica con el área de sistemas como puede: a veces por teléfono, otras por WhatsApp, incluso personalmente. Luego, el área de sistemas lleva un registro en una planilla.
Que no tenemos trazabilidad. Muchas veces no sabemos cuánto tarda en resolverse un problema ni en qué etapa está. Además, cada empleado usa un canal distinto y eso genera desorden.
Perdemos tiempo y eficiencia. Además, cuando dependemos de un especialista externo, la comunicación se vuelve aún más lenta porque pasa por correos y no queda bien documentada.
Mandos medios(Jefe de sistemas).
¿Cómo reciben actualmente los pedidos de soporte técnico?
¿Qué hacen ustedes cuando reciben un pedido?
Respuestas.
Los pedidos llegan por múltiples canales: algunos empleados nos escriben por WhatsApp, otros mandan un correo, a veces vienen directamente a la oficina a comentarlo, e incluso en ocasiones dejan una nota. No hay un único canal, lo cual nos obliga a estar atentos a diferentes medios al mismo tiempo.
Lo primero que hacemos es registrar el incidente en una planilla manual que tenemos en el área. Después evaluamos la prioridad del problema: si es algo que podemos resolver internamente, lo atendemos lo antes posible. Si no contamos con los conocimientos o herramientas necesarias, lo derivamos a un especialista externo. Una vez que está resuelto, volvemos a registrar en la planilla cómo se solucionó y avisamos al área que lo reportó, generalmente por el mismo canal en el que nos contactaron.
Mandos Operativos (ej: Empleados que usan la PC y el software a diario)
Cuando tenés un problema con tu computadora o con el software, ¿qué hacés?
¿Te queda algún comprobante o registro de que reportaste el problema?
Si el problema se deriva a un especialista externo, ¿cómo te enteras?
Respuestas.
Generalmente le mandó un mensaje por WhatsApp al de sistemas, o si lo cruzo en la oficina se lo digo directamente. Si estoy apurado porque necesito seguir trabajando, trato de que la comunicación sea lo más rápida posible.
No, salvo el chat en el celular o el correo si lo mandé por ahí. Pero después no tengo forma de ver en qué estado está, ni cuándo lo van a resolver.
Me avisan después de que ya se resolvió, pero no sé bien qué hicieron ni cómo lo arreglaron.
Observaciones directas.
Durante la observación de los procesos se identificó que los reclamos se realizan a través de múltiples canales informales como WhatsApp, correo electrónico, notas escritas o comunicación verbal. El área de sistemas utiliza una planilla manual para registrar los casos, sin un procedimiento estandarizado. Esto genera falta de trazabilidad, dificultad para hacer seguimiento y ausencia de estadísticas que permitan medir tiempos de resolución o frecuencia de incidencias.


---

## 4.0 Identificación de stakeholders
A continuación se identifican las partes interesadas relevantes para el Sistema de Gestión de Solicitudes y Mesa de Ayuda Operativa adaptado al sector logístico. Para cada una se describe su rol y se justifica por qué resulta clave para el proyecto.
Choferes y Operarios de Depósito (Solicitantes).
Son el personal operativo de primera línea que utiliza activamente los recursos físicos de la empresa. Su rol consiste en reportar incidentes técnicos de hardware o software (computadoras de abordo, escáneres portátiles PDA, terminales de stock o impresoras térmicas de etiquetas) que impidan el normal desarrollo de sus tareas de picking, despacho o distribución.
Por qué es clave: Son los usuarios finales principales y los generadores de la carga de trabajo del sistema. Al depender de la rapidez de sus tareas (tiempos de carga y descarga de camiones), sus necesidades determinan los requisitos de usabilidad más críticos: el formulario de tickets debe ser ultra rápido, mobile-friendly y contar con autocompletado de perfil y adjunto ágil de evidencias fotográficas para no retrasar la cadena de suministro.
Técnico de Soporte IT Interno
Es el agente informático propio de la organización encargado de la recepción, diagnóstico, comentarios de seguimiento y resolución de los incidentes reportados por el personal. Documenta los tiempos exactos trabajados y decide cuándo un problema supera su capacidad y debe escalarse.
Por qué es clave: Representa el núcleo operativo de la mesa de ayuda. El sistema debe adaptarse perfectamente a su flujo de trabajo, proveyendo un tablero gráfico en tiempo real y alertas de vencimiento. Si la interfaz para documentar tareas o comunicarse con el empleado no es eficiente, los tiempos de resolución se extienden, afectando directamente la productividad general de la empresa.
Jefe de Logística y Operaciones.
Es el directivo responsable de garantizar que los camiones salgan a tiempo y que los centros de distribución puedan operar sin cuellos de botella. Monitorea los indicadores de rendimiento (SLA) del equipo de sistemas y evalúa el impacto de los incidentes.
Por qué es clave: Es el comitente principal que define las reglas de negocio, los tiempos máximos permitidos para resolver fallas (SLA) y las prioridades de atención. Su rol es crítico porque utiliza el software para la toma de decisiones estratégicas, basándose en las estadísticas de rendimiento exportables y en la matriz de priorización automática para que el negocio no se detenga por fallas técnicas.
Proveedor Externo de Hardware y Redes Logísticas (Especialista Externo)
Es el servicio técnico tercerizado contratado por la empresa para dar soporte a infraestructura crítica, como el mantenimiento de los servidores de stock (WMS/ERP), la red Wi-Fi industrial del depósito o las garantías de las colectoras de datos.
Por qué es clave: Su intervención es fundamental en incidentes complejos de infraestructura. Al ser un actor externo, sus demoras no deben penalizar al equipo interno; por lo tanto, su asignación activa el requerimiento de pausa automática de SLA . El sistema debe controlar estrictamente sus accesos y obligar a que sus soluciones sean validadas antes del cierre.



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
