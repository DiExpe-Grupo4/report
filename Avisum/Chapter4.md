# Capítulo IV: Product Design
## 4.1. Style Guidelines
Una guía de estilos o style guideline es un documento que enumera todas las elecciones y convenciones adoptadas en la empresa para mantener alineados al equipo de diseño y desarrollo. Seguir estos lineamientos permite desarrollar un prototipo de forma más rápida y eficiente (Kas, 2021).

### 4.1.1. General Style Guidelines
El estilo visual de la aplicación está orientado a transmitir seguridad, control y monitoreo. La decisión del diseño prioriza la claridad de la información, la rapidez de interpretación y la confianza del usuario, considerando que la aplicación está enfocada en un entorno de gestión y seguridad.

**Branding:**
La identidad de nuestra aplicación se construye como una plataforma tecnológica, confiable y eficiente, orientada a la supervisión y gestión de transporte.

Se busca que el usuario perciba el sistema como: 
-Seguro
-Preciso
-Moderno
-Siempre activo.

Visualmente, se toma como referencia interfaces tipo dashboard y sistemas de monitoreo, donde la información es el elemento central y debe ser comprendida rápidamente.

**Color Palette:**
La paleta de colores de Avissum se despliega en tonos oscuros y con contrastes, principalmente usamos el negro y verde neon, tambien el blanco y acentos de otros colores. Esta selección responde a la necesidad de crear un entorno visual tecnológico, seguro y orientado a la acción inmediata. La combinación de estos colores está pensada para transmitir monitoreo constante, control y respuesta en tiempo real, alineándose en el enfoque del que queremos dar con el producto respecto a la seguridad y gestión de buses.

- **Negro:** Usamos el color negro como la base de la interfaz. Este tono aporta elegancia, seriedad y profundidad, además de generar un entorno visual enfocado y libre de distracciones, refuerza la percepción de control, vigilancia y tecnología.
<center>
<img src="assets/img/negro.png">
</center>

- **Verde** Usamos en verde neón (#C3F400) como color principal de aceto. Lo usamos en botones, indicadores y títulos. Este color se asocia a sistemas digitales, monitoreo y confirmación, transmitiendo dinamismo e innovación. El otro verde (#596D0B) lo usamos de color secundario para generar contraste.
<center>
<img src="assets/img/Verde.png">
</center>

- **Rojo:** Este rojo lo usamos de manera puntual en elementos críticos, para transmitir alerta, ya que es un color que se asocia mucho a emergencia, urgencia, peligro o acción inmediata.
<center>
<img src="assets/img/Rojo.png">
</center>

**Typography:**

Se emplean tipografías **Space Grotesk** e **Inter**, debido a su alta legibilidad en entornos digitales y su fácil asociación visual con interfaces modernas.
Se establecerá la siguiente jerarquía:

- Títulos: Claros y visibles para identificar secciones rápidamente. **Space Grotesk-Bold.(96px)**
- Subtítulos: Apoyo estructural. **Space Grotesk- Bold (60-48px)**
- Párrafos: legible y de lectura rápida. **Inter- Light/Bold (24-12px)**

<center>
<img src="assets/img/Type.png">
</center>

**Spacing y Layout:**
El diseño se organizará mediante el uso de espacios consistentes y estructuras tipo tarjetas. Las medidas de estos elementos siempre será múltiplo de 2.

- Base unit: Se usará la regla de múltiplos de px para paddings y spacing.
<center>
<img src="assets/img/spacing.png">
</center>

- Grid: Márgenes de 24px para mantener armonía en la vista.
- Breakpoints: Ancho fijo de 1440px y alto de 1024px para web.

**Componentes visuales:**
- Botones: Verde para acciones principales, rojo para acciones críticas, gris para acciones secundarias.
<center>
<img src="assets/img/button.png">
</center>
- Cards: Contenedores de información organizados y fáciles de entender.
<center>
<img src="assets/img/cuadros.png">
</center>
- Iconografía: Estilo simple y de fácil reconocimiento.
<center>
<img src="assets/img/icons.png">
</center>

**Tono de comunicación:**
Nuestro tono de aplicación se define como serio, formal, respetuoso y sereno. Esto se debe a que la aplicación está orientada a un contexto de seguridad y monitoreo, donde la claridad y la confianza son prioritarias. Evitaremos el uso de lenguaje informal, priorizando mensajes directos, claros y profesionales.
**Principios de diseño:**
Las decisiones de diseño se sustentan en los siguientes principios:
- Claridad: Información comprensible de forma inmediata
- Jerarquía visual: Elementos importantes son los primeros en destacar
- Consistencia: Uso uniforme de colores, tipografías y componentes
- Accesibilidad: Buen contraste y legibilidad
- Feedback inmediato: El sistema responde visualmente a las acciones del usuario

### 4.1.2. Web Style Guidelines
En esta sección, definiremos los estándares visuales e interactivos de la aplicación en entorno web, asegurando una experiencia consistente y funcional.

**Navbar:**
<img src="assets/img/Navbar.png">

**Botones:**
<img src="assets/img/Botones.png">

**Responsive:**

<img src="assets/img/responsive_avisum.png">

### 4.1.3. Mobile Style Guidelines.
#### 4.1.3.1 iOS Mobile Style Guidelines.
En esta sección, definiremos los estándares visuales e interactivos de la aplicación en entorno web, asegurando una experiencia consistente y funcional.

Navbar:

<img src="assets/img/mobilenavbar.png">

Botones:

<img src="assets/img/mobilebotones1.png">

<img src="assets/img/mobilebotones2.png">

<img src="assets/img/mobilebotones3.png">

##### 4.1.3.2 Andrpid Mobile Style Guidelines.
En esta sección, definiremos los estándares visuales e interactivos de la aplicación en entorno web, asegurando una experiencia consistente y funcional.

Navbar:

<img src="assets/img/mobilenavbar.png">

Botones

<img src="assets/img/mobilebotones1.png">

<img src="assets/img/mobilebotones2.png">

<img src="assets/img/mobilebotones3.png">

## 4.2. Information Architecture


La Arquitectura de la Información (AI) de UrbanGuard está diseñada para organizar de manera lógica y clara el contenido, asegurando una navegación fluida y eficiente. Cada sección de la página cumple con un propósito específico, alineado con el objetivo de mejorar la seguridad en el transporte público. A continuación, damos una descripción más detallada.

#### 4.2.1. Organization Systems

Para la Landing Page se emplea una organización jerárquica y secuencial. Es jerárquica porque el usuario puede acceder a secciones clave desde la barra de navegación principal, y es secuencial porque el contenido está ordenado como una narrativa de conversión: primero se presenta la propuesta de valor, luego el problema, después la solución, sus beneficios, la comparación, los planes y finalmente el llamado a la acción.

| Nivel | Sección | Propósito dentro de la arquitectura |
|-------|---------|--------------------------------------|
| Global | Header (Navbar) | Permite acceso rápido a las secciones principales y a la pantalla de inicio de sesión. |
| Principal | Hero section | Presenta la propuesta de valor de UrbanGuard con botones de llamada a la acción. |
| Contextual | Problem section | Explica los problemas operativos del transporte público. |
| Functional | Main features section | Agrupa las funcionalidades principales: Verificación QR, Botón de pánico, Conteo de pasajeros, Monitoreo real, Alertas inteligentes. |
| Explicativo | How it works section | Explica el proceso de funcionamiento de UrbanGuard en 4 etapas. |
| Persuasivo | User benefits section | Resume los beneficios operativos directos para los transportistas. |
| Confianza | Client trust section | Explica cómo UrbanGuard mejora la seguridad y genera confianza. |
| Comparativo | Comparative section | Contrasta el sistema con otros métodos tradicionales de seguridad. |
| Comercial | Pricing section | Presenta los planes disponibles. |
| Soporte | FAQ section | Resuelve dudas frecuentes sobre el uso del sistema. |
| Conversión | Next step section | Refuerza el llamado a la acción. |
| Cierre | Footer section | Repite accesos clave, enlaces de contacto y redes sociales. |

#### 4.2.2. Labeling Systems
Con esto, identificamos el contenido en categorías y nodos. De esta manera, logramos una comunicación eficiente y efectiva para los usuarios, en nuestro caso, identificamos y empleamos las siguiente etiquetas:


| Etiqueta | Tipo | Uso dentro de la landing |
|----------|------|--------------------------|
| Cómo funciona | Navegación principal | Lleva al usuario a la explicación del flujo de funcionamiento de UrbanGuard. |
| Beneficios | Navegación principal | Dirige a la sección de beneficios operativos. |
| Planes | Navegación principal | Permite revisar las opciones de suscripción. |
| FAQ | Navegación principal | Abre la sección de preguntas frecuentes. |
| Iniciar sesión | Acción de acceso | Permite que un usuario existente acceda a su cuenta. |
| Comenzar ahora | CTA principal | Dirige al visitante hacia el flujo de registro. |
| Ver características | CTA secundario | Lleva al visitante a la sección de características. |
| Plan Free | Etiqueta comercial | Identifica el plan gratuito con funciones básicas. |
| Plan Control | Etiqueta comercial | Identifica el plan con mayores funciones operativas. |
| Comparativa breve | Encabezado de sección | Presenta una comparación entre UrbanGuard y otros sistemas. |
| Da el siguiente paso | CTA final | Refuerza el llamado a registrarse o revisar los planes. |
| Explorar | Footer | Agrupa enlaces hacia secciones informativas adicionales. |
| Siguiente paso | Footer | Agrupa enlaces hacia el proceso de registro. |

Estas adaptaciones de la estructura de la landing page para UrbanGuard toman los elementos de seguridad, funcionalidades y beneficios del sistema, alineándose con la información clave que los usuarios necesitan. Además, se utiliza un enfoque claro y persuasivo en cada una de las secciones para facilitar la conversión y maximizar la interacción con el producto.

### 4.2.3. SEO Tags and Meta Tags
La Landing Page de UrbanGuard incluye metadatos orientados a la indexación básica, compatibilidad móvil, carga de recursos visuales y reconocimiento de marca. Estos elementos ayudan a que la página sea interpretada correctamente por navegadores, buscadores y dispositivos móviles.
**Titulo de la pagina:**
```html
<title>UrbanGuard - Seguridad para el Transporte Público</title>
```
_Descripción_: El título debe ser claro y directo, utilizando palabras clave relevantes como "seguridad", "transporte público" y "UrbanGuard".

**Codificación de caracteres:**
```html
<meta charset="UTF-8">
```

**Configuración del responsive:**
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```
_Descripción_: Esto asegura que la página sea completamente funcional en dispositivos móviles y tablets.

**Descripción SEO:**
```html
<meta name="description" content="UrbanGuard ofrece soluciones de seguridad para el transporte público, con verificación de conductores, monitoreo en tiempo real y alertas de emergencia.">
```
_Descripción_: Este meta tag proporciona una breve descripción de la página, destacando los beneficios clave del sistema de seguridad.

**Ícono de marca:**
```html
<link rel="icon" type="image/png" href="/assets/urban-guard-icon.png" />
```
_Descripción_: El favicon que se muestra en las pestañas del navegador para aumentar la visibilidad de la marca.

**Optimización de carga tipográfica:**
```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
```
_Descripción_: Esto mejora el rendimiento de la carga de fuentes tipográficas, garantizando una carga más rápida.

**Etiquetas de autor, copyright y Open Graph (para redes sociales y aplicaciones de mensajería):**
```html
<meta name="author" content="UrbanGuard Team">
<meta name="copyright" content="UrbanGuard 2026">
<meta property="og:title" content="UrbanGuard - Seguridad para el Transporte Público">
<meta property="og:description" content="Aumenta la seguridad en el transporte público con verificación de conductores y monitoreo en tiempo real.">
<meta property="og:type" content="website">
```

#### 4.2.4. Searching Systems
Los Searching Systems son herramientas fundamentales cuando se maneja una gran cantidad de información o cuando el sitio web está dividido en diferentes secciones, estas, permiten al usuario localizar contenidos de manera rápida, eficiente y precisa, mejorando significativamente la experiencia de navegación. Además, contribuye a facilitar el acceso inmediato a la información deseada.


**Primera aproximación: Búsqueda incompleta conocida.**
Este sistema permite que los usuarios realicen búsquedas aunque no conozcan la información completa, en este caso, el nombre del conductor. Utiliza la filtración de palabras existentes en una lista de conductores para ir descartando nombres, por lo que, solo se mostraran los datos cercanos. Este método resulta especialmente útil cuando el usuario recuerda solo una parte de la información, sin embargo, tendrá que corroborar con los datos que visualice para no confundir identidad a los conductores con un mismo nombre o apellido.

**Segunda aproximación: Búsqueda mediante filtros.**
Nuestra aplicación permite filtrar por categoría a todos los conductores, depende del tipo de categoría que quieras visualizar y solo se te mostraran a los conductores de dicha categoría.

#### 4.2.5. Navigation Systems
Los Navigation Systems son esenciales para guiar al usuario dentro del sitio web, ayudando a localizar y acceder a la información de manera ordenada y eficiente. Un sistema de navegación bien diseñado mejora la usabilidad, la accesibilidad y la experiencia del usuario al interactuar con el contenido.
En nuestro proyecto hemos implementado los siguientes sistemas de navegación:

- **Menús de navegación:** Se utilizan para acceder a las diferentes secciones del sistema. En la versión web, los menús se ubican tanto en el header como en el footer. En la versión móvil, se emplea un menú tipo “hamburguesa” que, al desplegarse, permite acceder de manera clara a las funciones principales del sistema.
- **Etiquetas:** Permiten categorizar y agrupar contenidos por temas o funcionalidades, facilitando la búsqueda y el acceso a la información. En nuestra aplicación, las etiquetas se utilizan para identificar a los conductores con la categoría y estado. 
- **Barras de búsqueda:** Incluidas para los perfiles con permisos de administrador, permite ubicar a los conductores de forma directa mediante nombre o etiqueta asociada. Esta integrada con los sistemas de búsqueda previamente descritos, garantizando resultados precisos y una experiencia fluida.

### 4.3. Landing Page UI Design
En esta sección se presenta la propuesta de interfaz de usuario (UI) para el Landing Page. El diseño integra las decisiones establecidas en la arquitectura de información y los Style Guidelines previamente definidos, con el propósito de construir una experiencia visual coherente, atractiva y fácil de comprender.
El objetivo principal del Landing Page es comunicar de manera clara la propuesta de valor de la startup, transmitir confianza a los nuevos visitantes y motivarlos a registrarse en la plataforma. De esta manera, se constituye como el principal punto de acceso al ecosistema de colaboración interuniversitaria.

### 4.3.1. Landing Page Wireframe
Para la Landing page se desarrollaron en Figma cada apartado del sitio web.  
<center>
<img src = "assets/img/LandingPageWireframe.png">
</center>

**Elementos de diseño:** En los wireframes de la landing page se destacan tres elementos de diseño clave: tamaño, espacio y figuras. Se busca implementar un estilo tactico, lo que se refleja en el uso de espacios amplios que crean una interfaz limpia, ligera y fácil de navegar. Esta disposición evita la sobrecarga visual y mejora la legibilidad.

**Diseño inclusivo:** La interfaz presenta una estructura clara y organizada, diferenciando adecuadamente los elementos de navegación del contenido principal para facilitar su comprensión y recorrido. La distribución de los componentes sigue patrones visuales consistentes que permiten a los usuarios identificar y acceder fácilmente a la información. Asimismo, la correcta alineación de los elementos y el uso equilibrado de espacios en blanco contribuyen a una experiencia visual limpia, ordenada y libre de saturación.

**Arquitectura de la información:** El wireframe de la landing page presenta una estructura clara, sencilla y coherente con el enfoque minimalista del diseño. Se priorizan los elementos esenciales, como el boton “Registrarse” cuya funcion se identifica fácilmente. Esta distribución permite reducir la carga cognitiva y facilita la comprensión de la interfaz desde el primer contacto. Asimismo, la jerarquía visual organiza la información de manera estratégica, mostrando únicamente los contenidos necesarios y orientando al usuario hacia las principales acciones sin generar distracciones.

### 4.3.2. Landing Page Mock-up
**Desktop Web Browser Mock-up:**
<center>
<img src = "assets/img/mocup_avissum.png">
</center>


## 4.4. Mobile Applications UX/UI Design

### 4.4.1 Mobile Applications Wireframes
### 4.4.2 Mobile Applications Wireflow Diagrams
### 4.4.3 Mobile Applications Mock-ups
### 4.4.4 Mobile Applications User Flow Diagrams

## 4.5. Mobile Applications Prototyping
### 4.5.1 Android Mobile Prototyping
### 4.5.1 IOS Mobile Prototyping


## 4.6. Web Applications UX/UI Design

### 4.6.1. Web Applications Wireframes

Los wireframes de la aplicación web fueron diseñados para definir la estructura funcional de las principales pantallas del sistema. En esta etapa se identificaron los elementos clave de interacción, como paneles de control, visualización de datos, navegación entre secciones y componentes necesarios para la gestión del sistema. Estos wireframes permiten validar la distribución de información antes de la implementación visual, asegurando que las funcionalidades respondan a las necesidades del usuario.  
Wireframe Landing Page: En este wireframe vemos la organización de los elementos que se le presentan al usuario inicialmente al entrar a la página.  
Aquí vemos la organización de secciones individuales que componen las distintas pantallas de la página web. 
<center>
<img src = "assets/img/LandingPageWireframe.png">
<img src = "assets/img/ga1.png">
<img src = "assets/img/ga2.png">
<img src = "assets/img/ga3.png">
<img src = "assets/img/ga4.png">
</center>

### 4.6.2. Web Applications Wireflow Diagrams

Los wireflow diagrams representan el flujo de interacción del usuario dentro de la aplicación, mostrando la navegación entre pantallas y las acciones que el usuario puede realizar en cada etapa. Estos diagramas permiten entender el recorrido del usuario (user flow), facilitando la identificación de puntos clave de interacción y mejorando la experiencia general del sistema.

<img src="assets/img/Wireflow.png">

### 4.6.3. Web Applications Mock-ups
<center>
<img src = "assets/img/SafeBus - Acceso Conductor.png">
<img src = "assets/img/SafeBus - ImpactoEnNumeros.png">
<img src = "assets/img/SafeBus - Inicio.png">
<img src = "assets/img/SafeRide - Inicio de Servicio.png">
</center>

### 4.6.4. Web Applications User Flow Diagrams

**User flow 1: ADMIN**
<center>
<img src = "assets/img/UserflowAdmin.png">
</center>

**User Flow 2: Conductor**
<img src = "assets/img/UserFlowConductor.png">


## 4.7. Web Applications Prototyping

<h4>Introducción y criterios de diseño</h4>

El prototipo interactivo de SafeBus simula la navegación y los principales flujos de interacción de la aplicación web, permitiendo evaluar la coherencia de la experiencia de usuario antes del desarrollo, identificar puntos de fricción y validar las decisiones de arquitectura de información tomadas a lo largo del capítulo 4. El prototipo fue construido en Figma utilizando conexiones de prototipado entre frames, transiciones y overlays para representar de forma fiel los comportamientos especificados en los User Flow Diagrams.

Los criterios de diseño que guiaron las decisiones de interacción y navegación del prototipo son los siguientes:

**Orientación al rol y al flujo operativo de urgencia:** La arquitectura de navegación prioriza el acceso inmediato a las tareas de mayor frecuencia e importancia definidas en el User Task Matrix del capítulo 2. Para el conductor, el botón de pánico es el elemento más prominente de su pantalla principal, visible desde el primer momento en que inicia sesión. Para el operador de la central, el panel de alertas activas clasificadas por nivel de gravedad es la primera vista al iniciar sesión. Para el administrador de la empresa, el dashboard con el estado en tiempo real de toda la flota carga como vista inicial sin pasos adicionales.

**Consistencia en los patrones de interacción:** Se emplearon cuatro patrones de navegación a lo largo de toda la aplicación: (1) Navegación por Sidebar para el cambio entre módulos principales según el rol activo — conductor, central o empresa; (2) Drawer lateral deslizante para formularios de registro y edición que no requieren cambio de contexto, como el registro de un nuevo conductor o la asignación de vehículo; (3) Modal central para acciones críticas que requieren confirmación del usuario, como finalizar el turno, desactivar un conductor o escalar una alerta no atendida; y (4) Toast o Snackbar para retroalimentación inmediata de resultado sin interrumpir el flujo operativo, como la confirmación de recepción de una alerta de pánico.

**Prevención de errores en acciones de alto impacto:** En operaciones con consecuencias irreversibles o de alto impacto operativo, como activar el botón de pánico, finalizar un turno activo, desactivar un conductor o escalar una alerta, el prototipo incluye una capa adicional de confirmación mediante modal que describe el impacto de la acción antes de ejecutarla. Esto es especialmente crítico en el contexto de SafeBus, donde una acción incorrecta puede comprometer la trazabilidad de un incidente real de seguridad en el transporte público.

**Retroalimentación inmediata en tiempo real:** Todos los cambios en el estado del sistema que afectan al usuario se comunican de forma inmediata: el panel de alertas de la central se actualiza al recibirse una nueva alerta de pánico, el contador de pasajeros se actualiza en tiempo real al registrarse cada abordaje o bajada, y los campos de formulario muestran validación inline sin necesidad de enviar el formulario completo. Las alertas no confirmadas muestran un indicador de reintento automático visible en el panel de la central.

**Accesibilidad y objetivos táctiles:** Todos los elementos interactivos del prototipo tienen dimensiones mínimas de 48 × 48 px, especialmente relevantes para conductores que interactúan con la aplicación desde su smartphone durante la jornada de manejo. El botón de pánico tiene dimensiones ampliadas y color rojo con alto contraste para garantizar su activación inmediata bajo condiciones de estrés. Los contrastes de color en todos los estados cumplen el mínimo WCAG 2.1 AA.

<center>
<img src= "assets/img/SafeBusLading.png">
</center>

<h4> Flujos de interacción cubiertos por el prototipo </h4>

**Flujo 1 — Verificación e inicio de servicio del conductor:** Comprende la pantalla de verificación de identidad mediante código QR, la validación de autorización del conductor para el vehículo asignado, la validación de que el conductor no esté operando otra unidad simultáneamente, la pantalla de servicio activo con el botón de pánico, el contador de pasajeros en tiempo real y el botón de finalización de turno con confirmación modal.
<center>
<img src= "assets/img/AccesoAutorizadoConductor.png">
</center>

**Flujo 2 — Gestión de pasajeros y detección de anomalías:** Comprende la pantalla de conteo de pasajeros con botones de abordaje y bajada, la alerta visual al superar la capacidad máxima del vehículo, la detección y notificación de variaciones anómalas en el número de pasajeros y la consulta del estado actual del servicio.
<center>
<img src= "assets/img/ConteoDePasajeros.png">
</center>

**Flujo 3 — Activación y gestión de alertas de emergencia:** Comprende la activación del botón de pánico por el conductor, la confirmación de envío con indicador de reintento automático si no hay respuesta, la recepción de la alerta en el panel de la central con clasificación automática por nivel de gravedad, el detalle de la alerta con conductor, vehículo, número de pasajeros y ubicación, el registro del tiempo de respuesta al confirmar la atención y el escalamiento automático de alertas no atendidas con notificación a múltiples destinatarios.
<center>
<img src= "assets/img/EnvioDeAlerta.png">
</center>

**Flujo 4 — Monitoreo de flota por la empresa administradora:** Comprende el dashboard de estado en tiempo real de todas las unidades activas, el módulo de seguimiento de ubicación por vehículo, el monitoreo de ocupación con comparación entre rutas, la detección de unidades que superan su capacidad y el historial completo de emergencias filtrable por fecha, conductor y vehículo.
<center>
<img src= "assets/img/MonitoreoEmpresaAdministradora.png">
</center>

## 4.8. Domain-Driven Software Architecture
### 4.8.1. Design-Level Event Storming
Durante la sesión de Design-Level EventStorming, el equipo exploró los flujos del dominio de forma independiente y granular, identificando contextos delimitados preliminares para cada proceso de negocio. Como parte del proceso metodológico exigido para este ejercicio, se incluyó también la exploración de un Shared Kernel & Infrastructure Context y un Communication & Notifications Bounded Context, orientados a preocupaciones transversales
del sistema.

Avisum es una plataforma orientada a mejorar la seguridad en el transporte público mediante monitoreo en tiempo real, protocolos de emergencia, sensores inteligentes y comunicación inmediata entre pasajeros, conductores y autoridades.
El objetivo principal del sistema es detectar situaciones de riesgo, gestionar incidentes de seguridad y proporcionar respuesta rápida dentro de las unidades de transporte.

![Event Storming](assets/img/event_Storming.png)

### 4.8.2. Software Architecture Context Diagram
<center>
<img src = "assets/img/SAcontextDiagram.png">
</center>

### 4.8.3. Software Architecture Container Diagrams
<center>
<img src = "assets/img/SAcontainerDiagram.png">
</center>

### 4.8.4. Software Architecture Components Diagrams
<center>
<h4>Components Diagram — Authentication Service</h4>

![container1](assets/img/cd1.png)

<h4>Components Diagram — User Service</h4>

![container2](assets/img/cd2.png)

<h4>Components Diagram — Profile Service</h4>

![container3](assets/img/cd3.png)

<h4>Components Diagram — Monitoring Service</h4>

![container4](assets/img/cd4.png)

</center>

---

## 4.9. Software Object-Oriented Design
### 4.9.1. Class Diagrams
La arquitectura del sistema se ha modelado bajo el enfoque de Domain-Driven Design (DDD) para garantizar una alta cohesión y un bajo acoplamiento. Con el objetivo de facilitar el análisis del dominio y asegurar la legibilidad técnica, la representación visual del backend se ha segmentado. A continuación, se presentan los diagramas de clases correspondientes a los 4 Bounded Contexts identificados, detallando sus respectivos Agregados, Entidades y Objetos de Valor (Value Objects).

<center>
<h4>Bounded Context: Authentication Management</h4>

![bounded context 1](assets/img/bc1.png)

<h4>Bounded Context: User</h4>

![bounded context 2](assets/img/bc2.png)

<h4>Bounded Context: Profile</h4>

![bounded context 3](assets/img/bc3.png)

<h4>Bounded Context: Monitoring</h4>

![bounded context 4](assets/img/bc4.png)

</center>

### 4.9.2 Class Dictionary
Diccionario de clases correspondiente a los diagramas del punto anterior, para cada Aggregate Root, Entity y Value Object, sus atributos (nombre, tipo y descripción) y, cuando corresponde, sus métodos de dominio.

<h4>Bounded Context: Authentication Management</h4>

**`Authentication`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único del registro de autenticación. |
| driverId | String | Referencia al conductor que intenta autenticarse. |
| status | CodeStatus | Estado actual del proceso de autenticación (Value Object). |
| createdAt | DateTime | Fecha y hora en que se inició el intento de inicio de sesión. |

**Métodos**

| Método | Descripción |
|---|---|
| validateCode(code: String): bool | Verifica que el código ingresado coincida con el generado y no esté expirado. |
| authenticate(): void | Marca la autenticación como exitosa y habilita el acceso del conductor. |

**`AuthenticationCode`** — *Entity*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único del código generado. |
| code | String | Valor del código de acceso enviado al conductor. |
| expiresAt | DateTime | Momento a partir del cual el código deja de ser válido. |
| used | bool | Indica si el código ya fue consumido. |

**`CodeStatus`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | String | Estado del código: PENDING \| VALIDATED \| EXPIRED. |

<h4>Bounded Context: User</h4>

**`Driver`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único del conductor. |
| fullName | String | Nombre completo del conductor. |
| licenseNumber | String | Número de licencia de conducir. |
| status | DriverStatus | Estado del conductor dentro del sistema (Value Object). |

**Métodos**

| Método | Descripción |
|---|---|
| identify(): void | Recupera y confirma la identidad del conductor ya autenticado. |
| activate(): void | Habilita el acceso del conductor al panel principal. |

**`ContactInfo`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| phone | String | Número de teléfono de contacto del conductor. |
| email | String | Correo electrónico de contacto del conductor. |

**`DriverStatus`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | String | Estado del conductor: ACTIVE \| INACTIVE \| SUSPENDED. |

<h4> Bounded Context: Profile </h4>

**`DriverProfile`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único del perfil. |
| driverId | String | Referencia al conductor propietario del perfil. |
| photoUrl | String | URL de la fotografía del conductor. |
| experienceYears | int | Años de experiencia como conductor. |

**Métodos**

| Método | Descripción |
|---|---|
| getProfile(): ProfileSummary | Devuelve un resumen de los datos del perfil del conductor. |

**`Bus`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único del vehículo. |
| plate | VehiclePlate | Placa del vehículo (Value Object). |
| capacity | int | Capacidad máxima de pasajeros del vehículo. |
| model | String | Modelo del vehículo. |

**Métodos**

| Método | Descripción |
|---|---|
| getVehicleInfo(): void | Retorna la información básica del vehículo asignado a la ruta. |

**`VehiclePlate`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | String | Número de placa del vehículo, validado por formato. |

**`ProfileSummary`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| driverName | String | Nombre del conductor. |
| photoUrl | String | URL de la fotografía del conductor. |
| experienceYears | int | Años de experiencia del conductor. |

<h4>Bounded Context: Monitoring</h4>

**`Route`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único de la ruta. |
| driverId | String | Conductor asignado a la ruta. |
| busId | String | Vehículo asignado a la ruta. |
| startTime | DateTime | Fecha y hora de inicio de la ruta. |
| endTime | DateTime | Fecha y hora de finalización de la ruta. |
| status | String | Estado de la ruta: PLANNED \| IN_PROGRESS \| FINISHED. |

**Métodos**

| Método | Descripción |
|---|---|
| start(): void | Marca el inicio de la ruta y dispara la política de inicio de monitoreo. |
| finish(): void | Marca la finalización de la ruta. |

**`MonitoringSession`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único de la sesión de monitoreo. |
| routeId | String | Referencia a la ruta que está siendo monitoreada. |
| passengerCount | PassengerCount | Cantidad de pasajeros registrada (Value Object). |
| currentSpeed | Speed | Velocidad actual del bus (Value Object). |
| startedAt | DateTime | Momento en que inició la sesión de monitoreo. |

**Métodos**

| Método | Descripción |
|---|---|
| registerPassengers(count: int): void | Registra la cantidad de pasajeros detectada. |
| registerSpeed(speed: double): void | Registra la velocidad actual del bus. |

**`EmergencyAlert`** — *Aggregate Root*

| Atributo | Tipo | Descripción |
|---|---|---|
| id | String | Identificador único de la alerta de emergencia. |
| routeId | String | Ruta en la que ocurrió la alerta. |
| driverId | String | Conductor que activó la alerta. |
| status | AlertStatus | Estado actual de la alerta (Value Object). |
| createdAt | DateTime | Fecha y hora en que se activó la alerta. |
| attendedAt | DateTime | Fecha y hora en que la alerta fue atendida. |

**Métodos**

| Método | Descripción |
|---|---|
| activate(): void | Activa la alerta de emergencia a partir del altercado. |
| register(): void | Registra formalmente la alerta activada. |
| send(): void | Envía la alerta al administrador / central de operaciones. |
| attend(): void | Marca la alerta como atendida tras el apoyo del administrador. |
| close(): void | Cierra la alerta una vez resuelta. |

**`GeoLocation`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| lat | double | Latitud de la posición del bus. |
| lng | double | Longitud de la posición del bus. |

**`Speed`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | double | Valor numérico de la velocidad registrada. |
| unit | String | Unidad de medida, por ejemplo km/h. |

**`PassengerCount`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | int | Cantidad de pasajeros registrada; no puede ser negativa. |

**`AlertStatus`** — *Value Object*

| Atributo | Tipo | Descripción |
|---|---|---|
| value | String | Estado de la alerta: ACTIVATED \| REGISTERED \| SENT \| ATTENDED \| CLOSED. |

## 4.10. Database Design
Se adopta una estrategia de persistencia poliglota, con una base de datos independiente por Bounded Context (*database-per-service*), siguiendo el mismo límite que los Aggregates definidos en la sección 4.9. Authentication, User y Profile manejan datos estructurados de bajo volumen de escritura y se modelan como bases de datos **relacionales** (PostgreSQL). Monitoring recibe escritura de alta frecuencia (velocidad, pasajeros, ubicación) y necesita un esquema flexible para el historial de ubicación, por lo que se modela como base de datos **no relacional** orientada a documentos (MongoDB).

### 4.10.1. Relational/Non-relational Database Diagram



**Authentication DB — Relacional (PostgreSQL)**

<center>

```mermaid
erDiagram
    AUTHENTICATIONS ||--o{ AUTHENTICATION_CODES : has
    AUTHENTICATIONS {
        uuid id PK
        uuid driver_id
        string status
        timestamp created_at
    }
    AUTHENTICATION_CODES {
        uuid id PK
        uuid authentication_id FK
        string code
        timestamp expires_at
        boolean used
    }
```
</center>

**User DB — Relacional (PostgreSQL)**

<center>

```mermaid
erDiagram
    DRIVERS {
        uuid id PK
        string full_name
        string license_number
        string status
        string phone
        string email
    }
```
</center>

**Profile DB — Relacional (PostgreSQL)**

<center>

```mermaid
erDiagram
    DRIVER_PROFILES {
        uuid id PK
        uuid driver_id
        string photo_url
        int experience_years
    }
    BUSES {
        uuid id PK
        string plate
        int capacity
        string model
    }
```

</center>

**Monitoring DB — No relacional (MongoDB, orientada a documentos)**

Las colecciones no tienen llaves foráneas físicas: las referencias entre documentos se resuelven por convención de identificador (`routeId`), propio del modelo de documentos, y no como un JOIN relacional.

**Colección `routes`**

```json
{
  "_id": "ObjectId",
  "driverId": "String",
  "busId": "String",
  "startTime": "Date",
  "endTime": "Date",
  "status": "String"
}
```

**Colección `monitoring_sessions`**

```json
{
  "_id": "ObjectId",
  "routeId": "String", 
  "passengerCount": { "value": "Int" },
  "currentSpeed": { "value": "Double", "unit": "String" },
  "startedAt": "Date",
  "locationHistory": [
    { "lat": "Double", "lng": "Double", "timestamp": "Date" }
  ]
}
```

**Colección `emergency_alerts`**

```json
{
  "_id": "ObjectId",
  "routeId": "String",  
  "driverId": "String",
  "status": "String",
  "createdAt": "Date",
  "attendedAt": "Date"
}
```


**Relaciones lógicas (sin FK física):**
- 1 `routes` ↔ 1 `monitoring_sessions` (por `routeId`)
- 1 `routes` ↔ 0..N `emergency_alerts` (por `routeId`)

