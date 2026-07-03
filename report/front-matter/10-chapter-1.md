# Capítulo I: Introducción
## 1.1. Startup Profile 
### 1.1.1. Descripción de la Startup 
Somos Aurora, un grupo de estudiantes apasionados por la innovación tecnológica de la Universidad Peruana de Ciencias Aplicadas. Nuestra startup está enfocada en optimizar la gestión operativa y de abastecimiento en restaurantes tipo chifa mediante soluciones tecnológicas inteligentes. Nuestra plataforma conecta a restaurantes y proveedores a través de un sistema centralizado que permite gestionar inventarios, preveenir accidentes, anticipar la demanda y mejorar la coordinación en la cadena de suministro.

- **Misión:** Nuestra misión es mejorar la eficiencia operativa de los restaurantes mediante herramientas tecnológicas que permitan gestionar inventarios, anticipar necesidades de abastecimiento y optimizar la coordinación con proveedores, contribuyendo a una gestión más inteligente y sostenible del negocio gastronómico.

- **Visión:** Convertirnos en una plataforma líder en la digitalización de operaciones para restaurantes en Latinoamérica, facilitando la toma de decisiones basada en datos y fortaleciendo la integración entre restaurantes y proveedores.

- **Valores:**
    - **Eficiencia**: Buscamos optimizar procesos clave para reducir pérdidas y mejorar la operación diaria.
    - **Innovación**: Aplicamos tecnología y análisis de datos para resolver problemas reales del sector gastronómico.
    - **Confiabilidad**: Proporcionamos información precisa y útil para la toma de decisiones.
    - **Escalabilidad**: Diseñamos soluciones adaptables a distintos tamaños de negocio.
    - **Colaboración**: Facilitamos la interacción entre restaurantes y proveedores para mejorar resultados conjuntos.

### 1.1.2. Perfiles de integrantes del equipo 


| Datos                                                                                                           | Descripción                                                                                                                                                                                                                                                                                                                | Foto                                                                                   |
| :-------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------- |
| **Nombre:** Marcelo Fabio Cuadros Villanueva<br>**Carrera:** Ingeniería de Software<br>**Código:** U202422890   | **Descripción breve de sus habilidades:** <br> Soy Marcelo Cuadros, estudiante de Ingeniería de Software en la UPC actualmente cursando mi cuarto ciclo academico. Me considero una persona proactiva, sociable y con gran capacidad de trabajo en equipo; con conocimientos en c++, python, java, html, css y javascript. | <img src="../assets/images/members/marcelo.png" alt="Marcelo-logo" width="500" />      |
| **Nombre:** Zayd Jaffar Ayasta Martel<br>**Carrera:** Ingeniería de Software<br>**Código:** U202410837          | **Descripción breve de sus habilidades:** <br>Soy Zayd Ayasta, estudiante de Ingeniería de Software con conocimientos en C++, SQL, Java y Kotlin. Me caracterizo por ser creativo y adaptable, con interés en la innovación tecnológica y el desarrollo de soluciones que aporten valor real a los usuarios.               | <img src="../assets/images/members/zayd.jpg" alt="Zayd-logo" width="500" />            |
| **Nombre:** Milenko Rubén Cayanchi Avila<br>**Carrera:** Ingeniería de Software<br>**Código:** U202312566       | **Descripción breve de sus habilidades:** <br> Soy Milenko Cayanchi, estudiante de Ingeniería de Software en la UPC actualmente cursando mi quinto ciclo academico. Me considero una persona proactiva, sociable y con gran capacidad de trabajo en equipo; con conocimientos en c++, python.                              | <img src="../assets/images/members/milenko-foto.png" alt="Milenko-logo" width="500" /> |
| **Nombre:** Juan Sung Jau Wang Chen <br>**Carrera:** Ingeniería de Software<br>**Código:** U202318609           | **Descripción breve de sus habilidades:**<br> Soy Juan Wang, estudiante de Ingeniería de Software en la UPC. Me considero alguien amigable y sociable, puedo adaptarme sin problemas a cualquier entorno, tengo experiencia en organizacion de equipos y conocimientos de c++, python, html, css y javascript.<br>         | <img src="../assets/images/members/juan.png" width="500px" alt="Juan-pic">             |
| **Nombre:** Mathias Enrique Sanchez Espinoza <br>**Carrera:** Ingeniería de Software <br>**Código:** U20231C524 | **Descripción breve de sus habilidades:** <br> Soy Mathias Sanchez, estudiante de Ingeniería de Software en la UPC. Poseo conocimientos en C++, SQL y HTML.                                                                                                                                                                | <img src="../assets/images/members/mathias.jpg" alt="Mathias-logo" width="500px" />    |

<sub>*Tabla 1. Perfiles de integrantes de equipo*</sub>

## 1.2. Solution Profile 
### 1.2.1.  Antecedentes y problemática
Los restaurantes tipo chifa enfrentan dificultades en la gestión eficiente de sus inventarios y en la planificación de abastecimiento debido a la falta de herramientas tecnológicas que integren información operativa en tiempo real. Esta situación genera pérdidas económicas por sobrestock o desabastecimiento, decisiones basadas en estimaciones imprecisas y una coordinación ineficiente con proveedores. Asimismo, los proveedores carecen de visibilidad sobre la demanda real de sus clientes, lo que dificulta la planificación de producción y distribución. Existe la necesidad de una solución que permita centralizar la gestión de inventarios, analizar datos operativos y facilitar la coordinación entre restaurantes y proveedores, mejorando así la eficiencia y reduciendo la incertidumbre en la toma de decisiones.

<h4>5W + 2H</h4>

- **¿Qué ocurre? (WHAT)**
    Los restaurantes tipo chifa y sus proveedores enfrentan limitaciones en la gestión integrada de sus procesos operativos y de abastecimiento. Esto se refleja en problemas como control deficiente de inventarios, poca visibilidad del estado de mesas y comandas, riesgos en cocina, pérdidas por almacenamiento inadecuado y dificultad para anticipar la demanda. Según INACAL (2023)[^1], los restaurantes deben asegurar controles de recepción, inocuidad, seguridad e infraestructura, pero muchos procesos siguen ejecutándose de forma manual o fragmentada. Además, la digitalización de la cadena de suministro alimentaria todavía presenta brechas de coordinación e intercambio de información entre actores, lo que limita la eficiencia y la reducción de desperdicios (Annosi et al., 2021)[^2].

- **¿Quiénes se ven afectados? (WHO)**
    El problema afecta principalmente a los dueños y administradores de restaurantes chifa, quienes deben controlar cocina, salón, almacén y compras con recursos limitados. También impacta a los proveedores de insumos, ya que la falta de información oportuna sobre consumo, rotación y demanda reduce la precisión del abastecimiento y dificulta la planificación conjunta (Annosi et al., 2021)[^2]. De manera complementaria, los trabajadores de cocina resultan afectados por la exposición a accidentes y enfermedades laborales en entornos de trabajo intensivos, donde la prevención muchas veces no está soportada por sistemas de monitoreo continuo (Wassif et al., 2024)[^3].

- **¿Dónde ocurre? (WHERE)**
    Este problema se presenta en restaurantes y servicios de alimentación, especialmente en negocios con alta rotación de insumos perecibles y múltiples procesos simultáneos, como los chifas. En el contexto peruano, la problemática resulta relevante por el crecimiento sostenido del rubro restaurantes, donde el INEI (2024)[^4] reporta expansión del sector e incluye explícitamente a los chifas dentro de los negocios con desempeño positivo. Además, las exigencias de calidad e inocuidad planteadas por INACAL (2023)[^1] muestran que el reto no solo está en vender más, sino en operar mejor y con mayor seguridad.

- **¿Cuándo ocurre? (WHEN)**
    El problema es permanente, pero se intensifica en horas pico, campañas comerciales, fines de semana, feriados y temporadas de alta demanda, cuando aumentan simultáneamente los pedidos, la presión sobre cocina, el consumo de insumos y la necesidad de reposición rápida. Tanizaki et al. (2020)[^5] señalan que la gestión del restaurante mejora cuando el pronóstico de demanda incorpora datos internos y externos, precisamente porque la variabilidad del consumo afecta decisiones críticas como compras, personal e inventario.

- **¿Por qué es importante resolverlo? (WHY)**
    Resolver este problema es clave porque impacta directamente en la eficiencia operativa, la seguridad del personal, la calidad del servicio y la relación con los proveedores. La adopción de soluciones digitales e IoT puede fortalecer la trazabilidad, la supervisión de variables críticas como temperatura y almacenamiento, y la respuesta oportuna ante fallas o riesgos operativos (Bouzembrak et al., 2019)[^6]. Además, una mejor coordinación digital en la cadena de suministro permite reducir desperdicios, mejorar el flujo de información y sostener relaciones más eficientes entre restaurantes y proveedores (Annosi et al., 2021)[^2].

- **¿Cómo se manifiesta? (HOW)**
    El problema se evidencia en quiebres o excesos de stock, demora en comandas, poca trazabilidad de insumos, limitada visibilidad de la ocupación de mesas,v fallas en el control del almacén y exposición constante a riesgos en cocina. También se manifiesta en pedidos mal planificados a proveedores y en decisiones reactivas basadas en experiencia más que en datos. Wassif et al. (2024)[^3] muestran que el entorno de cocina puede concentrar altas tasas de lesiones y enfermedades ocupacionales, mientras que Bouzembrak et al. (2019)[^6] destacan que sensores IoT permiten monitorear temperatura, humedad y trazabilidad en procesos alimentarios, justamente para atender estas brechas operativas.

- **¿Cuánto impacta? (HOW MUCH)**
    El impacto es operativo, económico y humano. En términos sectoriales, el INEI (2024)[^4] reportó que la actividad de restaurantes en Perú creció 2,57% en febrero de 2024, reflejando un entorno competitivo donde la eficiencia del servicio y del abastecimiento se vuelve más importante. En el plano ocupacional, Wassif et al. (2024)[^3] encontraron prevalencias de 77,3% en lesiones laborales y 81,3% en enfermedades relacionadas con el trabajo entre personal de cocina estudiado, lo que confirma la relevancia de la prevención. En el plano logístico, Tanizaki et al. (2020)[^5] sostienen que el pronóstico de demanda mejora decisiones de pedidos e inventarios, mientras que Annosi et al. (2021)[^2] destacan que la digitalización favorece la colaboración y la reducción de desperdicios a lo largo de la cadena alimentaria. En conjunto, esto demuestra que la ausencia de una plataforma integrada genera pérdidas por ineficiencia, riesgos para el personal y menor capacidad de coordinación entre restaurante y proveedor.

**Objetivos del proyecto**

- Desarrollar una plataforma web que permita a restaurantes tipo chifa centralizar el control de inventario, pedidos, alertas operativas y seguimiento básico de la demanda.
- Mejorar la coordinación entre restaurantes y proveedores mediante un entorno digital compartido que facilite la generación, visualización y seguimiento de órdenes de compra.
- Reducir decisiones reactivas, pérdidas por desabastecimiento o sobrestock y fallas operativas asociadas a registros manuales o información fragmentada.
- Proporcionar visibilidad operativa suficiente para apoyar decisiones de abastecimiento, control interno y prevención de riesgos en cocina y almacenamiento.

**Restricciones del proyecto**

- La solución debe implementarse como una aplicación web responsiva, accesible desde navegador en entornos de escritorio y móviles.
- El alcance del producto debe centrarse en la gestión operativa y de abastecimiento de restaurantes tipo chifa y su relación con proveedores, sin abarcar procesos contables o logísticos avanzados de alcance empresarial completo.
- La primera versión debe priorizar funcionalidades viables para validación académica y de negocio, como inventario, alertas, pedidos, demanda estimada y monitoreo operativo básico.
- La propuesta debe sostenerse sobre evidencia bibliográfica y validación con usuarios, por lo que los componentes más avanzados del producto quedan condicionados a iteraciones posteriores.


### 1.2.2 Lean UX Process   

#### 1.2.2.1 Lean UX Problem Statement


- Domain: La gestión operativa y de abastecimiento en restaurantes tipo chifa sigue dependiendo en gran medida de controles manuales, registros dispersos y coordinación informal entre restaurantes y proveedores. Esto limita la capacidad de mantener inventarios actualizados, anticipar la demanda y responder oportunamente a eventos críticos dentro de la operación.

- Customer Segments: Los principales segmentos involucrados son los dueños y administradores de restaurantes chifa, quienes necesitan controlar inventario, reducir pérdidas y tomar decisiones rápidas de abastecimiento, y los proveedores de insumos, quienes requieren visibilidad sobre la demanda de sus clientes para planificar mejor sus entregas y distribución.

- Pain Points: Los restaurantes enfrentan quiebres de stock, compras de emergencia, desperdicio de insumos y poca visibilidad del estado real de su operación. Los proveedores, por su parte, trabajan con información incompleta sobre pedidos futuros, lo que dificulta la planificación de abastecimiento y entregas. Además, la falta de monitoreo de condiciones operativas, como la temperatura de almacenamiento o cocina, incrementa el riesgo de pérdidas y fallas en la operación.

- Gap: Las soluciones existentes no resuelven de forma integrada el control de inventario, la generación de alertas, la proyección de demanda, la coordinación digital de pedidos y el monitoreo operativo. Como consecuencia, restaurantes y proveedores siguen tomando decisiones de manera reactiva, tardía y con información fragmentada.

- Vision / Strategy: SupplyWok busca cerrar esta brecha mediante una plataforma web que conecte a restaurantes y proveedores en un mismo entorno digital. La estrategia del producto es centralizar la gestión de inventario, alertas, pedidos, proyecciones de demanda y monitoreo operativo para facilitar decisiones preventivas, mejorar la coordinación y reducir ineficiencias en la cadena de abastecimiento.

- Initial Segment: Inicialmente, el producto se enfocará en dueños y administradores de restaurantes chifa, validando con ellos las funcionalidades esenciales relacionadas con inventario, alertas y generación de pedidos. De forma complementaria, se incorporará un grupo de proveedores clave para validar la visualización de demanda y la coordinación de entregas.


#### 1.2.2.2 Lean UX Assumptions

**Usuarios objetivo**
- Asumimos que los dueños y administradores de restaurantes chifa necesitan una forma más simple y centralizada de controlar inventario, evitar pérdidas y reaccionar a tiempo ante problemas operativos.
- Asumimos que los proveedores de insumos necesitan mayor visibilidad sobre la demanda de sus clientes para planificar pedidos, rutas y entregas con menor incertidumbre.
- Asumimos que ambos segmentos estarán dispuestos a adoptar una plataforma compartida si esta reduce trabajo manual, mejora la coordinación y ofrece beneficios claros en su operación diaria.

**Objetivos de los usuarios**
- Asumimos que los restaurantes valorarán poder registrar inventario, configurar alertas y visualizar su operación en tiempo real desde una sola plataforma.
- Asumimos que los proveedores valorarán contar con información de demanda estimada, estado de pedidos y herramientas para organizar sus entregas.
- Asumimos que ambos segmentos preferirán información clara, actualizada y fácil de interpretar antes que procesos manuales o dispersos.

**Business Outcomes**
- Asumimos que una plataforma que unifique inventario, pedidos, alertas y monitoreo operativo puede mejorar la eficiencia de los restaurantes.
- Asumimos que una mejor coordinación digital entre restaurantes y proveedores puede reducir retrasos, desabastecimientos y compras de emergencia.
- Asumimos que la reducción de desperdicio y de fallas operativas generará valor económico suficiente para que los usuarios perciban utilidad real en el producto.
- Asumimos que un modelo de suscripción con planes diferenciados puede sostener el producto en el tiempo si los usuarios perciben beneficios concretos.

**Solution Assumptions**
- Asumimos que el registro de inventario y las alertas de stock mínimo serán funcionalidades prioritarias para la adopción inicial del producto.
- Asumimos que una proyección básica de demanda será suficiente para ayudar a los restaurantes a anticipar compras en una primera etapa.
- Asumimos que el monitoreo de variables operativas como la temperatura aportará valor al permitir detectar riesgos antes de que afecten la calidad de los insumos.
- Asumimos que la integración de restaurantes y proveedores en una misma plataforma generará una mejor coordinación que el uso de canales informales.

#### 1.2.2.3 Lean UX Hypothesis Statements
- Creemos que la reducción de desabastecimientos y la mejora del control operativo se logrará si los dueños y administradores de restaurantes chifa obtienen visibilidad centralizada de sus insumos con la funcionalidad de registro de inventario.
- Creemos que la disminución de compras de emergencia y quiebres de stock se logrará si los dueños y administradores de restaurantes chifa obtienen alertas oportunas sobre niveles críticos de insumos con la funcionalidad de alertas de stock mínimo.
- Creemos que una toma de decisiones más rápida y mejor informada se logrará si los dueños y administradores de restaurantes chifa obtienen una vista clara del estado de sus insumos con la funcionalidad de dashboard de inventario.
- Creemos que una mejor planificación de compras y abastecimiento se logrará si los dueños y administradores de restaurantes chifa obtienen una estimación anticipada de consumo con la funcionalidad de proyección básica de demanda.
- Creemos que una coordinación más eficiente con proveedores se logrará si los dueños y administradores de restaurantes chifa obtienen un proceso más simple para solicitar abastecimiento con la funcionalidad de generación de órdenes de compra.
- Creemos que una mejor coordinación operativa entre restaurantes y proveedores se logrará si los dueños y administradores de restaurantes chifa obtienen visibilidad del estado de sus pedidos con la funcionalidad de seguimiento de órdenes de compra.
- Creemos que una relación de abastecimiento más ordenada y eficiente se logrará si los dueños y administradores de restaurantes chifa obtienen un directorio centralizado de sus proveedores con la funcionalidad de gestión de proveedores vinculados.
- Creemos que una mejor planificación de entregas y distribución se logrará si los proveedores de insumos obtienen mayor visibilidad de las necesidades futuras de sus clientes con la funcionalidad de visualización de demanda estimada.
- Creemos que una mejor coordinación comercial y menor fricción al generar pedidos se logrará si los proveedores de insumos obtienen una forma clara de mostrar precios, unidades y disponibilidad con la funcionalidad de gestión de catálogo de productos.
- Creemos que la reducción del riesgo operativo y de pérdidas de insumos se logrará si los dueños y administradores de restaurantes chifa obtienen alertas sobre condiciones críticas del entorno con la funcionalidad de monitoreo de temperatura.
- Creemos que una respuesta más rápida ante eventos críticos se logrará si los dueños y administradores de restaurantes chifa obtienen notificaciones visibles y accionables con la funcionalidad de alertas operativas.

#### 1.2.2.4 Lean UX Canvas

# Lean UX Canvas

| 1. Business Problem                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | 5. Solution Ideas                                                                                                                                                                                                                                                                                                                             | 2. Business Outcomes                                                                                                                                                                                                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - Los restaurantes tipo chifa gestionan inventarios y abastecimiento con procesos poco integrados.<br>- Los proveedores no tienen suficiente visibilidad sobre la demanda futura de sus clientes.<br>- La operación manual incrementa el riesgo de desperdicio, desabastecimiento y retrasos en entregas.<br>- Existe una oportunidad de digitalizar la gestión operativa con una solución escalable y basada en suscripción.                                                                                                                                                 | - Aplicación web con acceso diferenciado para restaurantes y proveedores.<br>- Registro centralizado de inventario para restaurantes.<br>- Dashboard de inventario con alertas de stock mínimo.<br>- Módulo de proyección básica de demanda para anticipar compras.<br>- Vista de demanda estimada y estado de pedidos para proveedores.<br>- Monitoreo de temperatura y alertas operativas para reducir riesgos en cocina y almacenamiento.      | - Reducir pérdidas por sobrestock y desabastecimiento.<br>- Mejorar la coordinación entre restaurantes y proveedores.<br>- Incrementar la eficiencia operativa en cocina, almacén y abastecimiento.<br>- Facilitar decisiones basadas en datos y alertas.<br>- Sostener el producto mediante planes de suscripción Premium y Enterprise. |
| **3. Users**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | **7. Most Important Learning**                                                                                                                                                                                                                                                                                                                | **4. User Outcomes & Benefits**                                                                                                                                                                                                                                                                                                          |
| - Dueños de restaurantes chifa.<br>- Administradores o encargados de operación.<br>- Proveedores de insumos para restaurantes.                                                                                                                                                                                                                                                                                                                                                                                                                                                | - Validar si restaurantes y proveedores realmente estarían dispuestos a usar una plataforma compartida para inventario, demanda y pedidos.<br>- Identificar qué funcionalidades entregan más valor al inicio para cada segmento.<br>- Confirmar si la proyección de demanda y las alertas operativas son entendidas como útiles y confiables. | - Controlar inventario de manera centralizada.<br>- Recibir alertas de stock bajo y temperatura fuera de rango.<br>- Visualizar una proyección básica de demanda.<br>- Crear y seguir pedidos de abastecimiento.<br>- Consultar información útil para coordinar entregas y planificación.                                                |
| **6. Hypotheses**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                                                               | **8. Least Effort to Learn**                                                                                                                                                                                                                                                                                                             |
| - Creemos que la reducción de desabastecimientos se logrará si los restaurantes obtienen mejor control de sus insumos con el registro de inventario.<br>- Creemos que la disminución de compras de emergencia se logrará si los restaurantes obtienen alertas oportunas con las alertas de stock mínimo.<br>- Creemos que una mejor planificación de compras se logrará si los restaurantes obtienen una estimación anticipada de consumo con la proyección de demanda.<br>- Creemos que una mejor coordinación de abastecimiento se logrará si restaurantes y proveedores obtienen visibilidad del proceso con la generación y seguimiento de órdenes de compra.<br>- Creemos que una mejor planificación de entregas se logrará si los proveedores obtienen visibilidad de necesidades futuras con la visualización de demanda estimada.<br>- Creemos que la reducción del riesgo operativo se logrará si los restaurantes obtienen alertas de condiciones críticas con el monitoreo de temperatura. |                                                                                                                                                                                                                                                                                                                                               | - Construir un prototipo navegable de baja fidelidad con login, dashboard de inventario, alertas, pedidos y vista de demanda.<br>- Probarlo con entrevistas a dueños de chifas y proveedores para validar interés, utilidad y claridad de uso.                                                                                           |

<sub>*Tabla 2. Lean UX Canvas*</sub>


## 1.3 Segmentos Objetivo

Con la investigación y el enfoque del producto, se identificaron 2 segmentos objetivos principales:

**- Segmento 1: Dueños de restaurantes chifa y administradores**

**Descripción:** Usuarios responsables de la operación diaria del restaurante, la compra de insumos, el control de stock y la supervisión de procesos internos. En su mayoría representan pequeños negocios gastronómicos urbanos o locales con operación intensiva, donde una misma persona concentra decisiones de compras, almacenamiento y coordinación del servicio. Su motivación principal es reducir pérdidas, mejorar la planificación y tener mayor control sobre la operación.

**Características generales:**
- **Ubicación:** Restaurantes urbanos y zonas con alta concentración de oferta gastronómica.
- **Rol:** Dueños, administradores o encargados de operación.
- **Perfil del negocio:** Pequeños o medianos restaurantes con alta rotación de insumos perecibles y necesidad de control diario.
- **Necesidad principal:** Control de inventario, alertas, proyección de demanda y coordinación de pedidos.
- **Nivel tecnológico:** Uso frecuente de sistemas web o móviles para gestión básica del negocio.

**Información de sustento:**
- El sector restaurantes mantiene actividad y competencia sostenida en el contexto peruano; el INEI (2024)[^4] reportó crecimiento de 2,57% y menciona expresamente a los chifas dentro de las actividades con desempeño positivo, lo que refuerza la relevancia de digitalizar su operación.
- Tanizaki et al. (2020)[^5] muestran que el pronóstico de demanda en restaurantes mejora decisiones sobre compras, inventario y operación, por lo que este segmento sí enfrenta un problema real y recurrente de planificación.
- Bouzembrak et al. (2019)[^6] sostienen que los enfoques basados en IoT mejoran monitoreo, trazabilidad y control de variables críticas en entornos alimentarios, algo directamente alineado con las necesidades operativas de este segmento.

**- Segmento 2: Proveedores de insumos para restaurantes**

**Descripción:** Usuarios que abastecen a uno o varios restaurantes y necesitan anticipar pedidos, organizar entregas y mantener una relación más eficiente con sus clientes. Corresponden a proveedores o distribuidores que operan relaciones B2B recurrentes y dependen de una mejor visibilidad de la demanda para planificar reposición, rutas y tiempos de entrega. Su motivación principal es planificar mejor su distribución y contar con información útil para sus rutas y abastecimiento.

**Características generales:**
- **Ubicación:** Empresas o negocios de distribución de insumos alimentarios.
- **Rol:** Proveedores, distribuidores o encargados comerciales.
- **Perfil de operación:** Atención recurrente a varios clientes gastronómicos con necesidad de coordinar pedidos y entregas con baja incertidumbre.
- **Necesidad principal:** Visibilidad de demanda, seguimiento de pedidos y planificación de entregas.
- **Nivel tecnológico:** Uso de plataformas digitales para pedidos, coordinación y seguimiento.

**Información de sustento:**
- Annosi et al. (2021)[^1] identifican que la digitalización en cadenas de suministro alimentarias mejora la colaboración, el intercambio de información y la reducción de desperdicios, lo cual justifica incluir a los proveedores como segmento clave y no solo como actor secundario.
- La misma evidencia muestra que las barreras de coordinación e intercambio de información entre actores de la cadena alimentaria siguen siendo relevantes, por lo que un proveedor con visibilidad parcial de la demanda sí constituye un usuario directamente afectado por el problema.
- Tanizaki et al. (2020)[^5] respaldan que una mejor anticipación de la demanda mejora decisiones de abastecimiento; trasladado al proveedor, esto se traduce en mejor planificación de oferta, rutas y tiempos de respuesta.



[^1]: Annosi, M. C., Brunetta, F., Bimbo, F., & Kostoula, M. (2021). Digitalization within food supply chains to prevent food waste: Drivers, barriers and collaboration practices. *Industrial Marketing Management, 93*, 208–220. https://doi.org/10.1016/j.indmarman.2021.01.005

[^2]: Bouzembrak, Y., Klüche, M., Gavai, A., & Marvin, H. J. P. (2019). Internet of things in food safety: Literature review and a bibliometric analysis. *Trends in Food Science & Technology, 94*, 54–64. https://doi.org/10.1016/j.tifs.2019.11.002

[^3]: Instituto Nacional de Calidad (INACAL). (2023). *Turismo: Inacal promueve la calidad en servicios de restaurantes*. https://www.gob.pe/institucion/inacal/noticias/809133-turismo-inacal-promueve-la-calidad-en-servicios-de-restaurantes

[^4]: Instituto Nacional de Estadística e Informática (INEI). (2024). *Actividad de restaurantes aumentó en 2,57% en febrero de 2024*. https://m.inei.gob.pe/prensa/noticias/actividad-de-restaurantes-aumento-en-257-en-febrero-de-2024-15121/

[^5]: Tanizaki, T., Hoshino, T., Shimmura, T., & Takenaka, T. (2020). Restaurant store management based on demand forecasting. *Procedia CIRP, 88*, 580–583. https://doi.org/10.1016/j.procir.2020.05.101

[^6]: Wassif, G. O., Abdelsalam, A., Eldin, W. S., Abdel-Hamid, M. A., & Damaty, S. I. (2024). Work-related injuries and illnesses among kitchen workers at two major students’ hostels. *Journal of the Egyptian Public Health Association, 99*, Article 16. https://doi.org/10.1186/s42506-024-00163-x
