# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

En esta sección el equipo de Avisum organiza lo que sabe, cree y desconoce de su solución para convertirlo en preguntas listas para experimentar. Siguiendo el enfoque de Experiment-Driven Product Development (XDPD), el foco está en **generar y priorizar preguntas, no soluciones**: en lugar de probar si el botón de alerta o el conteo de pasajeros "funcionan", se prueban las premisas que sostienen cada idea. El punto de partida es la evidencia de los capítulos I a III (Lean UX, entrevistas, Needfinding y requerimientos) y el estado de implementación de los capítulos V a VII.

### 8.1.1. As-Is Summary.

A continuación se resume el material bruto de partida al cierre del Sprint 1, con el objetivo de generar preguntas y no soluciones. La Tabla 1 reúne lo que el equipo ya sabe con respaldo en evidencia propia, y la Tabla 2 lo que aún no se ha validado.

| # | Hallazgo | Evidencia | Sección del informe |
|---|---|---|---|
| 1 | Los conductores enfrentan cobros de cupo de forma cotidiana a semanal y trabajan jornadas de entre 14 y más de 18 horas, con mayor sensación de riesgo en horario nocturno. | Entrevistas a 3 conductores (jornadas de 4:00–22:00, 4:30–21:00 y 6:00–20:00). | 2.2.2, 2.2.3 |
| 2 | Pedir ayuda hoy depende del celular personal del conductor o de un número de la empresa que no siempre responde a tiempo. | Los 3 conductores entrevistados coinciden; dos señalan que llamar mientras conducen es lento o peligroso. | 2.2.2 |
| 3 | Las empresas suelen enterarse de los incidentes por llamadas y, en algunos casos, cuando el hecho ya ocurrió. | Entrevistas a 3 representantes de empresas (2 lo mencionan de forma explícita). | 2.2.2, 2.3.2 |
| 4 | La verificación del conductor es manual o documental y admite suplantación o personas no autorizadas. | Los 3 representantes de empresas lo reconocen. | 2.2.2 |
| 5 | Los seis entrevistados valoran una solución tecnológica. Los conductores declaran alta disposición a usar una app con validación por QR; las empresas señalan como barreras el costo, la capacitación y la falta de apoyo institucional. | Análisis de entrevistas y User Personas. | 2.2.3, 2.3.1 |
| 6 | Las historias del Sprint 1 figuran como realizadas: alerta con confirmación de recepción, clasificación por gravedad, verificación de identidad, conteo con sensor, seguimiento GPS, panel de la central, historial y API REST. Cuentan con pruebas unitarias y de integración, y despliegue en Render y Vercel. | Sprint Backlog, Testing Suites y pipelines de despliegue. | 5.2.1, 6.1, 7.1–7.3 |


_Tabla 1. Lo que el equipo sabe hoy - Elaboración propia._

| # | Lo que aún no sabemos o no hemos validado | Por qué importa |
|---|---|---|
| 1 | Ninguna funcionalidad ha sido usada por conductores o empresas en operación real. Lo recogido es disposición declarada, no comportamiento observado. | Decir que se usaría una app no garantiza que se use bajo presión, de noche o durante un cobro de cupo. |
| 2 | Las 6 entrevistas se realizaron en Lima y Callao. No hay voces de conductores o empresas del norte del país, donde el problema también está descrito. | La muestra es pequeña y puede no representar a todo el segmento objetivo. |
| 3 | No existe una línea base del tiempo que tarda hoy una empresa en enterarse de un incidente y reaccionar. | "Reducir el tiempo de respuesta" es el principal Business Outcome (1.2.2.2) y no podemos afirmar una mejora sin una referencia. |
| 4 | Las pruebas actuales verifican el código del backend, no el comportamiento del sistema con red móvil real, vehículo en movimiento o puerta con pasajeros. | Una alerta o un conteo que funcionan en pruebas pueden fallar en las condiciones reales de ruta. |
| 5 | El precio de S/ 99 por unidad al mes, con 20 % de descuento desde 3 unidades (2.1.1), no se ha contrastado con ninguna empresa. | Sostiene el modelo de ingresos y el interés de las empresas en adoptar la solución. |
| 6 | No se sabe quién atiende el panel dentro de la empresa, en qué horarios ni con qué protocolo. | Una alerta enviada con éxito no sirve si nadie la ve y actúa a tiempo. |


_Tabla 2. Vacíos de conocimiento al cierre del Sprint 1 - Elaboración propia._

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims.

Se recopilan las fuentes de inspiración de las preguntas, identificadas con un código para rastrear de qué material proviene cada pregunta. Las ideas se tratan como puntos de partida para descubrir sus premisas, no como algo que se vaya a experimentar en sí mismo.

**Ideas**

| ID | Idea | Premisa subyacente que habría que probar | Origen |
|---|---|---|---|
| I-01 | Botón de alerta discreto (silencioso) en la app del conductor. | El conductor puede activarlo sin que el agresor lo note y sin soltar el volante. | EP002, US03; entrevistas a conductores 2 y 3 |
| I-02 | Confirmación de recepción (ACK) de la alerta hacia el conductor. | Ver la confirmación reduce la incertidumbre y la alerta llega a la central más rápido que una llamada. | US19, 3.1 |
| I-03 | Verificación de identidad del conductor (QR o reconocimiento facial) antes de iniciar el servicio. | Los conductores la aceptan y no retrasa el inicio de jornada, que empieza de madrugada. | EP001, US01 |
| I-04 | Conteo automático de pasajeros con sensor en la puerta. | El sensor cuenta con precisión suficiente en condiciones reales y el dato ayuda a gestionar emergencias. | EP003, US06, US35 |
| I-05 | Panel centralizado con ubicación, estado y alertas clasificadas por gravedad. | La empresa entiende y decide con la información del panel más rápido que hoy. | US21, US26, US28 |


_Tabla 3. Ideas - Elaboración propia._

**Claims (Afirmaciones)**

| ID | Afirmación | Quién la hace / fuente |
|---|---|---|
| C-01 | Los cobros de cupo son prácticamente cotidianos y se asumen como parte del trabajo. | Conductores 1 y 2 (2.2.2) |
| C-02 | Pedir ayuda en una emergencia es lento y complicado porque depende del celular personal. | Conductores 1 y 2 (2.2.2) |
| C-03 | Lo prioritario es una alarma silenciosa, porque una alerta visible puede empeorar la situación. | Conductora 3 (2.2.2) |
| C-04 | La verificación manual del conductor no garantiza control total y hay personas infiltradas. | Empresas 2 y 3 (2.2.2) |
| C-05 | La eficacia de la tecnología depende también del apoyo institucional y de la respuesta de las autoridades. | Empresa 2 (2.2.2) |
| C-06 | Cerca del 40 % de empresas de Lima y Callao pagan cupos y el 68 % de mujeres ha sufrido inseguridad o acoso en el transporte público. | Gremios y Defensoría del Pueblo, citados en 1.2.1 (fuentes secundarias) |


_Tabla 4. Claims - Elaboración propia._

**Assumptions (Suposiciones)**

| ID | Suposición | Origen |
|---|---|---|
| A-01 | Las empresas operadoras necesitan herramientas digitales para supervisar sus unidades y gestionar incidentes de seguridad. | Business Assumptions (1.2.2.2) |
| A-02 | Las empresas adoptarían y pagarían por la solución si mejora la trazabilidad (S/ 99 por unidad al mes). | 1.2.2.2 y 2.1.1 |
| A-03 | Los conductores que declaran disposición a usar la app la usarán, y activarán la alerta, en una emergencia real. | Entrevistas (2.2.3); no verificada |
| A-04 | Siempre hay alguien en la empresa con capacidad y protocolo para atender una alerta, incluso de noche. | Implícita en Hypothesis Statement 1 (1.2.2.3) |
| A-05 | Hay cobertura de datos móviles suficiente en las rutas de riesgo para enviar la alerta. | Implícita en US03, US04 y US36 |
| A-06 | Una alerta digital con confirmación mejora el tiempo de respuesta frente a la llamada telefónica. | Hypothesis Statement 1 (1.2.2.3) |
| A-07 | Los conductores perciben el seguimiento de ubicación y la validación de identidad como protección y no como vigilancia. | Preguntas 9–11 del diseño de entrevistas (2.2.1) |


_Tabla 5. Assumptions - Elaboración propia._

**Knowledge Gaps (Brechas de Conocimiento)**

| ID | Brecha | Relacionada con |
|---|---|---|
| K-01 | ¿Cuánto demora hoy una empresa en enterarse de un incidente y en actuar? No hay línea base. | Tabla 2 (#3), A-06 |
| K-02 | ¿Quién atiende los avisos en la empresa, con qué protocolo y en qué horarios? | Tabla 2 (#6), A-04 |
| K-03 | ¿Con qué precisión cuenta el sensor con puerta llena, hora punta o pasajeros que suben y bajan a la vez? | I-04, US35 |
| K-04 | ¿Qué celulares y planes de datos tienen los conductores y dónde se pierde la señal en sus rutas? | A-05 |
| K-05 | ¿Quién decide la compra (dueño de unidad o consorcio) y qué presupuesto maneja? | A-02, Tabla 2 (#5) |
| K-06 | ¿Qué pasa si el agresor detecta la alerta? ¿Hay situaciones en las que el conductor prefiera no usarla por miedo a represalias? | C-03, A-03 |


_Tabla 6. Knowledge Gaps - Elaboración propia._

### 8.1.3. Experiment-Ready Questions.

Las preguntas **impulsadas por creencias (belief-led)** ponen a prueba una suposición o premisa concreta. Las **exploratorias** recopilan conocimiento donde el equipo no tiene una creencia previa. Los umbrales numéricos de las tarjetas de la sección 8.1.5 son propuestas iniciales que el equipo ajustará antes de ejecutar.

| ID | Pregunta | Tipo | Material de origen |
|---|---|---|---|
| BQ-01 | ¿Es cierto que un conductor puede activar la alerta de forma discreta, sin soltar el volante ni que el agresor lo note? | Belief-led | I-01, C-03, A-03 |
| BQ-02 | ¿Es cierto que la alerta de Avisum llega a la central y es confirmada más rápido que el método actual (llamada telefónica)? | Belief-led | I-02, C-02, A-06 |
| BQ-03 | ¿Es cierto que una persona de la empresa puede ver, entender y decidir ante una alerta en el panel en un tiempo razonable? | Belief-led | I-05, A-04 |
| BQ-04 | ¿Es cierto que las empresas estarían dispuestas a pagar S/ 99 por unidad al mes? | Belief-led | A-02 |
| BQ-05 | ¿Es cierto que la verificación de identidad no retrasa el inicio de la jornada del conductor? | Belief-led | I-03, C-04 |
| BQ-06 | ¿Es cierto que el sensor cuenta pasajeros con una precisión aceptable en condiciones reales de ruta? | Belief-led | I-04, K-03 |
| BQ-07 | ¿Es cierto que los conductores perciben el seguimiento de ubicación como protección y no como vigilancia? | Belief-led | A-07 |
| EQ-01 | ¿Cómo se entera y cómo reacciona hoy una empresa ante un incidente, y cuánto demora cada paso? | Exploratoria | K-01 |
| EQ-02 | ¿Qué dispositivos y cobertura de datos tienen los conductores en sus rutas? | Exploratoria | K-04, A-05 |
| EQ-03 | ¿Quién decide la compra de una solución como Avisum y qué presupuesto maneja? | Exploratoria | K-05 |
| EQ-04 | ¿En qué situaciones un conductor no usaría el botón de alerta y por qué? | Exploratoria | K-06, C-03 |


_Tabla 7. Experiment-Ready Questions - Elaboración propia._

**Técnica de las Cinco Ws (y una H) aplicada a la idea del botón de alerta**

Se aplicó la técnica sobre la idea I-01 para descubrir premisas ocultas. Varias de las preguntas de la Tabla 7 surgieron de este ejercicio.

| W / H | Pregunta formulada | Premisa oculta descubierta | Pregunta derivada |
|---|---|---|---|
| **Who** | ¿Quién recibe la alerta en la empresa a las 4 a.m. o de noche y quién decide qué hacer? | Siempre hay alguien disponible y con autoridad para actuar. | BQ-03 |
| **What** | ¿Qué situaciones considera el conductor una emergencia que justifica pulsar el botón? | El conductor reconoce a tiempo el momento de pulsarlo y lo hace. | EQ-04 |
| **Where** | ¿En qué tramos de la ruta se pierde la señal móvil? | Hay datos móviles en las zonas donde más se necesita la alerta. | EQ-02 |
| **When** | ¿En qué momento puede pulsarlo sin ser visto: durante el cobro, antes o después? | El conductor tiene una mano libre y la pantalla no lo delata. | BQ-01 |
| **Why** | ¿Por qué una empresa pagaría por unidad cada mes por esta solución? | El valor percibido supera el costo y el precio es viable. | BQ-04, EQ-03 |
| **How** | ¿Cómo se atiende hoy un incidente y cómo sabremos si Avisum lo mejora? | Existe una referencia contra la cual comparar. | EQ-01, BQ-02 |


_Tabla 8. Cinco Ws y una H - Elaboración propia._

### 8.1.4. Question Backlog.

El backlog es una **lista priorizada de preguntas de investigación**, no de funcionalidades. Cada pregunta registra su **motivación (el "por qué")**, necesaria para justificar el esfuerzo del experimento, y se puntúa con cuatro criterios en una escala de 1 a 5: **Confianza** (qué tan seguros estamos de la respuesta; 1 = no tenemos idea), **Riesgo** (qué tan grave es que la creencia sea falsa), **Impacto** (cuánto cambia el producto o el negocio según la respuesta) e **Interés** (cuánto quiere el equipo saber la respuesta).

Como convención del equipo, la puntuación es **Confianza invertida + Riesgo + Impacto + Interés**, es decir (6 − Confianza) + R + I + In, con un máximo de 20: cuanto menos confiamos en la respuesta, más urge probarla. **En caso de empate se prioriza la pregunta con mayor Riesgo.**

| # | ID | Pregunta (resumen) | Por qué | C | R | I | In | Pts |
|---|---|---|---|---|---|---|---|---|
| 1 | BQ-02 | ¿La alerta llega y se confirma más rápido que una llamada? | Es el resultado de negocio central (reducir el tiempo de respuesta). Si falla, la propuesta de valor pierde sentido. | 2 | 5 | 5 | 5 | 19 |
| 2 | EQ-01 | ¿Cómo reacciona hoy una empresa ante un incidente y cuánto demora? | Sin línea base no se puede demostrar mejora. Es requisito previo de BQ-02. | 1 | 4 | 5 | 5 | 19 |
| 3 | BQ-01 | ¿Se puede activar la alerta de forma discreta sin soltar el volante? | Afecta la seguridad física del conductor: una alerta visible puede agravar la situación. | 2 | 5 | 5 | 4 | 18 |
| 4 | EQ-04 | ¿Cuándo no usaría el botón un conductor y por qué? | Un botón que no se usa por miedo no aporta valor, aunque funcione técnicamente. | 2 | 5 | 4 | 4 | 17 |
| 5 | BQ-03 | ¿La central puede ver, entender y decidir ante una alerta a tiempo? | Una alerta recibida y nadie que actúe no reduce el riesgo. | 2 | 4 | 5 | 4 | 17 |
| 6 | EQ-02 | ¿Qué dispositivos y cobertura tienen los conductores? | La alerta depende de datos móviles; sin cobertura el sistema falla donde más se necesita. | 2 | 4 | 4 | 3 | 15 |
| 7 | BQ-06 | ¿El sensor cuenta con precisión aceptable en ruta? | El conteo es una pieza técnica con riesgo de hardware y apoya la gestión de emergencias. | 3 | 4 | 3 | 4 | 14 |
| 8 | BQ-04 | ¿Pagarían S/ 99 por unidad al mes? | Sostiene el modelo de ingresos y la decisión de compra. | 2 | 3 | 4 | 3 | 14 |
| 9 | BQ-07 | ¿Perciben el seguimiento como protección y no como vigilancia? | El rechazo por sensación de vigilancia frenaría la adopción de los conductores. | 3 | 4 | 3 | 3 | 13 |
| 10 | BQ-05 | ¿La verificación de identidad retrasa el inicio de jornada? | La fricción en el arranque de la jornada podría llevar a evitar el sistema. | 3 | 3 | 4 | 3 | 13 |
| 11 | EQ-03 | ¿Quién decide la compra y con qué presupuesto? | Define a quién y cómo se vende; condiciona la estrategia comercial. | 3 | 3 | 3 | 3 | 12 |


_Tabla 9. Question Backlog priorizado - Elaboración propia. C = Confianza, R = Riesgo, I = Impacto, In = Interés, Pts = puntuación total._

Hubo cuatro empates resueltos por mayor Riesgo: BQ-02 se ubica sobre EQ-01 (19 puntos), EQ-04 sobre BQ-03 (17), BQ-06 sobre BQ-04 (14) y BQ-07 sobre BQ-05 (13). Aunque EQ-01 puntúa igual que BQ-02, debe ejecutarse primero o en paralelo, porque entrega la línea base contra la cual se compara BQ-02.

**Estructura del backlog: amplio y profundo**

En esta etapa el backlog es **amplio (broad)**: cubre varias áreas (alerta, empresa, precio, hardware) con una pregunta por cada una, porque el equipo aún no sabe cuáles premisas son las más frágiles. Una vez ejecutados los primeros experimentos, la pregunta de mayor puntuación se vuelve **profunda (deep)** y se descompone en subpreguntas. A modo de ejemplo, así se profundizaría BQ-02:

| ID | Subpregunta | Dato que aporta |
|---|---|---|
| BQ-02.1 | ¿Cuánto tarda la alerta desde que se pulsa hasta que aparece en el panel con red 4G real y vehículo en movimiento? | Latencia de punta a punta |
| BQ-02.2 | ¿Con qué frecuencia la alerta no llega y el reintento automático la recupera? | Tasa de entrega |
| BQ-02.3 | ¿Cuánto tarda en verse la confirmación (ACK) en la app del conductor? | Tiempo hasta el ACK |
| BQ-02.4 | ¿Cambia el resultado cuando el servicio del backend estuvo inactivo y arranca en frío? | Efecto del arranque en frío |


_Tabla 10. Ejemplo de backlog profundo para BQ-02 - Elaboración propia._

### 8.1.5. Experiment Cards.

La Tarjeta de Experimento captura lo esencial antes de ejecutar. El **lado frontal** registra la pregunta, el por qué, la hipótesis (si aplica) y el qué: la cosa más simple y útil (Simplest Useful Thing) que permite responder. El **lado posterior** detalla la configuración: medidas, condiciones y escala. Se presentan las tarjetas de las cuatro preguntas con mayor puntuación; las demás se elaborarán cuando lleguen a la cabeza del backlog.

**Tarjeta EX-01 · EQ-01 · Línea base de respuesta ante incidentes**

| EX-01 · Lado frontal | |
|---|---|
| **Pregunta** | ¿Cómo se entera y cómo reacciona hoy una empresa ante un incidente, y cuánto demora cada paso? |
| **Por qué** | Sin una línea base no podemos afirmar que Avisum reduce el tiempo de respuesta, que es el principal Business Outcome (1.2.2.2). Es requisito previo de BQ-02. |
| **Hipótesis** | No aplica (pregunta exploratoria). |
| **Qué (Simplest Useful Thing)** | Entrevistas cortas de reconstrucción de los dos últimos incidentes reales de cada empresa, armando la línea de tiempo: hora del hecho, hora del aviso, hora de la primera acción. No requiere construir nada. |


| EX-01 · Lado posterior | |
|---|---|
| **Medidas** | - Minutos entre el hecho y el aviso a la empresa</br>- Minutos entre el aviso y la primera acción</br>- Canal usado (llamada, WhatsApp, otro) y quién actuó |
| **Condiciones** | - Empresas de Lima y Callao con 3 o más unidades</br>- Incidentes de los últimos 3 meses</br>- Entrevista de 20 a 30 minutos, sin mostrar Avisum para no sesgar las respuestas |
| **Escala** | 5 empresas (las 3 ya entrevistadas más 2 nuevas), 2 incidentes por empresa, hasta 10 incidentes. Duración estimada: 1 semana. |


_Tarjeta EX-01. Línea base de respuesta ante incidentes - Elaboración propia._

**Tarjeta EX-02 · BQ-02 · Alerta frente a llamada telefónica**

| EX-02 · Lado frontal | |
|---|---|
| **Pregunta** | ¿Es cierto que la alerta de Avisum llega a la central y es confirmada más rápido que el método actual (llamada telefónica)? |
| **Por qué** | Es el resultado de negocio central de la solución. Si la alerta no es más rápida o confiable que una llamada, la propuesta de valor no se sostiene. |
| **Hipótesis** | Creemos que la alerta llega al panel y el conductor recibe el ACK más rápido que una llamada al número de la empresa. Sabremos que es cierto si se cumplen los umbrales propuestos en el lado posterior. |
| **Qué (Simplest Useful Thing)** | Prueba de campo con el sistema ya construido en el Sprint 1: un conductor simulado pulsa el botón durante un recorrido y una persona en la central cronometra la llegada en el panel; en el mismo escenario se cronometra una llamada. |


| EX-02 · Lado posterior | |
|---|---|
| **Medidas** | - Segundos desde que se pulsa hasta que la alerta aparece en el panel</br>- Segundos hasta ver el ACK en la app del conductor</br>- Porcentaje de alertas entregadas</br>- Segundos desde que se marca el número hasta que contestan (llamada) |
| **Condiciones** | - Recorrido urbano en vehículo en movimiento</br>- Tres condiciones de red: 4G estable, 4G débil y sin datos con recuperación</br>- Backend activo y backend tras un periodo de inactividad (arranque en frío)</br>- Umbrales propuestos: entrega mayor o igual a 95 %, notificación en panel en 5 s o menos (mediana) y ACK en 10 s o menos |
| **Escala** | 30 alertas por condición de red (90 en total) y 10 llamadas de comparación. Dos recorridos. Duración estimada: 1 semana, después de EX-01. |


_Tarjeta EX-02. Alerta frente a llamada telefónica - Elaboración propia._

**Tarjeta EX-03 · BQ-01 · Activación discreta de la alerta**

| EX-03 · Lado frontal | |
|---|---|
| **Pregunta** | ¿Es cierto que un conductor puede activar la alerta de forma discreta, sin soltar el volante ni que el agresor lo note? |
| **Por qué** | Afecta la seguridad física del conductor. Una alerta visible podría agravar la situación (C-03) y el diseño actual no se ha probado con conductores. |
| **Hipótesis** | Creemos que un conductor activa la alerta en 3 s o menos, con un máximo de 2 toques y sin mirar la pantalla más de 1 s. Sabremos que es cierto si al menos 4 de cada 5 conductores lo logran sin que el observador lo detecte. |
| **Qué (Simplest Useful Thing)** | Prueba de usabilidad con el prototipo actual de la app, con la unidad detenida. Un observador representa al cobrador y el conductor debe activar la alerta sin que este lo note. |


| EX-03 · Lado posterior | |
|---|---|
| **Medidas** | - Segundos hasta la activación</br>- Número de toques y errores</br>- Tiempo con la vista en la pantalla</br>- Si el observador detectó la acción (sí/no)</br>- Percepción de discreción del conductor (1 a 5) |
| **Condiciones** | - Unidad detenida y apagada. No se pide operar la app mientras se conduce, por seguridad</br>- Celular en el soporte habitual del conductor</br>- Tres intentos por conductor, el último de noche o con poca luz |
| **Escala** | 5 conductores (los 3 entrevistados, entre ellos la conductora que pidió la alarma silenciosa, más 2 nuevos), 3 intentos cada uno, 15 intentos. Duración estimada: 2 a 3 días. |


_Tarjeta EX-03. Activación discreta de la alerta - Elaboración propia._

**Tarjeta EX-04 · EQ-04 · Cuándo no usaría el botón**

| EX-04 · Lado frontal | |
|---|---|
| **Pregunta** | ¿En qué situaciones un conductor no usaría el botón de alerta y por qué? |
| **Por qué** | Un botón que no se usa por miedo a represalias no aporta valor aunque funcione. Hoy solo tenemos disposición declarada (A-03), no los límites reales de uso. |
| **Hipótesis** | No aplica (pregunta exploratoria). |
| **Qué (Simplest Useful Thing)** | Entrevistas semiestructuradas con escenarios hipotéticos: se describen situaciones (cobro de cupo, asalto, acoso, accidente) y se pregunta qué haría el conductor y qué lo frenaría. No requiere software. |


| EX-04 · Lado posterior | |
|---|---|
| **Medidas** | - Situaciones en las que NO usaría el botón</br>- Motivos mencionados (represalias, vergüenza, desconfianza en la respuesta)</br>- Frecuencia con que se menciona cada motivo</br>- Qué cambio en el diseño o el protocolo lo haría usarlo |
| **Condiciones** | - Entrevista individual de 20 minutos y con confidencialidad</br>- Conductores de distintas rutas y turnos, incluyendo al menos una mujer</br>- Sin presentar el botón como solución para no inducir respuestas |
| **Escala** | 6 conductores, entre ellos los 3 ya entrevistados. Duración estimada: 1 semana, en paralelo con EX-01. |


_Tarjeta EX-04. Cuándo no usaría el botón - Elaboración propia._

## 8.2. Experiment Design

### 8.2.1. Hypotheses.

Las hipótesis formales corresponden únicamente a las preguntas belief-led (BQ). Las preguntas exploratorias (EQ-01 y EQ-04) no generan hipótesis previas porque su propósito es descubrir, no confirmar una creencia del equipo.

| ID | Pregunta | Enunciado de hipótesis | Criterio de éxito |
|---|---|---|---|
| H-01 | BQ-02 | Creemos que la alerta de Avisum llega al panel de la central y el conductor recibe la confirmación (ACK) más rápido que una llamada telefónica al número de la empresa. | Tasa de entrega ≥ 95 %; notificación en el panel en ≤ 5 s (mediana); ACK en ≤ 10 s; cumplidos en al menos 2 de las 3 condiciones de red evaluadas. |
| H-02 | BQ-01 | Creemos que un conductor puede activar la alerta de forma discreta en ≤ 3 s, con un máximo de 2 toques y sin que el observador lo detecte. | Al menos 4 de cada 5 conductores superan el umbral en los 3 intentos; ninguno es detectado por el observador en el último intento (con poca luz). |
| H-03 | BQ-03 | Creemos que un operador de la central puede ver, interpretar y tomar una primera decisión ante una alerta en el panel en ≤ 2 minutos desde su llegada. | ≥ 4 de cada 5 operadores reaccionan dentro del umbral sin haber recibido más de 10 minutos de entrenamiento previo. |
| H-04 | BQ-04 | Creemos que al menos 3 de cada 5 empresas con 3 o más unidades declaran disposición a pagar S/ 99 por unidad al mes tras ver el sistema en funcionamiento. | Mínimo 3 de 5 empresas confirman disposición de pago después de la demostración. |
| H-05 | BQ-05 | Creemos que la verificación de identidad del conductor no agrega más de 30 segundos al inicio de la jornada. | Tiempo medio de verificación ≤ 30 s en al menos 4 de cada 5 conductores en la prueba. |
| H-06 | BQ-06 | Creemos que el sensor cuenta pasajeros con una precisión ≥ 90 % en condiciones reales de ruta (hora punta, subidas y bajadas simultáneas). | Precisión ≥ 90 % en al menos 80 % de las mediciones registradas durante el recorrido de prueba. |
| H-07 | BQ-07 | Creemos que al menos 4 de cada 5 conductores perciben el seguimiento de ubicación como una medida de protección y no como vigilancia. | ≥ 4 de cada 5 conductores puntúan la afirmación "Me siento protegido, no vigilado" con 4 o 5 en escala de 1 a 5 tras ver la funcionalidad. |

_Tabla 11. Hipótesis del proyecto Avisum - Elaboración propia._

---

### 8.2.2. Domain Business Metrics.

Las métricas de negocio son los indicadores de alto nivel con los que Avisum medirá si su propuesta de valor se cumple. Se dividen en métricas de resultado (lo que el negocio persigue) y métricas de producto (señales que explican por qué el resultado mejora o empeora).

**Métricas de resultado**

| ID | Métrica | Definición | Meta inicial |
|---|---|---|---|
| BM-01 | Tiempo de respuesta ante incidentes | Minutos entre el hecho y la primera acción documentada de la empresa | Reducción ≥ 30 % respecto a la línea base obtenida en EX-01 |
| BM-02 | Tasa de adopción por conductores | Porcentaje de conductores registrados que activan al menos una sesión semanal | ≥ 70 % en el primer mes de operación |
| BM-03 | Retención de empresas cliente | Porcentaje de empresas que renuevan el pago en el segundo mes | ≥ 80 % |
| BM-04 | Alertas gestionadas a tiempo | Porcentaje de alertas ante las que la central ejecuta una primera acción en ≤ 5 minutos | ≥ 90 % |

**Métricas de producto**

| ID | Métrica | Definición | Experimento que la produce |
|---|---|---|---|
| PM-01 | Latencia de alerta extremo a extremo | Segundos entre la pulsación del botón y la aparición de la alerta en el panel | EX-02 |
| PM-02 | Tasa de entrega de alertas | Porcentaje de alertas que llegan al panel sin intervención manual | EX-02 |
| PM-03 | Tiempo de verificación de identidad | Segundos desde que el conductor abre la validación hasta la confirmación | Sin experimento definido aún (H-05); se alimenta de los eventos identity_verification_* de 8.2.8 |
| PM-04 | Tiempo de activación discreta | Segundos hasta pulsar el botón de alerta sin ser detectado | EX-03 |
| PM-05 | Precisión del sensor de pasajeros | Porcentaje de conteos correctos respecto al conteo manual de referencia | Sin experimento definido aún (H-06, BQ-06) |
| PM-06 | Tiempo de reacción del operador en el panel | Segundos desde que la alerta aparece en el panel hasta que el operador ejecuta la primera acción | EX-01 (línea base); la medición con Avisum depende de un experimento aún no definido (H-03, BQ-03) |

_Tabla 12. Domain Business Metrics - Elaboración propia._

---

### 8.2.3. Measures.

Cada medida se expresa como una variable concreta, observable y registrable, ligada a un experimento.

| Experimento | Variable | Tipo | Instrumento de registro |
|---|---|---|---|
| EX-01 | Minutos entre el hecho y el aviso a la empresa | Cuantitativa continua | Reconstrucción cronológica en entrevista |
| EX-01 | Minutos entre el aviso y la primera acción | Cuantitativa continua | Reconstrucción cronológica en entrevista |
| EX-01 | Canal de aviso usado (llamada, WhatsApp, radio, otro) | Categórica nominal | Entrevista estructurada |
| EX-01 | Persona que atendió (rol y horario) | Categórica nominal | Entrevista estructurada |
| EX-02 | Segundos entre pulsación y aparición en panel | Cuantitativa continua | Cronómetro manual + log del backend |
| EX-02 | Segundos entre pulsación y ACK en la app del conductor | Cuantitativa continua | Log del backend |
| EX-02 | Alerta entregada (sí/no) | Dicotómica | Log del backend |
| EX-02 | Segundos hasta que contestan la llamada (comparación) | Cuantitativa continua | Cronómetro manual |
| EX-02 | Condición de red activa (4G estable / 4G débil / sin datos) | Categórica ordinal | Medición de señal en tiempo real |
| EX-03 | Segundos hasta la activación | Cuantitativa continua | Cronómetro manual |
| EX-03 | Número de toques para activar | Cuantitativa discreta | Observación directa |
| EX-03 | Segundos con vista en la pantalla | Cuantitativa continua | Observación directa |
| EX-03 | Observador detectó la acción (sí/no) | Dicotómica | Juicio del observador |
| EX-03 | Percepción de discreción del conductor (1 a 5) | Cuantitativa ordinal | Escala Likert post-intento |
| EX-04 | Situaciones en que no usaría el botón | Cualitativa | Transcripción de entrevista |
| EX-04 | Motivos de no uso (represalias, desconfianza, vergüenza) | Categórica nominal | Codificación temática |
| EX-04 | Cambio de diseño o protocolo que lo haría usarlo | Cualitativa | Transcripción de entrevista |

_Tabla 13. Medidas por experimento - Elaboración propia._

---

### 8.2.4. Conditions.

Las condiciones definen el entorno bajo el cual se ejecuta cada experimento para garantizar comparabilidad entre repeticiones y validez externa de los resultados.

**EX-01 — Línea base de respuesta ante incidentes**

- Empresas de Lima y Callao con 3 o más unidades en operación.
- Incidentes reales ocurridos en los últimos 3 meses.
- Entrevista individual de 20 a 30 minutos; sin mostrar Avisum para evitar sesgo de comparación.
- Entrevistador neutro que sigue un guion de reconstrucción cronológica.

**EX-02 — Alerta frente a llamada telefónica**

- Recorrido urbano en vehículo en movimiento (mínimo 20 minutos de duración).
- Tres condiciones de red evaluadas en sesiones separadas: 4G estable, 4G con señal débil (1–2 barras), y pérdida de datos con recuperación automática.
- Backend activo en Render y backend tras un periodo de inactividad de 30 minutos (arranque en frío).
- La comparación de llamada usa el número de empresa de las 3 empresas ya entrevistadas; se cronometra desde que se marca hasta que contesta un operador.
- Hora del día: una sesión diurna y una nocturna por condición de red.

**EX-03 — Activación discreta de la alerta**

- Vehículo detenido y apagado (no se opera la app mientras se conduce, por seguridad).
- Celular ubicado en el soporte habitual del conductor (parabrisas o tablero).
- El observador se sienta en el asiento del copiloto, simulando al cobrador, y registra si nota actividad en el celular.
- Tres intentos por conductor: primer intento con luz normal, segundo con iluminación reducida, tercero de noche o con la cabina oscura.
- Entre intentos, el conductor descansa 2 minutos para evitar efecto de aprendizaje acumulado en el tercer intento.

**EX-04 — Cuándo no usaría el botón**

- Entrevista individual de 20 minutos; lugar elegido por el conductor (su vehículo, un café, etc.) para garantizar comodidad.
- Escenarios hipotéticos presentados en orden fijo: cobro de cupo, asalto, acoso a pasajera, accidente mecánico.
- No se muestra ni describe el botón de Avisum antes de preguntar; se pregunta qué haría el conductor hoy.
- Confidencialidad explicada al inicio y grabación solo con consentimiento explícito.
- Al menos una conductora mujer en la muestra.

_Tabla 14. Condiciones por experimento - Elaboración propia._

---

### 8.2.5. Scale Calculations and Decisions.

El tamaño de cada experimento responde a dos criterios: la naturaleza de la pregunta (exploratoria o cuantitativa) y la disponibilidad de participantes del segmento objetivo.

| Experimento | Muestra | Justificación | Duración estimada |
|---|---|---|---|
| EX-01 | 5 empresas, 2 incidentes por empresa (10 incidentes totales) | La saturación temática en entrevistas exploratorias del sector transporte suele alcanzarse entre 5 y 8 participantes. Se añaden 2 empresas nuevas a las 3 ya conocidas para ampliar diversidad. | 1 semana |
| EX-02 | 90 alertas (30 por condición de red) + 10 llamadas de comparación | Con n = 30 por condición y un efecto esperado grande (diferencia de varios segundos), la potencia estadística es suficiente para detectar diferencias con α = 0,05. Las 10 llamadas permiten estimar el intervalo de confianza del tiempo de llamada. Las sesiones se reparten además entre backend activo y en frío y entre día y noche (unas 7 u 8 alertas por combinación), por lo que el análisis estadístico se hace por condición de red y esas dos variables se reportan de forma descriptiva. | 1 semana (después de EX-01) |
| EX-03 | 5 conductores, 3 intentos cada uno (15 intentos totales) | La prueba de usabilidad evalúa un umbral de proporción (≥ 4/5 exitosos). Con 5 participantes y criterio binario por intento se puede detectar un fallo sistemático. Se prioriza incluir a los 3 conductores ya entrevistados por su familiaridad con el contexto. | 2 a 3 días (en paralelo con EX-01) |
| EX-04 | 6 conductores | Pregunta exploratoria; el criterio de parada es la saturación de motivos de no uso. Se incluyen los 3 ya entrevistados más 3 nuevos de rutas distintas para maximizar diversidad de respuestas. | 1 semana (en paralelo con EX-01) |

_Tabla 15. Escala y decisiones de tamaño muestral - Elaboración propia._

**Decisiones de secuenciación**

EX-01 y EX-04 se ejecutan primero y en paralelo porque no requieren construir nada nuevo y EX-01 entrega la línea base que valida EX-02. EX-02 comienza solo cuando EX-01 ha concluido. EX-03 puede ejecutarse en paralelo con EX-01 y EX-04 porque sus condiciones son independientes.

---

### 8.2.6. Methods Selection.

La selección del método para cada experimento obedece a la naturaleza de la pregunta y al estado de desarrollo del producto.

| Experimento | Método principal | Razón de elección |
|---|---|---|
| EX-01 | Entrevista semiestructurada de reconstrucción cronológica | Pregunta exploratoria sin hipótesis previa. Se necesita el detalle del proceso real de respuesta, no una medición puntual. No requiere el sistema construido. |
| EX-02 | Prueba de campo cuantitativa con cronometría y logs del backend | El sistema ya está desplegado en Render; la pregunta exige medidas numéricas de latencia bajo condiciones controladas pero realistas. El log del backend complementa la cronometría manual y reduce sesgo de observador. |
| EX-03 | Prueba de usabilidad con observador encubierto | La pregunta mezcla rendimiento (tiempo y toques) y comportamiento social (si el agresor lo detecta). Un estudio de laboratorio ligero con observador simula el contexto sin requerir un escenario de riesgo real. |
| EX-04 | Entrevista semiestructurada con escenarios hipotéticos | Pregunta exploratoria sobre comportamiento en situaciones de riesgo. No es ético ni práctico replicar las situaciones reales; los escenarios permiten aproximarse a las motivaciones sin exponer a los participantes. |

_Tabla 16. Selección de métodos - Elaboración propia._

---

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection.

**Objetivo analítico general**

Determinar si las premisas centrales de Avisum son suficientemente sólidas para invertir en el siguiente ciclo de desarrollo, o si alguna de ellas requiere rediseño antes de continuar.

**KPIs por pregunta**

| Pregunta | KPI principal | Umbral de éxito | Acción si no se cumple |
|---|---|---|---|
| BQ-02 | Latencia mediana de alerta extremo a extremo (s) | ≤ 5 s en el panel; ≤ 10 s el ACK | Revisar protocolo de comunicación (WebSocket vs. polling) |
| BQ-02 | Tasa de entrega de alertas | ≥ 95 % | Implementar reintento automático con almacenamiento local offline |
| BQ-01 | Proporción de activaciones discretas exitosas | ≥ 4/5 conductores | Rediseñar la ubicación y el gesto del botón de alerta |
| BQ-03 | Tiempo de reacción del operador ante la alerta | ≤ 2 min | Agregar sonido y notificación push al panel; revisar UX |
| BQ-04 | Proporción de empresas con disposición a pagar | ≥ 3/5 | Revisar el modelo de precios o el empaquetado de la solución |
| BQ-05 | Tiempo medio de verificación de identidad | ≤ 30 s | Simplificar el flujo de validación (menos pasos, biometría más rápida) |
| BQ-06 | Precisión del sensor de conteo | ≥ 90 % | Evaluar tecnología alternativa de sensor o ajustar el modelo de detección |
| BQ-07 | Proporción de conductores con percepción de protección | ≥ 4/5 | Ajustar comunicación del producto y agregar controles de privacidad visibles |

_Tabla 17. KPIs y umbrales de decisión - Elaboración propia._

**Análisis estadístico aplicado**

- EX-02: Mediana y percentil 95 de latencia por condición de red; intervalo de confianza del 95 % para la tasa de entrega; prueba de Wilcoxon para comparar alerta vs. llamada.
- EX-03: Proporción de éxito con intervalo de confianza exacto de Clopper-Pearson; tiempo medio de activación con desviación estándar.
- EX-01 y EX-04: Análisis temático inductivo; frecuencia de menciones por categoría de respuesta.

---

### 8.2.8. Web and Mobile Tracking Plan.

El plan de tracking define los eventos que la app móvil del conductor y el panel web de la central deben registrar para alimentar los KPIs de los experimentos y el monitoreo continuo del producto.

**Eventos de la app del conductor**

| Evento | Propiedades | Propósito |
|---|---|---|
| `session_start` | `conductor_id`, `service_id`, `timestamp`, `device_model`, `os_version` | Medir adopción y detectar dispositivos con problemas |
| `identity_verification_start` | `conductor_id`, `timestamp`, `method` (QR / facial) | Iniciar medición del tiempo de verificación (H-05) |
| `identity_verification_complete` | `conductor_id`, `timestamp`, `duration_ms`, `success` | Cerrar medición de verificación; detectar fallos |
| `service_started` | `conductor_id`, `service_id`, `timestamp` | Confirmar inicio de jornada registrado |
| `alert_button_pressed` | `conductor_id`, `service_id`, `timestamp`, `battery_level`, `network_type` | Inicio de medición de latencia (PM-01) |
| `alert_ack_received` | `conductor_id`, `alert_id`, `timestamp`, `latency_ms` | Tiempo hasta ACK (PM-01, H-01) |
| `service_ended` | `conductor_id`, `service_id`, `timestamp` | Cierre de jornada |
| `session_end` | `conductor_id`, `timestamp`, `duration_ms` | Duración de sesión para métricas de retención |

**Eventos del panel web de la central**

| Evento | Propiedades | Propósito |
|---|---|---|
| `alert_received` | `alert_id`, `service_id`, `timestamp`, `severity_level`, `latency_from_press_ms` | Latencia extremo a extremo (EX-02, PM-01) |
| `alert_viewed` | `alert_id`, `operator_id`, `timestamp` | Tiempo de reacción del operador (H-03) |
| `alert_action_taken` | `alert_id`, `operator_id`, `action_type`, `timestamp` | Cierre del ciclo de respuesta; alimenta BM-04 |
| `panel_session_start` | `operator_id`, `timestamp` | Verificar cobertura horaria del panel (K-02) |
| `vehicle_location_updated` | `vehicle_id`, `lat`, `lng`, `timestamp` | Seguimiento GPS continuo |
| `passenger_count_updated` | `vehicle_id`, `count`, `timestamp`, `source` (sensor / manual) | Precisión del conteo (PM-05) |

**Consideraciones de implementación**

- Todos los eventos se envían a un endpoint de analytics propio (`/api/v1/events`) para evitar dependencia de terceros en zonas con tráfico restringido.
- Los eventos del conductor se almacenan localmente en SQLite si no hay conexión y se sincronizan al recuperar señal, garantizando trazabilidad incluso en zonas de cobertura débil (K-04).
- El `timestamp` siempre es UTC; la conversión a hora local se realiza en el panel.
- Durante los experimentos EX-02 y EX-03 se activa un flag `experiment_session: true` en los eventos para segmentar los datos de prueba de los de producción futura.

_Tabla 18. Plan de tracking web y móvil - Elaboración propia._

---

## 8.3. Experimentation

En esta sección se presenta la fase de Experimentación de Avisum, que lleva los experimentos planificados (sección 8.1) y diseñados (sección 8.2) a trabajo ejecutable por el equipo. El punto de partida es un sistema que ya cuenta con su primera versión: las 37 historias del Capítulo III se completaron en el Sprint 1 (sección 5.2.1). Lo que falta no es más funcionalidad de negocio, sino la capacidad de **medir** si esa funcionalidad cumple lo que el equipo cree. Por eso, las historias de esta sección no reemplazan a las del Capítulo III: se suman a ellas y registran los datos que necesitan los experimentos EX-01 a EX-04 (8.1.5) y el plan de tracking de la sección 8.2.8.

Se trabaja con dos familias de hipótesis que no deben confundirse. Las **hipótesis Lean UX H1 a H4** (sección 1.2.2.3) son las del producto y se resumen en la Tabla 19. Las **hipótesis de experimento H-01 a H-07** (sección 8.2.1) son las que se contrastan en cada experimento; cada historia indica a cuáles aporta datos. Las historias cuyo experimento aparece como “—” sostienen una hipótesis Lean UX, pero la sección 8.2 todavía no define un experimento para ellas.

| Hipótesis | Lo que el equipo cree | Evidencia que el sistema debe poder entregar |
| :--: | :--: | :--: |
| H1 | La gestión de alertas permite al conductor comunicar un riesgo a la central de forma más rápida y oportuna. | Tiempo entre la activación de una alerta y la confirmación de su recepción por la central. |
| H2 | Conocer el estado y la ubicación de las unidades mejora la supervisión de la empresa durante el servicio. | Uso del panel de supervisión y tiempo que toma ubicar una unidad. |
| H3 | Validar y autorizar al conductor antes del servicio mejora la trazabilidad de las operaciones. | Resultado de cada validación y tiempo hasta registrar el inicio del servicio. |
| H4 | Centralizar alertas, ubicaciones y servicios permite un mejor seguimiento de los incidentes. | Alertas almacenadas con su información y uso real del historial de emergencias. |

_Tabla 19. Hipótesis Lean UX que respalda la Experimentación - Elaboración propia._

Para construir estas historias se siguieron tres criterios del enfoque XDPD:

- **La cosa más simple y útil:** cada historia registra solo la información necesaria para responder una pregunta concreta, sin instrumentar todo el sistema.
- **Condiciones de control y experimental:** cada medición se etiqueta con su condición (por ejemplo, alerta de Avisum frente a llamada telefónica, o la condición de red) y los eventos de un experimento se separan de los de producción con el indicador experiment_session definido en la sección 8.2.8.
- **No causar daño:** ningún experimento puede degradar el botón de pánico. En ambas condiciones el conductor conserva el acceso completo a la alerta; la condición experimental solo agrega o mejora comportamiento, y las pruebas de activación (EX-03) se hacen con el vehículo detenido, como define la sección 8.2.4.

### 8.3.1. To-Be User Stories.

Las historias To-Be se agrupan en una nueva épica, EP006, que reúne el trabajo de instrumentación y operación de experimentos. EP006 se relaciona con EP002 (gestión de alertas) y con EP003 (seguimiento de unidades). Tres historias, US45, US46 y US48, profundizan funcionalidad de alertas ya existente, por lo que pertenecen directamente a EP002.

| Epic ID | Title | Description | Acceptance Criteria | Related to (Epic ID) |
| :--: | :--: | :--: | :--: | :--: |
| EP006 | Medición y operación de experimentos | Como equipo de producto, quiero registrar el comportamiento del sistema y comparar condiciones de experimento, para contrastar las hipótesis con evidencia y decidir qué mantener, cambiar o descartar. | No aplicable | EP002, EP003 |

_Tabla 20. Epic To-Be del proyecto - Elaboración propia._

La numeración continúa la del Capítulo III (US01 a US37). Se incorpora el actor **Equipo de producto**, que es quien consulta los resultados de los experimentos.

| Story ID | Title | User | Description | Acceptance Criteria | Epic ID | Priority | Hipótesis Lean UX | H. XDPD (8.2.1) | Experimento (8.1.5) |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| US38 | Registrar marcas de tiempo del ciclo de la alerta | Sistema | Como sistema, quiero registrar la hora de activación, recepción y confirmación de cada alerta, para calcular el tiempo de respuesta de la central. | **Escenario (Éxito):**</br> **Given** que un conductor activa una alerta durante un servicio activo,</br> **When** la central recibe y confirma la alerta,</br> **Then** el sistema guarda las tres marcas de tiempo asociadas a esa alerta.</br> **Escenario (Fracaso):**</br> **Given** que la alerta no recibe confirmación,</br> **When** vence el tiempo de espera,</br> **Then** el sistema conserva la activación y la recepción, deja la confirmación vacía y marca la alerta como no confirmada. | EP006 | Alta | H1 | H-01 | EX-02 |
| US39 | Registrar eventos de atención en el panel de supervisión | Sistema | Como sistema, quiero registrar cuándo un operador abre sesión en el panel, cuándo ve una alerta y cuándo consulta el estado o la ubicación de una unidad, para medir cuánto tarda la central en reaccionar. | **Escenario (Éxito):**</br> **Given** que un operador usa el panel de supervisión,</br> **When** abre sesión, ve una alerta o consulta una unidad,</br> **Then** el sistema registra el evento con el operador, la hora y la alerta o unidad involucrada.</br> **Escenario (Fracaso):**</br> **Given** que el registro del evento falla,</br> **When** el operador consulta la alerta o la unidad,</br> **Then** el panel muestra la información igualmente y el fallo queda anotado en el registro interno. | EP006 | Media | H2 | H-03 | — |
| US40 | Registrar resultado y duración del inicio de servicio | Sistema | Como sistema, quiero registrar el resultado de cada validación de conductor y el tiempo hasta el inicio del servicio, para evaluar la trazabilidad de las operaciones. | **Escenario (Éxito):**</br> **Given** que un conductor intenta iniciar su jornada,</br> **When** el sistema valida su identidad y su autorización,</br> **Then** registra el resultado (aceptada o rechazada), el motivo y el tiempo hasta el inicio del servicio.</br> **Escenario (Fracaso):**</br> **Given** que la validación fue rechazada,</br> **When** el conductor vuelve a intentarlo,</br> **Then** cada intento se registra por separado, sin sobrescribir los anteriores. | EP006 | Media | H3 | H-05 | — |
| US41 | Registrar consultas al historial de alertas | Sistema | Como sistema, quiero registrar cuándo una empresa consulta el historial de alertas, para saber si lo usa en el seguimiento de incidentes. | **Escenario (Éxito):**</br> **Given** que una empresa se encuentra en el historial de alertas,</br> **When** aplica un filtro o abre una alerta,</br> **Then** el sistema registra la consulta con la hora y el filtro usado.</br> **Escenario (Fracaso):**</br> **Given** que no existen alertas registradas,</br> **When** la empresa consulta el historial,</br> **Then** el sistema registra la consulta como una búsqueda sin resultados. | EP006 | Baja | H4 | — | — |
| US42 | Marcar sesiones y eventos de experimento | Sistema | Como sistema, quiero marcar los eventos registrados durante un experimento con su identificador y su condición (control o experimental), para separar los datos de prueba de los de producción y comparar las condiciones. | **Escenario (Éxito):**</br> **Given** que el equipo inicia una sesión de experimento e indica su condición,</br> **When** el conductor o la central generan eventos durante la sesión,</br> **Then** todos los eventos quedan con experiment_session en verdadero, el identificador del experimento y la condición, y la alerta de pánico funciona igual en ambas condiciones.</br> **Escenario (Fracaso):**</br> **Given** que no hay una sesión de experimento activa,</br> **When** se registran eventos,</br> **Then** quedan con experiment_session en falso y no entran en las métricas de ningún experimento. | EP006 | Alta | H1, H2, H3, H4 | H-01, H-02 | EX-02, EX-03 |
| US43 | Consultar métricas del experimento | Equipo de producto | Como equipo de producto, quiero consultar las métricas de cada condición, para contrastar los resultados con las hipótesis. | **Escenario (Éxito):**</br> **Given** que un experimento tiene datos registrados,</br> **When** el equipo consulta sus métricas,</br> **Then** el sistema muestra cada métrica por condición (control y experimental) junto con el número de observaciones.</br> **Escenario (Fracaso):**</br> **Given** que aún no hay datos suficientes,</br> **When** el equipo consulta las métricas,</br> **Then** el sistema indica que la muestra es insuficiente y no presenta conclusiones. | EP006 | Alta | H1, H2, H3, H4 | H-01 | EX-02 |
| US44 | Endpoint de métricas del experimento | Developer | Como developer, quiero consultar las métricas de un experimento mediante API, para usarlas en reportes y en el análisis de resultados. | **Escenario (Éxito):**</br> **Given** un identificador de experimento válido,</br> **When** se envía la consulta,</br> **Then** el API retorna las métricas por condición.</br> **Escenario (Fracaso):**</br> **Given** un identificador de experimento inválido,</br> **When** el API procesa la consulta,</br> **Then** retorna un error. | EP006 | Media | H1, H2, H3, H4 | H-01 | EX-02 |
| US45 | Marcar una alerta como atendida | Empresa | Como empresa, quiero marcar una alerta como atendida, para dejar registro de cuándo se resolvió el incidente. | **Escenario (Éxito):**</br> **Given** una alerta confirmada por la central,</br> **When** la empresa la marca como atendida,</br> **Then** el sistema guarda el nuevo estado y la hora.</br> **Escenario (Fracaso):**</br> **Given** una alerta no confirmada o que ya fue atendida,</br> **When** la empresa intenta marcarla como atendida,</br> **Then** el sistema rechaza la operación. | EP002 | Alta | H1, H4 | H-03 | — |
| US46 | Resumir incidentes por zona y franja horaria | Empresa | Como empresa, quiero ver un resumen de las alertas por zona y franja horaria, para identificar patrones de riesgo en mis rutas. | **Escenario (Éxito):**</br> **Given** que existen alertas con ubicación registrada,</br> **When** la empresa consulta el resumen,</br> **Then** el sistema agrupa las alertas por zona y franja horaria.</br> **Escenario (Fracaso):**</br> **Given** que las alertas no tienen ubicación registrada,</br> **When** la empresa consulta el resumen,</br> **Then** el sistema indica que no hay datos suficientes para agrupar. | EP002 | Media | H4 | — | — |
| US47 | Endpoint de eventos de analytics | Developer | Como developer, quiero un endpoint POST /api/v1/events que reciba los eventos de la app del conductor y del panel, para centralizar los datos de los experimentos sin depender de servicios de terceros. | **Escenario (Éxito):**</br> **Given** un evento válido con tipo, propiedades y marca de tiempo en UTC,</br> **When** se envía al endpoint,</br> **Then** el sistema lo guarda con su tipo y sus propiedades.</br> **Escenario (Fracaso):**</br> **Given** un evento con tipo desconocido o sin marca de tiempo,</br> **When** se envía al endpoint,</br> **Then** el API retorna un error y no lo guarda. | EP006 | Alta | H1, H2, H3, H4 | H-01, H-03, H-05 | EX-02 |
| US48 | Guardar eventos sin conexión y sincronizarlos | Sistema | Como sistema, quiero guardar en el celular los eventos y las alertas cuando no hay señal y enviarlos al recuperarla, para no perder datos en zonas de cobertura débil. | **Escenario (Éxito):**</br> **Given** que el celular del conductor no tiene conexión,</br> **When** el conductor activa una alerta o se genera un evento,</br> **Then** queda guardado en el celular y se envía en cuanto se recupera la señal, conservando su marca de tiempo original.</br> **Escenario (Fracaso):**</br> **Given** que el almacenamiento local falla,</br> **When** se genera un evento,</br> **Then** el fallo queda anotado en el registro interno y la alerta se sigue intentando enviar cuando haya señal. | EP002 | Alta | H1 | H-01 | EX-02 |

_Tabla 21. User Stories To-Be del proyecto - Elaboración propia._

### 8.3.2. To-Be Product Backlog.

El To-Be Product Backlog reúne las historias de la sección 8.3.1. El orden lo determina el valor para el negocio, según los Business Outcomes de la sección 1.2.2.2: primero se atiende el tiempo de respuesta ante alertas (US45, US38), luego se habilita el registro y la comparación de datos (US47, US48, US42, US43), después el resumen de incidentes para la empresa (US46) y, al final, el registro de uso del panel, de la validación y del historial, junto con el endpoint de métricas. Dentro de ese orden se respetan las dependencias técnicas: ninguna historia aparece antes de otra de la que depende. Las estimaciones usan la misma escala de Fibonacci (1, 2, 3, 5, 8) del Product Backlog de la sección 3.3. Las 37 historias del Capítulo III ya implementadas siguen siendo la base del producto.

Link: https://ivonneibanez.atlassian.net/jira/software/projects/AV/boards/38?filter=&groupBy=none

| Orden | User Story ID | Título | Descripción | Hipótesis Lean UX | Story Points | Experimento (8.1.5) |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| 1 | US45 | Marcar una alerta como atendida | Como empresa, quiero marcar una alerta como atendida, para dejar registro de cuándo se resolvió el incidente. | H1, H4 | 3 | — |
| 2 | US38 | Registrar marcas de tiempo del ciclo de la alerta | Como sistema, quiero registrar la hora de activación, recepción y confirmación de cada alerta, para calcular el tiempo de respuesta de la central. | H1 | 3 | EX-02 |
| 3 | US47 | Endpoint de eventos de analytics | Como developer, quiero un endpoint POST /api/v1/events que reciba los eventos de la app del conductor y del panel, para centralizar los datos de los experimentos sin depender de servicios de terceros. | H1, H2, H3, H4 | 3 | EX-02 |
| 4 | US48 | Guardar eventos sin conexión y sincronizarlos | Como sistema, quiero guardar en el celular los eventos y las alertas cuando no hay señal y enviarlos al recuperarla, para no perder datos en zonas de cobertura débil. | H1 | 5 | EX-02 |
| 5 | US42 | Marcar sesiones y eventos de experimento | Como sistema, quiero marcar los eventos registrados durante un experimento con su identificador y su condición (control o experimental), para separar los datos de prueba de los de producción y comparar las condiciones. | H1, H2, H3, H4 | 3 | EX-02, EX-03 |
| 6 | US43 | Consultar métricas del experimento | Como equipo de producto, quiero consultar las métricas de cada condición, para contrastar los resultados con las hipótesis. | H1, H2, H3, H4 | 5 | EX-02 |
| 7 | US46 | Resumir incidentes por zona y franja horaria | Como empresa, quiero ver un resumen de las alertas por zona y franja horaria, para identificar patrones de riesgo en mis rutas. | H4 | 5 | — |
| 8 | US39 | Registrar eventos de atención en el panel de supervisión | Como sistema, quiero registrar cuándo un operador abre sesión en el panel, cuándo ve una alerta y cuándo consulta el estado o la ubicación de una unidad, para medir cuánto tarda la central en reaccionar. | H2 | 2 | — |
| 9 | US40 | Registrar resultado y duración del inicio de servicio | Como sistema, quiero registrar el resultado de cada validación de conductor y el tiempo hasta el inicio del servicio, para evaluar la trazabilidad de las operaciones. | H3 | 3 | — |
| 10 | US44 | Endpoint de métricas del experimento | Como developer, quiero consultar las métricas de un experimento mediante API, para usarlas en reportes y en el análisis de resultados. | H1, H2, H3, H4 | 3 | EX-02 |
| 11 | US41 | Registrar consultas al historial de alertas | Como sistema, quiero registrar cuándo una empresa consulta el historial de alertas, para saber si lo usa en el seguimiento de incidentes. | H4 | 2 | — |

_Tabla 22. To-Be Product Backlog del proyecto (total: 37 Story Points) - Elaboración propia._

### 8.3.3. Pipeline-supported, Experiment-Driven To-Be Software Platform Lifecycle.

Los sprints de la Experimentación se ejecutan sobre el pipeline de integración y entrega continua descrito en el Capítulo VII, de modo que cada historia pasa por las mismas pruebas y validaciones antes de integrarse.

#### 8.3.3.1. To-Be Sprint Backlogs.

Las historias del To-Be Product Backlog se distribuyen en dos sprints siguiendo el orden de prioridad. Cada sprint tiene un objetivo asociado a las hipótesis que permite medir.

**Sprint 2 (17 Story Points).** Objetivo: poder medir el ciclo completo de una alerta, incluso sin señal, y etiquetar los datos por experimento y condición, que es lo necesario para ejecutar EX-02 y contrastar H-01.

**Sprint 3 (20 Story Points).** Objetivo: consultar las métricas por condición, registrar la atención de la central (H-03) y la validación del conductor (H-05), y entregar a la empresa el resumen de incidentes por zona y franja horaria.

| Sprint | US | Título | Tareas | SP |
| :--: | :--: | :--: | :--: | :--: |
| Sprint 2 | US45 | Marcar una alerta como atendida | Agregar el estado "Atendida" a la alerta; crear la acción en el panel de la empresa; guardar estado y hora; rechazar si la alerta no está confirmada | 3 |
| Sprint 2 | US38 | Registrar marcas de tiempo del ciclo de la alerta | Agregar los campos de hora de activación, recepción y confirmación; guardarlos en el flujo de la alerta; marcar la alerta como no confirmada al vencer el tiempo de espera | 3 |
| Sprint 2 | US47 | Endpoint de eventos de analytics | Crear el endpoint POST /api/v1/events; validar tipo y marca de tiempo UTC; guardar el evento con sus propiedades; documentar en Swagger | 3 |
| Sprint 2 | US48 | Guardar eventos sin conexión y sincronizarlos | Guardar localmente los eventos y alertas sin conexión; sincronizarlos al recuperar la señal con su marca de tiempo original; registrar los fallos de almacenamiento | 5 |
| Sprint 2 | US42 | Marcar sesiones y eventos de experimento | Agregar el indicador experiment_session y la condición a los eventos; guardar el identificador del experimento; excluir de las métricas los eventos sin sesión; verificar que la alerta de pánico siga disponible en ambas condiciones | 3 |
| Sprint 3 | US43 | Consultar métricas del experimento | Calcular las métricas por condición; crear la vista de métricas con el número de observaciones; mostrar el aviso de muestra insuficiente | 5 |
| Sprint 3 | US46 | Resumir incidentes por zona y franja horaria | Agrupar las alertas por zona y franja horaria; crear la vista del resumen; manejar las alertas sin ubicación | 5 |
| Sprint 3 | US39 | Registrar eventos de atención en el panel de supervisión | Registrar apertura de sesión, vista de alerta y consulta de unidad con operador y hora; evitar que un fallo del registro bloquee el panel | 2 |
| Sprint 3 | US40 | Registrar resultado y duración del inicio de servicio | Registrar resultado, motivo y tiempo de cada validación; guardar cada intento por separado | 3 |
| Sprint 3 | US44 | Endpoint de métricas del experimento | Crear el endpoint GET de métricas por experimento; devolver error ante un identificador inválido; documentar en Swagger | 3 |
| Sprint 3 | US41 | Registrar consultas al historial de alertas | Registrar la consulta al historial con hora y filtro; registrar las búsquedas sin resultados | 2 |

_Tabla 23. To-Be Sprint Backlogs del proyecto - Elaboración propia._
