# Capítulo IV: Product Design.
## 4.1. Style Guidelines

### 4.1.1. General Style Guidelines

SupplyWok adopta un sistema de diseño coherente, funcional y alineado con el contexto operativo de restaurantes tipo chifa y sus proveedores. En esta sección se detallan los lineamientos de estilo que hemos definido para mantener la coherencia visual de la plataforma, la cual incluye la landing page, la web application y las versiones mobile. Se detallan el branding, la paleta de colores y las tipografías a utilizar en el proyecto.

**1. Logo:**

El logo de nuestra plataforma está compuesto por los caracteres **S** y **W**, provenientes del nombre *SupplyWok*, representados de forma creativa para mantener una relación con nuestro público objetivo. La **S** se encuentra en forma de humo que sale de un recipiente con forma de **W**. Esta composición transmite una conexión con el entorno de un restaurante chifa y genera familiaridad con nuestros usuarios.

<div align="center">
  <img src="../assets/images/supplywok-logo.png" width="300" height="300" alt="SupplyWok Logo">
</div>

**2. Branding:**

SupplyWok busca transmitir una identidad visual **moderna, confiable, cercana y ordenada**, alineada con las necesidades de restaurantes tipo chifa y sus proveedores. La marca debe reflejar rapidez operativa, control sobre el abastecimiento y facilidad de uso en entornos donde la gestión diaria requiere eficiencia.

El branding de SupplyWok se fundamenta en los siguientes conceptos:

- **Confianza:** la interfaz debe proyectar seguridad al manejar información sensible como stock, pedidos, alertas y proveedores.
- **Agilidad:** la experiencia debe facilitar acciones rápidas y reducir fricción en tareas frecuentes.
- **Cercanía:** la comunicación visual y textual debe ser comprensible y accesible para usuarios con distintos niveles de experiencia digital.
- **Orden:** la presentación de la información debe ser clara, estructurada y fácil de escanear.
- **Identidad gastronómica:** el logotipo y la paleta de colores deben mantener una relación visual con el contexto del chifa, sin perder limpieza ni profesionalismo.

Para reforzar esta identidad, se utilizarán elementos visuales con un estilo consistente en toda la plataforma. El objetivo es que SupplyWok sea percibido como una solución especializada, profesional y fácil de adoptar.

**3. Typography:**

La tipografía que se ha decidido usar en nuestra plataforma son dos: **Poppins** y **Montserrat**. Estas elecciones fueron hechas pensando en la comodidad de lectura de nuestros usuarios y en el diseño moderno que se quiere lograr.

- **Títulos:** Para los títulos se usará **Poppins** en pesos **Bold** o **SemiBold**, dependiendo del nivel jerárquico del texto. Esto permite darles la fuerza y relevancia necesarias.

<div align="center">
  <img src="../assets/images/poppins-example.png" alt="SupplyWok Poppins">
</div>

- **Párrafos o cuerpo del texto:** Se usará **Montserrat** en pesos variados como **Bold**, **Regular** o **Light**, dependiendo de la intención del texto. Esto asegura la legibilidad necesaria para los usuarios al momento de leer.

<div align="center">
  <img src="../assets/images/monserrat-example.png" alt="SupplyWok Montserrat">
</div>

**4. Colors:**

La identidad visual de SupplyWok busca mantener una relación con el entorno de un restaurante chifa clásico, por lo que predominan los tonos rojos y amarillos, combinados con blanco y negro para lograr un contraste óptimo.

- **Rojo (#C21204):** Este color se usará en botones principales, alertas y elementos que requieran atención. Se eligió por su fuerza visual y por su asociación con energía, dinamismo y relevancia.
- **Amarillo (#E9B824):** Este color se usará como contraste del rojo y para resaltar textos o elementos puntuales.
- **Mostaza o amarillo oscuro (#A07832):** Variante más oscura del amarillo, utilizada en detalles para ayudar a armonizar la vista de los usuarios.
- **Blanco (#FFFFFF):** Color neutro para mantener balance y aportar limpieza visual.
- **Negro (#000000):** Color neutro para reforzar contraste y legibilidad.

<div align="center">
  <img src="../assets/images/paleta-colors.png" width="1000" height="200" alt="SupplyWok Colors">
</div>

**5. Spacing:**

El sistema de espaciado de SupplyWok se ha definido para mantener orden visual, legibilidad y consistencia entre la landing page, la web application y las vistas móviles. Se adopta una escala base de **8 px**. En el caso de separar secciones, se pueden usar espacios de hasta **24 px**, lo que permite construir interfaces limpias y fácilmente adaptables a distintos tamaños de pantalla.

**6. Tone:**

El tono de comunicación de SupplyWok será **profesional, claro y confiable**, pero sin caer en tecnicismos innecesarios. Debido a que la plataforma está orientada a restaurantes tipo chifa y proveedores que trabajan en contextos operativos de alta demanda, la comunicación debe transmitir orden, rapidez y seguridad en la gestión del abastecimiento.

SupplyWok busca proyectar:

- **Confianza**, al tratar información crítica como stock, pedidos y alertas.
- **Agilidad**, al guiar al usuario hacia acciones rápidas y concretas.
- **Cercanía**, utilizando mensajes comprensibles para usuarios con distintos niveles de familiaridad tecnológica.
- **Control**, al presentar la información de manera estructurada y orientada a la toma de decisiones.

Por ello, la experiencia visual y verbal evita un tono alarmista o excesivamente informal. En su lugar, se prioriza una comunicación sobria, directa y enfocada en la eficiencia operativa.

**7. Language:**

El lenguaje de SupplyWok será **directo, breve y orientado a la acción**. Se utilizarán etiquetas y mensajes simples que permitan al usuario identificar rápidamente qué está ocurriendo y qué acción puede realizar a continuación.

Se evitarán expresiones ambiguas o excesivamente técnicas. Por ejemplo, se priorizarán frases como:

- `Crear pedido` en lugar de `Registrar nueva orden de abastecimiento`.
- `Stock bajo` en lugar de `Nivel de inventario inferior al umbral configurado`.
- `Ver proveedor` en lugar de `Consultar información detallada del proveedor asociado`.
- `Actualizar estado` en lugar de `Modificar el flujo transaccional del pedido`.

Este enfoque reduce la fricción cognitiva y mejora la usabilidad, especialmente en escenarios donde el usuario necesita actuar rápido, como reposición de insumos, revisión de alertas o seguimiento de entregas.

### 4.1.2. Web Style Guidelines

Las Web Style Guidelines de SupplyWok establecen los criterios visuales y de interacción que guían el diseño de la landing page y la web application. Estas pautas aseguran consistencia entre dispositivos, favorecen la legibilidad y permiten que tanto restaurantes como proveedores naveguen de forma intuitiva por la plataforma.

#### Estructura general

SupplyWok adopta un enfoque **responsive web design**, de modo que la interfaz se adapte correctamente a desktop, laptop, tablet y mobile web sin perder claridad ni coherencia visual.

- **Desktop:** La navegación principal se presenta mediante sidebar lateral y header superior. Los módulos con mayor densidad informativa, como inventario y reportes, aprovechan mejor el ancho disponible mediante tablas, tarjetas comparativas y filtros visibles.
- **Tablet:** La estructura se reorganiza a 6 u 8 columnas, reduciendo el número de elementos visibles por fila. Los paneles laterales pueden colapsarse y ciertas tablas pasan a formatos más compactos para facilitar la interacción táctil.
- **Mobile Web:** La estructura se simplifica a una sola columna. Los elementos se apilan verticalmente, se priorizan botones de acción principal y la navegación se compacta mediante menú hamburguesa o navegación inferior, según el flujo.

#### Breakpoints

Se proponen los siguientes breakpoints para asegurar una adaptación consistente:

- **Mobile:** hasta 767 px.
- **Tablet:** desde 768 px hasta 1023 px.
- **Desktop:** 1024 px en adelante.

#### Componentes básicos de UI

- **Botones primarios:** fondo rojo `#C21204` o marrón `#2D241E`, texto blanco, bordes redondeados de 10 px a 12 px. Se utilizan para acciones clave como `Crear pedido`, `Export PDF`, `Confirmar` o `Iniciar sesión`.
- **Botones secundarios:** fondo blanco o amarillo claro, borde en rojo o mostaza, con texto oscuro. Se emplean para acciones complementarias como `Cancelar`, `Ver detalle` o `Volver`.
- **Inputs y formularios:** bordes suaves, fondo claro y suficiente padding interno para facilitar lectura e interacción. El estado enfocado resalta mediante borde rojo o mostaza. El estado de error utiliza borde rojo más oscuro y un mensaje de validación visible.
- **Cards:** contenedores rectangulares con esquinas redondeadas, padding interno de 16 px a 24 px y jerarquía clara entre título, contenido y acciones. Se usan en dashboard, alertas, métricas y secciones de resumen.
- **Tablas:** encabezados destacados, filas con separación visual suficiente y acciones agrupadas al extremo derecho. En resoluciones pequeñas, las tablas pueden transformarse en listas o tarjetas para mejorar la lectura.
- **Sidebar:** navegación vertical persistente en desktop, con acceso a Dashboard, Inventario, Pedidos, Proveedores, Alertas, Reportes y Configuración. En tablet y mobile se colapsa.
- **Header:** barra superior con nombre del usuario, rol, notificaciones y acceso rápido a configuración y cierre de sesión.

#### Tipografía en web

La propuesta tipográfica de SupplyWok mantiene como base las fuentes **Poppins** y **Montserrat**, según la identidad visual previamente definida.

- **Títulos principales (H1):** Poppins Bold, 24 px a 28 px.
- **Subtítulos (H2):** Poppins SemiBold, 20 px a 22 px.
- **Encabezados de sección (H3):** Poppins Medium, 18 px.
- **Texto de párrafo y descripciones:** Montserrat Regular, 14 px a 16 px.
- **Texto en botones:** Poppins SemiBold, 14 px a 16 px.
- **Etiquetas de formularios y tablas:** Montserrat Medium, 13 px a 14 px.

#### Interacción

- **Hover:** Los botones incrementan ligeramente el contraste o brillo del color base. Los links se subrayan o cambian a una variante más intensa del color principal.
- **Focus:** Todo componente interactivo debe mostrar un estado visible de foco, especialmente inputs, botones y enlaces, para favorecer accesibilidad y navegación por teclado.
- **Active / Click:** Los botones aplican una ligera reducción de escala o sombra interna para confirmar la interacción.
- **Feedback visual:** Estados como éxito, error, advertencia o información se distinguen mediante color, iconografía y texto breve.
- **Scroll y navegación persistente:** En desktop, el header y ciertos filtros pueden permanecer visibles para facilitar navegación rápida en vistas largas.
- **Responsive behavior:** El contenido prioritario siempre debe conservar visibilidad antes que elementos decorativos o secundarios.

### 4.1.3. Mobile Style Guidelines

Las Mobile Style Guidelines de SupplyWok tienen como objetivo adaptar la experiencia de uso a pantallas reducidas sin perder funcionalidad, claridad visual ni consistencia con la propuesta general del producto. Estas pautas priorizan rapidez de interacción, facilidad de lectura y acceso inmediato a acciones frecuentes.

#### Estructura general

La experiencia móvil de SupplyWok está diseñada para que restaurantes y proveedores puedan consultar información crítica y ejecutar acciones esenciales desde cualquier lugar.

- **Pantallas en una sola columna**, con contenido apilado verticalmente.
- **Header compacto**, con logo, nombre de la vista y acceso a notificaciones o menú.
- **Navegación simplificada**, priorizando las secciones más importantes según el rol del usuario.
- **Botones de acción visibles**, especialmente en flujos como crear pedido, registrar stock o confirmar entregas.
- **Tarjetas resumidas**, en lugar de tablas complejas, para mostrar inventario, pedidos y alertas de forma clara.

#### Componentes básicos en mobile

- **Botones primarios:** rojo `#C21204` o marrón `#2D241E`, texto blanco, esquinas redondeadas de 12 px y tamaño suficiente para interacción táctil.
- **Botones secundarios:** fondo blanco o amarillo claro con borde visible y alto contraste.
- **Inputs:** ancho completo, padding amplio y separación mínima de 16 px entre campos.
- **Cards de resumen:** usadas para pedidos, insumos, alertas y métricas, con distribución vertical y jerarquía clara.
- **Listas:** los registros se organizan en bloques táctiles con título, estado, fecha y acción principal.
- **Indicadores de estado:** cada pedido o alerta utiliza color y texto para distinguir rápidamente condiciones como pendiente, entregado, stock bajo o fuera de rango.

#### Tipografía en mobile

- **Título principal (H1):** Poppins Bold, 20 px a 22 px.
- **Subtítulos (H2):** Poppins SemiBold, 16 px a 18 px.
- **Texto general:** Montserrat Regular, 14 px.
- **Botones:** Poppins SemiBold, 14 px.
- **Etiquetas pequeñas o estados:** Montserrat Medium, 12 px a 13 px.

#### Interacción en mobile

- Se prioriza el uso de **acciones rápidas** y **flujos cortos**.
- Los botones deben tener un tamaño mínimo adecuado para interacción táctil.
- Los formularios se dividen en bloques cortos para evitar fatiga visual.
- Las acciones críticas se colocan al alcance natural del pulgar.
- Los cambios de estado deben mostrarse inmediatamente mediante mensajes visibles o indicadores contextuales.

### 4.2. Information Architecture.

La arquitectura de información de SupplyWok ha sido diseñada para que los dos segmentos principales del producto, restaurantes tipo chifa y proveedores de insumos, puedan localizar información, ejecutar tareas y comprender el estado de sus operaciones de forma rápida y consistente. Esta propuesta abarca tanto la Landing Page como la Web Application, de modo que exista continuidad entre la experiencia de descubrimiento del producto y la experiencia de uso dentro de la plataforma.

En el caso de la Landing Page, la arquitectura de información busca guiar al visitante desde una comprensión inicial del problema hacia una acción concreta, ya sea registrarse, iniciar sesión o explorar las funcionalidades clave según su rol. Para ello, el contenido se organiza en bloques progresivos como propuesta de valor, beneficios, funcionalidades, impacto, testimonios, preguntas frecuentes y llamadas a la acción. Esta secuencia permite que el usuario comprenda qué resuelve SupplyWok, a quién está dirigido y cómo puede empezar a utilizarlo.

En la Web Application, la arquitectura de información responde a una lógica operativa. En lugar de priorizar persuasión o descubrimiento, la aplicación prioriza velocidad de acceso, visibilidad del estado actual y ejecución eficiente de tareas. Por ello, el contenido se distribuye en módulos funcionales diferenciados por rol, donde cada usuario accede únicamente a las secciones que necesita para gestionar inventario, pedidos, proveedores, alertas, reportes o catálogos.

De esta manera, la arquitectura de información de SupplyWok se apoya en cuatro sistemas complementarios: Organization Systems, Labeling Systems, Searching Systems y Navigation Systems. En conjunto, estos sistemas permiten estructurar la información de forma entendible, reducir la sobrecarga cognitiva y mantener una experiencia coherente entre web pública y aplicación transaccional.

### 4.2.1. Organization Systems.

La organización del contenido en SupplyWok responde a la naturaleza de cada producto digital y al tipo de tarea que el usuario necesita realizar. La Landing Page organiza información para presentar, explicar y convencer; mientras que la Web Application organiza información para operar, monitorear y tomar decisiones. Por ello, se aplican distintos esquemas de organización visual y categorización según el contexto.

#### Organization Systems in the Landing Page

En la Landing Page, la información se organiza principalmente de forma **jerárquica** y **secuencial**. La jerarquía visual permite destacar de inmediato la propuesta de valor, los beneficios principales y los llamados a la acción más importantes. La secuencia guía al visitante por un recorrido progresivo: primero entiende el problema, luego conoce la solución, después explora sus funcionalidades y finalmente recibe estímulos para registrarse o iniciar sesión.

La estructura general de la Landing Page sigue el siguiente flujo:

- **Hero section:** Presenta la propuesta de valor principal y los CTAs principales.
- **Sección de beneficios:** Resume de forma rápida los problemas que resuelve la plataforma.
- **Sección de funcionalidades:** Explica las capacidades clave para restaurantes y proveedores.
- **Sección de impacto o métricas:** Refuerza credibilidad mediante cifras, indicadores o resultados esperados.
- **Sección de muestra del producto:** Permite visualizar pantallas, imágenes o video del sistema.
- **Sección de preguntas frecuentes:** Resuelve dudas antes de la conversión.
- **Footer:** Reúne enlaces secundarios, contacto, páginas legales y accesos finales.

Esta estructura no es aleatoria: busca reducir fricción en el recorrido del visitante y facilitar que identifique en pocos segundos si el producto es relevante para su necesidad.

#### Organization Systems in the Web Application

En la Web Application, la organización del contenido es principalmente **por tópicos**, **por audiencia** y **cronológica**, según el tipo de información mostrada.

- **Por tópicos:** Se emplea en el menú principal, donde las funcionalidades se agrupan en módulos como Inventario, Pedidos, Proveedores, Alertas, Reportes y Configuración.
- **Por audiencia:** Se aplica al separar claramente la experiencia del restaurante y la del proveedor. Cada rol visualiza solamente los módulos, flujos y datos relevantes para sus operaciones.
- **Cronológica:** Se utiliza en historiales, pedidos, movimientos de inventario, alertas y registros, donde el tiempo es una variable importante para trazabilidad y seguimiento.
- **Matricial:** Se emplea en vistas donde el usuario necesita comparar múltiples variables simultáneamente, como tablas de inventario, catálogos o reportes.

#### Organización visual del contenido

| Tipo de organización | Aplicación en SupplyWok | Justificación |
|---|---|---|
| Jerárquica | Hero section, dashboards, cards de alertas y KPIs | Permite destacar información crítica y dirigir la atención hacia las acciones prioritarias. |
| Secuencial | Registro, onboarding, creación de pedidos, configuración inicial | Ayuda al usuario a completar procesos paso a paso, reduciendo errores. |
| Matricial | Inventario, historial de pedidos, catálogos, reportes | Facilita comparar atributos como cantidad, proveedor, fecha, precio y estado. |

#### Esquemas de categorización

| Tipo de esquema | Aplicación en SupplyWok | Justificación |
|---|---|---|
| Por tópicos | Inventario, Pedidos, Proveedores, Alertas, Reportes, Configuración | Agrupa el contenido según la tarea que el usuario busca realizar. |
| Cronológico | Historial de pedidos, movimientos de stock, alertas registradas | Facilita seguimiento y auditoría de eventos pasados. |
| Por audiencia | Vista Restaurante y Vista Proveedor | Reduce ruido informativo y adapta la experiencia al rol del usuario. |

#### Esquemas no priorizados

SupplyWok no prioriza un esquema **alfabético** como estructura principal, ya que la mayoría de sus tareas no dependen de exploración lexical, sino de acciones operativas y contextuales. Aunque ciertos listados pueden ordenarse alfabéticamente de manera secundaria, la plataforma privilegia estructuras orientadas a flujo de trabajo, prioridad operativa y estado de la información.

Tampoco se utiliza una organización puramente temática en la Landing Page sin jerarquía de conversión, porque el objetivo de esa interfaz no es solo informar, sino llevar al usuario hacia una acción clara en el menor número posible de pasos.

#### Secciones principales de SupplyWok

La aplicación se divide en dos grandes espacios según el rol del usuario.

**Vista Restaurante**

| Sección | Descripción |
|---|---|
| Dashboard | Resumen del estado operativo del día: alertas de stock, pedidos pendientes, lecturas críticas y métricas principales. |
| Inventario | Registro y seguimiento de insumos, stock actual, stock mínimo, unidad de medida y movimientos. |
| Pedidos | Creación, seguimiento e historial de órdenes de abastecimiento dirigidas a proveedores. |
| Proveedores | Directorio y detalle de proveedores vinculados al restaurante. |
| Alertas | Centro de notificaciones operativas y eventos críticos. |
| Reportes | Visualización de métricas, consumo, evolución del inventario y comportamiento de pedidos. |
| Configuración | Gestión de perfil, usuarios, preferencias y parámetros generales. |

**Vista Proveedor**

| Sección | Descripción |
|---|---|
| Dashboard | Resumen de pedidos recibidos, entregas en curso y demanda proyectada. |
| Pedidos recibidos | Gestión y seguimiento de las órdenes enviadas por restaurantes. |
| Mis clientes | Directorio de restaurantes vinculados y su historial de demanda. |
| Demanda proyectada | Estimación de necesidades futuras por cliente o producto. |
| Catálogo de productos | Gestión de los insumos ofrecidos, precios y disponibilidad. |
| Configuración | Gestión del perfil, cobertura, contacto y preferencias. |

### 4.2.2. Labeling Systems.

El sistema de etiquetado de SupplyWok ha sido diseñado para que cada elemento de la interfaz comunique su propósito de forma inmediata. Las etiquetas se redactan con términos breves, directos y familiares para el contexto gastronómico y logístico, evitando tecnicismos innecesarios. Esto permite que el usuario comprenda con rapidez qué sección está visitando, qué acción puede ejecutar y qué resultado debe esperar.

A diferencia de un simple glosario, el sistema de etiquetado de SupplyWok se aplica de manera concreta en zonas específicas de la interfaz, como la navbar de la Landing Page, el sidebar de la aplicación, los botones principales, los formularios, los breadcrumbs y los mensajes de estado.

#### Labeling in the Landing Page

En la Landing Page, las etiquetas priorizan claridad comercial y orientación a la conversión. Se emplean principalmente en:

- **Navbar superior:** `Inicio`, `Funcionalidades`, `Planes`, `FAQ`, `Iniciar sesión`.
- **Botones principales del hero:** `Crear cuenta`, `Ver demo`, `Soy restaurante`, `Soy proveedor`.
- **Secciones informativas:** `Beneficios`, `Cómo funciona`, `Impacto`, `Preguntas frecuentes`.
- **Footer:** `Contacto`, `Política de privacidad`, `Términos y condiciones`.

Estas etiquetas permiten que el visitante identifique rápidamente la estructura del contenido y pueda desplazarse hacia las secciones que más le interesan antes de tomar una decisión.

#### Labeling in the Web Application

En la Web Application, las etiquetas se enfocan en apoyar la operación diaria del usuario. Se distribuyen en los siguientes puntos:

- **Sidebar o menú lateral:** `Dashboard`, `Inventario`, `Pedidos`, `Proveedores`, `Alertas`, `Reportes`, `Configuración`.
- **Header:** `Notificaciones`, `Mi perfil`, `Cambiar de vista`, `Cerrar sesión`.
- **Botones de acción:** `Agregar insumo`, `Crear pedido`, `Actualizar estado`, `Ver detalle`, `Guardar cambios`, `Cancelar`.
- **Breadcrumbs:** `Pedidos > Detalle del pedido`, `Inventario > Agregar insumo`, `Proveedores > Perfil del proveedor`.
- **Formularios:** `Nombre del insumo`, `Unidad de medida`, `Stock mínimo`, `Proveedor asociado`, `Fecha de entrega`, `Precio unitario`.
- **Mensajes de estado:** `Pendiente`, `En camino`, `Entregado`, `Cancelado`, `Stock bajo`, `Fuera de rango`.

#### Criterios del sistema de etiquetado

El sistema de etiquetado de SupplyWok sigue los siguientes criterios:

- **Brevedad:** Las etiquetas deben usar el menor número de palabras posible sin perder claridad.
- **Consistencia:** Un mismo concepto debe nombrarse siempre de la misma manera en toda la plataforma.
- **Familiaridad:** Se priorizan términos cercanos al usuario real del dominio.
- **Orientación a la acción:** Los botones y acciones usan verbos claros que indican lo que ocurrirá.
- **Escaneabilidad:** Las etiquetas deben poder comprenderse rápidamente incluso en interfaces densas como tablas y dashboards.

#### Etiquetas principales del sistema

| Etiqueta | Lugar de uso | Descripción |
|---|---|---|
| Iniciar sesión | Navbar, formularios de acceso | Permite ingresar con una cuenta existente. |
| Crear cuenta | Hero section, formularios de registro | Permite registrarse como nuevo usuario. |
| Dashboard | Sidebar, header, breadcrumbs | Pantalla inicial con el resumen principal del rol. |
| Inventario | Sidebar, títulos de vista | Módulo de control de insumos y stock. |
| Agregar insumo | Botón principal, formularios | Acción para registrar un nuevo producto en inventario. |
| Stock mínimo | Formularios, tablas, alertas | Umbral que activa reposición o advertencia. |
| Crear pedido | Botón principal, módulo de pedidos | Acción para generar una nueva orden. |
| Estado del pedido | Tablas, cards, detalle de pedido | Indicador del avance operativo del pedido. |
| Alerta de stock | Dashboard, alertas, notificaciones | Notificación sobre nivel crítico de inventario. |
| Proveedor vinculado | Formularios, tablas, fichas | Relación activa entre restaurante y proveedor. |
| Historial | Tablas, reportes, filtros | Registro cronológico de eventos o transacciones. |
| Reportes | Sidebar, títulos, cards | Módulo de análisis y visualización de métricas. |
| Configuración | Sidebar, header | Área de gestión del perfil y parámetros del sistema. |
| Cerrar sesión | Header, menú de usuario | Acción para salir de la cuenta actual. |

### 4.2.3. SEO Tags and Meta Tags.

Las etiquetas SEO y Meta Tags de SupplyWok se definen para mejorar la visibilidad del producto en buscadores, reforzar la claridad del contenido presentado y optimizar la manera en que las páginas se muestran en navegadores y redes sociales. Debido a que la solución cuenta con una Landing Page pública y una Web Application privada, las decisiones de etiquetado SEO se concentran principalmente en las páginas públicas y en las pantallas principales que pueden funcionar como punto de acceso o referencia de producto.

A continuación, se detallan los principales títulos y metadatos propuestos para las páginas más relevantes de la experiencia digital.

#### Home / Landing Page

- **Title:** SupplyWok | Gestión inteligente de abastecimiento para restaurantes
- **Meta Description:** Optimiza inventario, pedidos y coordinación con proveedores desde una sola plataforma diseñada para restaurantes tipo chifa y negocios gastronómicos.
- **Meta Keywords:** gestión de inventario restaurantes, abastecimiento gastronómico, control de stock, pedidos a proveedores, software para chifas, supply chain restaurante
- **Meta Author:** Aurora

#### Funcionalidades / Features

- **Title:** Funcionalidades de SupplyWok | Inventario, pedidos y alertas en una sola plataforma
- **Meta Description:** Conoce cómo SupplyWok ayuda a restaurantes y proveedores a gestionar inventario, coordinar pedidos, monitorear alertas y tomar mejores decisiones operativas.
- **Meta Keywords:** funcionalidades software restaurante, inventario digital, pedidos a proveedores, alertas de stock, dashboard gastronómico
- **Meta Author:** Aurora

#### Planes / Pricing

- **Title:** Planes de SupplyWok | Soluciones para restaurantes y proveedores
- **Meta Description:** Explora los planes de SupplyWok y descubre la opción adecuada para digitalizar el control de inventario, pedidos y abastecimiento de tu negocio.
- **Meta Keywords:** precios software restaurante, planes gestión de inventario, suscripción software gastronómico, plataforma para proveedores
- **Meta Author:** Aurora

#### Login / Iniciar sesión

- **Title:** Iniciar sesión | SupplyWok
- **Meta Description:** Accede a tu cuenta de SupplyWok para gestionar inventario, pedidos, alertas y reportes desde una plataforma centralizada.
- **Meta Keywords:** login supplywok, acceso plataforma inventario, panel restaurante, panel proveedor
- **Meta Author:** Aurora

#### Register / Crear cuenta

- **Title:** Crear cuenta | SupplyWok
- **Meta Description:** Regístrate en SupplyWok como restaurante o proveedor y empieza a organizar tu abastecimiento de forma más eficiente.
- **Meta Keywords:** registro supplywok, crear cuenta restaurante, crear cuenta proveedor, software abastecimiento
- **Meta Author:** Aurora

#### Dashboard

- **Title:** Dashboard | SupplyWok
- **Meta Description:** Revisa el estado actual de tu operación, alertas activas, pedidos pendientes y métricas clave desde el panel principal de SupplyWok.
- **Meta Keywords:** dashboard restaurante, dashboard proveedor, panel operativo, alertas de stock, pedidos pendientes
- **Meta Author:** Aurora

#### Inventario

- **Title:** Inventario | SupplyWok
- **Meta Description:** Gestiona tus insumos, controla niveles de stock y detecta productos críticos desde el módulo de inventario de SupplyWok.
- **Meta Keywords:** inventario restaurante, control de insumos, stock mínimo, abastecimiento digital
- **Meta Author:** Aurora

#### Pedidos

- **Title:** Pedidos | SupplyWok
- **Meta Description:** Crea, consulta y supervisa órdenes de abastecimiento entre restaurantes y proveedores con trazabilidad centralizada.
- **Meta Keywords:** pedidos restaurante, órdenes de compra, seguimiento de pedidos, abastecimiento proveedor
- **Meta Author:** Aurora

Estas etiquetas permiten diferenciar el propósito de cada página dentro del ecosistema digital, mantener coherencia entre la propuesta comercial y la experiencia operativa, y reforzar el posicionamiento del producto en búsquedas relacionadas con inventario, abastecimiento y gestión gastronómica.

### 4.2.4. Searching Systems.

SupplyWok incorpora sistemas de búsqueda y filtrado para reducir el tiempo que el usuario dedica a localizar información dentro de la plataforma. Dado que gran parte de la experiencia está orientada a tareas operativas, las búsquedas no solo deben encontrar datos, sino también presentarlos en un formato comprensible y accionable.

#### Searching in the Web Application

Los mecanismos de búsqueda se aplican en módulos donde el volumen de información puede crecer rápidamente, como inventario, pedidos, proveedores, clientes, alertas e historiales. Cada búsqueda se acompaña de filtros específicos según el contexto del módulo.

| Sistema de búsqueda | Ubicación | Descripción |
|---|---|---|
| Búsqueda de insumos | Inventario | Permite localizar productos por nombre, categoría o unidad de medida. |
| Búsqueda de proveedores | Proveedores | Permite encontrar proveedores por nombre o tipo de insumo ofrecido. |
| Búsqueda de pedidos | Pedidos | Permite filtrar pedidos por estado, proveedor, cliente o rango de fechas. |
| Búsqueda de clientes | Vista Proveedor | Permite encontrar restaurantes vinculados por nombre o historial de actividad. |
| Filtro por categoría | Inventario y catálogos | Reduce el listado a un tipo específico de producto. |
| Filtro por fecha | Historial, reportes y pedidos | Permite analizar periodos específicos de operación. |
| Filtro por estado | Pedidos y alertas | Muestra solamente registros con una condición determinada. |

#### Visualización de resultados

Los resultados de búsqueda en SupplyWok se presentan de forma distinta según la naturaleza del contenido:

- **Inventario:** Los resultados se muestran en una tabla o lista con columnas como nombre del insumo, stock actual, stock mínimo, unidad de medida y proveedor asociado.
- **Pedidos:** Los resultados se presentan en tabla o cards con número de pedido, proveedor o cliente, fecha, estado y acceso a detalle.
- **Proveedores y clientes:** Los resultados se muestran como fichas resumidas con nombre, contacto, rubro o historial asociado.
- **Alertas:** Los resultados se muestran como lista priorizada con nivel de criticidad, fecha y acceso a la sección relacionada.
- **Reportes o historiales:** Los resultados se representan mediante tablas filtradas o gráficos ajustados al rango seleccionado.

#### Comportamiento esperado de los resultados

Los resultados de búsqueda deben seguir estos criterios:

- Responder en tiempo razonable y con feedback visual claro.
- Mostrar solo la información necesaria para que el usuario tome una decisión rápida.
- Permitir ordenar o refinar el resultado sin reiniciar completamente la búsqueda.
- Indicar cuando no existen coincidencias mediante mensajes como `No se encontraron resultados`.
- Mantener visibles los filtros aplicados para que el usuario entienda por qué ve cierto subconjunto de datos.

#### Searching in the Landing Page

La Landing Page no depende de un buscador interno complejo, pero sí incorpora mecanismos de exploración rápida mediante navegación por secciones y anchors. En este caso, el “searching” se resuelve a través de una estructura visible y predecible que permite al visitante llegar rápidamente a contenido como funcionalidades, planes, preguntas frecuentes o acceso al registro.

### 4.2.5. Navigation Systems.

El sistema de navegación de SupplyWok ha sido diseñado para que el usuario pueda recorrer la experiencia con claridad tanto en la Landing Page como en la Web Application. En ambos casos, la navegación busca reducir fricción, mantener consistencia y facilitar el acceso rápido a acciones clave.

#### Navigation in the Landing Page

En la Landing Page, la navegación se estructura como un recorrido progresivo orientado a conversión. El usuario puede desplazarse por la página de forma lineal o saltar directamente a secciones específicas mediante enlaces visibles en la barra superior.

Los principales mecanismos de navegación en la Landing Page son:

- **Navbar superior fija:** Incluye accesos a `Inicio`, `Funcionalidades`, `Planes`, `FAQ` e `Iniciar sesión`.
- **Navegación por anchors:** Cada opción del menú dirige a una sección concreta de la misma página.
- **Hero section con CTAs principales:** Botones como `Crear cuenta`, `Ver demo`, `Soy restaurante` o `Soy proveedor` redirigen al usuario al flujo correspondiente.
- **CTAs secundarios distribuidos:** Se repiten en secciones estratégicas para evitar que el usuario tenga que volver al inicio para actuar.
- **Footer con enlaces complementarios:** Contacto, políticas, términos y accesos secundarios.

Este sistema permite que un visitante nuevo entienda rápidamente el producto, navegue según su interés y llegue a la acción principal en pocos pasos.

#### Navigation in the Web Application

En la aplicación, la navegación se orienta a productividad y ejecución de tareas. Cada rol accede a una estructura estable que prioriza las funcionalidades más utilizadas.

| Elemento de navegación | Descripción |
|---|---|
| Sidebar | Menú lateral persistente con acceso directo a las secciones principales del rol activo. |
| Header | Barra superior con perfil, rol, notificaciones y accesos rápidos. |
| Dashboard como punto de entrada | Pantalla inicial tras autenticación, desde donde el usuario visualiza su estado operativo general. |
| Breadcrumbs | Indicadores de ruta para secciones de detalle, permitiendo comprender ubicación y retroceder fácilmente. |
| Botones contextuales | Acciones principales visibles dentro de cada módulo, como `Crear pedido` o `Agregar insumo`. |
| Notificaciones | Panel accesible desde el header para revisar alertas recientes y redirigirse a la sección relacionada. |
| Cambio de vista por rol | En caso de usuarios con más de un rol, se puede alternar entre contexto restaurante y proveedor. |

#### Recorridos principales de navegación

La navegación de SupplyWok considera recorridos típicos como los siguientes:

- **Visitante de Landing Page -> CTA principal -> Registro o login -> Dashboard del rol correspondiente.**
- **Restaurante -> Dashboard -> Inventario -> Agregar insumo o revisar stock crítico.**
- **Restaurante -> Dashboard -> Pedidos -> Crear pedido -> Seguimiento del estado.**
- **Proveedor -> Dashboard -> Pedidos recibidos -> Actualizar estado de entrega.**
- **Proveedor -> Dashboard -> Catálogo -> Actualizar disponibilidad o precios.**

#### Criterios de navegación

La navegación en SupplyWok sigue estos criterios:

- **Consistencia:** Los elementos principales conservan posición y lógica entre pantallas.
- **Claridad:** Cada enlace y botón comunica claramente su destino o acción.
- **Economía de pasos:** Las tareas frecuentes deben completarse con el menor número posible de interacciones.
- **Visibilidad del estado actual:** El usuario debe saber siempre en qué módulo está y qué acciones puede ejecutar.
- **Adaptabilidad responsive:** La navegación debe mantenerse usable en desktop, tablet y mobile web.

#### Navegación — Landing Page

| Elemento | Descripción |
|---|---|
| Navbar fija | Barra superior visible en todo momento durante el scroll. Contiene logo, enlaces a secciones (anclas) y botones de Iniciar sesión / Registrarse. En mobile se colapsa en menú hamburguesa. |
| Anclas de sección | Los enlaces del navbar desplazan suavemente (smooth scroll) a cada sección de la página: #hero, #como-funciona, #funcionalidades, #para-quien, #precios, #faq. |
| CTA primario en Hero | Botón "Comenzar gratis" redirige a /register. Es el punto de conversión principal de la landing. |
| CTA secundario en Hero | Botón "Ver cómo funciona" hace scroll a la sección #como-funciona, manteniendo al usuario en la landing para informarse antes de registrarse. |
| CTAs por segmento | En la sección "¿Para quién es SupplyWok?", cada card (restaurante / proveedor) tiene un botón que redirige a /register con el parámetro de rol preseleccionado (?rol=restaurante o ?rol=proveedor). |
| CTA en sección Precios | Cada plan tiene un botón que redirige a /register con el plan preseleccionado, reduciendo pasos en el onboarding. |
| CTA final (bottom of page) | Sección de cierre con un último llamado a la acción antes del footer, dirigido a usuarios que llegaron al final sin convertir. |
| Footer | Contiene enlaces a páginas legales (política de privacidad, términos), redes sociales y el enlace de inicio de sesión para usuarios ya registrados. |

#### Navegación — Web Application

| Elemento | Descripción |
|---|---|
| Sidebar  | Menú principal fijo a la izquierda, visible en todo momento. Contiene accesos directos a todas las secciones del rol activo con ícono y etiqueta. En mobile se colapsa en hamburguesa. |
| Header | Barra superior con nombre del negocio, badge del plan activo, ícono de notificaciones con contador y avatar del usuario con menú desplegable (Perfil / Configuración / Cerrar sesión). |
| Dashboard como home | Tras iniciar sesión, el usuario es redirigido automáticamente al Dashboard de su rol. El Dashboard funciona como hub de acceso rápido: las tarjetas de métricas (low stock, pending orders, alerts) son clicables y llevan a la sección correspondiente. |
| Breadcrumbs | Visibles en vistas de detalle para indicar la ruta actual y permitir la navegación hacia atrás. Ejemplo: Pedidos › #PO-8821. |
| Botones de acción contextual | Cada sección tiene un botón primario ("+ Agregar insumo", "+ Crear pedido") ubicado en la esquina superior derecha del contenido, accesible sin scroll. |
| Panel de notificaciones | Al hacer clic en el ícono de campana del header, se despliega un panel lateral con las alertas recientes ordenadas cronológicamente. Cada alerta tiene un acceso directo a la sección donde ocurrió el evento. |
| Modo restringido | El dueño puede activar un modo de acceso limitado desde Configuración. En este modo solo son visibles Kitchen Tickets y Tables and Occupancy, ocultando las secciones administrativas. Útil para personal de cocina y servicio. |
| Cambio de rol | Si un usuario tiene ambos roles (restaurante y proveedor), puede cambiar de vista desde un selector en el header sin cerrar sesión. |
---
## 4.3. Landing Page UI Design.
La propuesta de UI del Landing Page de SupplyWok traduce las decisiones previas de identidad visual, estilo y arquitectura de información en una experiencia clara, persuasiva y orientada a conversión. Su objetivo principal es presentar la propuesta de valor del producto, explicar de manera rápida cómo ayuda a restaurantes tipo chifa y proveedores, y conducir al visitante hacia una acción concreta, como registrarse, iniciar sesión o explorar el funcionamiento de la plataforma.

El diseño del Landing Page se estructura en bloques progresivos que responden a una lógica de descubrimiento: primero captar atención, luego explicar el problema, mostrar beneficios y funcionalidades, reforzar confianza con evidencia visual y finalmente cerrar con llamadas a la acción claras. Esta organización permite que el usuario entienda qué resuelve SupplyWok, cómo funciona y por qué debería usarlo, sin tener que navegar por una interfaz compleja ni enfrentarse a una sobrecarga de información.

A nivel visual, la interfaz aprovecha la paleta cromática definida para la marca, con predominio de rojo, amarillo, blanco y negro, para transmitir dinamismo, energía y asociación cultural con el entorno de los restaurantes tipo chifa. La jerarquía visual se apoya en titulares fuertes, CTAs visibles, tarjetas informativas y bloques diferenciados por espaciado, logrando que el recorrido sea intuitivo y consistente tanto en escritorio como en dispositivos móviles.

### 4.3.1. Landing Page Wireframe.
#### Desktop
<p align="center">
  <img src="../assets/images/figma/landingpage-desktop-wireframe.png" width="600px">
</p>

#### Mobile
<p align="center">
  <img src="../assets/images/figma/landingpage-mobile-wireframe.png" width="600px">
</p>

### 4.3.2. Landing Page Mock-up.
#### Desktop
<p align="center">
  <img src="../assets/images/figma/landingpage-desktop-mockup.png" >
</p>

#### Mobile
<p align="center">
  <img src="../assets/images/figma/landingpage-mobile-mockup.png" width="600px">
</p>


## 4.4. Web Applications UX/UI Design.

### 4.4.1. Web Applications Wireframes.

<p align="center">
  <img src="../assets/images/figma/wireframes-web.jpg" width="600px">
</p>

![web-application-mobile-wireframe1](../assets/images/figma/web-app-mobile-wireframe1.png)
![web-application-mobile-wireframe2](../assets/images/figma/web-app-mobile-wireframe2.png)
![web-application-mobile-wireframe3](../assets/images/figma/web-app-mobile-wireframe3.png)

### 4.4.2. Web Applications Wireflow Diagrams.
![web-application-mobile-wireflow1](../assets/images/figma/web-app-mobile-wireflow1.jpeg)
![web-application-mobile-wireflow2](../assets/images/figma/web-app-mobile-wireflow2.jpeg)
![web-application-mobile-wireflow3](../assets/images/figma/web-app-mobile-wireflow3.jpeg)
![web-application-mobile-wireflow4](../assets/images/figma/web-app-mobile-wireflow4.jpeg)

### 4.4.2. Web Applications Mock-ups.

Se muestran los mock ups del diseño de la aplicacion web para escritorio

**dashboard principal**
<p align="center">
  <img src="../assets/images/figma/mockup-web1.png" width="600px">
</p>

**Inventario del restaurante**
<p align="center">
  <img src="../assets/images/figma/mockup-web2.png" width="600px">
</p>

**Ordenes de insumos**
<p align="center">
  <img src="../assets/images/figma/mockup-web3.png" width="600px">
</p>

**Pedidos de los clientes**
<p align="center">
  <img src="../assets/images/figma/mockup-web4.png" width="600px">
</p>

**Lista de proveedores**
<p align="center">
  <img src="../assets/images/figma/mockup-web5.png" width="600px">
</p>

**Mesas ocupadas**
<p align="center">
  <img src="../assets/images/figma/mockup-web6.png" width="600px">
</p>

**Menu de notificaciones de alertas**
<p align="center">
  <img src="../assets/images/figma/mockup-web7.png" width="600px">
</p>

**Reportes estadisticos**
<p align="center">
  <img src="../assets/images/figma/mockup-web8.png" width="600px">
</p>

**Configuracion del restaurante**
<p align="center">
  <img src="../assets/images/figma/mockup-web9.png" width="600px">
</p>

**Planes de suscribción**
<p align="center">
  <img src="../assets/images/figma/mockup-web10.png" width="600px">
</p>

Se muestran los respectivos mock ups del diseño de la aplicacion para mobile 

![web-application-mobile-mockup1](../assets/images/figma/web-app-mobile-mockup1.png)
![web-application-mobile-mockup2](../assets/images/figma/web-app-mobile-mockup2.png)
![web-application-mobile-mockup3](../assets/images/figma/web-app-mobile-mockup3.png)
### 4.4.3. Web Applications User Flow Diagrams.


![web-application-mobile-userflow1](../assets/images/figma/web-app-mobile-userflow1.jpeg)
![web-application-mobile-userflow2](../assets/images/figma/web-app-mobile-userflow2.jpeg)
![web-application-mobile-userflow3](../assets/images/figma/web-app-mobile-userflow3.jpeg)
![web-application-mobile-userflow4](../assets/images/figma/web-app-mobile-userflow4.jpeg)
## 4.5. Web Applications Prototyping.

#### Escritorio
![desktop-prototype](../assets/images/figma/desktop-prototype.png)

[video del prototipo de escritorio](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBzkLBme7KrQ7W3hSiUgvLXAadwJ4sFVek0clbOC9pBKhA?e=Vuhi1W&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D) 

[prototipo de escritorio](https://www.figma.com/proto/JUBnvZfJvlrpxIpW8ICRvS/SupplyWok?node-id=428-4042&p=f&t=kGhZbpCdqH2BntGS-0&scaling=scale-down&content-scaling=fixed&page-id=428%3A2335)

#### Mobile
![mobile-protoype](../assets/images/figma/mobile-prototype.png)

[video de prototipo de mobile](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQClHjcgmteDRZIiQWrFX27vAWCILR7o7T66T98C5OGOTNQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=TcaZn0)

[prototipo mobile](https://www.figma.com/proto/JUBnvZfJvlrpxIpW8ICRvS/SupplyWok?node-id=428-2336&p=f&t=kGhZbpCdqH2BntGS-0&scaling=scale-down&content-scaling=fixed&page-id=428%3A2336)

## 4.6. Domain-Driven Software Architecture.


### 4.6.1. Design-Level EventStorming.

En esta sección se detalla el proceso de Design-Level EventStorming realizado por el equipo para perfeccionar el modelo del dominio de Aurora. Partiendo del Big Picture, profundizamos en el comportamiento interno del sistema para alcanzar el mayor nivel de detalle arquitectónico posible.

Primero, refinamos la línea de tiempo original, eliminando eventos redundantes o procesos manuales que quedaban fuera del alcance tecnológico de la plataforma. Sobre este flujo depurado, incorporamos los elementos tácticos del Domain-Driven Design: Actores y Comandos para representar las intenciones, Políticas para las reglas automáticas, y Agregados (Aggregates) como responsables de procesar las operaciones y emitir los eventos de dominio. Este nivel de granularidad nos permitió consolidar y justificar las fronteras definitivas de nuestros Bounded Contexts.

Este contexto delimitado constituye el núcleo operativo para los restaurantes tipo chifa dentro de la plataforma Aurora. Su propósito principal es centralizar y automatizar el control de los insumos, transformando la gestión manual tradicional en un proceso preciso y basado en datos.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD1.png" alt="SupplyWok System Context Diagram">
</div>

Este contexto delimitado actúa como el puente transaccional entre los restaurantes tipo chifa y sus proveedores dentro del ecosistema Aurora. Su objetivo fundamental es digitalizar y estructurar la coordinación de pedidos de insumos, reemplazando las vías de comunicación informales por un flujo de trabajo centralizado y rastreable en la plataforma.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD2.png" alt="SupplyWok System Context Diagram">
</div>

Este contexto delimitado tiene como propósito supervisar las condiciones físicas críticas en las instalaciones del restaurante, específicamente en áreas vulnerables como la cocina y el almacén. Mediante la integración simulada de sensores IoT, el sistema monitorea variables ambientales clave de forma continua, tales como la temperatura y la humedad.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD3.png" alt="SupplyWok System Context Diagram">
</div>

Este contexto delimitado está diseñado para centralizar la gestión de los proveedores, brindándoles las herramientas necesarias para optimizar su logística y planificación comercial. A través de este módulo, los proveedores obtienen visibilidad sobre la demanda futura de sus clientes, lo que les permite gestionar sus catálogos de insumos y realizar un seguimiento detallado del estado de los pedidos recibidos.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD4.png" alt="SupplyWok System Context Diagram">
</div>

Este contexto delimitado representa la capa transversal de seguridad y administración comercial de la plataforma Aurora. Su propósito principal es proporcionar un entorno centralizado y seguro donde todos los usuarios puedan autenticarse, gestionar sus cuentas y recibir soporte técnico de manera eficiente.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD5.png" alt="SupplyWok System Context Diagram">
</div>

Este contexto delimitado representa el núcleo operativo del restaurante chifa dentro de la plataforma Aurora. Su propósito principal es orquestar la comunicación crítica entre el salón y la cocina, asegurando que los pedidos se procesen con precisión, se monitoreen en tiempo real y se mantenga la integridad operativa.

<div align="center">
  <img src="../assets/images/Bounded-context-cavnvas-DDD6.png" alt="SupplyWok System Context Diagram">
</div>

### 4.6.2. Software Architecture Context Diagram.

<div align="center">
  <img src="../assets/images/suppluwok-system-context.png" alt="SupplyWok System Context Diagram">
</div>

### 4.6.3. Software Architecture Container Diagrams.

<div align="center">
  <img src="../assets/images/supplywok-containers.png" alt="SupplyWok Containers Diagram">
</div>

### 4.6.4. Software Architecture Components Diagrams.

<div align="center">
  <img src="../assets/images/supplywok-components.png" alt="SupplyWok Components Diagram">
</div>

## 4.7. Software Object-Oriented Design.
### 4.7.1. Class Diagrams.

En esta seccion se presentara y se explicara el diagrama de clases por cada Boundes Context

<div align="center">
  <img src="../assets/images/IMBC.png" alt="SupplyWok Components Diagram">
</div>

El **Inventory Management Bounded Context** es el encargado de gestionar los recursos de inventario de cada restaurante, incluyendo el control de stock, niveles mínimos y movimientos de entrada y salida.

El **InventoryService** actúa como capa de aplicación, coordinando las operaciones del sistema. Este servicio utiliza el **InventoryRepository** para la persistencia de datos y el **InventoryItem** como entidad principal del dominio, encargada de representar cada insumo almacenado en el Inventario del restaurante.El **StockMovement** representa las modificaciones realizadas al stock de cada ítem, permitiendo llevar un registro detallado de entradas, salidas y ajustes.

<div align="center">
  <img src="../assets/images/S&PBC.png" alt="SupplyWok Components Diagram">
</div>

El **Supply and Purchasing Bounded Context** es el encargado de gestionar las órdenes de compra realizadas por cada restaurante, incluyendo el registro, cancelación y seguimiento de los pedidos.

El **PurchaseOrderService** actúa como capa de aplicación, coordinando las operaciones del sistema. Este servicio utiliza el **PurchaseOrderRepository** para la persistencia de datos y el **PurchaseOrder** como entidad principal del dominio, encargada de representar toda la información de una orden de compra de insumos del restaurante. Además, el **OrderItem** encapsula las especificaciones de cada producto dentro de la orden, como la cantidad solicitada y el precio unitario, permitiendo un control detallado de cada pedido.

<div align="center">
  <img src="../assets/images/O&IBC.png" alt="SupplyWok Components Diagram">
</div>

El **Operational Monitoring and IoT Alerts Bounded Context** es el encargado de gestionar la información recopilada por los sensores del restaurante, así como la configuración y generación de alertas ante condiciones fuera de los rangos establecidos.

El **SensorService** actúa como capa de aplicación, coordinando las operaciones del sistema. Este servicio utiliza los repositorios **IAlertRepository** y **ISensorRepository** para la persistencia de datos.

Además, emplea la entidad **Sensor**, junto con **SensorReading**, para representar la información capturada por los sensores. Por otro lado, la entidad **Alert** modela las alertas generadas cuando una medición supera los límites configurados.

<div align="center">
  <img src="../assets/images/RMBC.png" alt="SupplyWok Components Diagram">
</div>

El **Restaurant Management Bounded Context** es el encargado de gestionar todo lo relacionado con la operación del establecimiento, incluyendo la administración de mesas y la gestión de comandas en cada restaurante.

Los servicios **ComandaService**, **RestaurantService** y **TableService** actúan como capa de aplicación, coordinando las distintas operaciones del sistema. Estos servicios utilizan los repositorios **ComandaRepository**, **IRestaurantRepository** y **TableRepository** respectivamente para la persistencia de datos.

Además, se emplean las entidades **Table**, que representa una mesa dentro del restaurante; **Comanda** y **ComandaItem**, que modelan las órdenes de consumo; y **Restaurant**, que encapsula la información principal de cada restaurante.

<div align="center">
  <img src="../assets/images/S&OBC.png" alt="SupplyWok Components Diagram">
</div>

El **Supplier Management & Operations Bounded Context** es el encargado de gestionar la información de los proveedores, sus catálogos de productos y las operaciones relacionadas con el cumplimiento de pedidos.

Los servicios **SupplierService**, **SupplierCatalogService**, **DemandForecastService** y **OrderFulfillmentService** actúan como capa de aplicación, coordinando las distintas operaciones del sistema dentro de este contexto.

El **SupplierService** gestiona la información de los proveedores utilizando el repositorio **SupplierRepository**. Por su parte, el **SupplierCatalogService** administra los productos ofrecidos por cada proveedor mediante **SupplierCatalog** y **CatalogItem**, utilizando **SupplierCatalogRepository** para la persistencia.

Además, el **DemandForecastService** se encarga de generar proyecciones de demanda a través de la entidad **DemandForecast**, la cual contiene múltiples **ProductDemand** que representan estimaciones de consumo.

Finalmente, el **OrderFulfillmentService** gestiona el proceso de entrega de pedidos mediante la entidad **OrderFulfillment**, permitiendo hacer seguimiento al estado de los envíos desde su despacho hasta su entrega final.

<div align="center">
  <img src="../assets/images/I&ABC.png" alt="SupplyWok Components Diagram">
</div>

El **Identity & Access Bounded Context** es el encargado de gestionar todo lo relacionado con la autenticación y administración de cuentas de usuario en el sistema.

Los servicios **AuthService** y **TokenService** actúan como capa de aplicación, coordinando las operaciones de autenticación. El **AuthService** utiliza el repositorio UserRepository para la persistencia de datos, mientras que **TokenService** se encarga de la generación y validación de tokens de acceso.

La entidad **User** encapsula toda la información relevante de un usuario en la plataforma, como su correo electrónico, contraseña (almacenada de forma segura) y su **Role**, el cual define sus permisos dentro del sistema.

<div align="center">
  <img src="../assets/images/SBC.png" alt="SupplyWok Components Diagram">
</div>

El **Shared Bounded Context** contiene Value Objects comunes que son reutilizados por múltiples bounded contexts del sistema, evitando duplicación y promoviendo consistencia en el modelo.

El **ContactInfo** encapsula la información de contacto relevante, como teléfono, correo electrónico y sitio web. Este value object es utilizado por entidades como **Supplier** y **Restaurant**. Por otro lado, **Address** encapsula la información de dirección necesaria, siendo utilizado también por entidades como **Supplier** y **Restaurant** para representar ubicaciones físicas de manera estructurada.

## 4.8. Database Design.

El siguiente Diagrama Entidad-Relación detalla la estructura de datos fundamental que soporta la lógica de la plataforma. A este modelo, compuesto por 25 entidades, se le aplicaron las tres fases de normalización para garantizar un diseño robusto y eficiente. Esto asegura la escalabilidad, la separación de responsabilidades y el mantenimiento de la aplicación, organizada en los siguientes seis módulos:

- #### Gestión de Inventario

Controla las entradas, salidas y niveles de stock para evitar desabastecimientos o excesos.

- #### Abastecimiento y Órdenes de Compra

Gestiona los pedidos de insumos entre el restaurante y el proveedor, reduciendo los tiempos de respuesta entre ambos.

- #### Panel del Proveedor

Centraliza la funcionalidad del proveedor, permitiendo una mejor gestión de catálogos y pedidos.

- #### Plataforma y Acceso

Administra el acceso seguro de los usuarios, sus cuentas y planes de suscripción.

- #### Monitoreo Operativo y Alertas IoT

Representa el núcleo operativo del sistema; controla sensores y notificaciones para garantizar la seguridad en el entorno de trabajo.

- #### Comandas y Órdenes para Cocina

Facilita la comunicación eficiente entre la cocina y las mesas para garantizar un servicio rápido y sin errores.


### 4.8.1. Database Diagrams.

<div align="center">
  <img src="../assets/images/database-diagram.png" alt="SupplyWok Database Diagram">
</div>

[^1]: Clec. (s.f.). El color rojo en China: orígenes y tradiciones. Recuperado el 23 de abril de 2026, de https://fundacionclec.org/el-color-rojo-en-china-origenes-y-tradiciones/