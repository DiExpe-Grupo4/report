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

### 8.2.2. Domain Business Metrics

### 8.2.3. Measures.

### 8.2.4. Conditions.

### 8.2.5. Scale Calculations and Decisions.

### 8.2.6. Methods Selection.

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection.

### 8.2.8. Web and Mobile Tracking Plan.

## 8.3. Experimentation

### 8.3.1. To-Be User Stories.

### 8.3.2. To-Be Product Backlog
