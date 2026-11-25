# [PE 90.1] Logisticfy

**Marta Elcacho Pola · MF0490**

Logisticfy es una empresa ficticia que gestiona envíos para otras empresas. En este proyecto propongo unas normas de seguridad, un programa de concienciación para sus trabajadores y una guía para reconocer mensajes sospechosos.

## 1.1. Análisis del contexto y necesidades de protección

> Consulta la documentación corporativa [PE 90.1] Logisticfy y analiza los elementos del negocio que deben tenerse en cuenta para establecer su marco de protección.
>
> 1. Identifica los procesos, funciones y activos más relevantes para fundamentar tu propuesta de ciberseguridad.
> 2. Explica brevemente qué necesidades de protección presentan y por qué son importantes para la actividad de Logisticfy.
> 3. Relaciona los activos seleccionados con los procesos o funciones a los que dan soporte, utilizando los identificadores del inventario corporativo.
>
> Documenta el análisis en el apartado 1.1. Análisis del contexto y necesidades de protección de [PE 90.1] Plantilla .
>
> Consideraciones:
>
> - No es necesario analizar todos los activos de Logisticfy.
> - No se requiere realizar una evaluación de riesgos, asignar criticidades ni elaborar un nuevo inventario.
> - Diferencia los hechos documentados de los supuestos o propuestas. La ausencia de información sobre un control no demuestra que exista un incumplimiento.

**Respuesta**

Los datos de los envíos deben ser correctos y estar disponibles para poder trabajar. También hay que evitar que personas sin permiso vean información de clientes, destinatarios o facturas.

| ID del activo | Activo | Necesidad de protección | Proceso o función relacionada |
| --- | --- | --- | --- |
| SW-01 | Plataforma web y backoffice | Evitar accesos sin permiso y mantener el servicio disponible. | Crear, gestionar y consultar envíos. |
| SW-02 | API de integración con transportistas | Proteger los datos que se intercambian. | Asignar transportistas y actualizar estados. |
| EXT-01 | Integraciones con transportistas externos | Prever qué hacer si falla un proveedor. | Transporte y seguimiento de envíos. |
| DAT-01 | Base de datos de clientes, envíos y facturación | Evitar pérdidas, cambios indebidos y accesos no autorizados. | Envíos, consultas y facturación. |
| INF-01 | Servidor Ubuntu de aplicación | Mantenerlo actualizado y protegido. | Funcionamiento de la plataforma. |
| IAM-01 | Identidades y mecanismos de acceso | Dar a cada persona solo los permisos necesarios. | Acceso a los sistemas. |
| HW-01 | Equipos Windows del personal | Evitar infecciones y accesos a sesiones abiertas. | Trabajo diario del personal. |
| COM-01 | Correo corporativo | Evitar engaños y envíos a destinatarios equivocados. | Comunicación interna y externa. |
| BKP-01 | Copias de seguridad | Poder recuperar la información que contienen. | Recuperación de datos y servicios. |
| SW-03 | Repositorios de código fuente | Proteger el código y no publicar contraseñas. | Desarrollo y mantenimiento. |

## 1.2. Principios generales de ciberseguridad

> A partir del análisis del contexto empresarial, define los principios generales de ciberseguridad que deberían orientar las decisiones de seguridad de Logisticfy.
>
> 1. Establece los principios que consideres necesarios para proteger la información, los sistemas y las actividades de la organización.
> 2. Explica brevemente el propósito de cada principio y cómo se aplicaría en Logisticfy.
> 3. Justifica su elección relacionándolo con los procesos, funciones o activos relevantes de la empresa.
> 4. Propón cómo Dirección conocería y respaldaría los principios, cómo quedaría constancia de ese respaldo y cómo se comunicarían al personal.
>
> Documenta tu propuesta en el apartado Principios generales de ciberseguridad de [PE 90.1] Plantilla .
>
> Consideraciones:
>
> - Los principios deben ser claros, coherentes entre sí y adaptados a Logisticfy.
> - No se establece un número obligatorio de principios; prioriza su pertinencia y justificación.
> - Diferencia los principios generales de las normas operativas, que desarrollarás en el apartado siguiente.
> - El respaldo de Dirección es una propuesta: no debes presentarlo como una aprobación que ya se ha producido.

**Respuesta**

| ID | Principio propuesto | Aplicación en Logisticfy | Justificación |
| --- | --- | --- | --- |
| P-01 | Confidencialidad | Que solo accedan a los datos las personas autorizadas. | Se manejan datos de clientes, destinatarios y facturas en DAT-01. |
| P-02 | Integridad | Evitar cambios indebidos y comprobar los datos importantes. | Una dirección incorrecta puede provocar un error en el envío. |
| P-03 | Disponibilidad y recuperación | Mantener los servicios disponibles y poder recuperarlos si fallan. | La actividad depende de la plataforma, del servidor y de los transportistas. BKP-01 ayudaría a recuperar datos. |
| P-04 | Mínimo privilegio | Dar solo los permisos necesarios para cada puesto. | No todos necesitan el mismo acceso mediante IAM-01, incluida la persona en prácticas. |
| P-05 | Prevención y responsabilidad compartida | Trabajar con cuidado y avisar de posibles problemas. | Cualquier trabajador puede recibir un correo sospechoso o cometer un error. |
| P-06 | Mejora continua y proporcionalidad | Revisar las medidas y adaptarlas a la empresa. | Una plantilla de 20 personas necesita medidas sencillas que pueda mantener. |

### Conocimiento y respaldo de Dirección

Presentaría los principios al CEO y al responsable de operaciones en una reunión con IT. Explicaría para qué sirven y cómo ayudan al negocio. Si los respaldan, lo recogería en un acta con fecha, versión y responsables. Después se comunicarían al personal por correo y en una reunión breve.

## 1.3. Normativa de protección del puesto de trabajo

> A partir de los principios definidos, desarrolla una normativa de ciberseguridad que establezca las reglas de protección que deberán seguir los trabajadores de Logisticfy en sus actividades habituales.
>
> 1. Define el ámbito de aplicación de la normativa e identifica a qué trabajadores, departamentos o funciones está dirigida.
> 2. Establece normas de seguridad concretas y aplicables, teniendo en cuenta los siguientes ámbitos:
>    - Identidades y accesos: cuentas, autenticación y permisos.
>    - Equipos y software: utilización de dispositivos y aplicaciones corporativas.
>    - Protección de la información: acceso, tratamiento y almacenamiento.
>    - Comunicaciones: uso de canales corporativos e intercambio de información.
>    - Seguridad física: protección de espacios y recursos de trabajo.
>    - Comunicación de anomalías: notificación interna de posibles problemas de seguridad.
> 3. Para cada norma, especifica:
>    - Qué conducta debe seguirse.
>    - A quién se aplica.
>    - Cómo debe aplicarse y cómo podría comprobarse su cumplimiento.
> 4. Establece las responsabilidades generales de aplicación y cómo se gestionarían las excepciones que requieran autorización, cuando corresponda.
> 5. Define brevemente cómo se comunicaría la normativa a los trabajadores y cómo se revisaría o actualizaría.
>
> Documenta la propuesta en el apartado Normativa de protección del puesto de trabajo de [PE 90.1] Plantilla .
>
> Consideraciones:
>
> - Las normas deben adaptarse a los procesos y funciones descritos en [PE 90.1] Logisticfy .
> - Mantén la coherencia con los principios definidos en el apartado 1.2.
> - Revisa todos los ámbitos de protección indicados y desarrolla las normas pertinentes. No es necesario establecer una norma por cada ámbito ni elaborar un manual exhaustivo.
> - Formula reglas que los trabajadores puedan comprender y aplicar, evitando recomendaciones demasiado genéricas.
> - No presentes las medidas propuestas como controles ya implantados en Logisticfy.
>
> La comprobación efectiva del cumplimiento de la normativa se abordará posteriormente en AEA2.

**Respuesta**

**Ámbito de aplicación:** todo el personal de Dirección, Operaciones, Atención al Cliente, IT, Comercial y Administración, incluida la persona en prácticas.

**Responsabilidades generales:** Dirección respaldaría las normas e IT coordinaría la parte técnica. Los responsables de cada área comunicarían las necesidades de acceso. Todos los trabajadores deberían cumplir las normas y avisar de los problemas. La persona en prácticas tendría supervisión de IT.

| ID | Norma propuesta | Destinatarios | Aplicación y posible verificación | Excepciones, si procede |
| --- | --- | --- | --- | --- |
| N-01 | Usar cuentas individuales, contraseñas únicas de al menos 15 caracteres y doble factor (MFA) cuando el servicio lo permita. No compartir contraseñas ni códigos. | Todo el personal. | Guardarlas en un gestor autorizado. IT podría revisar la configuración de contraseñas y MFA sin pedir las contraseñas. | Si no hay MFA, IT propondría una protección alternativa para autorizarla. |
| N-02 | Pedir los permisos al responsable y usar solo los necesarios para el puesto. | Todo el personal; IT gestionaría los accesos. | Registrar las autorizaciones y revisar los permisos al cambiar de puesto o salir de la empresa. Las prácticas tendrían acceso limitado. | Los permisos temporales tendrían aprobación y fecha de retirada. |
| N-03 | Bloquear la sesión al levantarse y no desactivar las protecciones. | Todo el personal. | Usar `Windows + L`. IT podría revisar el bloqueo automático y el antivirus. | Si una protección da problemas, avisar a IT. |
| N-04 | Instalar solo programas autorizados y aplicar las actualizaciones indicadas por IT. | Todo el personal. | Pedir los programas a IT, que podría revisar las aplicaciones y sus versiones. | IT registraría el motivo y una nueva fecha si se aplaza una actualización. |
| N-05 | Guardar los archivos en ubicaciones corporativas autorizadas, sin usar correos, nubes o USB personales. | Todo el personal. | IT definiría las ubicaciones y qué datos se copiarían. Podría revisar los permisos y probar la recuperación. | Una copia excepcional necesitaría autorización, protección y fecha de eliminación. |
| N-06 | Revisar el destinatario y compartir solo los datos necesarios por canales corporativos autorizados. | Operaciones, Atención al Cliente, Comercial y Administración. | Comprobar el cliente y los adjuntos antes de enviar. Confirmar los cambios importantes con un contacto conocido. Se podrían revisar ejemplos de comunicaciones. | IT tendría que validar cualquier canal alternativo. |
| N-07 | No abrir enlaces o adjuntos sospechosos ni dar contraseñas por un mensaje. | Todo el personal. | Verificar las peticiones urgentes por otra vía conocida. Se podría comprobar con ejercicios y avisos recibidos. | La urgencia no elimina la comprobación. |
| N-08 | Recoger documentos, proteger los equipos y acompañar a las visitas. | Todo el personal. | Guardar los documentos y recoger las impresiones. Se podrían revisar las zonas compartidas. | Los accesos fuera de horario necesitarían autorización. |
| N-09 | Avisar cuanto antes a IT de mensajes sospechosos, pérdidas o errores al compartir datos. | Todo el personal. | Usar el contacto interno de IT; si el correo falla, llamar o avisar en persona. Explicar qué pasó y cuándo, sin borrar pruebas. IT podría revisar los avisos registrados. | Si IT no está disponible, avisar al responsable del área. |
| N-10 | No guardar contraseñas en el código y pedir revisión antes de incorporar cambios. | Desarrollador, administrador de sistemas y persona en prácticas cuando participe. | Guardar los secretos en el sistema autorizado por IT. Se podrían revisar los permisos y las revisiones del repositorio. | Un cambio urgente necesitaría autorización y una revisión posterior registrada. |

Las normas de accesos y datos se relacionan con P-01 y P-04; las comprobaciones, con P-02; las actualizaciones y copias, con P-03; y los avisos y revisiones, con P-05 y P-06.

### Comunicación y revisión de la normativa

La enviaría por correo corporativo y la explicaría en una sesión breve, dejando constancia de su recepción. También se entregaría a las nuevas incorporaciones. IT y los responsables la revisarían cada seis meses o después de un incidente o cambio importante.

Las excepciones se pedirían por escrito, con motivo, duración y protección alternativa. IT las valoraría y Dirección las autorizaría con el responsable del área. Quedarían registradas y se retirarían al terminar el plazo.

## Programa de concienciación

> Diseña un programa de concienciación en ciberseguridad dirigido al personal de Logisticfy, tomando como referencia las necesidades de protección y la normativa establecidas en el Bloque 01.
>
> El programa debe proponer acciones viables para que los trabajadores conozcan los riesgos relacionados con sus funciones y adopten buenas prácticas de seguridad.

### 2.1. Objetivos y destinatarios

> 1. Define los objetivos de concienciación que consideres prioritarios para Logisticfy, orientados a comportamientos o conocimientos que deban adquirir o reforzar los trabajadores.
> 2. Identifica los departamentos o perfiles profesionales a los que se dirige cada objetivo.
> 3. Justifica brevemente la selección en función de las actividades y responsabilidades de sus destinatarios.
>
> Ten en cuenta las diferencias entre las funciones del personal, incluida la persona en prácticas.

**Respuesta**

| ID | Objetivo de concienciación | Destinatarios | Justificación |
| --- | --- | --- | --- |
| O-01 | Reconocer mensajes sospechosos, comprobarlos y avisar a IT. | Todo el personal, con ejemplos de envíos para Operaciones y Atención al Cliente, y de facturas para Administración. | El correo se utiliza a diario y puede servir para engañar al personal. N-07 y N-09. |
| O-02 | Usar correctamente las cuentas, el MFA y los permisos. | Todo el personal; ejemplos de accesos y código para IT y la persona en prácticas. | Cada puesto necesita permisos distintos y las prácticas requieren supervisión. N-01, N-02 y N-10. |
| O-03 | Compartir los datos necesarios con la persona correcta y por un canal autorizado. | Operaciones, Atención al Cliente, Comercial y Administración. | Estos departamentos intercambian datos de clientes, envíos y facturas. N-05 y N-06. |
| O-04 | Bloquear la sesión, cuidar el puesto y pedir a IT las instalaciones y actualizaciones. | Todo el personal, incluida Dirección y la persona en prácticas. | Todos utilizan equipos y espacios de trabajo. N-03, N-04 y N-08. |

### 2.2. Plan de acciones de concienciación

> Establece las acciones necesarias para alcanzar los objetivos definidos.
>
> Para cada acción, especifica:
>
> 1. Objetivo: qué se pretende conseguir y con qué objetivo del programa se relaciona.
> 2. Destinatarios: trabajadores o departamentos a los que va dirigida.
> 3. Acción y canal: actividad propuesta y medio utilizado para desarrollarla.
> 4. Temporalización: duración o momento previsto para realizarla.
> 5. Responsable: función encargada de organizarla o llevarla a cabo.
> 6. Materiales: recursos necesarios para su ejecución.
>
> Las acciones deben ser coherentes con la normativa definida en el Bloque 01 y ajustarse a los recursos y características de Logisticfy.
>
> No es necesario desarrollar todos los materiales del programa. En el Bloque 03 elaborarás a menos uno de ellos.

**Respuesta**

Haría el programa durante un mes, en grupos pequeños para no dejar el servicio sin atender. Quien no pueda asistir tendría otra sesión.

| ID | Objetivo | Destinatarios | Acción y canal | Temporalización | Responsable | Materiales |
| --- | --- | --- | --- | --- | --- | --- |
| A-01 | O-01: reconocer y comunicar mensajes sospechosos. | Todo el personal. | Taller presencial o por videollamada con guía, dos casos y tres preguntas. Envío de la guía por correo. | Semana 1: 20 minutos. Recordatorio al mes. | Responsable IT. | M-01: guía del apartado 3.1, terminada. |
| A-02 | O-02: usar bien las cuentas y los permisos. | Todo el personal; parte específica para IT y prácticas. | Demostración presencial o por videollamada con una cuenta ficticia. | Semana 2: 15 minutos y 10 más para IT y prácticas. | Responsable IT y administrador de sistemas. | M-02: ficha de accesos y caso de código, por preparar. |
| A-03 | O-03: compartir y guardar datos con cuidado. | Operaciones, Atención al Cliente, Comercial y Administración. | Ejercicio con un envío de datos ficticios en una reunión de equipo. | Semana 3: 20 minutos. | Responsable IT y responsables de las áreas. | M-03: ejemplos de destinatarios, archivos y ubicaciones, por preparar. |
| A-04 | O-04: proteger el puesto de trabajo. | Todo el personal. | Demostración del bloqueo de sesión y tres situaciones sobre visitas, programas y actualizaciones. Sesión presencial. | Semana 4: 10 minutos. También al incorporarse a la empresa. | Administrador de sistemas. | M-04: lista de comprobación del puesto, por preparar. |

### 2.3. Seguimiento y evaluación del programa

> Define cómo se comprobaría si las acciones de concienciación han conseguido los objetivos previstos.
>
> 1. Establece indicadores que permitan valorar los resultados.
> 2. Identifica qué evidencias permitirían comprobarlos.
> 3. Indica cuándo se revisarían los resultados y cómo se utilizarían para mejorar el programa.
>
> Los mecanismos de seguimiento deben ser proporcionales a las acciones propuestas.
>
> No debes presentar resultados de concienciación como si las actividades ya se hubieran realizado. Se solicita el diseño del programa, no su ejecución.

**Respuesta**

| Objetivo o acción | Indicador | Evidencia prevista | Momento de revisión |
| --- | --- | --- | --- |
| A-01 a A-04 | Porcentaje que completa cada acción. Objetivo: 100 %, contando las sesiones de recuperación. | Registro de asistencia. | Tras cada sesión y al terminar el mes. |
| O-01 / A-01 | Porcentaje que detecta el engaño y explica cómo comprobarlo y avisar. Objetivo: al menos 80 %. | Respuestas individuales a los casos de M-01, antes de mostrar las soluciones. | Al terminar y al mes con otro caso. |
| O-02 / A-02 | Porcentaje que responde bien a dos situaciones sobre permisos y contraseñas. Objetivo: al menos 80 %. | Respuestas al ejercicio y al caso de código de IT y prácticas. | Al terminar la sesión. |
| O-03 / A-03 | Porcentaje que elige bien destinatario, datos y canal. Objetivo: al menos 80 %. | Ejercicio corregido con datos ficticios. | Al terminar y al mes con otro ejemplo. |
| O-04 / A-04 | Porcentaje que bloquea la sesión y resuelve las situaciones del puesto. Objetivo: al menos 80 %. | Lista de comprobación y respuestas breves. | Durante la sesión y al mes con unas preguntas. |

**Revisión y mejora:** IT revisaría los resultados con los responsables al terminar el programa y un mes después. Si un objetivo no llega al 80 %, se repasaría con otro ejemplo. Estos porcentajes son metas, no resultados obtenidos.

## Desarrollo del material de concienciación

> Selecciona una de las acciones definidas en el programa de concienciación del Bloque 02 y desarrolla al menos un material completo y utilizable para llevarla a cabo.
>
> El material debe estar adaptado a sus destinatarios y permitir transmitir conocimientos o promover conductas de ciberseguridad aplicables al entorno laboral de Logisticfy.

### 3.1. Material desarrollado

> **3.1. Selección y desarrollo del material**
>
> 1. Selecciona una acción del programa de concienciación y determina qué material necesitas para realizarla.
> 2. Elige el formato más adecuado según el objetivo, los destinatarios y el canal previsto. Puedes utilizar, entre otros, una guía breve, una infografía, una comunicación interna, una presentación, un cuestionario o un recurso audiovisual.
> 3. Desarrolla el contenido completo del material, asegurando que:
>    - La información sea técnicamente correcta y coherente con la normativa propuesta.
>    - El lenguaje y la presentación sean adecuados para sus destinatarios.
>    - El contenido sea claro, legible y accesible en el formato elegido.
>    - El material permita desarrollar la acción de concienciación prevista.
>
> El formato es libre. No es necesario utilizar herramientas de diseño gráfico ni producir varios recursos.

**Respuesta**

- **ID del material:** M-01.
- **Título:** Antes de hacer clic: mensajes sospechosos en Logisticfy.
- **Formato:** guía breve con ejercicios.

### Contenido del material

#### M-01 · Antes de hacer clic

**Guía para el personal de Logisticfy**

El phishing es un engaño que intenta conseguir tus datos o contraseñas, o hacer que abras un archivo peligroso. Puede parecer un mensaje de un cliente, transportista o compañero.

**1. Revisa el mensaje**

- Desconfía si te meten prisa, amenazan con bloquear algo o piden contraseñas y códigos MFA.
- Comprueba la dirección completa del remitente. El nombre puede ser falso y una cuenta conocida también puede estar comprometida.
- Que el mensaje esté bien escrito o la página tenga HTTPS no demuestra que sea seguro.

**2. Comprueba por otra vía**

- Entra en el servicio desde su dirección habitual, sin usar el enlace del mensaje.
- Confirma las peticiones extrañas con el contacto que ya conoces. No uses un teléfono que solo aparezca en el mensaje sospechoso.
- Si tienes dudas, no abras el archivo ni des datos. Pregunta a IT.

**3. Avisa a IT**

Usa el contacto corporativo conocido de IT. Si el correo no funciona, llama o avisa en persona. Si IT no está disponible, avisa a tu responsable.

Explica qué recibiste, cuándo y si abriste algo o introdujiste datos. Conserva el mensaje y sigue las indicaciones de IT para enviárselo. No lo reenvíes a los compañeros ni borres las pruebas.

**Si ya has hecho clic:** deja de usar la página y avisa cuanto antes a IT. Si has dado tu contraseña, cámbiala desde el servicio auténtico y un equipo fiable. Explica también si aprobaste un aviso MFA. Cambiar la contraseña no sustituye el aviso a IT, porque podría ser necesario cerrar sesiones u otras medidas.

#### Casos para practicar

Los mensajes y las direcciones de los ejemplos son ficticios. No hay que abrir enlaces.

**Caso 1: envío bloqueado**

> De: Soporte Transportista `<avisos@transportista-verificacion.example>`  
> Asunto: URGENTE: expedición bloqueada  
> Tu envío no saldrá hoy si no verificas tu cuenta. Entra en `https://transportista-verificacion.example/acceso` e introduce tu contraseña y el código de verificación.

**Pregunta:** ¿Qué señales te hacen desconfiar y cómo comprobarías el aviso?

**Caso 2: factura inesperada**

> De: Proveedor habitual  
> Asunto: Factura corregida  
> Hemos cambiado los datos de facturación. Abre el adjunto y habilita las macros para ver la factura. Necesitamos que lo tramites hoy.

**Pregunta:** ¿Qué harías antes de abrir el archivo y a quién avisarías?

#### Preguntas rápidas

1. ¿Ver el nombre de un transportista conocido demuestra que el mensaje es auténtico?
2. ¿Debes dar un código MFA si un mensaje dice que es de soporte?
3. Si has escrito tu contraseña en una página sospechosa, ¿basta con cerrar la pestaña?

#### Soluciones

- **Caso 1:** desconfiaría de la urgencia y de que pidan la contraseña y el código. Consultaría el envío desde el acceso habitual, confirmaría con el contacto conocido y avisaría a IT.
- **Caso 2:** no abriría el adjunto ni habilitaría macros. Confirmaría la petición con el contacto habitual del proveedor y avisaría a IT.
- **Pregunta 1:** no. El nombre puede ser falso o la cuenta estar comprometida.
- **Pregunta 2:** no. No se comparten códigos ni se aprueban accesos que no hemos iniciado.
- **Pregunta 3:** no. Hay que avisar a IT y cambiar la contraseña desde el servicio auténtico y un equipo fiable.

**Recuerda: para, comprueba y avisa.**

### 3.2. Vinculación con el programa

> Documenta en [PE 90.1] Plantilla :
>
> 1. El título y la identificación del material.
> 2. El objetivo y la acción del programa con los que se relaciona.
> 3. Los destinatarios y el canal de comunicación.
> 4. Cómo se utilizaría el material durante la acción.
> 5. Su ubicación dentro de la entrega.
>
> Incluye el material terminado en el propio documento si es textual o adjunta el archivo correspondiente si utilizas otro formato.
>
> Consideraciones:
>
> - El material debe estar desarrollado, no únicamente descrito. Una propuesta, un esquema o una ficha de planificación no sustituyen al recurso final.
> - No se requiere ejecutar la acción de concienciación con trabajadores reales.
> - Utiliza únicamente información ficticia de Logisticfy y recursos que puedas compartir legítimamente, identificando las fuentes externas cuando corresponda.
> - El material debe poder abrirse y consultarse sin depender de archivos o permisos que no se hayan facilitado.

**Respuesta**

- **Título e identificación:** M-01, «Antes de hacer clic: mensajes sospechosos en Logisticfy».
- **Objetivo relacionado:** O-01.
- **Acción relacionada:** A-01.
- **Destinatarios:** todo el personal, con ejemplos de envíos y facturación.
- **Canal:** correo corporativo y taller presencial o por videollamada.
- **Uso previsto:** 5 minutos de lectura, 8 para los casos, 4 para las preguntas y 3 para comentar las soluciones. IT recogería las respuestas antes de enseñar las soluciones.
- **Ubicación:** el material completo se adjunta en un PDF independiente.
- **Material:** [Consultar la guía «Antes de hacer clic»](Logisticfy_M01_Antes_de_hacer_clic.pdf).

## Fuentes, supuestos y autoría

### 4.1. Fuentes y recursos utilizados

> Fuente o recurso · Referencia · Uso realizado

| Fuente o recurso | Referencia | Uso realizado |
| --- | --- | --- |
| [PE 90.1] Logisticfy | Documentación corporativa. | Datos de la empresa, procesos y activos. |
| [PE 90.1] Breafing y Actividades | Encargo y actividades. | Objetivos y requisitos. |
| [PE 90.1] Plantilla y Rúbrica de correción | Plantilla y criterios de evaluación. | Organización y revisión del trabajo. |

### 4.2. Supuestos y limitaciones

> [Indica únicamente los supuestos o datos pendientes que hayan condicionado tu propuesta. Diferencia lo conocido de lo propuesto. Si no existen, elimina este apartado.]

No conozco la configuración de los sistemas, los permisos ni el alcance de las copias. IT tendría que concretar esos puntos y el contacto para comunicar problemas. El calendario y las responsabilidades son una propuesta. No se han realizado pruebas ni sesiones con trabajadores.

### 4.3. Autoría y revisiones

> [Identifica brevemente tus decisiones propias, las revisiones relevantes y los apoyos utilizados, incluido el uso relevante de IA si corresponde.]


La propuesta se centra en proteger los datos, limitar los accesos y reconocer mensajes sospechosos. Las normas, las actividades y la guía se relacionan con estas necesidades.

He utilizado ChatGPT como apoyo para organizar las ideas y redactar la propuesta.
