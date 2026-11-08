# Capitulo VI: Product Verification & Validation
## 6.1. Testing Suites & Validation
### 6.1.1. Core Entities Unit Tests.

Las pruebas unitarias de las core entities son fundamentales en el desarrollo de software, ya que permiten verificar su correcto funcionamiento, detectar errores de manera temprana y facilitar el mantenimiento del código.

**Alert Test**

![Alert Test](assets/img/AlertTest.png)

**Face Verification Test**

![Face Verification Test](assets/img/FaceVerificationTest.png)

**Employee Test**

![Employee Test](assets/img/EmployeeTest.png)

**Bus Unit Test**

![Bus Unit Test](assets/img/BusUnitTest.png)

**Passenger Count Test**

![Passenger Count Test](assets/img/PassengeCountTest.png)

**Sensor Test**

![Sensot Test](assets/img/SensorTest.png)

**Shift Test**

![Shift Test](assets/img/ShiftTest.png)

**Driver Profile Test**

![Driver Profile Test](assets/img/DriverProfileTest.png)

### 6.1.2. Core Integration Tests.

Las Core Integration Tests son esenciales para verificar que los controladores funcionen correctamente junto con otros componentes del sistema, como los servicios y las bases de datos. Además, permiten evaluar escenarios de error para comprobar que el sistema gestione adecuadamente situaciones inesperadas y devuelva los códigos de estado correspondientes. Esto contribuye a mejorar la experiencia del usuario, facilitar la detección de errores y garantizar un software más confiable y de calidad.

**Employees Api Integration Test**

![Employees Api Integration Test](assets/img/EmployeesApiIntegrationTest.png)

**Bus Units Api Integration Test**

![Bus Units Api Integration Test](assets/img/BusUnitsApiIntegrationTest.png)

**Shifts Api Integration Test**

![Shifts Api Integration Test](assets/img/ShiftsApiIntegrationTest.png)

**Alerts Api Integration Test**

![Alerts Api Integration Test](assets/img/AlertsApiIntegrationTest.png)

### 6.1.3. Core Behavior-Driven Development

El Behavior-Driven Development (BDD) permite validar el comportamiento del sistema a partir de escenarios que representan situaciones reales de uso. Estas pruebas ayudan a comprobar que las funcionalidades implementadas respondan correctamente a las necesidades definidas en los requerimientos, utilizando criterios claros y comprensibles para el equipo de desarrollo y los usuarios.

<center>

![features](assets/img/features.png)

</center>

**Identidad y autorización del conductor**

![BDD1](assets/img/BDD1.png)

**Inicio y cierre del servicio**

![BDD2](assets/img/BDD2.png)

**Alertas de emergencia**

![BDD3](assets/img/BDD3.png)

**Monitoreo de unidades y conteo de pasajeros**

![BDD4](assets/img/BDD4.png)

**Gestión de conoductores mediante Api**

![BDD5](assets/img/BDD5.png)

### 6.1.4. Core System Tests.

Las Core System Tests permiten evaluar el funcionamiento completo del sistema, verificando la interacción entre sus principales componentes y funcionalidades. Estas pruebas buscan comprobar que el producto cumpla con los requerimientos establecidos y que los flujos principales se ejecuten correctamente en escenarios similares a los de un entorno real.

#### Entorno y herramienta de prueba

Las pruebas se ejecutaron de punta a punta sobre el sistema desplegado (frontend, backend y base de datos), simulando las acciones de un usuario real desde el navegador.

| Elemento | Detalle |
|---|---|
| Herramienta | Selenium IDE (extensión de Microsoft Edge) |
| Navegador | Microsoft Edge |
| Frontend web | `https://avisum-frontend.vercel.app` |
| Landing page | `https://lading-page-six-psi.vercel.app/` |
| Backend | `https://avisum-backendv2.onrender.com` |
| Alcance | Aplicación web (frontend Angular y landing page). La aplicación móvil nativa queda fuera del alcance de estas pruebas |

**Precondiciones de ejecución**

- El backend se despierta antes de iniciar (abriendo su Swagger y esperando la respuesta), porque el plan gratuito de Render lo suspende tras 15 minutos de inactividad y la primera petición tarda entre 30 y 50 segundos.
- Se utiliza el código de empleado de prueba `EMP-001`.
- Cada prueba incluye pausas explícitas entre pasos, para dar tiempo a que responda el backend.

**Orden de ejecución:** ST-02, ST-04, ST-01, ST-03, ST-05, ST-06, ST-07, ST-09, ST-10, ST-08, ST-11 y ST-12. ST-07 genera una alerta real y ST-08 cierra el turno, por lo que se ejecutan en ese orden.

#### Criterio de selección

Cada prueba se deriva de una historia de usuario del Capítulo 3, usando sus escenarios de éxito y de fracaso (Given/When/Then), y recorre un flujo definido en los user flows y el prototipo del Capítulo 4. Las historias de tipo developer (endpoints) ya están cubiertas por las pruebas de integración de la sección 6.1.2.

#### Plan de pruebas

| ID | Historias | Escenario | Resultado esperado |
|---|---|---|---|
| ST-01 | US01, US14 | Login con código de conductor válido | El sistema valida el código y muestra la pantalla de acceso autorizado |
| ST-02 | US01 | Login con código inexistente | El sistema rechaza el acceso y permanece en la pantalla de verificación |
| ST-03 | US02, US15 | Verificación de identidad y arranque del servicio | Se abre el dashboard del conductor con la unidad asignada |
| ST-04 | US02 | Acceso al dashboard sin haberse validado | El sistema impide el acceso y redirige al login |
| ST-05 | US06, US07 | Dashboard del conductor en servicio | Se muestran distancia, tiempo, pasajeros y recaudación |
| ST-06 | US28 | Mapa en tiempo real | Se muestra el mapa con la posición de la unidad |
| ST-07 | US03, US04, US19 | Botón de pánico con servicio activo | Se muestra la confirmación de alerta enviada |
| ST-08 | US20 | Finalizar el servicio | Se muestra la confirmación de servicio finalizado |
| ST-09 | US04, US21 | Panel de administración | El panel carga y muestra unidades y alertas recientes |
| ST-10 | US16 | Historial de alertas del administrador | Se muestra el registro de alertas |
| ST-11 | US08, US09, US25, US29 | Contenido de la landing page | Las secciones informativas son visibles |
| ST-12 | US17 | Navegación entre secciones de la landing | Cada enlace del menú lleva a su sección |

#### Detalle de los casos de prueba

**ST-01 — Login con código válido** (US01, US14)

Se abre la pantalla de verificación de identidad (`/conductor/login`), se ingresa el código de empleado `EMP-001` y se pulsa "Verificar credenciales". Luego de una pausa para dar tiempo de respuesta al backend, se verifica que aparezca el título "Acceso Autorizado".

- **Resultado esperado:** el sistema valida el código y muestra la pantalla de acceso autorizado.
- **Resultado obtenido:** ✅ Pasó.
- **Observación:** la pantalla de acceso autorizado también muestra textos propios de una alerta ("Transmisión de emergencia activa", "Central notificada", "Audio remoto: grabando"). Conviene revisar si es el comportamiento previsto.

![ST-01 Login con código válido](assets/img/ST01.png)

**ST-02 — Código inválido** (US01)

Se ingresa un código inexistente (`xxxx000`) en la pantalla de verificación y se pulsa "Verificar credenciales". Luego de una pausa de 8 segundos, se verifica que la ruta siga siendo `/conductor/login`, es decir, que el sistema no avanzó.

- **Resultado esperado:** el sistema rechaza el acceso y permanece en la pantalla de verificación.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** la prueba valida que el sistema no avanza con un código falso. No distingue visualmente un mensaje de error, porque los tres avisos de la pantalla ("Código inválido", "Conductor no autorizado" y "Conflicto de vehículo") se ven igual antes y después del intento.

![ST-02 Código inválido](assets/img/ST02.png)

**ST-03 — Verificación e inicio de servicio** (US02, US15)

Se verifica la identidad con `EMP-001`, se espera la pantalla de acceso autorizado y se pulsa "Seguir". Luego de las pausas correspondientes, se verifica que cargue el dashboard del conductor, comprobando su encabezado "TRANSIT MONITOR v2.4".

- **Resultado esperado:** se abre el dashboard del conductor con la unidad asignada.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** la prueba confirma que se llega al dashboard. No verifica por sí sola que el turno quede registrado, ya que el tiempo total se mostraba en `00:00:00`.

![ST-03 Verificación e inicio de servicio](assets/img/ST03.png)

**ST-04 — Acceso sin validación** (US02)

Sin sesión iniciada, se abre directamente la ruta `/conductor/dashboard`. Luego de una pausa de 5 segundos, se verifica que el sistema haya redirigido al login (`/conductor/login`).

- **Resultado esperado:** el sistema impide el acceso y redirige al login.
- **Resultado obtenido:** ❌ Falló. La ruta se mantuvo en `/conductor/dashboard` y el dashboard cargó completo, sin pasar por la verificación.
- **Verificación adicional:** la comprobación se repitió manualmente en una ventana InPrivate, sin ninguna sesión guardada, con el mismo resultado. Esto descarta que el acceso se debiera a una sesión previa del navegador.
- **Hallazgo:** el sistema permite abrir el dashboard sin verificación previa, lo que contradice el escenario de fracaso de la historia US02.

![ST-04 Acceso sin validación](assets/img/ST04.png)

**ST-05 — Dashboard del conductor** (US06, US07)

Con el servicio iniciado desde la verificación, se comprueba que el dashboard muestre las etiquetas de las cuatro métricas: Distancia, Tiempo total, Pasajeros y Recaudación.

- **Resultado esperado:** se muestran las cuatro métricas del servicio.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** la prueba comprueba que las métricas están presentes en pantalla, no que se actualicen en vivo.

![ST-05 Dashboard del conductor](assets/img/ST05.png)

**ST-06 — Mapa en tiempo real** (US28)

Desde el dashboard, la prueba entra al marco que contiene el mapa y verifica que su lienzo (`maplibregl-canvas`) esté presente.

- **Resultado esperado:** se muestra el mapa con la posición de la unidad.
- **Resultado obtenido:** ✅ Pasó. El mapa se carga y se aprecia un marcador sobre Lima.
- **Nota:** el mapa del dashboard del conductor usa MapLibre, mientras que el del panel de administración usa Leaflet.

![ST-06 Mapa en tiempo real](assets/img/ST06.png)

**ST-07 — Botón de pánico** (US03, US04, US19)

Con el servicio activo, se pulsa "Panic Signal", se espera la respuesta del backend y se verifica que aparezca el título "¡ALERTA ENVIADA!".

- **Resultado esperado:** se crea la alerta y se muestra la confirmación de alerta enviada.
- **Resultado obtenido:** ✅ Pasó. Al generar una alerta de pánico, esta queda registrada en "Alert Logs" (tipo Pánico, nivel Crítico, estado Activa), verificado manualmente.
- **Observaciones:** la alerta se envía sin ventana de confirmación previa, que el prototipo del Capítulo 4 sí contemplaba. Además, la pantalla ofrece un botón "Cancelar alerta" que no figura en las historias del Capítulo 3.
- **Nota:** cada ejecución crea una alerta real en el backend.

![ST-07 Botón de pánico](assets/img/ST07.png)

**ST-08 — Finalizar servicio** (US20)

Con el servicio activo, se marcan las tres casillas del protocolo de cierre, se pulsa "Finalizar servicio" y se verifica que aparezca la ventana de confirmación "Servicio finalizado correctamente".

- **Resultado esperado:** se registra el cierre y se muestra la confirmación de servicio finalizado.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** la prueba verifica que la ventana de confirmación aparece. Una comparación literal del texto del título no coincidió pese a verse idéntico en pantalla, y no se identificó la causa, por lo que la verificación se hizo sobre la existencia del elemento. Cada ejecución cierra un turno.

![ST-08 Finalizar servicio](assets/img/ST08.png)

**ST-09 — Panel de administración** (US04, US21)

Desde la sesión de `EMP-001`, se pulsa "Administration" y se verifica que cargue el panel ("AVISUM ADMIN") y que exista la sección "Alertas recientes".

- **Resultado esperado:** el panel carga y muestra las unidades y las alertas recientes.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** las cifras del panel (unidades activas, alertas activas y pasajeros a bordo) variaron entre ejecuciones sin intervención, por lo que la prueba no verifica valores concretos ni la alerta específica generada en ST-07. En una carga con cero alertas, la sección "Alertas recientes" se mostró vacía, sin ningún mensaje.

![ST-09 Panel de administración](assets/img/ST09.png)

**ST-10 — Historial de alertas** (US16)

En el panel de administración se pulsa "Notificaciones" y se verifica que exista el "Registro de entregas", que lista los eventos de alerta (pánico, velocidad, sobrecapacidad y desvío).

- **Resultado esperado:** se muestra el registro de eventos de alerta.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** esta es la pantalla del panel de administración que más se acerca a lo que describe US16. La pantalla "Alert Logs" del conductor también incluye una tabla "Historial de alertas", que no fue cubierta por esta prueba. Los datos del registro de entregas parecen fijos (por ejemplo, la unidad GHI-9012), por lo que no se verifican entradas concretas.

![ST-10 Historial de alertas](assets/img/ST10.png)

**ST-11 — Contenido de la landing** (US08, US09, US25, US29)

Se abre la landing page y se verifica la presencia de sus secciones principales: el encabezado, la cifra "340+", "Tres capas de defensa operativa", "Cómo funciona", "Solicita una auditoría de seguridad para tu flota" y el pie de página.

- **Resultado esperado:** las secciones informativas son visibles.
- **Resultado obtenido:** ✅ Pasó.
- **Cobertura de historias:** US08, US09 y US25 quedan cubiertas, y US29 de forma parcial (a través de las cifras). Las historias US22, US23 y US30 (segmento de clientes, misión y visión, y equipo de trabajo) no se encontraron en la landing, por lo que no se probaron.

![ST-11 Contenido de la landing](assets/img/ST11.png)

**ST-12 — Navegación de la landing** (US17)

Se pulsa cada enlace del menú superior (Características, Cómo funciona, Estadística y Apoyo) y, tras una pausa, se verifica que exista el elemento de la sección correspondiente. "Apoyo" lleva a la sección "Solicita una auditoría de seguridad para tu flota".

- **Resultado esperado:** cada enlace del menú lleva a su sección.
- **Resultado obtenido:** ✅ Pasó.
- **Nota:** la prueba comprueba que el elemento de cada sección existe tras pulsar el enlace, no el desplazamiento de la página.

![ST-12 Navegación de la landing](assets/img/ST12.png)

#### Resumen de resultados

| ID | Escenario | Historias | Resultado |
|---|---|---|---|
| ST-01 | Login con código válido | US01, US14 | ✅ Pasó |
| ST-02 | Código inválido | US01 | ✅ Pasó |
| ST-03 | Verificación e inicio de servicio | US02, US15 | ✅ Pasó |
| ST-04 | Acceso sin validación | US02 | ❌ Falló |
| ST-05 | Dashboard del conductor | US06, US07 | ✅ Pasó |
| ST-06 | Mapa en tiempo real | US28 | ✅ Pasó |
| ST-07 | Botón de pánico | US03, US04, US19 | ✅ Pasó |
| ST-08 | Finalizar servicio | US20 | ✅ Pasó |
| ST-09 | Panel de administración | US04, US21 | ✅ Pasó |
| ST-10 | Historial de alertas | US16 | ✅ Pasó |
| ST-11 | Contenido de la landing | US08, US09, US25, US29 | ✅ Pasó |
| ST-12 | Navegación de la landing | US17 | ✅ Pasó |

De las 12 pruebas ejecutadas, 11 pasaron y 1 falló.

#### Hallazgos y observaciones

**Hallazgo confirmado**

- **ST-04:** la ruta `/conductor/dashboard` es accesible sin verificación previa, incluso en una ventana sin sesión guardada.

**Observaciones por revisar**

- La pantalla de acceso autorizado muestra textos de alerta de emergencia (ST-01).
- El botón de pánico envía la alerta sin ventana de confirmación y la pantalla incluye un botón "Cancelar alerta" que no figura en las historias de usuario (ST-07).
- Las cifras del panel de administración cambian entre cargas y la sección de alertas recientes quedó vacía, sin mensaje, en una de ellas (ST-09).
- Las historias US22, US23 y US30 no tienen una sección equivalente en la landing page (ST-11).
- El producto aparece con tres nombres distintos: "Avisum" en la landing y los capítulos, "SafeBus" en la pantalla de verificación y "UrbanGuard" en el título de la pestaña del frontend.

#### Limitaciones

- El backend corre en el plan gratuito de Render, por lo que la primera ejecución tras un periodo de inactividad puede fallar por tiempo de espera. Por eso se despierta el servicio antes de correr las pruebas y se usan pausas explícitas.
- Las pruebas del panel de administración no verifican cifras ni alertas concretas, porque los datos mostrados cambian entre ejecuciones.
- Las pruebas cubren la aplicación web; la aplicación móvil nativa no se probó con Selenium.

## 6.2. Static testing & Verification
### 6.2.1. Static Code Analysis
Esta sección aborda las técnicas de prueba y verificación estática, cuyo objetivo es garantizar que el software cumpla con los estándares de calidad y seguridad antes de ser ejecutado. Al aplicarlas, es posible detectar defectos en las primeras etapas del ciclo de vida del desarrollo.

El análisis estático consiste en examinar el código fuente sin ejecutarlo, ya sea mediante herramientas automatizadas o revisiones manuales. Con este enfoque se pueden identificar errores, vulnerabilidades de seguridad y aspectos susceptibles de mejora, lo que eleva la calidad general del software y reduce el costo de corregir problemas en fases posteriores.

#### 6.2.1.1. Coding standard & Code conventions
Los estándares de codificación y las convenciones son pautas que los desarrolladores deben seguir para lograr un código legible, mantenible y consistente. Para ello, se aplican los siguientes principios:

- Clean Code: Se deben usar nombres claros y descriptivos para variables, funciones y clases. Las funciones han de ser breves y cumplir una única responsabilidad, y se debe eliminar el código muerto y los comentarios innecesarios. Esto facilita la comprensión del código y la colaboración entre desarrolladores.
- Domain-Driven Design (DDD): Se debe adoptar un lenguaje ubicuo que refleje la terminología del negocio. Es clave dividir el sistema en bounded contexts y emplear correctamente entidades y objetos de valor. Asimismo, la lógica del dominio debe gestionarse mediante servicios de dominio y repositorios, lo que favorece una arquitectura más ordenada y alineada con los objetivos del negocio.

#### 6.2.1.2. Code Quality & Code Security
La calidad y la seguridad del código son esenciales para desarrollar software confiable:

- Calidad del código: Debe medirse con métricas como la cobertura de pruebas y la complejidad ciclomática. Se recomienda emplear herramientas como SonarQube para dar seguimiento continuo a la calidad y verificar que se cumplan los estándares definidos. SonarQube realiza un análisis exhaustivo del código, detecta problemas de calidad y sugiere cómo corregirlos.
- Seguridad del código: Es fundamental identificar y mitigar vulnerabilidades comunes, como las inyecciones SQL y el XSS, mediante la revisión del código. Aplicar prácticas de codificación segura y validar correctamente las entradas del usuario resulta clave para proteger el software.

Dado este enfoque en calidad y seguridad, se utilizará SonarLint, una herramienta complementaria que analiza el código en tiempo real mientras se desarrolla. SonarLint se integra con los IDE más populares, como IntelliJ IDEA, Eclipse y Visual Studio, y permite a los desarrolladores detectar problemas de calidad y seguridad a medida que escriben, recibiendo recomendaciones inmediatas para resolverlos. De esta manera se fomenta una cultura de calidad y mejora continua desde el inicio del desarrollo, y se garantiza que los problemas se atiendan antes de llegar a las etapas de revisión y prueba.

### 6.2.2. Reviews
Las revisiones de código son un proceso fundamental para asegurar la calidad y el cumplimiento de las normas establecidas. Incluyen tanto revisiones manuales como automáticas y deben seguir las pautas descritas a continuación.

**Tipos de revisiones**
- _Revisión por pares_: Un desarrollador examina el código de otro para comprobar que cumple con los estándares y que resulta fácil de entender.
- _Revisión formal_: Se realiza en una reunión estructurada en la que el código se evalúa con un checklist, lo que permite detectar problemas de manera colectiva.
- _Revisión automática_: Se apoya en herramientas como SonarLint y SonarQube para identificar errores y problemas de calidad en tiempo real.

**Proceso de revisión**
- _Creación de Pull Requests_: Los desarrolladores deben crear un PR con una descripción clara de los cambios realizados y de las pruebas asociadas.
- _Checklist de revisión_: Debe existir una lista de verificación que contemple aspectos como la claridad del código, la cobertura de pruebas y el manejo de errores.
- _Comentarios y retroalimentación_: Los revisores deben ofrecer comentarios constructivos y específicos, y todo problema identificado debe resolverse antes de la aprobación final.
- _Aprobación o rechazo del PR_: Todo PR requiere la aprobación de al menos un revisor adicional antes de integrarse en la rama principal.

**Criterios de aceptación**
- _Calidad y seguridad del código_: El código debe cumplir con los estándares de calidad y no introducir vulnerabilidades de seguridad.
- _Cobertura de pruebas_: Se exige una cobertura mínima (por ejemplo, 80 %) para garantizar que el código nuevo esté debidamente probado.

## 6.3. Validation Interviews
### 6.3.1. Diseño de Entrevistas.
A continuación se presentan las preguntas que se emplearán en las entrevistas de validación para evaluar la usabilidad de la aplicación actual. Estas preguntas han sido elaboradas para explorar las heurísticas de usabilidad y recoger información valiosa sobre la experiencia de los usuarios.

**Segmento Objetivo 1: Conductores**

1. ¿La información mostrada al iniciar sesión permite entender rápidamente el servicio?
2. ¿El proceso de iniciar y finalizar un turno es sencillo para su trabajo diario?
3. ¿Registrar una emergencia o enviar una alerta sería fácil durante una situación real?
4. ¿La información del recorrido en tiempo real ayudaría a mejorar su trabajo?
5. ¿Qué parte de la aplicación considera más útil y qué debería mejorar?
6. Del 1 al 5, ¿qué tan probable sería utilizar esta aplicación durante sus jornadas? ¿Por qué?

**Segmento objetivo 2: Empresas / Consorcios de transporte público**

1. ¿El dashboard permite encontrar fácilmente la información necesaria para controlar conductores, unidades y servicios?
2. ¿La gestión de turnos e historial de operaciones ayudaría a mejorar el control de la empresa?
3. ¿La información de una alerta es suficiente para tomar decisiones ante una incidencia?
4. ¿La visualización del estado de vehículos y servicios en tiempo real facilita la supervisión?
5. ¿Qué funcionalidad considera más importante y qué aspecto debería mejorarse?
6. Del 1 al 5, ¿qué tan probable sería implementar SafeBus en su empresa? ¿Por qué?

### 6.3.2. Registro de Entrevistas.

**Segmento Objetivo 1: Conductores**

- **Nombres y apellidos:** **PABLO CHACOT** 
- **Género:** Masculino
- **Edad:** 22 años

<img src="assets/img/EntrevistaPACO.png">

- **Inicio:** 0:00
- **Duración:** 6:59 min
- **URL:** [[https://upcedupe-my.sharepoint.com/:v:/g/personal/u202311082_upc_edu_pe/IQDu-vGArPjvQZbIJN1-flTDAfRFYF3reEetcAV8P1jpORY?](https://youtu.be/-4608rQgS-Y)]
- **Resumen:** Paco percibe la aplicación como una herramienta clara y fácil de usar, mostrando comodidad y familiaridad con cada paso que se le presenta. Repite varias veces que el sistema es “sencillo” e “intuitivo”, lo que refleja que no encuentra fricciones ni confusiones en el flujo. También valora especialmente la utilidad práctica de los sensores y las alertas, porque entiende que aportan información clave para la seguridad durante la actividad del transporte público. En general, su actitud es positiva, receptiva y sin objeciones técnicas importantes, transmitiendo que la app le parece funcional, bien organizada y adecuada para usuarios que quieren gestionar su seguridad.


- **Nombres y apellidos:** **VANESSA NUÑEZ** 
- **Género:** FEMENINO
- **Edad:** 26 años

<img src="assets/img/EntrevistaVANESSA.png">

- **Inicio:** 0:00
- **Duración:** 4:05 min
- **URL:** [https://upcedupe-my.sharepoint.com/:v:/g/personal/u20231c197_upc_edu_pe/IQBAPbPzZ9LaRLTMuplI1HgtAb3jY5Yyp_9oBWWvl_uLqoI?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=Nlzd3P](https://youtu.be/9hNV2Dpi0Bg)
- **Resumen:** Andre entiende la aplicación sin dificultad y siente que todo está ordenado y fácil de navegar. A lo largo de la demostración comenta que los procesos ingresar, ver el dashboard, registrar rutas, crear sensores y dispositivos le resultan claros y nada confusos. Le parece especialmente útil que la app permita vincular sensores y mostrar alertas, porque lo ve como algo realmente práctico para cuidar mejor las rutas. En general, transmite una impresión positiva: considera que la herramienta funciona bien, es intuitiva y podría ser utilizada sin problemas por cualquier transportista. 



**Segmento Objetivo 2: Representantes de Consorcios**

- **Nombres y apellidos:** **FRANCO ALCOCER** 
- **Género:** Masculino
- **Edad:** 25 años

<img src="assets/img/EntrevistaFRANCO.png">

- **Inicio:** 0:00
- **Duración:** 10:44 min
- **URL:** [https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241a352_upc_edu_pe/IQA3t8o3QYH8Q5MS_7G5JtQbAZmaOU4UJSALY0YLktrarOo?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=MEaIVx](https://youtu.be/hXUC10LIUPg) 
- **Resumen:** Franco transmite que la aplicación le resulta clara, ordenada y muy fácil de usar desde el inicio. Percibe que todo el flujo, desde la landing page hasta alertas es intuitivo, sin pasos confusos. La información está bien presentada, es relevante y le permite entender rápidamente cómo funciona cada sección. También valora que los formularios sean breves y que la navegación sea directa. En general, su impresión es positiva, siente que la app está bien estructurada, que cada parte cumple su propósito y que todas las funciones aportan valor a la experiencia del usuario. 


- **Nombres y apellidos:** **CARO CASTILO** 
- **Género:** Femenino
- **Edad:** 25 años

<img src="assets/img/EntrevistaCARO.png">

- **Inicio:** 0:00
- **Duración:** 6:25 min
- **URL:** [https://upcedupe-my.sharepoint.com/:v:/g/personal/u202323243_upc_edu_pe/IQDvG7qcbLA4SpbyXvgeLP6zAZK4JCsJsvKpmLwuEPqTFp4?e=TL1NWp&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D](https://youtu.be/eNBxgPOn_I4) 
- **Resumen:** Caro percibe que toda la aplicación es clara, directa y fácil de usar. Desde la landing page siente que la información está bien explicada y no encuentra ningún obstáculo para entender las funciones gratuitas ni para navegar. El formulario de registro le parece rápido y lógico, con los datos justos y necesarios. Al llegar al dashboard, entiende de inmediato cómo moverse entre secciones y considera que agregar una ruta es un proceso muy intuitivo, ya que todo está ordenado y bien identificado. También interpreta el módulo de administrador como una herramienta útil para organizar sus seguiminentos y anotar fechas, complicaciones y prioridades. En resumen, su impresión global es positiva: siente que la plataforma es sencilla, funcional y pensada para que cualquier usuario la pueda utilizar sin complicaciones.   

### 6.3.3. Evaluaciones según heurísticas.
## 6.4. Auditoría de Experiencias de Usuario.
### 6.4.1. Auditoría realizada.
#### 6.4.1.1. Información del grupo auditado.
Grupo a evaluar: El grupo de Milenko
Contexto
#### 6.4.1.2. Cronograma de auditoría realizada.
Cuadro de interacciones con el otro equipo
#### 6.4.1.3. Contenido de auditoría realizada.
Un cuadro

### 6.4.2. Auditoría recibida.
#### 6.4.2.1. Información del grupo auditor.
Grupo auditor: el grupo del compañero
Contexto
#### 6.4.2.2. Cronograma de auditoría recibida.
cauador
#### 6.4.2.3. Contenido de auditoría recibida.
##### 6.4.2.4. Resumen de modificaciones para subsanar hallazgos
correciones que desarrollamos o desarrollaremos
