
![LOGO UPC](./Informe/assets/LogoUPC.png)

Universidad Peruana de Ciencias Aplicadas

**Facultad de Ingeniería**

Ingenieria de Software

**Desarrollo de Aplicaciones Open Source - 1ASI0729 – 2610**

**Profesor: Juan Antonio Flores Moroco**

"Informe de Trabajo Final"

Startup: IntegraVIda

“GlucoSmart”

U202414054 – Jean Pool Alexander Arias Tasayco
U202318001 – Abigail Nadhim Raymundo Villarroel 
U202223405 – Juan Sebastian Estupiñan Olortegui
U202218387 - Javier Oswaldo Tello Murga

Abril 2026-10

# <a name="_toc226040379"></a>Registro de Versiones del Informe

| Versión | Fecha |   Autor    |                              Descripción de Modificación                               |
| :-----: | :---: | :--------: | :------------------------------------------------------------------------------------: |
|  0\.1   | 10/04 | Jean Arias | Definición del Startup Profile y Lean UX Assumption y Hypotesis Stament (Capítulo I).  |
|   0.2   | 13/04 | Jean Arias | Desarrollo del Artefactos de Negocio: Empathy Map, Persona y Journey Map (Capítulo II) |
|   0.3   | 16/04 | Jean Arias |           Especificación de requerimientos: Impact Mapping  (Capítulo III).            |
|   0.4   | 19/04 | Jean Arias |   Desarrollo e integración de la interfaz de usuario (UI) para la Landing Page de GlucoSmart.  (Capítulo IV)   |
|   0.5   | 19/04 | Abigail Raymundo |  Creación de wireframes para definir la estructura de contenidos y la elaboración de mockups de alta fidelidad en Figma.   |
|   0.6   | 21/04 | Jean Arias |   Implementación del Sprint 1, Configuración de Software y Despliegue (Capítulo V).    |
|   0.7   | 21/04 | Abigail Raymundo |   Desarrollo e integración de la interfaz de usuario (UI) para la Landing Page de GlucoSmart.    |

# <a name="_toc226040380"></a>Project Report Collaboration Insights

- Enlace del Repositorio:
	- [ <https://github.com/MTS-OpenSource/IntegraVida.git>](https://github.com/MTS-OpenSource/IntegraVida)
	- [ <https://github.com/MTS-OpenSource/InformeProyecto.git>](https://github.com/MTS-OpenSource/InformeProyecto)

- AV1:
  - ¿Qué Problema se encontró?
	  Se identificó una alta fragmentación y deficiencia en la gestión de la información clínica de pacientes diagnosticados con Diabetes Mellitus. Actualmente, el registro de métricas vitales (como los niveles de glucosa y hemoglobina glicosilada - HbA1c) y el control de la medicación se realizan, en su mayoría, de forma manual, aislada o dependiente de la memoria del paciente. Esta situación genera dos problemas críticos:
		1. **En el paciente:** Una baja adherencia al tratamiento debido a olvidos frecuentes de las dosis, sumado a la incertidumbre y falta de un canal directo para reportar efectos secundarios de los fármacos.
		2. **En el personal médico:** Pérdida de tiempo valioso durante las consultas al tener que unificar e interpretar historiales desordenados (en papel o Excel). Además, existe una nula capacidad de **farmacovigilancia activa**, lo que impide a los doctores intervenir preventivamente antes de que un paciente sufra una crisis de hipoglucemia severa o daño orgánico.
	
- ¿Cómo se resolverá?
	El problema se resolverá mediante el desarrollo y despliegue de IntegraVida una plataforma web B2B2C respaldada por una arquitectura de base de datos relacional robusta. Esta solución centralizará la información y conectará en tiempo real a los pacientes con sus médicos tratantes, resolviendo la problemática a través de tres pilares tecnológicos:
	
	1. **Sistema de Adherencia Automatizado:** Notificaciones y confirmaciones de toma de medicación que reducen drásticamente los olvidos en los pacientes.
	2. **Módulo de Farmacovigilancia y Alertas Críticas:** Un canal de registro rápido donde los pacientes reportan reacciones adversas, el cual dispara alertas inmediatas al médico si los parámetros indican un riesgo vital.
	3. **Ecosistema de Decisiones Clínicas:** Un panel de control (_Dashboard_) interactivo para el médico que procesa los datos registrados y los visualiza en gráficos de tendencias, permitiendo optimizar el tiempo de consulta y ajustar los tratamientos de forma rápida y segura basándose en evidencia real.

Contenido

[**REGISTRO DE VERSIONES DEL INFORME **2\*\*\*\*](#_toc226040379)

[**PROJECT REPORT COLLABORATION INSIGHTS **2\*\*\*\*](#_toc226040380)

[**STUDENT OUTCOME **6\*\*\*\*](#_toc226040381)

[**CAPITULO I: INTRODUCTION **7\*\*\*\*](#_toc226040382)

[1.1 Startup Profile 7](#_toc226040383)

[*1.1.1 Descripción de la Startup *7\*\*](#_toc226040384)

[*1.1.2. Perfiles de integrantes del equipo *7\*\*](#_toc226040385)

[1.2. Solution Profile 7](#_toc226040386)

[*1.2.1 Antecedentes y problemática *7\*\*](#_toc226040387)

[*1.2.2 Lean UX Process *7\*\*](#_toc226040388)

[1.2.2.1 Lean UX Problem Statements 7](#_toc226040389)

[1.2.2.2 Lean UX Assumption 7](#_toc226040390)

[12.2.3 Lean UX Hypothesis Statements 7](#_toc226040391)

[1.2.2.4 Lean UX Canvas 7](#_toc226040392)

[1.3 Segmento Objetivo 7](#_toc226040393)

[**CAPITULO II: REQUIREMENTS ELICITATION & ANALYSIS **7\*\*\*\*](#_toc226040394)

[2.1 Competidores 7](#_toc226040395)

[*2.1.1 Analisis Competitivo *7\*\*](#_toc226040396)

[*2.1.2 Estrategia y tácticas frente a competidores *7\*\*](#_toc226040397)

[2.2 Entrevistas 7](#_toc226040398)

[*2.2.1 Diseño de entrevistas *7\*\*](#_toc226040399)

[*2.2.2 Registro de entrevista *7\*\*](#_toc226040400)

[*2.2.3 Analisis de entrevista *7\*\*](#_toc226040401)

[2.3 Needfinding 7](#_toc226040402)

[*2.3.1 User Personas *7\*\*](#_toc226040403)

[*2.3.2 User Task Matrix *7\*\*](#_toc226040404)

[*2.3.3 User Journey Mapping *7\*\*](#_toc226040405)

[*2.3.4 Empathy Mapping *7\*\*](#_toc226040406)

[2.4 Big Picture Event Storming 7](#_toc226040407)

[2.5 Ubiquitous Language 7](#_toc226040408)

[**CAPITULO III: REQUIREMENTS SPECIFICATION **7\*\*\*\*](#_toc226040409)

[3.1 User Stories 7](#_toc226040410)

[3.2 Impact Mapping 7](#_toc226040411)

[3.3 Product Backlog 7](#_toc226040412)

[**CAPITULO IV: PRODUCT DESIGN **8\*\*\*\*](#_toc226040413)

[4.1. Style Guidelines. 8](#_toc226040414)

[*4.1.1. General Style Guidelines. *8\*\*](#_toc226040415)

[*4.1.2. Web Style Guidelines. *8\*\*](#_toc226040416)

[4.2. Information Architecture. 8](#_toc226040417)

[*4.2.1. Organization Systems. *8\*\*](#_toc226040418)

[*4.2.2. Labeling Systems. *8\*\*](#_toc226040419)

[*4.2.3. SEO Tags and Meta Tags *8\*\*](#_toc226040420)

[*4.2.4. Searching Systems. *8\*\*](#_toc226040421)

[*4.2.5. Navigation Systems. *8\*\*](#_toc226040422)

[4.3. Landing Page UI Design. 8](#_toc226040423)

[*4.3.1. Landing Page Wireframe. *8\*\*](#_toc226040424)

[*4.3.2. Landing Page Mock-up. *8\*\*](#_toc226040425)

[4.4. Web Applications UX/UI Design. 8](#_toc226040426)

[*4.4.1. Web Applications Wireframes. *8\*\*](#_toc226040427)

[*4.4.2. Web Applications Wireflow Diagrams. *8\*\*](#_toc226040428)

[*4.4.2. Web Applications Mock-ups. *8\*\*](#_toc226040429)

[*4.4.3. Web Applications User Flow Diagrams. *8\*\*](#_toc226040430)

[4.5. Web Applications Prototyping. 8](#_toc226040431)

[4.6. Domain-Driven Software Architecture. 8](#_toc226040432)

[*4.6.1. Design-Level Event Storming. *8\*\*](#_toc226040433)

[*4.6.2. Software Architecture Context Diagram. *8\*\*](#_toc226040434)

[*4.6.3. Software Architecture Container Diagrams. *8\*\*](#_toc226040435)

[*4.6.4. Software Architecture Components Diagrams. *8\*\*](#_toc226040436)

[4.7. Software Object-Oriented Design. 8](#_toc226040437)

[*4.7.1. Class Diagrams. *8\*\*](#_toc226040438)

[4.8. Database Design. 8](#_toc226040439)

[*4.8.1. Database Diagrams *8\*\*](#_toc226040440)

[**CAPITULO V: PRODUCT IMPLEMENTATION, VALIDATION & DEPLOYMENT **8\*\*\*\*](#_toc226040441)

[5.1. Software Configuration Management. 8](#_toc226040442)

[*5.1.1. Software Development Environment Configuration. *8\*\*](#_toc226040443)

[*5.1.2. Source Code Management. *8\*\*](#_toc226040444)

[*5.1.3. Source Code Style Guide & Conventions. *8\*\*](#_toc226040445)

[*5.1.4. Software Deployment Configuration. *8\*\*](#_toc226040446)

[5.2. Landing Page, Services & Applications Implementation. 8](#_toc226040447)

[*5.2.1. Sprint 1 *8\*\*](#_toc226040448)

[*5.2.1.1. Sprint Planning 1. *8\*\*](#_toc226040449)

[*5.2.1.2. Aspect Leaders and Collaborators. *8\*\*](#_toc226040450)

[*5.2.1.3. Sprint Backlog 1. *8\*\*](#_toc226040451)

[*5.2.1.4. Development Evidence for Sprint Review. *8\*\*](#_toc226040452)

[*5.2.1.5. Execution Evidence for Sprint Review. *8\*\*](#_toc226040453)

[*5.2.1.6. Services Documentation Evidence for Sprint Review. *8\*\*](#_toc226040454)

[*5.2.1.7. Software Deployment Evidence for Sprint Review. *8\*\*](#_toc226040455)

[*5.2.1.8. Team Collaboration Insights during Sprint. *8\*\*](#_toc226040456)

[**CONCLUSIONES **8\*\*\*\*](#_toc226040462)

[Conclusiones y recomendaciones 8](#_toc226040463)

[**BIBLIOGRAFÍA **8\*\*\*\*](#_toc226040465)

[**ANEXOS **9\*\*\*\*](#_toc226040466)

# <a name="_toc226040381"></a>Student Outcome

| Criterio Especifico                                                    | Acciones Realizadas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Conclusiones                                                                                                                                                                                                                                                                                                              |
| :--------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Proporciona Liderazgo y Planifica Tareas, Establece y Cumple Objetivos | Asumiendo un rol de liderazgo en IntegraVida, se planificó el desarrollo de la plataforma GlucoSmart utilizando el marco de trabajo Scrum para traducir los requerimientos médicos en un _Product Backlog_. Durante el Sprint 1, se cumplió la meta técnica al desplegar exitosamente la _Landing Page_ en GitHub Pages, alcanzando 18 de los 20 _Story Points_ estimados. La implementación de estas tareas críticas Estructura base, Navbar, Hero, Formulario de Contacto y Servicio de Idioma permitió validar de forma práctica las hipótesis del proceso Lean UX, estableciendo un primer hito sólido hacia la solución final de gestión de farmacovigilancia. | - El cumplimiento de los objetivos establecidos demuestra la viabilidad técnica de la solución. La metodología de validación constante (implementación-despliegue) permitió obtener una versión del producto que satisface las necesidades de los usuarios finales y los estándares de ingeniería de software requeridos. |
|                                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                           |

# <a name="_toc226040382"></a>Capitulo I: Introduction

## <a name="_toc226040383"></a>1.1 Startup Profile

IntegraVida es una startup tecnológica del sector HealthTech nacida con la ambición de transformar radicalmente el paradigma del manejo de enfermedades crónicas, con un enfoque inicial en la diabetes. Nos definimos como una organización orientada a la innovación que desarrolla ecosistemas de software abiertos, rompiendo con las limitaciones de las soluciones propietarias y cerradas que fragmentan la información médica. 

Nuestra propuesta de valor reside en la interoperabilidad y la democratización de los datos de salud. A través del uso de arquitecturas distribuidas y modernas, IntegraVida conecta a pacientes, especialistas y sistemas de farmacovigilancia en una red de colaboración en tiempo real. No solo buscamos registrar datos, sino transformarlos en activos clínicos accionables que permitan cerrar la brecha de tratamiento y mejorar la calidad de vida de las poblaciones vulnerables a nivel global. 

Misión 

Empoderar a pacientes que conviven con enfermedades crónicas a través de soluciones de software de código abierto de alto rendimiento, diseñadas para facilitar una gestión integral, autónoma y segura de su salud. Nos comprometemos a proporcionar una infraestructura digital robusta que garantice la trazabilidad terapéutica y la precisión clínica, permitiendo que las decisiones médicas se basen en la analítica de datos en tiempo real y en una comunicación bidireccional efectiva entre el paciente y el equipo multidisciplinario de salud. 

Visión 

Consolidarnos para el año 2030 como la plataforma referente a nivel mundial en el ecosistema de salud abierta, convirtiéndonos en el núcleo digital estándar para la atención médica personalizada. Aspiramos a liderar la integración tecnológica en el sector salud, donde nuestras arquitecturas de software sirvan de base para millones de usuarios, transformando los sistemas de salud tradicionales en modelos predictivos, inclusivos y altamente eficientes, escalando desde nuestra base operativa en Perú hacia mercados internacionales.

### <a name="_toc226040384"></a>1.1.1 Descripción de la Startup

**IntegraVida** es una startup peruana del sector **HealthTech** orientada al desarrollo de soluciones digitales para el seguimiento y control de enfermedades crónicas, con un enfoque inicial en la diabetes. La empresa surge como respuesta a la fragmentación de información clínica, la baja interoperabilidad entre actores del sistema de salud y la falta de herramientas que acompañen de forma continua tanto al paciente como al profesional médico en la toma de decisiones.

La startup propone una visión centrada en la integración de datos y en la construcción de un ecosistema digital accesible, seguro y escalable. En lugar de limitarse al registro aislado de indicadores de salud, **IntegraVida** busca consolidar información clínica relevante, hábitos del paciente, adherencia al tratamiento, alertas preventivas y comunicación médico-paciente dentro de una misma plataforma. De esta manera, se promueve una atención más precisa, preventiva y conectada con el contexto real del usuario.

Como primer producto, desarrolla **GlucoSmart**, una plataforma web que permite monitorear niveles de glucosa, registrar medicamentos, generar recordatorios, visualizar reportes y fortalecer la trazabilidad terapéutica. Esta solución está pensada para atender las necesidades de pacientes con diabetes y de profesionales de salud que requieren información confiable y oportuna para mejorar el seguimiento clínico.

El valor diferencial de la startup radica en combinar tecnología, enfoque centrado en el usuario y principios de software abierto para construir una solución con impacto social. Con ello, **IntegraVida** aspira a contribuir a la modernización del cuidado de la salud, reducir la brecha de tratamiento y mejorar la calidad de vida de las personas que conviven con enfermedades crónicas.

### <a name="_toc226040385"></a>1.1.2. Perfiles de integrantes del equipo

| Estudiante: Arias Tasayco, Jean Pool Alexander<br><br>Carrera:Ingeniería de Software<br><br>Soy un estudiante de la carrera de Ingeniería de Software. Me considero un apasionado por la tecnología y me dedico a transformar ideas en soluciones digitales eficientes y escalables.<br><br>Durante mi formación, he adquirido habilidades en el desarrollo de software y en la creación de soluciones que no solo cumplen con su propósito, sino que buscan innovar. Mi objetivo es utilizar mis conocimientos para resolver problemas reales y generar un impacto positivo a través de la tecnología |

| Estudiante: Raymundo Villarroel, Abigail Nadhimr<br><br>Carrera:Ingeniería de Software<br><br>Soy un estudiante de la carrera de Ingeniería de Software.Actualmente estoy cursando el 5° ciclo de Ingeniería de Software, avanzando algunos cursos del ciclo superior. Desde siempre me ha apasionado crear, diseñar y programar para ofrecer soluciones, me gusta aprender constantemente para ampliar mis conocimientos y perfil profesional. Me comprometo a aportar con responsabilidad al equipo, trabajar de manera colaborativa y contribuir a que juntos podamos desarrollar un proyecto sobresaliente. Mis principales habilidades incluyen creatividad, disciplina y trabajo en equipo, cualidades que aplico para lograr resultados efectivos y de calidad |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## <a name="_toc226040386"></a>1.2. Solution Profile

### <a name="_toc226040387"></a>1.2.1 Antecedentes y problemática

Who (¿A quiénes les afecta?) 

El impacto de esta problemática es sistémico y se distribuye en tres niveles críticos: 

- Pacientes con diabetes: Se ven obligados a gestionar su condición con herramientas que ofrecen datos fragmentados (silos de información), careciendo de una visión holística de su salud. Esto genera "fatiga de datos" y una alarmante ausencia de alertas preventivas que les permitan actuar antes de una crisis. 
- Personal Médico y Clínicas: Los especialistas reciben datos recolectados de forma asíncrona y sin contexto. Al no contar con trazabilidad real sobre la adherencia farmacológica o los efectos adversos, se ven limitados para realizar ajustes terapéuticos precisos, trabajando bajo un modelo de "ensayo y error" reactivo. 
- Sistemas de Salud Públicos y Privados: Estos organismos asumen el impacto financiero de las complicaciones crónicas (nefropatías, neuropatías, etc.) que podrían evitarse con un seguimiento preventivo. La ineficiencia en el manejo ambulatorio dispara los costos operativos y satura los servicios de emergencia. 

What (¿Cuál es el problema?) 

El problema central es la ineficiencia funcional y la desarticulación de datos en el ecosistema mHealth actual. Las aplicaciones convencionales se han limitado al registro cuantitativo de la glucosa, ignorando la integración de pilares fundamentales como la farmacovigilancia y la trazabilidad terapéutica. Existe una brecha crítica entre lo que el médico prescribe (indicación) y lo que el paciente realmente ejecuta (consumo real), lo que convierte a los datos recolectados en información estéril para el análisis clínico profesional. 

Where (¿Dónde surge el problema?) 

La problemática se localiza en la convergencia crítica entre el sector salud y la ingeniería de software (mHealth). No es solo un problema de software, sino de diseño arquitectónico: las interfaces y los flujos de datos no están anclados a los protocolos clínicos del mundo real. Esta desconexión impide que las intervenciones digitales logren su objetivo principal: la reducción sostenida de los niveles de hemoglobina glicosilada (HbA1c) en el paciente. 

When (¿Cu.ándo sucede el problema?) 

El problema persiste de manera ininterrumpida durante todo el ciclo de vida del tratamiento, pero se agudiza drásticamente en el periodo ambulatorio. Es precisamente cuando el paciente sale del entorno controlado del consultorio cuando se pierde el control sobre la adherencia a la medicación y se omiten las señales tempranas de reacciones adversas, rompiendo la continuidad del cuidado médico. 

Why (¿Por qué sucede el problema?) 

Esta situación es consecuencia de una visión técnica limitada que prioriza el registro de números sobre la gestión de la salud. Las herramientas actuales carecen de módulos de retroalimentación profesional y sistemas de apoyo a la decisión clínica. Al no existir una infraestructura integral que conecte la ingesta de fármacos con las variaciones glicémicas, el ciclo terapéutico permanece abierto, impidiendo la identificación de riesgos antes de que se conviertan en complicaciones severas. 

How (¿Cómo sucede el problema?) 

El problema se manifiesta a través de un ecosistema de aplicaciones reactivas e interacciones aisladas. Las apps generan alertas genéricas e irrelevantes que el paciente termina ignorando. Según investigaciones recientes (Tang, 2024), la falta de un diseño interactivo que incluya recordatorios personalizados, soporte profesional y una experiencia de usuario (UX) consistente, degrada la retención del paciente y, por ende, la sostenibilidad de cualquier beneficio clínico inicial. 

How Much (¿Qué impacto tiene?) 

A escala global, la diabetes afecta a 830 millones de personas, con la cifra alarmante de que más del 50% no recibe una terapia adecuada. En el contexto local, IntegraVida identifica en Lima Metropolitana un mercado de alta densidad que requiere soluciones urgentes. Proyectamos que la implementación de GlucoSmart permitirá no solo reducir costos por complicaciones en un porcentaje significativo, sino también escalar la solución a nivel nacional, transformando la brecha de tratamiento en el Perú en un caso de éxito de salud digital distribuida.

### <a name="_toc226040388"></a>1.2.2 Lean UX Process
#### <a name="_toc226040389"></a>*1.2.2.1 Lean UX Problem Statements*

Actualmente, el manejo de enfermedades crónicas como la diabetes se caracteriza por la fragmentación de datos y el uso de silos de información. Las aplicaciones existentes (mHealth) se limitan al registro cuantitativo de glucosa, pero carecen de una conexión real con los protocolos clínicos y la trazabilidad terapéutica. 

Descripcion del Problema: 

- Problema: La desarticulación de datos y la falta de alertas preventivas en el monitoreo ambulatorio de pacientes diabéticos. 
- Afectados: Pacientes que sufren "fatiga de datos", médicos que trabajan bajo ensayo y error reactivo, y sistemas de salud que asumen altos costos por complicaciones evitables. 
- Impacto: Los pacientes pierden el control sobre su adherencia farmacológica al salir del consultorio, lo que impide la reducción sostenida de niveles de hemoglobina glicosilada. 
- Solución: Una infraestructura de software de código abierto que garantice la interoperabilidad y transforme los datos en activos clínicos accionables en tiempo real.

#### <a name="_toc226040390"></a>*1.2.2.2 Lean UX Assumption*

Para el desarrollo de la plataforma **GlucoSmart** bajo la startup IntegraVida, hemos formulado los siguientes supuestos (Assumptions) divididos en supuestos de negocio, del usuario y de las características del producto. Estos nos permitirán validar nuestro modelo y entender el contexto de uso de la aplicación web.

**Supuestos de Negocio (Business Assumptions):**

1. Creemos que nuestros clientes principales (hospitales, clínicas y consultorios privados) necesitan una plataforma unificada para el monitoreo integral de la diabetes.
2. Creemos que estas instituciones están dispuestas a adoptar un nuevo software si este demuestra optimizar el tiempo de consulta y reducir las complicaciones derivadas de una mala adherencia al tratamiento.
3. Creemos que el valor principal que ofrecemos a los centros de salud es la centralización de datos clínicos (glucosa, historial de medicación, farmacovigilancia), lo que permite una toma de decisiones médicas más certera y rápida.

**Supuestos del Usuario (User Assumptions):**

1. **¿Quién es el usuario?** Nuestros usuarios principales son, por un lado, pacientes con diabetes (tipo 1 y 2) que requieren un seguimiento constante; y por otro, doctores (endocrinólogos y médicos generales) encargados de su tratamiento.
2. **¿Dónde encaja el producto en su trabajo o vida?** Para los pacientes, encaja en su rutina diaria como una herramienta móvil/web para registrar sus niveles y recibir alertas; para los médicos, encaja en su flujo de trabajo clínico durante y entre las consultas para revisar la evolución del paciente.
3. **¿Qué problemas tiene nuestro producto y cómo los resuelve?** El problema actual es la fragmentación de la información y la falta de seguimiento de la adherencia y reacciones adversas. Nuestro producto resuelve esto al proporcionar un historial clínico consolidado e interactivo.
4. **¿Cuándo y cómo es usado nuestro producto?** El paciente lo usará diariamente para registrar la ingesta de medicamentos (adherencia) y los niveles de glucosa. El médico lo usará durante las consultas para revisar los reportes y tendencias, y recibirá alertas inmediatas en caso de riesgo de hipoglucemia severa o reacciones adversas.

**Supuestos de Características (Feature Assumptions):**

1. Creemos que la funcionalidad de **registro de farmacovigilancia y reacciones adversas** será una de las más valoradas por los doctores, ya que mejora la seguridad del paciente.
2. Creemos que el **módulo de recordatorios y control de adherencia** incrementará drásticamente la fidelidad de los pacientes a su tratamiento prescrito.
3. Creemos que la **generación de gráficos de tendencias automáticos** permitirá a los médicos optimizar el tiempo de diagnóstico y ajuste de dosis.

#### <a name="_toc226040391"></a>*12.2.3 Lean UX Hypothesis Statements*

A partir de nuestros supuestos, hemos formulado las siguientes declaraciones de hipótesis (Hypothesis Statements) que validaremos a lo largo del ciclo de desarrollo de **GlucoSmart**:

- **Hipótesis 1 (Focalizada en la Adherencia del Paciente):** Creemos que lograremos un _incremento en la adherencia a la medicación_ en un 30% dentro de los primeros 3 meses, si los _pacientes con diabetes_ logran _reducir sus episodios de olvido de medicación_ a través de la característica de _un sistema automatizado de alarmas y confirmación de consumo de medicamentos_.
- **Hipótesis 2 (Focalizada en la Eficiencia Médica):** Creemos que lograremos _reducir el tiempo de revisión de historial clínico en las consultas médicas_ en un 20%, si los _endocrinólogos y médicos generales_ logran _interpretar el estado del paciente en menos de 2 minutos_ mediante la característica de _un dashboard interactivo con gráficas de evolución de glucosa (HbA1c) y reportes de adherencia_.
- **Hipótesis 3 (Focalizada en la Farmacovigilancia):** Creemos que _reduciremos las complicaciones de salud evitables por cambios de tratamiento inadecuados_, si los _médicos tratantes_ logran _identificar rápidamente las reacciones adversas a la medicación_ mediante la característica de _un módulo de alertas inmediatas y registros de efectos adversos directamente vinculados a la historia clínica del paciente_.
- **Hipótesis 4 (Focalizada en la Comunicación):** Creemos que _aumentaremos la retención de pacientes en el uso de la plataforma_, si los _pacientes con diabetes_ logran _sentir un mayor acompañamiento médico_ a través de la característica de _compartir reportes en tiempo real con sus médicos y recibir sugerencias personalizadas.
#### <a name="_toc226040392"></a>*1.2.2.4 Lean UX Canvas*

![LeanUXCanvas](./Informe/assets/LeanUxCanvas.png)

## <a name="_toc226040393"></a>1.3 Segmento Objetivo

El éxito de GlucoSmart radica en su capacidad para interconectar a los actores principales del ecosistema de salud. Por ello, se han identificado dos segmentos objetivos primarios y uno secundario, definidos a partir de los hallazgos en las entrevistas y el análisis del dominio del problema.

#### 1.3.1 Segmento Primario 1: Pacientes con Diabetes Mellitus (Tipo 1 y 2)

Este segmento comprende a personas que requieren un control constante de sus niveles de glucosa y una gestión rigurosa de su medicación.

- **Perfil Demográfico:** Hombres y mujeres de 18 a 65 años, residentes en zonas urbanas con acceso a dispositivos móviles y conexión a internet.
- **Perfil Psicográfico:** Personas que buscan mayor autonomía en el manejo de su enfermedad, pero que experimentan frustración por el olvido de dosis o la falta de interpretación de sus datos clínicos.
- **Necesidades Críticas:** * Automatización de recordatorios de medicación para mejorar la adherencia.
    
    - Visualización clara (gráficos) de sus niveles de glucosa y hemoglobina glicosilada (HbA1c).
    - Un canal para reportar efectos adversos (farmacovigilancia) y recibir retroalimentación médica.
    - Consejos personalizados sobre nutrición y manejo del estrés.

#### 1.3.2 Segmento Primario 2: Médicos Especialistas y Personal de Salud

Este segmento incluye a endocrinólogos, médicos generales y personal de enfermería encargados del seguimiento de pacientes crónicos.

- **Perfil Profesional:** Médicos de clínicas privadas y hospitales que atienden una alta carga de pacientes con diabetes mensualmente (como el caso del Dr. Walter Gómez, con 40 años de experiencia).
- **Necesidades Críticas:**
    
    - Acceso a una historia clínica centralizada y actualizada en tiempo real.
    - Herramientas de análisis de tendencias para optimizar el tiempo de consulta.
    - Sistemas de alertas tempranas ante crisis de hipoglucemia o hiperglucemia para prevenir daños orgánicos.
    - Registro estructurado de reacciones adversas a medicamentos para ajustar tratamientos de forma segura

# <a name="_toc226040394"></a>Capitulo II: Requirements Elicitation & Analysis
## <a name="_toc226040395"></a>2.1 Competidores

Para comprender el posicionamiento de **GlucoSmart** en el mercado de la salud digital, se ha realizado un análisis competitivo identificando a los principales actores actuales que ofrecen soluciones para el manejo de la diabetes y la integración de datos de salud. A continuación, se detallan los principales competidores directos e indirectos:

#### 1. mySugr

- **Descripción:** Es una de las aplicaciones líderes a nivel mundial para el control de la diabetes. Permite a los pacientes registrar sus niveles de glucosa en sangre, comidas, medicación y actividad física.
- **Fortalezas:** Cuenta con un alto nivel de usabilidad, gamificación para motivar al paciente, y una calculadora de bolos de insulina muy precisa. Además, permite generar informes en PDF o Excel para ser compartidos con los médicos.
- **Debilidades (Oportunidad para GlucoSmart):** mySugr está orientada principalmente al paciente de forma individual. Carece de un entorno o _dashboard_ integral a nivel hospitalario que consolide historiales médicos masivos, y no cuenta con un módulo de farmacovigilancia automatizado para alertar a los médicos sobre reacciones adversas a medicamentos específicos.

#### 2. SocialDiabetes

- **Descripción:** Es una plataforma de origen español orientada al control de la diabetes tipo 1 y 2. Destaca por tener la certificación de dispositivo médico (CE) y busca conectar la información del paciente con el personal sanitario.
- **Fortalezas:** Permite sincronizar datos directamente con múltiples glucómetros y monitores continuos de glucosa (MCG). Ofrece una interfaz tanto para el paciente como para el profesional de la salud, permitiendo ajustes en el tratamiento de manera remota.
- **Debilidades (Oportunidad para GlucoSmart):** Su enfoque es predominantemente insulinodependiente. Además, algunas de las funcionalidades más importantes para las clínicas y la conexión en tiempo real están reservadas para planes corporativos de muy alto costo, lo que dificulta su adopción en clínicas emergentes o de presupuesto moderado.

#### 3. Glucose Buddy

- **Descripción:** Aplicación de registro de salud centrada en el paciente que permite el seguimiento del azúcar en la sangre, los medicamentos administrados, los resultados del laboratorio (como la HbA1c) y la presión arterial.
- **Fortalezas:** Posee una curva de aprendizaje corta y un sistema de recordatorios muy eficiente para que los usuarios no olviden registrar sus datos diarios ni tomar su medicación.
- **Debilidades (Oportunidad para GlucoSmart):** Funciona como un diario electrónico personal y no como una base de datos relacional médica. No facilita una comunicación bidireccional ágil con el médico tratante, y la gestión de dietas o el reporte de efectos adversos está muy limitado, dejando de lado el seguimiento clínico integral.

#### Ventaja Competitiva de GlucoSmart (IntegraVida)

A diferencia de los competidores mencionados, que actúan principalmente como diarios digitales o herramientas aisladas para el usuario final, **GlucoSmart** se posiciona como una solución integral _B2B2C_. Nuestra plataforma destaca por su robusta arquitectura de base de datos relacional orientada no solo al registro, sino al **control de la adherencia** y a la **farmacovigilancia**. Al proporcionar a los hospitales y consultorios un historial clínico centralizado y alertas inmediatas ante reacciones adversas, GlucoSmart empodera la toma de decisiones clínicas y garantiza la seguridad del paciente de manera más efectiva que las aplicaciones convencionales.
### <a name="_toc226040396"></a>2.1.1 Analisis Competitivo

| **Perfil**                   | **Su Startup: IntegraVida (GlucoSmart)**                                                  | **Competidor 1: mySugr**                                                       | **Competidor 2: SocialDiabetes**                                                | **Competidor 3: Glucose Buddy**                                    |
| ---------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Logo / Nombre**            | **IntegraVida**                                                                           | **mySugr**                                                                     | **SocialDiabetes**                                                              | **Glucose Buddy**                                                  |
| **Overview**                 | Plataforma integral B2B2C para el monitoreo de diabetes con enfoque en farmacovigilancia. | Aplicación móvil enfocada en el registro diario y gamificación para pacientes. | Plataforma certificada para la interconexión de dispositivos y ajuste de dosis. | Diario digital para el seguimiento de métricas de glucosa y dieta. |
| **Ventaja Competitiva**      | Centralización de historial clínico para médicos y alertas de reacciones adversas.        | Interfaz altamente intuitiva y "monstruo" de diabetes para gamificación.       | Alta compatibilidad con hardware (glucómetros y bombas) y certificación CE.     | Simplicidad de uso y amplia base de datos de alimentos.            |
| **Mercado Objetivo**         | Clínicas, hospitales, endocrinólogos y pacientes crónicos.                                | Pacientes con diabetes tipo 1 y 2 que buscan autogestión.                      | Usuarios avanzados que requieren sincronización con dispositivos médicos.       | Usuarios que buscan un registro manual sencillo y gratuito.        |
| **Estrategias de Marketing** | Venta directa a instituciones de salud y marketing de contenidos médicos.                 | Alianzas con farmacéuticas (Roche) y posicionamiento en App Stores.            | Enfoque en certificaciones médicas y prescripción por profesionales.            | Modelo Freemium con publicidad y presencia orgánica en móviles.    |
| **Productos & Servicios**    | Dashboard médico, App para pacientes, Módulo de Farmacovigilancia.                        | Diario de azúcar, Calculadora de bolos, Reportes médicos.                      | Registro de carbohidratos, Conector en la nube, Telemedicina.                   | Diario de glucosa, seguimiento de presión arterial y peso.         |
| **Precios & Costos**         | Modelo SaaS por suscripción institucional o premium para pacientes.                       | Gratis (Básico) / Suscripción Pro (SaaS).                                      | Suscripción mensual/anual para funciones premium.                               | Gratuito con anuncios / Versión Premium sin anuncios.              |
| **Canales de Distribución**  | Web (Panel Médico) y Móvil (Paciente).                                                    | Principalmente Móvil (iOS/Android).                                            | Web y Móvil.                                                                    | Móvil (iOS/Android).                                               |
#### Análisis SWOT (FODA)

**1. IntegraVida (Su Startup)**

- **Fortalezas:** Base de datos relacional robusta, enfoque único en farmacovigilancia, interoperabilidad médico-paciente.
- **Debilidades:** Marca nueva en el mercado, dependencia de la adopción por parte de instituciones médicas.
- **Oportunidades:** Creciente digitalización del sector salud en la región, falta de herramientas que consoliden reacciones adversas.
- **Amenazas:** Regulaciones gubernamentales estrictas sobre datos de salud (Ley de Protección de Datos Personales).

**2. mySugr**

- **Fortalezas:** Gran base de usuarios, respaldo de Roche, excelente experiencia de usuario (UX).
- **Debilidades:** Poca profundidad en el análisis de farmacovigilancia para el médico.
- **Oportunidades:** Expansión a mercados emergentes.
- **Amenazas:** Nuevas aplicaciones con IA que automaticen el registro sin intervención del usuario.

**3. SocialDiabetes**

- **Fortalezas:** Certificaciones sanitarias europeas, conectividad con hardware médico.
- **Debilidades:** Costo elevado para integración en clínicas pequeñas.
- **Oportunidades:** Alianzas con sistemas de salud pública.
- **Amenazas:** Competencia directa de fabricantes de glucómetros que lanzan sus propias apps.

**4. Glucose Buddy**

- **Fortalezas:** Facilidad de uso, marca establecida desde los inicios de las App Stores.
- **Debilidades:** Funcionalidades limitadas para el seguimiento médico profesional.
- **Oportunidades:** Mejora de su plataforma web para telemedicina.
- **Amenazas:** Pérdida de usuarios que migran a apps más especializadas o gamificadas.
### <a name="_toc226040397"></a>2.1.2 Estrategia y tácticas frente a competidores

Para asegurar la penetración en el mercado de **IntegraVida** frente a los competidores analizados, se plantean las siguientes estrategias:

1. **Diferenciación Técnica (Frente a mySugr y Glucose Buddy):**
    
    - Mientras los competidores se centran en el "diario del paciente", nuestra táctica será el **"Ecosistema de Decisiones Clínicas"**. Implementaremos reportes automáticos de farmacovigilancia que los competidores no poseen, permitiendo que el médico identifique si un síntoma es una reacción adversa al medicamento, algo que las apps de registro manual ignoran.
    
2. **Estrategia de Alianzas Institucionales (Frente a SocialDiabetes):**
    
    - En lugar de competir solo por el usuario final, IntegraVida buscará convenios con clínicas locales para que el uso de **GlucoSmart** sea el estándar de seguimiento en sus consultas. La táctica incluye ofrecer un "Dashboard de Gestión" gratuito para el médico por cada _N_ pacientes referidos, facilitando la adopción tecnológica en centros de salud.
    
3. **Táctica de Contenido y Confianza:**
    
    - Publicaremos casos de estudio sobre cómo la centralización de datos en una base de datos relacional (nuestra arquitectura) reduce errores en la prescripción, atacando la debilidad de las aplicaciones "diario" que mantienen la información aislada del flujo de trabajo del doctor.
    
4. **Optimización de Canales:**
    
    - A diferencia de mySugr, que es casi 100% móvil, fortaleceremos nuestra **plataforma Web** con visualizaciones de datos complejas (gráficos de tendencia de HbA1c), orientadas específicamente a la pantalla del consultorio médico, mejorando la experiencia de revisión en la cita presencial o virtual.

## <a name="_toc226040398"></a>2.2 Entrevistas

### <a name="_toc226040399"></a>2.2.1 Diseño de entrevistas

Segmento 1: Pacientes con Diabetes 

1. ¿Cómo describes tu experiencia diaria gestionando su diabetes con las herramientas o apps que usa actualmente?.
2. ¿Ha sentido alguna vez "fatiga de datos" o agotamiento por tener que registrar manualmente sus niveles de glucosa constantemente?  
3. ¿Qué tan difícil le resulta mantener el control y la adherencia a sus medicamentos cuando se encuentra fuera del consultorio o centro médico?  
4. ¿Siente que las apps actuales le brindan alertas preventivas realmente útiles antes de sufrir una crisis o descompensación?  
5. ¿Alguna vez ha ignorado notificaciones de salud por considerarlas poco relevantes para su situación específica?  
6. ¿Le resultaría valioso que sus registros de glucosa se cruzaran automáticamente con los horarios en que toma sus medicamentos?  
7. ¿Qué opina de la posibilidad de que su médico pueda visualizar sus datos en tiempo real sin esperar a su próxima cita presencial? 
8. ¿Estaría dispuesto a usar nuestra nueva app que garantice la transparencia y la seguridad de su información médica?  
9. ¿Cómo cree que mejoraría su calidad de vida si tuviera una visión completa de su tratamiento (dieta, medicamentos, glucosa) en una sola aplicación?  
10. Al conocer la propuesta de GlucoSmart, ¿qué función le parece que resolvería mejor sus problemas diarios?  
11. ¿Qué otras funciones no anunciadas en la propuesta de la app le gustaría agregar y cómo le resultaría de uso importante?  
12. ¿Estaría dispuesto a usar GlucoSmart como su herramienta principal de gestión de glucosa si estuviera disponible hoy mismo? 

Segmento 2: Doctores 

1. ¿Qué tan complicado le resulta a usted realizar ajustes terapéuticos precisos utilizando solo los datos manuales que el paciente trae a consulta? 
2. ¿Considera que los actuales silos de información en salud dificultan obtener una visión más precisa de la condición de sus pacientes? 
3. ¿Cómo afecta a su diagnóstico el hecho de recibir datos recolectados de forma asíncrona y sin un contexto clínico real? 
4. ¿Ha sentido que su tratamiento a veces se basa en realizar ensayo y error debido a la falta de trazabilidad del paciente? 
5. ¿Qué importancia le asigna a la brecha existente entre lo que usted recomienda a sus pacientes y lo que el paciente realmente consume en su periodo ambulatorio? 
6. ¿Cree que una app o plataforma facilitaría la integración de datos entre diferentes instituciones de salud? 
7. ¿Qué valor le daría a contar con herramientas de analítica de datos en tiempo real para apoyar su toma de decisiones clínicas? 
8. ¿De qué manera una app podría mejorar la precisión en el seguimiento de enfermedades crónicas que suelen considerarse complejas? 
9. ¿Le interesaría una plataforma que conecte directamente el sistema de farmacovigilancia con las variaciones glicémicas del paciente? 
10. ¿Cómo evaluaría una solución digital cuyo diseño esté estrictamente anclado a los protocolos clínicos del mundo real? 
11. ¿Considera que acceder a datos accionables en tiempo real ayudaría a reducir las complicaciones severas y los costos operativos en salud? 
12. ¿Integraría GlucoSmart en su flujo de trabajo clínico si esto le permitiera cerrar el ciclo terapéutico de manera proactiva?
### <a name="_toc226040400"></a>2.2.2 Registro de entrevista

- Entrevista a Pacientes con Diabetes (Segmento 1)
	
	Nombre: Jorge
	Apellidos: Quispe 
	Edad: 19 años
	Distrito: San Miguel
	
	![](./Informe/assets/CapturaEntrevista1.png)
	
	[Entrevista_a_Paciente01.mp4](https://youtu.be/siAso9B_aSc)
	
	- Resumen de la entrevista a Paciente
	
	La entrevista fue realizada a Jorge Quispe, de 19 años y residente de San Miguel, quien fue diagnosticado con diabetes tipo 2 hace aproximadamente 7 u 8 años.
	
	Control de Glucosa y Medicación:
	
	- Medición: Mide sus niveles de glucosa diariamente, por las mañanas, utilizando un glucómetro.
	- Episodios: En el último mes, experimentó dos episodios de hiperglucemia.
	- Medicamentos: Actualmente utiliza metformina y glibenclamida.
	- Adherencia: Ocasionalmente olvida o retrasa una dosis, lo que ocurre aproximadamente una o dos veces al mes.
	- Efectos Secundarios: Ha experimentado efectos secundarios leves, como mareos.
	
	Hábitos y Estilo de Vida:
	
	- Actividad Física: Realiza actividad física tres veces por semana, saliendo a caminar y a andar en bicicleta.
	- Alimentación: Sigue una dieta con restricción de azúcares y frituras.
	- Factores Adicionales: El estrés afecta sus niveles de glucosa, causando un aumento.
	
	Uso de Tecnología y Apoyo Digital:
	
	- Recordatorios: Le gustaría recibir recordatorios para la toma de medicamentos.
	- Visualización de Datos: Le parece útil ver gráficos de la evolución de su glucosa para monitorear su salud.
	- Recomendaciones: Le gustaría que una aplicación le sugiera recetas y recomendaciones personalizadas.
	- Compartir Datos: Estaría dispuesto a compartir sus datos de salud con su médico a través de una aplicación para facilitar las consultas.
	
	Sugerencia de Valor Añadido: Propone la adición de un chat en la aplicación con profesionales (nutricionistas o doctores) para resolver dudas rápidas, lo que le brindaría mayor confianza.

- Entrevista a Pacientes con Diabetes (Segmento 1)
    
    Nombre: Virgilia
    Apellidos: Velasque Huarcalla
	Edad: 49 años
	
	![](./Informe/assets/CapturaEntrevista2.png)
	
	Distrito: callao
	[Entrevista a paciente 02.mp4](https://youtu.be/RhP6C_cGmqs)
	
	- Resumen de la entrevista a Paciente
    
	La entrevista fue realizada a Virgilia Velasque, de 49 años y residente del Callao, quien fue diagnosticada con diabetes tipo 2 hace aproximadamente 15 años.
	
	Control de Glucosa y Medicación:
	
	- Medición: Mide sus niveles de glucosa cada 2-3 meses, dependiendo de cómo se siente, utilizando un glucómetro en postas o farmacias.
	- Episodios: A lo largo de 15 años ha tenido dos episodios de hipoglucemia.
	- Medicamentos: Uso metformina durante 10 años; desde hace 6 meses cambio a otra medicación.
	- Adherencia: En los primeros años tomaba tratamiento de forma desordenada, pero desde hace 6 años cumple al pie de la letra las indicaciones de su médico.
	- Efectos Secundarios: Con la metformina tuvo ardor gástrico; con la nueva medicación presentó maremotos leves, que con el tiempo disminuyeron por la adaptación de su propio cuerpo.
	
	Hábitos y Estilo de Vida:
	
	- Actividad Física: Hace 6 años realizaba ejercicio con el peso corporal y desde hace 1 año y medio entrena con pesas, principalmente para controlar sus niveles de estrés.
	- Alimentación: Su dieta se basa en un mayor consumo de proteínas y verduras, con baja ingesta de carbohidratos; solo en raras ocasiones consume grandes cantidades de estos
	- Factores Adicionales: El estrés afecta directamente sus niveles de glucosa, generando descompensaciones y falta de sueño.
	
	Uso de Tecnología y Apoyo Digital:
	
	- Recordatorios: Considera muy útil recibir alarmas o recordatorios que le ayuden a no olvidar la toma de sus medicamentos.
	- Visualización de Datos: Le interesa contar con gráficos que muestran cómo evoluciona o se dispara su glucosa a lo largo del tiempo.
	- Recomendaciones:Le gustaría recibir sugerencias personalizadas relacionadas con su tratamiento, principalmente enfocadas en alarmas para recordar la medicación.
	- Compartir Datos: Vería beneficioso poder compartir sus registros directamente con el médico a través de la aplicación, especialmente en citas virtuales personalizadas.
	- Sugerencia de Valor Añadido: Destaca la importancia de contar con citas virtuales enfocadas en el paciente, pues le dan mayor confianza y apoyo en su control.

- Entrevista a Pacientes con Diabetes (Segmento 1)
	
	Nombre: Andy Jermy Ascalla Venancio
	Edad: 18
	Distrito: San Martin de Porres
	
	![](./Informe/assets/CapturaEntrevista3.png)
	
	[Entrevista a paciente 03.mp4](https://youtu.be/rn8sOZuT5MM)
	
	Resumen de la entrevista a Paciente
	
	La entrevista fue realizada a Andy Jermy Ascalla Venancio, de 18 años y residente de San Miguel, quien fue diagnosticado con diabetes tipo 1 hace aproximadamente 5  años.
	
	Control de Glucosa y Medicación:
	
	- Medición: Mide sus niveles de glucosa diariamente, por las mañanas, utilizando un glucómetro.
	- Episodios: En el último mes, experimentó dos episodios de hiperglucemia.
	- Medicamentos: Actualmente utiliza metformina y glibenclamida.
	- Adherencia: Ocasionalmente olvida o retrasa una dosis, lo que ocurre aproximadamente una o dos veces al mes.
	- Efectos Secundarios: Ha experimentado efectos secundarios leves, como mareos.
	
	Hábitos y Estilo de Vida:
	
	- Actividad Física: Realiza actividad física tres veces por semana, saliendo a caminar y a andar en bicicleta.
	- Alimentación: Sigue una dieta con restricción de azúcares y frituras.
	- Factores Adicionales: El estrés afecta sus niveles de glucosa, causando un aumento.
	
	Uso de Tecnología y Apoyo Digital:
	
	- Recordatorios: Le gustaría recibir recordatorios para la toma de medicamentos.
	- Visualización de Datos: Le parece útil ver gráficos de la evolución de su glucosa para monitorear su salud.
	- Recomendaciones: Le gustaría que una aplicación le sugiera recetas y recomendaciones personalizadas.
	- Compartir Datos: Estaría dispuesto a compartir sus datos de salud con su médico a través de una aplicación para facilitar las consultas.

- Entrevista a medicos (Segmento 2
	
	Nombre: Walter
	Apellidos: Gomez Navarro
	Edad: 70 años
	Distrito: La Molina
	
	![](./Informe/assets/CapturaEntrevista4.png)
	
	[Entrevista a medico 01.mp4](https://youtu.be/O9gIC_WXCfg)
	
	- Resumen de la entrevista a Paciente
	
	La entrevista se realizó con Walter Gómez Navarro (70), médico con 40 años de experiencia. Destaca la hemoglobina glicosilada como clave en el control de la diabetes, señala problemas de adherencia al tratamiento y considera muy útiles los gráficos y alertas en tiempo real para prevenir riesgos.
	
	Manejo de la diabetes: 
	
	- Pacientes atendidos: 5 pacientes diabéticos mensuales
	- Monitoreo de glucosa: Revisión cada 3 meses.
	- Métodos: Benedict (menos preciso) y hemoglobina glicosilada (HbA1c), considerado el estándar internacional, porque refleja el promedio de glucosa de los últimos 3 meses.
	- Indicadores clave: HbA1c por debajo de 7 indica buen control; por encima, diabetes mal controlada.
	- Registro: Historia clínica como unidad central, complementada con bases de datos personales y hojas Excel.
	
	Tratamiento y adherencia:
	
	- Adherencia: Problema frecuente, muchos pacientes olvidan la medicación.. Un olvido aislado no es grave, pero múltiples omisiones desencadenan riesgo de hiperglucemia, coma diabético y estado premortem.
	- Ajustes de tratamiento: Según evolución del paciente. Dificultad: los pacientes no cumplen dietas y fallan los hipoglucemiantes orales.
	- Efectos adversos: Considera muy importante registrarlos. 
	
	Uso de Tecnología y Apoyo Digital:
	
	- Dispositivos: Recomienda glucómetros de punción digital.
	- Datos en gráficos: Considera que ver tendencias gráficas de glucosa es muy útil para entender la evolución del paciente rápidamente. Incluso lo ve como indicador de calidad en la práctica médica.
	- Alertas inmediatas: Considera esencial recibir avisos de hipoglucemia para la prevención de daños cerebrales, cardíacos, hepáticos y renales, además de riesgo de muerte.

### <a name="_toc226040401"></a>2.2.3 Analisis de entrevista

Tras el procesamiento de las entrevistas realizadas a los segmentos de pacientes y al médico especialista (Dr. Walter Gómez), se han identificado patrones críticos que justifican la arquitectura y funcionalidades de **GlucoSmart**. El análisis se divide en los siguientes hallazgos clave, los cuales son la base directa para las Historias de Usuario de nuestro Product Backlog:

1. **Deficiencia en la Adherencia y Necesidad de Automatización:** Los pacientes jóvenes (Jorge y Andy, 18-19 años) reportan olvidos mensuales de medicación, mientras que Virgilia (49 años) destaca la importancia de las alarmas. El Dr. Gómez advierte que estos olvidos "aislados" incrementan el riesgo de coma diabético. Esto valida la prioridad alta de un **sistema automatizado de recordatorios**.
2. **Monitoreo Basado en Evidencia y Tendencias:** El Dr. Gómez señala que la revisión cada 3 meses debe basarse en la hemoglobina glicosilada (HbA1c) y tendencias gráficas, ya que son indicadores de calidad. Los tres pacientes entrevistados solicitaron ver su evolución visualmente en lugar de datos aislados. Esto justifica la creación de un **Dashboard de Tendencias** interactivo.
3. **Gestión de Seguridad del Paciente: Farmacovigilancia:** Se identificaron efectos secundarios reales: ardor gástrico en Virgilia y mareos en Jorge. El Dr. Gómez califica como "esencial" recibir alertas inmediatas de hipoglucemia para prevenir daños cerebrales o muerte. Estos hallazgos fundamentan el **Registro de Efectos Adversos** y el **Sistema de Alertas Críticas** en tiempo real.
4. **Colaboración y Telemedicina:** Los pacientes expresaron su total disposición a compartir datos para facilitar consultas virtuales (especialmente Virgilia y Jorge). Jorge propuso un chat directo con profesionales para resolver dudas rápidas, lo que incrementaría su confianza. Esto da soporte al **Módulo de Compartición de Datos** y al **Chat de Consultas**.
5. **Educación y Factores Externos:** El análisis reveló que el estrés afecta directamente los niveles de glucosa de todos los pacientes. Jorge y Andy solicitaron recetas y recomendaciones personalizadas. Esto justifica la inclusión de **Sugerencias de Estilo de Vida** para un manejo integral de la enfermedad.
## <a name="_toc226040402"></a>2.3 Needfinding

### <a name="_toc226040403"></a>2.3.1 User Personas

User Persona Segmento 2:
![UserPersonaSegmento1](./Informe/assets/UserPersona1.png)

User Persona Segmento 1:
![UserPersonaSegmento2](./Informe/assets/UserPersona2.png)

### <a name="_toc226040404"></a>2.3.2 User Task Matrix

| **Segmento** | **Tarea Principal**   | **Descripción**                                                  | **Frecuencia**         |
| ------------ | --------------------- | ---------------------------------------------------------------- | ---------------------- |
| **Paciente** | Registro de Glucosa   | Ingreso manual o sincronizado de niveles medidos con glucómetro. | Diaria (Mañanas)       |
| **Paciente** | Confirmación de Dosis | Notificar al sistema la ingesta de la medicación prescrita.      | Diaria (Según receta)  |
| **Paciente** | Reporte de Síntomas   | Registrar mareos, ardor u otros efectos secundarios.             | Ocasional (Evento)     |
| **Médico**   | Revisión de Dashboard | Analizar gráficos de tendencias y HbA1c del paciente.            | Trimestral (Consulta)  |
| **Médico**   | Atención de Alertas   | Evaluar notificaciones críticas de hipoglucemia severa.          | Inmediata (Emergencia) |
| **Médico**   | Ajuste de Tratamiento | Modificar medicación basándose en el historial de adherencia.    | Trimestral / Remoto    |
### <a name="_toc226040405"></a>2.3.3 User Journey Mapping

| **Etapa**      | **Acciones**                                                  | **Pensamientos**                                       | **Emociones**         | **Oportunidades**                                     |
| -------------- | ------------------------------------------------------------- | ------------------------------------------------------ | --------------------- | ----------------------------------------------------- |
| **Registro**   | Crea cuenta y configura su medicación y metas de glucosa.     | "¿Será difícil configurar todas mis pastillas?"        | Ansiedad / Esperanza  | Tutorial guiado y carga masiva de medicamentos.       |
| **Uso Diario** | Recibe alertas, confirma toma de medicina y registra glucosa. | "Es bueno que la app me recuerde, a veces se me pasa." | Alivio / Control      | Gamificación por días de adherencia perfecta.         |
| **Crisis**     | Siente mareo y registra el síntoma y un nivel bajo en la app. | "Me siento mal, ¿qué debo hacer ahora?"                | Preocupación / Miedo  | Botón de pánico o guía rápida de primeros auxilios.   |
| **Consulta**   | Comparte el acceso de sus datos con el Dr. Walter.            | "Ahora mi doctor verá exactamente qué pasó este mes."  | Confianza / Seguridad | Generación de reporte PDF profesional para el médico. |

### <a name="_toc226040406"></a>2.3.4 Empathy Mapping

![EmpathyMapSegmento1](./Informe/assets/EmpathyMap1.png)

![EmpathyMapSegmento2](./Informe/assets/EmpathyMap2.png)
## <a name="_toc226040407"></a>2.4 Big Picture Event Storming

![EventStorming|601](./Informe/assets/EventStorming.jpg)

El análisis de _Big Picture Event Storming_ se ha realizado con el objetivo de comprender la complejidad del dominio de la gestión de la diabetes y la farmacovigilancia. Esta dinámica nos permitió visualizar cronológicamente cómo interactúan los pacientes, los médicos y el sistema a lo largo del proceso de tratamiento.

Para este análisis se ha definido la siguiente leyenda estándar:

- **Actores (Amarillo):** Quién ejecuta la acción (Paciente, Médico, Sistema Automatizado).
- **Comandos (Azul):** La intención o acción ejecutada (Ej. "Registrar Glucosa")
- **Eventos de Dominio (Naranja):** El resultado inmutable en tiempo pasado (Ej. "Glucosa Registrada").
- **Sistemas Externos (Rosado):** Servicios de terceros (Ej. "Servicio de Notificaciones Push").
- **Modelos de Lectura (Verde):** La información que el actor visualiza para tomar decisiones (Ej. "Dashboard de Tendencias").

#### Flujo Cronológico del Dominio (GlucoSmart)

El flujo del negocio se ha dividido en cuatro fases principales, basadas en las necesidades identificadas en las entrevistas de validación:

**Fase 1: Configuración Inicial y Vinculación**

- **Actor:** Paciente / Médico.
    
- **Comando:** Crear cuenta de usuario $\rightarrow$ **Evento:** Cuenta Creada.
    
- **Comando:** Configurar plan de medicación $\rightarrow$ **Evento:** Plan de Medicación Establecido.
    
- **Comando:** Generar código de acceso clínico $\rightarrow$ **Evento:** Código de Acceso Generado.
    
- **Comando:** Ingresar código de paciente $\rightarrow$ **Evento:** Paciente Vinculado al Médico.
    

**Fase 2: Monitoreo Diario y Adherencia (Prevención de Olvidos)**

- **Actor:** Sistema Automatizado.
- **Comando:** Evaluar horario de medicación $\rightarrow$ **Evento:** Recordatorio Disparado.
- **Sistema Externo:** Servicio de Notificaciones Push notifica al usuario.
- **Actor:** Paciente.
- **Comando:** Confirmar ingesta de medicamento $\rightarrow$ **Evento:** Medicación Confirmada.
- **Comando:** Ingresar nivel de glucosa matutino $\rightarrow$ **Evento:** Medición de Glucosa Registrada.

**Fase 3: Farmacovigilancia y Gestión de Crisis**

- **Actor:** Paciente.
- **Modelo de Lectura:** Formulario de síntomas.
- **Comando:** Registrar reacción adversa (Ej. mareos/ardor) $\rightarrow$ **Evento:** Efecto Adverso Registrado.
- **Actor:** Sistema Automatizado.
- **Comando:** Evaluar umbral de riesgo clínico $\rightarrow$ **Evento:** Límite de Hipoglucemia Excedido.
- **Comando:** Generar alerta de riesgo $\rightarrow$ **Evento:** Alerta Crítica Generada.
- **Sistema Externo:** Servicio de Mensajería (Email/SMS) envía aviso al médico tratante.

**Fase 4: Consulta y Ajuste de Tratamiento**

- **Actor:** Médico (Ej. Dr. Gómez).
- **Modelo de Lectura:** Dashboard de Tendencias de HbA1c y Registro de Farmacovigilancia.
- **Comando:** Visualizar evolución trimestral $\rightarrow$ **Evento:** Historial Clínico Consultado.
- **Comando:** Modificar dosis o tipo de medicamento $\rightarrow$ **Evento:** Tratamiento Ajustado.
- **Actor:** Sistema Automatizado.
- **Comando:** Actualizar plan del paciente $\rightarrow$ **Evento:** Plan de Medicación Actualizado (Cierra el ciclo volviendo a la Fase 2).

#### Análisis de Puntos Críticos (Cuellos de Botella)

Durante el Event Storming, se identificaron dos áreas de fricción (representadas con notas adhesivas rojas en el diseño visual) que el software debe mitigar de forma prioritaria:

1. **Fricción en el Registro Manual:** La dependencia de que el paciente ingrese manualmente sus niveles de glucosa puede generar vacíos en la base de datos.
2. **Tiempo de Reacción ante Alertas:** La alerta crítica de hipoglucemia debe ser bidireccional; si el médico no está disponible de inmediato, el sistema debe proporcionar instrucciones de primeros auxilios básicas al paciente para mitigar el daño orgánico inmediato.
## <a name="_toc226040408"></a>2.5 Ubiquitous Language

El lenguaje ubicuo del proyecto **GlucoSmart** define los términos clave que serán utilizados de manera consistente a lo largo del análisis, diseño e implementación del sistema. Este glosario permite que todos los integrantes del equipo compartan una misma comprensión del dominio de negocio relacionado con el monitoreo y control de la diabetes.

### Términos generales

**1. Platform (Plataforma):**  
Sistema digital de GlucoSmart que permite centralizar la información clínica del paciente y facilitar la interacción con el doctor.

**2. Patient (Paciente):**  
Persona con diabetes que utiliza la plataforma para registrar su información de salud, recibir seguimiento y controlar su tratamiento.

**3. Doctor (Doctor):**  
Profesional de salud encargado de revisar la información del paciente, brindar seguimiento médico y tomar decisiones clínicas.

**4. Diabetes Management (Gestión de la diabetes):**  
Proceso de control, seguimiento y tratamiento continuo de la diabetes mediante registros clínicos, monitoreo y atención médica.

**5. Clinical Information (Información clínica):**  
Conjunto de datos relacionados con el estado de salud del paciente, tales como niveles de glucosa, síntomas, medicamentos y observaciones médicas.

**6. Treatment (Tratamiento):**  
Plan médico definido para el paciente, que incluye medicamentos, indicaciones y controles necesarios para el manejo de la diabetes.

**7. Monitoring (Monitoreo):**  
Seguimiento continuo de los datos de salud del paciente registrados dentro de la plataforma.

**8. Clinical Record (Registro clínico):**  
Historial digital donde se almacena la información médica relevante del paciente para su consulta y seguimiento.

---

### Perfil de usuario – Paciente

**1. Glucose Level (Nivel de glucosa):**  
Valor registrado en la plataforma para representar la concentración de glucosa del paciente en sangre.

**2. Glucose Log (Registro de glucosa):**  
Historial de mediciones de glucosa ingresadas por el paciente para el control de su estado de salud.

**3. Medication (Medicamento):**  
Fármaco indicado al paciente para controlar la diabetes o tratar condiciones relacionadas.

**4. Medication Intake (Toma de medicación):**  
Acción de registrar el consumo de un medicamento en la plataforma.

**5. Symptom (Síntoma):**  
Malestar o señal física reportada por el paciente durante su tratamiento o seguimiento.

**6. Treatment Adherence (Adherencia al tratamiento):**  
Nivel de cumplimiento del paciente respecto a las indicaciones médicas, medicamentos y controles establecidos.

**7. Reminder (Recordatorio):**  
Notificación generada por el sistema para avisar al paciente sobre la toma de medicamentos, controles o citas médicas.

**8. Alert (Alerta):**  
Aviso emitido por la plataforma cuando se detecta una situación que requiere atención, como una medición fuera del rango esperado.

**9. Appointment (Cita médica):**  
Encuentro programado entre el paciente y el doctor para revisión, seguimiento o evaluación del tratamiento.

**10. Health History (Historial de salud):**  
Conjunto de registros del paciente relacionados con su evolución, controles, síntomas y tratamiento.

---

### Perfil de usuario – Doctor

**1. Clinical Review (Revisión clínica):**  
Proceso mediante el cual el doctor analiza la información registrada por el paciente en la plataforma.

**2. Diagnosis (Diagnóstico):**  
Determinación médica sobre la condición de salud del paciente a partir de su evaluación clínica.

**3. Prescription (Prescripción):**  
Indicación médica que define qué medicamentos debe tomar el paciente, en qué dosis y con qué frecuencia.

**4. Clinical Follow-up (Seguimiento clínico):**  
Supervisión periódica realizada por el doctor sobre el estado de salud y evolución del paciente.

**5. Therapeutic Adjustment (Ajuste terapéutico):**  
Modificación del tratamiento en función de la evolución clínica y los datos registrados en la plataforma.

**6. Medical Observation (Observación médica):**  
Comentario o anotación realizada por el doctor sobre el estado, avance o respuesta del paciente al tratamiento.

**7. Medical Decision (Decisión médica):**  
Acción clínica tomada por el doctor a partir de la información analizada en el sistema.

**8. Appointment Schedule (Agenda de citas):**  
Listado de citas médicas programadas que permite al doctor organizar su seguimiento con los pacientes.

---

### Gestión del tratamiento y seguimiento

**1. Dose (Dosis):**  
Cantidad específica de medicamento que el paciente debe consumir según la prescripción médica.

**2. Frequency (Frecuencia):**  
Número de veces o intervalo en el que el paciente debe tomar su medicación.

**3. Schedule (Horario):**  
Momento definido para la toma de medicamentos, controles o citas médicas.

**4. Medical Report (Reporte médico):**  
Resumen organizado de la información clínica del paciente en un periodo determinado.

**5. Traceability (Trazabilidad):**  
Capacidad del sistema para registrar y seguir la evolución del paciente y el cumplimiento de su tratamiento a lo largo del tiempo.

**6. Follow-up History (Historial de seguimiento):**  
Registro cronológico de revisiones, observaciones y cambios realizados durante el control médico del paciente.

---

### Alertas y control de riesgos

**1. Risk Alert (Alerta de riesgo):**  
Notificación emitida cuando el sistema detecta una posible situación peligrosa para la salud del paciente.

**2. Adverse Effect (Efecto adverso):**  
Reacción no deseada que puede presentarse en el paciente como consecuencia de un medicamento o tratamiento.

**3. Preventive Notification (Notificación preventiva):**  
Aviso generado para anticipar posibles complicaciones y promover una acción oportuna.

**4. Clinical Event (Evento clínico):**  
Situación relevante registrada en la plataforma, como una variación anormal de glucosa, un síntoma o un cambio en el tratamiento.

---

### Acceso a la plataforma

**1. Sign Up (Registro):**  
Proceso mediante el cual un usuario crea una cuenta en la plataforma GlucoSmart.

**2. Sign In (Inicio de sesión):**  
Acción de ingresar al sistema mediante credenciales para acceder a sus funcionalidades.

**3. User Account (Cuenta de usuario):**  
Perfil digital asociado a un paciente o doctor dentro de la plataforma.

**4. User Profile (Perfil de usuario):**  
Información personal y profesional registrada en el sistema según el tipo de usuario.

# <a name="_toc226040409"></a>Capitulo III: Requirements Specification

## <a name="_toc226040410"></a>3.1 User Stories

En esta sección se presentan las épicas y las historias de usuario del proyecto **GlucoSmart**, alineadas con las necesidades funcionales de los principales actores del sistema: **pacientes** y **doctores**. Estas historias de usuario servirán como base para la priorización del backlog, el diseño del sistema y la planificación del desarrollo.

### Epics

| Epic ID | Título                               | Descripción                                                                                                                       |
| ------- | ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| EP-01   | Landing Page y Captación de Usuarios | Como startup, queremos presentar claramente la propuesta de valor de GlucoSmart para informar y captar potenciales usuarios.      |
| EP-02   | Gestión de Cuenta y Acceso           | Como usuario, queremos registrarnos e iniciar sesión de forma segura para acceder a las funcionalidades de la plataforma.         |
| EP-03   | Perfil y Datos Clínicos del Paciente | Como paciente, queremos gestionar nuestro perfil y antecedentes clínicos para mantener información médica actualizada.            |
| EP-04   | Monitoreo y Registro de Salud        | Como paciente, queremos registrar y consultar nuestros datos de salud para llevar control continuo de la diabetes.                |
| EP-05   | Tratamiento, Medicación y Alertas    | Como paciente y doctor, queremos gestionar tratamientos, medicación y alertas para mejorar la adherencia y prevención de riesgos. |
| EP-06   | Seguimiento Clínico del Doctor       | Como doctor, queremos revisar y registrar información clínica del paciente para realizar un seguimiento médico adecuado.          |
| EP-07   | Gestión de Citas Médicas             | Como usuario, queremos gestionar citas médicas para organizar el seguimiento y la atención de salud.                              |

### User Stories

| Story ID | Título                                       | Descripción                                                                                                                                         | Criterios de Aceptación                                                                                                                                                                                                            | Epic ID |
| -------- | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| US-01    | Hero section del Landing Page                | Como visitante, quiero visualizar la propuesta de valor principal de GlucoSmart para comprender rápidamente el propósito de la plataforma.          | **Scenario 1:**<br>**Given** the visitor accesses the landing page,<br>**When** the main section is displayed,<br>**Then** the visitor can clearly identify the purpose of GlucoSmart and its focus on diabetes management.        | EP-01   |
| US-02    | Registro de paciente                         | Como paciente, quiero registrarme en la plataforma para acceder a las funcionalidades de monitoreo y seguimiento de mi salud.                       | **Scenario 1:**<br>**Given** the patient completes the registration form with valid data,<br>**When** the patient selects the “Sign Up” option,<br>**Then** the system creates the account successfully.                           | EP-02   |
| US-03    | Registro de doctor                           | Como doctor, quiero registrarme en la plataforma para acceder a la información clínica de mis pacientes y realizar seguimiento médico.              | **Scenario 1:**<br>**Given** the doctor completes the registration form with valid data,<br>**When** the doctor selects the “Sign Up” option,<br>**Then** the system creates the account successfully.                             | EP-02   |
| US-04    | Log in                                       | Como usuario, quiero iniciar sesión con mis credenciales para acceder de forma segura a mi cuenta.                                                  | **Scenario 1:**<br>**Given** the user already has a registered account,<br>**When** the user enters valid credentials,<br>**Then** the system grants access to the account.                                                        | EP-02   |
| US-05    | Recuperación de contraseña                   | Como usuario, quiero recuperar mi contraseña para volver a acceder a mi cuenta si la he olvidado.                                                   | **Scenario 1:**<br>**Given** the user selects the password recovery option,<br>**When** the user enters a valid email address,<br>**Then** the system sends instructions to restore access.                                        | EP-02   |
| US-06    | Cerrar sesión                                | Como usuario, quiero cerrar sesión de manera segura para proteger la privacidad de mi información.                                                  | **Scenario 1:**<br>**Given** the user is authenticated in the platform,<br>**When** the user selects the “Log Out” option,<br>**Then** the system ends the session and redirects the user out of the private area.                 | EP-02   |
| US-07    | Crear perfil de paciente                     | Como paciente, quiero completar mi perfil personal y clínico para contar con un registro base dentro de la plataforma.                              | **Scenario 1:**<br>**Given** the patient accesses the profile section,<br>**When** the patient completes the required personal and clinical information,<br>**Then** the system stores the information successfully.               | EP-03   |
| US-08    | Editar perfil de paciente                    | Como paciente, quiero actualizar mis datos personales y clínicos para mantener mi información correcta y vigente.                                   | **Scenario 1:**<br>**Given** the patient already has a registered profile,<br>**When** the patient edits the data and saves the changes,<br>**Then** the system updates the information successfully.                              | EP-03   |
| US-09    | Registrar antecedentes médicos               | Como paciente, quiero registrar mis antecedentes médicos relevantes para que el doctor disponga de mayor contexto clínico.                          | **Scenario 1:**<br>**Given** the patient accesses the medical history section,<br>**When** the patient enters valid background information,<br>**Then** the system stores it correctly in the clinical record.                     | EP-03   |
| US-10    | Visualizar historial de salud                | Como paciente, quiero consultar mi historial de salud para revisar la evolución de mi condición a lo largo del tiempo.                              | **Scenario 1:**<br>**Given** the patient has previous health records in the platform,<br>**When** the patient accesses the health history section,<br>**Then** the system displays the stored information in an organized way.     | EP-03   |
| US-11    | Consultar perfil y datos clínicos personales | Como paciente, quiero visualizar mi información personal y clínica consolidada para tener una visión general de mi estado de salud.                 | **Scenario 1:**<br>**Given** the patient accesses the profile section,<br>**When** the patient requests to view the registered information,<br>**Then** the system displays the personal and clinical data in a consolidated view. | EP-03   |
| US-12    | Registrar nivel de glucosa                   | Como paciente, quiero registrar mis niveles de glucosa para llevar control sobre mi estado diario de salud.                                         | **Scenario 1:**<br>**Given** the patient accesses the monitoring module,<br>**When** the patient enters a valid glucose measurement,<br>**Then** the system stores the entered value successfully.                                 | EP-04   |
| US-13    | Visualizar historial de glucosa              | Como paciente, quiero consultar el historial de mis mediciones de glucosa para identificar cambios y patrones en el tiempo.                         | **Scenario 1:**<br>**Given** the patient has previous glucose records,<br>**When** the patient accesses the glucose history section,<br>**Then** the system displays the list of records in chronological order.                   | EP-04   |
| US-14    | Registrar síntomas                           | Como paciente, quiero registrar los síntomas que presento para complementar la información clínica de mi seguimiento.                               | **Scenario 1:**<br>**Given** the patient accesses the symptoms section,<br>**When** the patient enters valid symptom information,<br>**Then** the system stores the symptom in the clinical history.                               | EP-04   |
| US-15    | Visualizar evolución de salud                | Como paciente, quiero visualizar el resumen de mi evolución de salud para entender mejor mi progreso y condición actual.                            | **Scenario 1:**<br>**Given** the patient has health information registered in the platform,<br>**When** the patient accesses the health progress panel,<br>**Then** the system displays a summary of the health records.           | EP-04   |
| US-16    | Recibir alerta por glucosa fuera de rango    | Como paciente, quiero recibir alertas cuando mis niveles de glucosa estén fuera de rango para actuar de manera oportuna ante un posible riesgo.     | **Scenario 1:**<br>**Given** the patient registers a glucose measurement outside the expected range,<br>**When** the system validates the entered value,<br>**Then** the system generates an alert for the patient.                | EP-04   |
| US-17    | Visualizar tratamiento actual                | Como paciente, quiero consultar mi tratamiento actual para saber qué indicaciones y medicamentos debo seguir.                                       | **Scenario 1:**<br>**Given** the patient has an active treatment registered,<br>**When** the patient accesses the treatment section,<br>**Then** the system displays the current medical indications.                              | EP-05   |
| US-18    | Registrar tratamiento prescrito              | Como doctor, quiero registrar el tratamiento prescrito del paciente para dejar definidas las indicaciones médicas dentro de la plataforma.          | **Scenario 1:**<br>**Given** the doctor accesses the patient’s clinical profile,<br>**When** the doctor enters a valid treatment plan,<br>**Then** the system stores the treatment successfully.                                   | EP-05   |
| US-19    | Registrar toma de medicación                 | Como paciente, quiero registrar cada toma de mi medicación para llevar control del cumplimiento de mi tratamiento.                                  | **Scenario 1:**<br>**Given** the patient accesses the medication section,<br>**When** the patient records a completed medication intake,<br>**Then** the system stores the information in the corresponding history.               | EP-05   |
| US-20    | Recibir recordatorio de medicación           | Como paciente, quiero recibir recordatorios de medicación para no olvidar mis tomas programadas.                                                    | **Scenario 1:**<br>**Given** the patient has medication schedules configured,<br>**When** the scheduled time is reached,<br>**Then** the system sends a medication reminder.                                                       | EP-05   |
| US-21    | Reportar efectos adversos                    | Como paciente, quiero reportar efectos adversos relacionados con mi medicación para que el doctor pueda evaluarlos oportunamente.                   | **Scenario 1:**<br>**Given** the patient accesses the pharmacovigilance section,<br>**When** the patient records a valid adverse effect report,<br>**Then** the system stores the report successfully.                             | EP-05   |
| US-22    | Consultar adherencia al tratamiento          | Como doctor, quiero consultar el nivel de adherencia del paciente a su tratamiento para evaluar si está cumpliendo correctamente las indicaciones.  | **Scenario 1:**<br>**Given** the doctor accesses the patient’s history,<br>**When** the doctor reviews the recorded medication information,<br>**Then** the system displays the treatment adherence level.                         | EP-05   |
| US-23    | Revisar información clínica del paciente     | Como doctor, quiero revisar la información clínica registrada por el paciente para realizar un seguimiento adecuado de su estado de salud.          | **Scenario 1:**<br>**Given** the doctor accesses the patient record,<br>**When** the doctor reviews the clinical records,<br>**Then** the system displays the patient’s consolidated information.                                  | EP-06   |
| US-24    | Registrar observaciones médicas              | Como doctor, quiero registrar observaciones médicas sobre la evolución del paciente para dejar constancia del seguimiento clínico realizado.        | **Scenario 1:**<br>**Given** the doctor accesses the patient record,<br>**When** the doctor enters a valid medical observation,<br>**Then** the system stores the observation successfully.                                        | EP-06   |
| US-25    | Emitir diagnóstico                           | Como doctor, quiero registrar un diagnóstico dentro de la plataforma para documentar formalmente la evaluación clínica del paciente.                | **Scenario 1:**<br>**Given** the doctor accesses the patient’s clinical history,<br>**When** the doctor enters a valid diagnosis,<br>**Then** the system stores the diagnosis in the clinical record.                              | EP-06   |
| US-26    | Generar reporte clínico del paciente         | Como doctor, quiero generar un reporte clínico del paciente para contar con un resumen organizado de su información médica.                         | **Scenario 1:**<br>**Given** the doctor accesses the patient record,<br>**When** the doctor requests a clinical report,<br>**Then** the system displays a structured clinical summary.                                             | EP-06   |
| US-27    | Solicitar cita médica                        | Como paciente, quiero solicitar una cita médica para recibir atención y seguimiento por parte del doctor.                                           | **Scenario 1:**<br>**Given** the patient accesses the appointment module,<br>**When** the patient submits a request with valid data,<br>**Then** the system schedules the appointment successfully.                                | EP-07   |
| US-28    | Visualizar agenda de citas                   | Como usuario, quiero visualizar mis citas programadas para organizar mejor mi seguimiento médico.                                                   | **Scenario 1:**<br>**Given** the user has registered appointments,<br>**When** the user accesses the agenda section,<br>**Then** the system displays the scheduled appointments in chronological order.                            | EP-07   |
| US-29    | Navegación por el Landing Page               | Como visitante, quiero navegar fácilmente entre las secciones del landing page para encontrar información del producto de manera rápida y ordenada. | **Scenario 1:**<br>**Given** the visitor is on the landing page,<br>**When** the visitor selects a navigation menu option,<br>**Then** the system scrolls to the corresponding section.                                            | EP-01   |
| US-30    | Ver información de la Startup                | Como visitante, quiero visualizar información sobre IntegraVida y GlucoSmart para conocer el contexto y objetivo de la solución.                    | **Scenario 1:**<br>**Given** the visitor accesses the “About Us” section,<br>**When** the visitor reviews its content,<br>**Then** the system displays relevant information about the startup and the product.                     | EP-01   |
| US-31    | Conocer la misión y visión de la Startup     | Como visitante, quiero leer la misión y visión de la startup para entender su enfoque y compromiso con el manejo de la diabetes.                    | **Scenario 1:**<br>**Given** the visitor accesses the “About Us” section,<br>**When** the visitor reviews the information cards,<br>**Then** the system displays the startup’s mission and vision.                                 | EP-01   |
| US-32    | Cambiar idioma del Landing Page              | Como visitante, quiero cambiar el idioma del landing page para visualizar la información en el idioma de mi preferencia.                            | **Scenario 1:**<br>**Given** the visitor is on the landing page,<br>**When** the visitor selects one of the available languages,<br>**Then** the interface content is updated to the selected language.                            | EP-01   |
| US-33    | Contactar al equipo de soporte               | Como visitante, quiero enviar un mensaje al equipo de soporte para resolver dudas o solicitar información sobre la plataforma.                      | **Scenario 1:**<br>**Given** the visitor completes the contact form with valid data,<br>**When** the visitor selects the “Send” option,<br>**Then** the system registers or sends the message successfully.                        | EP-01   |
| US-34    | Reprogramar cita médica                      | Como usuario, quiero reprogramar una cita médica para adaptar el seguimiento a mi disponibilidad.                                                   | **Scenario 1:**<br>**Given** the user has a previously scheduled appointment,<br>**When** the user selects a new valid date and time,<br>**Then** the system updates the appointment successfully.                                 | EP-07   |
| US-35    | Cancelar cita médica                         | Como usuario, quiero cancelar una cita médica para liberar el espacio cuando no pueda asistir.                                                      | **Scenario 1:**<br>**Given** the user has a scheduled appointment,<br>**When** the user selects the “Cancel” option,<br>**Then** the system cancels the registered appointment successfully.                                       | EP-07   |
| US-36    | Recibir recordatorio de cita                 | Como usuario, quiero recibir recordatorios de mis citas médicas para no olvidar mis atenciones programadas.                                         | **Scenario 1:**<br>**Given** the user has an upcoming appointment registered,<br>**When** the appointment date is approaching,<br>**Then** the system sends the corresponding reminder.                                            | EP-07   |

## <a name="_toc226040411"></a>3.2 Impact Mapping

![](./Informe/assets/ImpactMapping.jpg)

Para asegurar que las funcionalidades de **GlucoSmart** estén alineadas con los objetivos estratégicos de **IntegraVida**, se ha desarrollado un Impact Mapping. Esta técnica nos permite visualizar cómo los entregables de software generarán un cambio de comportamiento en nuestros usuarios, logrando así el impacto de negocio deseado.

A continuación, se detalla la estructura del mapa de impacto:

#### 1. Objetivo del Negocio (WHY / ¿Por qué?)

- **Meta Principal:** Lograr una retención de uso continuo del 80% en pacientes durante los primeros 3 meses y reducir el tiempo de revisión de historial clínico en las consultas médicas en un 20%
#### 2. Actores (WHO / ¿Quién?)

Para alcanzar esta meta, dependemos de los dos segmentos principales identificados en nuestras entrevistas:

- **Actor 1:** Paciente con Diabetes (Ej. Jorge).
- **Actor 2:** Médico Especialista (Ej. Dr. Walter).
#### 3. Impactos (HOW / ¿Cómo?)

¿Cómo necesitamos que cambie el comportamiento de estos actores para lograr nuestra meta?

- **Para el Paciente:**
    
    - _Impacto 1.1:_ Que registre su glucosa y confirme la ingesta de su medicación diariamente sin olvidos.
    - _Impacto 1.2:_ Que reporte los efectos adversos o síntomas inusuales en el momento en que ocurren.
    
- **Para el Médico:**
    
    - _Impacto 2.1:_ Que interprete la evolución de la hemoglobina glicosilada (HbA1c) en segundos, en lugar de revisar apuntes desordenados.
    - _Impacto 2.2:_ Que intervenga de forma preventiva antes de que un paciente sufra daño orgánico por hipoglucemia.

#### 4. Entregables / Funcionalidades (WHAT / ¿Qué?)

¿Qué vamos a construir (desarrollar) en la plataforma para facilitar esos impactos?

- **Para lograr el Impacto 1.1 (Registro diario):**
    
    - _Entregable:_ Sistema automatizado de recordatorios y confirmación de dosis.
	
- **Para lograr el Impacto 1.2 (Reporte de síntomas):**
    
    - _Entregable:_ Módulo de registro rápido de farmacovigilancia y reacciones adversas.
    
- **Para lograr el Impacto 2.1 (Interpretación rápida):**
    
    - _Entregable:_ Dashboard interactivo con gráficos de tendencias de glucosa y filtros históricos.
    
- **Para lograr el Impacto 2.2 (Intervención preventiva):**
    
    - _Entregable:_ Sistema de alertas críticas enviadas en tiempo real ante niveles fuera del rango seguro.

## <a name="_toc226040412"></a>3.3 Product Backlog

El Product Backlog del proyecto **GlucoSmart** organiza las historias de usuario según su prioridad funcional y valor para el producto. El orden presentado considera el enfoque inicial del proyecto, comenzando por la validación de la propuesta de valor mediante el landing page y continuando con las funcionalidades principales del sistema orientadas al paciente y al doctor. La estimación técnica de cada historia se expresa mediante **Story Points**.

| # Orden | User Story ID | Título                                       | Descripción                                                                                                                                         | Story Point |
| ------- | ------------- | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| 1       | US-01         | Hero section del Landing Page                | Como visitante, quiero visualizar la propuesta de valor principal de GlucoSmart para comprender rápidamente el propósito de la plataforma.          | 2           |
| 2       | US-29         | Navegación por el Landing Page               | Como visitante, quiero navegar fácilmente entre las secciones del landing page para encontrar información del producto de manera rápida y ordenada. | 3           |
| 3       | US-30         | Ver información de la Startup                | Como visitante, quiero visualizar información sobre IntegraVida y GlucoSmart para conocer el contexto y objetivo de la solución.                    | 2           |
| 4       | US-31         | Conocer la misión y visión de la Startup     | Como visitante, quiero leer la misión y visión de la startup para entender su enfoque y compromiso con el manejo de la diabetes.                    | 2           |
| 5       | US-32         | Cambiar idioma del Landing Page              | Como visitante, quiero cambiar el idioma del landing page para visualizar la información en el idioma de mi preferencia.                            | 3           |
| 6       | US-33         | Contactar al equipo de soporte               | Como visitante, quiero enviar un mensaje al equipo de soporte para resolver dudas o solicitar información sobre la plataforma.                      | 3           |
| 7       | US-02         | Registro de paciente                         | Como paciente, quiero registrarme en la plataforma para acceder a las funcionalidades de monitoreo y seguimiento de mi salud.                       | 5           |
| 8       | US-03         | Registro de doctor                           | Como doctor, quiero registrarme en la plataforma para acceder a la información clínica de mis pacientes y realizar seguimiento médico.              | 5           |
| 9       | US-04         | Log in                                       | Como usuario, quiero iniciar sesión con mis credenciales para acceder de forma segura a mi cuenta.                                                  | 3           |
| 10      | US-05         | Recuperación de contraseña                   | Como usuario, quiero recuperar mi contraseña para volver a acceder a mi cuenta si la he olvidado.                                                   | 3           |
| 11      | US-06         | Cerrar sesión                                | Como usuario, quiero cerrar sesión de manera segura para proteger la privacidad de mi información.                                                  | 1           |
| 12      | US-07         | Crear perfil de paciente                     | Como paciente, quiero completar mi perfil personal y clínico para contar con un registro base dentro de la plataforma.                              | 5           |
| 13      | US-08         | Editar perfil de paciente                    | Como paciente, quiero actualizar mis datos personales y clínicos para mantener mi información correcta y vigente.                                   | 3           |
| 14      | US-09         | Registrar antecedentes médicos               | Como paciente, quiero registrar mis antecedentes médicos relevantes para que el doctor disponga de mayor contexto clínico.                          | 3           |
| 15      | US-11         | Consultar perfil y datos clínicos personales | Como paciente, quiero visualizar mi información personal y clínica consolidada para tener una visión general de mi estado de salud.                 | 2           |
| 16      | US-12         | Registrar nivel de glucosa                   | Como paciente, quiero registrar mis niveles de glucosa para llevar control sobre mi estado diario de salud.                                         | 5           |
| 17      | US-13         | Visualizar historial de glucosa              | Como paciente, quiero consultar el historial de mis mediciones de glucosa para identificar cambios y patrones en el tiempo.                         | 3           |
| 18      | US-14         | Registrar síntomas                           | Como paciente, quiero registrar los síntomas que presento para complementar la información clínica de mi seguimiento.                               | 2           |
| 19      | US-15         | Visualizar evolución de salud                | Como paciente, quiero visualizar el resumen de mi evolución de salud para entender mejor mi progreso y condición actual.                            | 5           |
| 20      | US-16         | Recibir alerta por glucosa fuera de rango    | Como paciente, quiero recibir alertas cuando mis niveles de glucosa estén fuera de rango para actuar de manera oportuna ante un posible riesgo.     | 5           |
| 21      | US-17         | Visualizar tratamiento actual                | Como paciente, quiero consultar mi tratamiento actual para saber qué indicaciones y medicamentos debo seguir.                                       | 3           |
| 22      | US-18         | Registrar tratamiento prescrito              | Como doctor, quiero registrar el tratamiento prescrito del paciente para dejar definidas las indicaciones médicas dentro de la plataforma.          | 5           |
| 23      | US-19         | Registrar toma de medicación                 | Como paciente, quiero registrar cada toma de mi medicación para llevar control del cumplimiento de mi tratamiento.                                  | 3           |
| 24      | US-20         | Recibir recordatorio de medicación           | Como paciente, quiero recibir recordatorios de medicación para no olvidar mis tomas programadas.                                                    | 5           |
| 25      | US-21         | Reportar efectos adversos                    | Como paciente, quiero reportar efectos adversos relacionados con mi medicación para que el doctor pueda evaluarlos oportunamente.                   | 3           |
| 26      | US-22         | Consultar adherencia al tratamiento          | Como doctor, quiero consultar el nivel de adherencia del paciente a su tratamiento para evaluar si está cumpliendo correctamente las indicaciones.  | 5           |
| 27      | US-23         | Revisar información clínica del paciente     | Como doctor, quiero revisar la información clínica registrada por el paciente para realizar un seguimiento adecuado de su estado de salud.          | 5           |
| 28      | US-24         | Registrar observaciones médicas              | Como doctor, quiero registrar observaciones médicas sobre la evolución del paciente para dejar constancia del seguimiento clínico realizado.        | 3           |
| 29      | US-25         | Emitir diagnóstico                           | Como doctor, quiero registrar un diagnóstico dentro de la plataforma para documentar formalmente la evaluación clínica del paciente.                | 3           |
| 30      | US-26         | Generar reporte clínico del paciente         | Como doctor, quiero generar un reporte clínico del paciente para contar con un resumen organizado de su información médica.                         | 5           |
| 31      | US-10         | Visualizar historial de salud                | Como paciente, quiero consultar mi historial de salud para revisar la evolución de mi condición a lo largo del tiempo.                              | 3           |
| 32      | US-27         | Solicitar cita médica                        | Como paciente, quiero solicitar una cita médica para recibir atención y seguimiento por parte del doctor.                                           | 5           |
| 33      | US-28         | Visualizar agenda de citas                   | Como usuario, quiero visualizar mis citas programadas para organizar mejor mi seguimiento médico.                                                   | 3           |
| 34      | US-34         | Reprogramar cita médica                      | Como usuario, quiero reprogramar una cita médica para adaptar el seguimiento a mi disponibilidad.                                                   | 3           |
| 35      | US-35         | Cancelar cita médica                         | Como usuario, quiero cancelar una cita médica para liberar el espacio cuando no pueda asistir.                                                      | 2           |
| 36      | US-36         | Recibir recordatorio de cita                 | Como usuario, quiero recibir recordatorios de mis citas médicas para no olvidar mis atenciones programadas.                                         | 3           |


# <a name="_toc226040413"></a>Capitulo IV: Product Design

## <a name="_toc226040414"></a>4.1. Style Guidelines.

El propósito de esta sección es establecer los lineamientos visuales y de diseño de interacción para la plataforma GlucoSmart de la startup IntegraVida. Estas directrices aseguran que la interfaz de usuario (UI) sea coherente, profesional y transmita confianza, factores críticos en un sistema de gestión de salud y farmacovigilancia tanto para pacientes como para personal médico.
### <a name="_toc226040415"></a>4.1.1. General Style Guidelines.

![](./Informe/assets/StudyGuidelines.jpeg)

Los lineamientos generales definen la identidad visual de la marca y los elementos base que componen todas las interfaces del sistema, tal como se muestra en la imagen de referencia adjunta.

- Tipografía (Typography):Para garantizar la máxima legibilidad de los datos clínicos (niveles de glucosa, registros de HbA1c), se ha seleccionado la familia tipográfica. Esta fuente _sans-serif_ ofrece claridad en pantallas digitales de cualquier tamaño. Se establece una jerarquía estructurada utilizando distintos pesos: _Bold_ o _SemiBold_ para encabezados y títulos principales, y _Regular_ para el cuerpo de texto y lectura de tablas médicas.
- Paleta de Colores (Color Palette): La selección de colores busca transmitir limpieza, tranquilidad y tecnología médica, evitando la fatiga visual del doctor durante la revisión de historiales.
    
    - Color Primario : Utilizado para resaltar los elementos de mayor importancia y establecer la identidad de la marca.
    - **Color Secundario y Fondos:** Tonos neutros y grises claros que permiten que la información y los gráficos destaquen sin saturar la vista.
    - **Colores Semánticos:** Fundamentales para el entorno de salud. Se emplea el color rojo para alertas críticas (ej. hipoglucemia severa o efectos adversos), amarillo para advertencias preventivas, y verde para confirmaciones de éxito y estados estables.
    
- **Logotipo e Iconografía:** El logotipo de IntegraVida se mantendrá constante en la cabecera (_header_) del sistema. La iconografía empleada debe ser minimalista, de trazos limpios y consistentes, facilitando el reconocimiento rápido de secciones clave como "Farmacovigilancia", "Dashboard Médico" y "Recordatorios".
### <a name="_toc226040416"></a>4.1.2. Web Style Guidelines.

Estas directrices especifican cómo los elementos generales se aplican directamente a la experiencia e interacción dentro de la aplicación web de **GlucoSmart**, asegurando que los usuarios completen sus tareas de manera eficiente.

- **Estructura y Disposición (Layout):** La plataforma está diseñada bajo los principios de diseño web adaptable (_Responsive Web Design_). Para la vista del médico, se implementa una estructura de panel de control (_Dashboard_) dividida en una barra lateral (_sidebar_) para la navegación principal, y una sección principal (_main view_) donde se despliegan las tablas de pacientes y los gráficos de tendencias.
- **Componentes de Interacción:**
    
    - **Botones (Buttons):** Los botones de llamada a la acción (CTA), como "Registrar Glucosa" o "Notificar Reacción Adversa", utilizarán el color primario con texto en alto contraste (blanco). Todo botón debe contar con estados visuales definidos (_hover_, _active_, _disabled_) para proporcionar retroalimentación inmediata al interactuar con ellos.
    - **Formularios de Entrada (Forms):** Los campos para ingresar la medicación o actualizar la historia clínica tendrán bordes sutiles y etiquetas descriptivas claras. Los mensajes de validación (errores al ingresar datos anómalos) aprovecharán los colores semánticos para guiar al usuario a corregir la información.
    - **Visualización de Datos:** Las gráficas de evolución y reportes de adherencia deben respetar el contraste establecido por las pautas de accesibilidad (WCAG). Se prioriza el uso de espacios en blanco (_white space_) para separar los bloques de información, evitando el uso excesivo de líneas divisorias, lo que garantiza una lectura ágil del historial clínico.

## <a name="_toc226040417"></a>4.2. Information Architecture.

### <a name="_toc226040418"></a>4.2.1. Organization Systems.

Para estructurar el contenido de la plataforma, se han implementado los siguientes sistemas:

- **Esquema Jerárquico:** Se utiliza para la navegación principal, permitiendo profundizar desde una visión general (Dashboard) hacia detalles específicos (Historial de dosis o Reporte de Farmacovigilancia).
- **Organización Orientada a Tareas:** Las interfaces están agrupadas según las acciones prioritarias identificadas en el _Task Mapping_: "Registrar Medición", "Consultar Alertas" y "Generar Reporte".
- **Esquema Matricial:** En el panel del médico, la información se organiza permitiendo múltiples puntos de acceso; un médico puede llegar a un reporte de efectos adversos filtrando por el nombre del paciente o por la gravedad de la alerta.

### <a name="_toc226040419"></a>4.2.2. Labeling Systems.

El sistema de etiquetado busca un equilibrio entre la precisión clínica y la claridad para el paciente, evitando ambigüedades:

- **Etiquetas para Médicos:** Se emplea terminología técnica estandarizada como _"HbA1c"_ (Hemoglobina Glicosilada), _"Farmacovigilancia"_ y _"Adherencia Terapéutica"_.
- **Etiquetas para Pacientes:** Se utilizan términos familiares y directos como _"Mi Glucosa"_, _"Mis Recordatorios"_ y _"¿Cómo me siento?"_ (para el registro de síntomas).
- **Iconografía Predictiva:** Se acompañan las etiquetas con iconos universales (ej. una campana para alarmas, un gráfico para tendencias) para acelerar el reconocimiento visual.

### <a name="_toc226040420"></a>4.2.3. SEO Tags and Meta Tags

Para posicionar a **IntegraVida** como un referente en salud digital y facilitar el acceso a la plataforma, se han definido los siguientes metadatos:

- **Index Title:** `IntegraVida | GlucoSmart - Control Inteligente de Diabetes y Farmacovigilancia`.
    
- **Meta Description:** `Plataforma integral para el monitoreo de diabetes. Conecta a médicos y pacientes en tiempo real para el seguimiento de glucosa, adherencia a medicación y prevención de efectos adversos.`
    
- **Keywords:** `Control de diabetes`, `monitoreo de glucosa`, `farmacovigilancia digital`, `salud digital Perú`, `historial clínico interactivo`.

### <a name="_toc226040421"></a>4.2.4. Searching Systems.

Dada la naturaleza crítica de los datos médicos, el sistema de búsqueda está optimizado para la velocidad:

- **Búsqueda Global (Médico):** Permite localizar pacientes por nombre, DNI o nivel de riesgo actual.
- **Filtros Avanzados:** En los reportes, el usuario puede filtrar por "Rango de Fechas", "Tipo de Síntoma" o "Nivel de Glucosa" (Hipoglucemia/Hiperglucemia).
- **Autocompletado:** El sistema sugiere nombres de medicamentos comunes para evitar errores ortográficos en el registro de dosis.

### <a name="_toc226040422"></a>4.2.5. Navigation Systems.

Se han implementado tres capas de navegación para garantizar que el usuario nunca se sienta perdido:

- **Navegación Global (Navbar):** Ubicada en la parte superior, permite el acceso a las secciones principales (Inicio, Mi Perfil, Soporte) y el cambio de idioma.
- **Navegación Local (Sidebar):** Una barra lateral persistente en el _Dashboard_ que permite conmutar entre las herramientas de gestión (Gráficos, Alarmas, Farmacovigilancia).
- **Navegación Contextual (Breadcrumbs):** Migas de pan que indican la ruta actual (ej. _Inicio > Pacientes > Jorge Quispe > Historial Mensual_), facilitando el retorno a niveles superiores sin usar el botón de retroceso del navegador.

## <a name="_toc226040423"></a>4.3. Landing Page UI Design.

### <a name="_toc226040424"></a>4.3.1. Landing Page Wireframe.

![](./Informe/assets/Wireframe.png)

### <a name="_toc226040425"></a>4.3.2. Landing Page Mock-up.

![](./Informe/assets/Prototipe.png)

## <a name="_toc226040426"></a>4.4. Web Applications UX/UI Design.

### <a name="_toc226040427"></a>4.4.1. Web Applications Wireframes.

### <a name="_toc226040428"></a>4.4.2. Web Applications Wireflow Diagrams.

### <a name="_toc226040429"></a>4.4.2. Web Applications Mock-ups.

### <a name="_toc226040430"></a>4.4.3. Web Applications User Flow Diagrams.

## <a name="_toc226040431"></a>4.5. Web Applications Prototyping.

## <a name="_toc226040432"></a>4.6. Domain-Driven Software Architecture.

### <a name="_toc226040433"></a>4.6.1. Design-Level Event Storming.

### <a name="_toc226040434"></a>4.6.2. Software Architecture Context Diagram.

### <a name="_toc226040435"></a>4.6.3. Software Architecture Container Diagrams.

### <a name="_toc226040436"></a>4.6.4. Software Architecture Components Diagrams.

## <a name="_toc226040437"></a>4.7. Software Object-Oriented Design.

### <a name="_toc226040438"></a>4.7.1. Class Diagrams.

Para representar de manera más clara la estructura orientada a objetos del sistema **GlucoSmart**, el diseño fue dividido en dos diagramas de clases complementarios. Ambos diagramas pertenecen al mismo dominio del sistema y se encuentran relacionados principalmente a través de las clases **Patient** y **Doctor**, que actúan como entidades centrales del modelo.

El primer diagrama, **User & Clinical Management**, presenta la estructura relacionada con la gestión de usuarios y la información clínica del paciente, incluyendo el expediente clínico, historial médico, registros de glucosa, síntomas, diagnósticos, observaciones médicas y reportes clínicos.

El segundo diagrama, **Treatment & Appointment Management**, presenta la estructura relacionada con la gestión de tratamientos, medicamentos, tomas de medicación, reportes de efectos adversos, alertas y citas médicas.

La separación en dos diagramas no implica una división del sistema en módulos independientes, sino una organización visual del mismo modelo orientado a objetos con el fin de mejorar la legibilidad, comprensión y trazabilidad del dominio.

#### Class Diagram 1: User & Clinical Management

![Class Diagram 1](./Informe/assets/class-diagram-1.png)

#### Class Diagram 2: Treatment & Appointment Management

![Class Diagram 2](./Informe/assets/class-diagram-2.png)

## <a name="_toc226040439"></a>4.8. Database Design.

### <a name="_toc226040440"></a>4.8.1. Database Diagrams

El siguiente diagrama entidad-relación representa el diseño de base de datos del sistema **GlucoSmart**, alineado con los diagramas de clases definidos previamente. El modelo relacional considera la gestión de usuarios, pacientes, doctores, expedientes clínicos, historial médico, registros de glucosa, síntomas, tratamientos, medicamentos, tomas de medicación, reportes de efectos adversos, alertas y citas médicas.

La estructura propuesta permite mantener la integridad de los datos y asegurar la trazabilidad clínica del paciente, además de brindar soporte a las principales funcionalidades de monitoreo, tratamiento y seguimiento médico de la plataforma.

![ERD - GlucoSmart](./Informe/assets/erd-database-diagram.png)

# <a name="_toc226040441"></a>Capitulo V: Product Implementation, Validation & Deployment

## <a name="_toc226040442"></a>5.1. Software Configuration Management.

La gestión de configuración del software del proyecto **IntegraVida** se definió con el objetivo de asegurar la organización del código fuente, la consistencia del entorno de desarrollo, la estandarización de convenciones técnicas y la correcta publicación del producto. Debido a que la solución implementada corresponde a una **Landing Page** desarrollada con **Angular**, **HTML**, **CSS** y **TypeScript**, se establecieron lineamientos simples pero formales para mantener la trazabilidad de cambios y facilitar el trabajo colaborativo del equipo.

### <a name="_toc226040443"></a>5.1.1. Software Development Environment Configuration.

Para el desarrollo del proyecto se configuró un entorno basado en tecnologías web modernas. La aplicación fue construida utilizando **Angular** como framework principal, con apoyo de **TypeScript** para la lógica de componentes y servicios, **HTML** para la estructura de las vistas y **CSS** para los estilos de la interfaz.

El entorno de desarrollo consideró la instalación de las siguientes herramientas:

- **Node.js**, como entorno de ejecución para las dependencias del proyecto.
- **npm**, para la administración de paquetes y librerías.
- **Angular CLI**, para la creación, ejecución y compilación del proyecto.
- **Git**, para el control de versiones distribuido.
- **Visual Studio Code**, como editor de código recomendado para el equipo.

Para ejecutar el proyecto en entorno local, primero se instalan las dependencias con el comando `npm install` y luego se inicia el servidor de desarrollo con `ng serve`. Con ello, la Landing Page puede visualizarse desde un navegador web en un entorno local, permitiendo validar cambios de manera continua durante la etapa de implementación.

### <a name="_toc226040444"></a>5.1.2. Source Code Management.

La administración del código fuente se realizó mediante **Git** y el repositorio remoto fue alojado en **GitHub**. Esta decisión permitió mantener un historial completo de cambios, facilitar la colaboración entre integrantes del equipo y asegurar la recuperación de versiones estables del producto.

El flujo de trabajo adoptado se basó en el uso de una rama principal, desde la cual se publican las versiones consolidadas del proyecto, y ramas de trabajo creadas para el desarrollo de funcionalidades o ajustes específicos. Cada cambio realizado fue registrado mediante **commits** descriptivos, lo que permitió identificar con claridad el propósito de cada modificación.

Asimismo, GitHub fue utilizado como plataforma de integración del trabajo colaborativo, ya que centralizó el almacenamiento del repositorio, el seguimiento de avances y la preparación de la versión desplegable de la Landing Page.

### <a name="_toc226040445"></a>5.1.3. Source Code Style Guide & Conventions.

Con el fin de mantener la legibilidad y uniformidad del proyecto, se aplicaron convenciones de desarrollo acordes con la estructura de Angular. Los componentes fueron organizados por responsabilidad funcional, separando secciones reutilizables y secciones propias de la Landing Page. De esta manera, el código quedó distribuido en carpetas orientadas a mejorar el mantenimiento y la escalabilidad del proyecto.

Las principales convenciones aplicadas fueron las siguientes:

- Uso de **TypeScript** para la lógica de componentes y servicios.
- Estructuración del proyecto por carpetas como `core`, `shared` y `components`.
- Nombres de archivos y componentes descriptivos, alineados con su responsabilidad funcional.
- Separación de responsabilidades entre estructura (`HTML`), presentación (`CSS`) y comportamiento (`TypeScript`).
- Reutilización de componentes comunes para mantener consistencia visual y reducir duplicidad de código.

Estas convenciones permitieron que el proyecto conserve una base ordenada, fácil de comprender y preparada para futuras ampliaciones.

### <a name="_toc226040446"></a>5.1.4. Software Deployment Configuration.

La configuración de despliegue del proyecto **IntegraVida** fue definida para publicar la Landing Page en **GitHub Pages**, permitiendo que el sistema sea accesible mediante una URL pública sin requerir infraestructura de servidor adicional.

El proceso de despliegue se encuentra vinculado al repositorio del proyecto y utiliza un archivo de configuración **`static.yaml`** ubicado dentro de la carpeta **`.github`**, el cual define el comportamiento necesario para la publicación del sitio estático. A partir de esta configuración, la versión compilada de la aplicación puede ser generada y publicada automáticamente en el entorno de GitHub Pages.

De manera general, el flujo de despliegue contempla las siguientes actividades:

1. Compilar la aplicación Angular para generar los archivos estáticos de producción.
2. Publicar la versión generada en la rama o entorno configurado para GitHub Pages.
3. Verificar que la URL pública cargue correctamente la Landing Page y sus recursos asociados.

Esta configuración permitió contar con un mecanismo de despliegue simple, reproducible y adecuado para un producto web estático orientado a presentación institucional y validación temprana de la propuesta de valor.

## <a name="_toc226040447"></a>5.2. Landing Page, Services & Applications Implementation.

### <a name="_toc226040448"></a>5.2.1. Sprint 1

### <a name="_toc226040449"></a>5.2.1.1. Sprint Planning 1.

| Sprint #                         | Sprint 1                                                                                                                                                                                                                                                                                                                                                                                              |     |
| :------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| **Sprint Planning Background**   |                                                                                                                                                                                                                                                                                                                                                                                                       |     |
| Date                             | 01/042026                                                                                                                                                                                                                                                                                                                                                                                             |     |
| Time                             | 6:00PM                                                                                                                                                                                                                                                                                                                                                                                                |     |
| Location                         | Virtual - Discord                                                                                                                                                                                                                                                                                                                                                                                     |     |
| Prepared By                      | Jean Pool Arias                                                                                                                                                                                                                                                                                                                                                                                       |     |
| Attendees (To planning meeting)  | Jean Pool Arias, Abigail Raymundo                                                                                                                                                                                                                                                                                                                                                                     |     |
| SprinT N-1 Review Summary        |                                                                                                                                                                                                                                                                                                                                                                                                       |     |
| SprinT N-1 Retrospective Summary |                                                                                                                                                                                                                                                                                                                                                                                                       |     |
| **Sprint Goal & User Stories**   |                                                                                                                                                                                                                                                                                                                                                                                                       |     |
| Sprint N Goal                    | Our focus is on delivering the first version of the GlucoSmart Landing Page. We believe it delivers a clear and attractive presentation of the product to potential users and medical professionals. This will be confirmed when the Landing Page is successfully deployed and accessible via a public URL, displaying all key sections including hero, services, about us, testimonials and contact. |     |
| Sprint N Velocity                | 20                                                                                                                                                                                                                                                                                                                                                                                                    |     |
| Sum of Story Points              | 18                                                                                                                                                                                                                                                                                                                                                                                                    |     |

### <a name="_toc226040450"></a>5.2.1.2. Aspect Leaders and Collaborators.

| Team Member      | GitHub Username | Landing Page Structure | Navbar & Footer | Hero & Service | About & Testiomonials | Contact Section |
| :--------------- | :-------------- | :--------------------- | :-------------- | :------------- | :-------------------- | --------------- |
| Jean, Arias      | Jean-AT         | L                      | L               | L              | C                     | C               |
| Abigail Raymundo | AbigailRv       | C                      | C               | L              | L                     | L               |

### <a name="_toc226040451"></a>5.2.1.3. Sprint Backlog 1.

| Sprint#    |                                   |                |                                                   |                                                                                                 |            |             |        |
| :--------- | :-------------------------------- | :------------- | :------------------------------------------------ | :---------------------------------------------------------------------------------------------- | :--------- | ----------- | ------ |
| User Story |                                   | Work-Item/Task |                                                   |                                                                                                 |            |             |        |
| Id         | Title                             | Id             | Title                                             | Description                                                                                     | Estimation | Assignet To | Status |
| US-29      | Navegacion por el Landing Page    | T01            | Crear estructura base del proyecto Angular        | Inicializar proyecto Angular con la estructura de carpetas definidas (shared,comoponents, core) | 1          | Jean Pool   | Done   |
| US-29      | Navegacion por el LandingPage     | T02            | Implementar Navbar component                      | Crear el componente navbar con logo, link de navegacion y botones de accion                     | 1          | Jean Pool   | Done   |
| US-29      | Navegación por el Landing Page    | T03            | Implementar Footer component                      | Crear el componente footer con logo, links, redes sociales y copyright                          | 1          | Abigail     | To-Do  |
| US-29      | Navegación por el Landing Page    | T04            | Implementar navegación entre secciones            | Configurar scroll suave entre secciones del Landing Page                                        | 0.5        | Jean Pool   | To-Do  |
| US-30      | Ver Información del Startup       | T05            | Implementar sección About                         | Crear el componente about con descripción, misión y visión de IntegraVida                       | 1          | Abigail     | To-Do  |
| US-31      | Conocer la mision de la Startup   | T06            | Agregar cards de Msion y vision                   | Implementar las cards dentro del componente about con su contenido                              | 0.5        | Abigail     | To-Do  |
| US-33      | Contactar al equipo de soporte    | T07            | Implementar seccion contact                       | Crear el componente contact con el formulario e informacion de contacto                         | 2          | Jean Pool   | Done   |
| US-01      | Hero section del Landing Page     | T08            | Implementar la seccion Hero                       | Crear el componente service con imagen y principal call to action                               | 1          | Abigail     | To-Do  |
| US-01      | Hero section del LandingPage      | T09            | Implementar seccion Service                       | Crear el componente con carousel de servicio especializados                                     | 2          | Abigail     | To-Do  |
| US-01      | Hero section del LandingPage      | 10             | Implementar Testimonios                           | Crear el componente testimonial con las cards de usuarios                                       | 1          | Abigai      | To-Do  |
| US-32      | Cambiar el idioma del LandingPage | T11            | Implementar Lenguage Service                      | Crear el servicio de internacionalizacion con traduciones en ES y EN                            | 1.5        | Jean Pool   | Done   |
| U-32       | Cambiar el idioma del LandingPage | T12            | Conectar Language Service a todos los componentes | Inyectar el servicio en cada componente y reemplazar textos estaticos                           | 1.5        | Jean Pool   | Done   |
| US-32      | Cambiar el idioma del LandingPage | T13            | Agregar toggle de idioma en navbar                | Implementar boton EN/ES en el navbar para cambiar idioma                                        | 0.5        | Jean Pool   | To-Do  |

### <a name="_toc226040452"></a>5.2.1.4. Development Evidence for Sprint Review.


| Repository  | Branch                  | Commit Id                                | Commit Message                                           | Commit Message Body                                                                                                                                                              | Commited on    |
| :---------- | :---------------------- | :--------------------------------------- | :------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- |
| IntegraVida | main                    | 79f9b95c9283ad21816efd8f2f5297a71ec4798d | Initial commit                                           | Initial commit                                                                                                                                                                   | 3 weeks ago    |
| IntegraVida | feature/button          | fad9eebb2bf9f8f036b123f834cff54a39c728e2 | Done the component Button                                | Complete make the componet button alreay to merge                                                                                                                                | Abril 12, 2026 |
| IntegraVida | feature/navbar          | 86686462672580b3e6f3212036c498fb613bfcf2 | Done the component Navbar                                | Make the component navbar                                                                                                                                                        | Abril 12, 2026 |
| IntegraVida | feature/hero            | dc48b680b66be028595bdef4daf27bb3aca86b50 | Done the component Hero                                  | Done the component Hero already to use                                                                                                                                           | Abril 12, 2026 |
| IntegraVida | feature/contact         | a330beb680a6ebc9e8a27463225811fc3e4af0db | Finish the contact component & already use to sent mails | I add the component. it's cards and a simple forms to contact with us and y add the fetch using Form Submit to send, I using my personal gmail to receive the mail users sending | Abril 13, 2026 |
| Integravida | feature/tooggleLanguage | 9fe7cee533381a7edfbd94216b838ebc7efc68f8 | Feature/toggle language                                  | Add the tooggleButtonLanguage and the Page Directory to organize the pages                                                                                                       | Abril 13,2026  |
|             |                         |                                          |                                                          |                                                                                                                                                                                  |                |

### <a name="_toc226040453"></a>5.2.1.5. Execution Evidence for Sprint Review.

En esta entrega el equipo ha desplegado con exito la primera version del LandingPage de IntegraVida 

Enlace del Landing Page desplegado: 

Las Secciones implementadas son: 

- Navbar con toggle de idioma ES/EN
- Hero section con imagen principal 
- Servicios Especializados con carousel
- Sobre Nosotros con cards de Mision y Vision
- Testimonio de usuarios 
- Formulario de Contacto 
- Footer con redes sociales

### <a name="_toc226040454"></a>5.2.1.6. Services Documentation Evidence for Sprint Review.

En este Sprint no se implementaron Web Services. El enfoque fue exclusivamente en desarrollo y despliegue del Landing Page estatico

### <a name="_toc226040455"></a>5.2.1.7. Software Deployment Evidence for Sprint Review.

Para el despliegue del Landing Page se utilizó GitHub Page. 

Pasos realizados: 

1. Subif el codigo fuentede la organizacion MTS-OpenSource 
2. Ir a Settings del repositorio 
3. Seleccionar el apartado Pages 
4. Eligir la rama ‘main’ y folder ‘/root’ 
5. Confirmar el despliegue y acceder al link generado

### <a name="_toc226040456"></a>5.2.1.8. Team Collaboration Insights during Sprint.

Durante este Sprint la tareas fueron distribuidas equitativamente entre los dos integrantes del equipo de desarollo Jean Pool Arias lidero la estructura vase del proyecto, el navbar, el contact y el language service. Abigail Raymundo liero el hero, el about, los testimonio y los servicio 

| Team Member      | Commits    |
| ---------------- | ---------- |
| Jean Pool Arias  | 14 commits |
| Abigail Raymundo | 11 commits  |

# <a name="_toc226040462"></a>Conclusiones

## <a name="_toc226040463"></a>Conclusiones y recomendaciones

#### Conclusiones

1. **Validación Temprana mediante Lean UX:** La aplicación del proceso Lean UX, respaldada por entrevistas a pacientes y personal médico, permitió validar que la fragmentación de la información y la falta de seguimiento de la adherencia son problemas críticos. Esta validación orientada al usuario garantizó que la definición del _Product Backlog_ se centrara en funcionalidades de alto valor, como el módulo de farmacovigilancia y el panel de control clínico, evitando el desarrollo de características innecesarias.
2. **Estandarización de la Arquitectura Frontend:** La configuración del entorno de desarrollo utilizando el marco de trabajo Angular y TypeScript permitió establecer una arquitectura escalable, modular y basada en componentes. La estricta separación de responsabilidades (lógica, estructura y presentación) asegura que el código fuente sea mantenible y esté preparado para la integración de funcionalidades dinámicas en los próximos ciclos de desarrollo.
3. **Cumplimiento de Objetivos de Despliegue:** La implementación y el despliegue exitoso de la _Landing Page_ estática en GitHub Pages al cierre del Sprint 1 demuestra la viabilidad técnica del equipo para cumplir con los hitos planificados. Este logro evidencia un dominio adecuado de las herramientas de gestión de configuración de software (Git/GitHub) y establece una base sólida para la futura entrega continua del producto web.

#### Recomendaciones

1. **Implementación de la Capa de Servicios (Backend):** Para los siguientes Sprints, se recomienda priorizar el diseño e implementación de la base de datos relacional y el desarrollo de servicios web (API RESTful). Esto es vital para dar vida a las historias de usuario de mayor impacto, permitiendo la persistencia de los registros de glucosa y la emisión automatizada de alertas de hipoglucemia hacia los médicos.
2. **Priorización de la Seguridad de Datos Clínicos:** Dado que **GlucoSmart** procesará información médica altamente sensible, se recomienda integrar requerimientos no funcionales de seguridad desde el inicio del desarrollo del backend. Esto incluye la encriptación de datos en tránsito y en reposo, autenticación robusta (ej. JSON Web Tokens) y el estricto cumplimiento de la Ley de Protección de Datos Personales vigente en el país.
3. **Integración de Pruebas Automatizadas:** Se sugiere incorporar la automatización de pruebas (unitarias y de integración) en el flujo de trabajo del repositorio. Considerando que el sistema maneja alertas de riesgo vital para los pacientes, asegurar la calidad del código mediante la integración continua (CI) minimizará la probabilidad de fallos en el entorno de producción al momento de notificar reacciones adversas o crisis glucémicas.

# <a name="_toc226040465"></a>Bibliografía

- Carrillo-Larco, R. M., & Bernabé-Ortiz, A. (2019). Diabetes mellitus tipo 2 en Perú: Una revisión sistemática sobre la prevalencia e incidencia en población general. Revista Peruana de Medicina Experimental y Salud Pública. [https://doi.org/10.17843/rpmesp.2019.361.4027](https://doi.org/10.17843/rpmesp.2019.361.4027)

- Lozano Ortiz, M., & Salazar González, B. C. (2007). Estrés percibido y adaptación en pacientes con diabetes mellitus tipo 2. [](http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S1657-59972007000100007) [http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S1657-59972007000100007](http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S1657-59972007000100007)

- Mishra, L. N. (2024, 5 de agosto). Functional Requirements Analysis – Benefits, Steps and Challenges. Adaptive US. Recuperado el 14 de septiembre de 2025. [https://www.adaptiveus-com.translate.goog/blog/functional-requirements-analysis/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc](https://www.adaptiveus-com.translate.goog/blog/functional-requirements-analysis/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc)

- Domínguez Reyes, M. Y., & Viamonte Pérez, Y. (2014). Ansiedad, depresión y vulnerabilidad al estrés ante el diagnóstico reciente de diabetes mellitus tipo 2. Gaceta Médica Espirituana. [http://scielo.sld.cu/scielo.php?pid=s1608-89212014000300009&script=sci_arttext&tlng=en](http://scielo.sld.cu/scielo.php?pid=s1608-89212014000300009&script=sci_arttext&tlng=en)

- Organización Mundial de la Salud. (2024, 14 de noviembre). Diabetes. [https://www.who.int/news-room/fact-sheets/detail/diabetes](https://www.who.int/news-room/fact-sheets/detail/diabetes?utm_source=chatgpt.com) [Organización Mundial de la Salud](https://www.who.int/news-room/fact-sheets/detail/diabetes)

- GBD 2021 Diabetes Collaborators. (2023). Global, regional, and national burden of diabetes from 1990 to 2021, with projections of prevalence to 2050: A systematic analysis for the Global Burden of Disease Study 2021. The Lancet, 402(10397), 203–234. [Global, regional, and national burden of diabetes from 1990 to 2021, with projections of prevalence to 2050: a systematic analysis for the Global Burden of Disease Study 2021 - The Lancet](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736\(23\)01301-6/fulltext)

- Yu, X., Wang, Z., Liu, S., & Jung, H. (2025). Technological functionality and system architecture of mobile health interventions for diabetes management: A systematic review and meta-analysis of randomized controlled trials. Frontiers in Public Health, 13, 1549568. [](https://doi.org/10.3389/fpubh.2025.1549568)[Frontiers | Technological functionality and system architecture of mobile health interventions for diabetes management: a systematic review and meta-analysis of randomized controlled trials  ](https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2025.1549568/full)

- Organización Panamericana de la Salud. (s. f.). Farmacovigilancia. [https://www.paho.org/es/temas/farmacovigilancia](https://www.paho.org/es/temas/farmacovigilancia?utm_source=chatgpt.com)

- Tang, Z., Zhao, L., Li, J., Yang, Y., Liu, F., Li, H., Yang, Z., Qin, S., & Li, X. (2024). Prognostic effectiveness of interactive vs. non-interactive mobile app interventions in type 2 diabetes: A systematic review and meta-analysis. Archives of Public Health, 82, 221. [](https://doi.org/10.1186/s13690-024-01450-x)[Prognostic effectiveness of interactive vs. non-interactive mobile app interventions in type 2 diabetes: a systematic review and meta-analysis | Archives of Public Health | Full Text](https://archpublichealth.biomedcentral.com/articles/10.1186/s13690-024-01450-x)

- Oracle. (s. f.). What is MySQL? Oracle. Recuperado el 4 de octubre de 2025, de [](https://www.oracle.com/mysql/what-is-mysql/?utm_source=chatgpt.com)[https://www.oracle.com/mysql/what-is-mysql/](https://www.oracle.com/mysql/what-is-mysql/)

- Amazon Web Services. (2024). Amazon DynamoDB documentation. [https://docs.aws.amazon.com/dynamodb/](https://docs.aws.amazon.com/dynamodb/)
# <a name="_toc226040466"></a>Anexos

Anexo 1: [LandignPage Desplegada](https://mts-opensource.github.io/IntegraVida/)
Anexo 2: [Mockups - Wireframe](https://www.figma.com/design/lu1p4NLglhTYnbHWT8lDl4/GlucoSmart-Prototype?node-id=0-1&t=LGg8wMfqWMWoYlOB-1)
Anexo 3: [Impact Mapping](https://miro.com/app/board/uXjVHdifA00=/?share_link_id=602434447345)
