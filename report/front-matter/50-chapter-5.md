# Capítulo V: Product Implementation, Validation & Deployment.

## 5.1. Software Configuration Management. 
Para tener consistencia y seguimiento del desarrollo de la plataforma, se ha definido una serie de herramientas y estrategias de desarrollo. El metodo cubre la configuracion del entorno de desarrollo, la gestion del codigo y el despliegue, alineado a las buenas prácticas de ingenieria de software y metodologias ágiles.
### 5.1.1. Software Development Environment Configuration. 
Para facilitar la colaboración del equipo en todas las actividades del ciclo de vida de desarrollo de SupplyWok, se ha definido un entorno de desarrollo común. Este entorno está compuesto por herramientas especializadas para la gestión del proyecto, diseño UX/UI, modelado, desarrollo, pruebas, documentación y despliegue. La selección de estas herramientas se basa en criterios de eficiencia, compatibilidad con tecnologías open-source (Vue + C#), y alineación con prácticas recomendadas de la industria.

|        Categoría        |      Herramienta      |                                               Propósito                                               |                                      Tipo de acceso/enlace                                      |
| :---------------------: | :-------------------: | :---------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
|    Project Management   |         Jira        |           Gestión del backlog, tareas y sprints del equipo usando metodología ágil (Scrum).           |                             [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira)                            |
| Requirements Management |       UXPressia       |                  Creación de User Personas, Journey Maps y artefactos de needfinding.                 |                          [https://uxpressia.com](https://uxpressia.com)                         |
|   Product UX/UI Design  |         Figma         |                Diseño de wireframes, mockups y prototipos de la aplicación web y móvil.               |                              [https://figma.com](https://figma.com)                             |
|   Modelado de Software  |    LucidChart / Miro / Structurizr     |                 Modelado de arquitectura (UML, C4, Event Storming, Bounded Contexts).                 |               [https://www.lucidchart.com/](https://www.lucidchart.com/)     / [https://miro.com/](https://miro.com/) / [https://structurizr.com/](https://structurizr.com/)               |
|   Frontend Development  |   Visual Studio Code / WebStorm   |                 Desarrollo del Landing Page y Web Application (HTML, CSS, JavaScript).                |                  [https://code.visualstudio.com](https://code.visualstudio.com) / [https://www.jetbrains.com/webstorm/](https://www.jetbrains.com/webstorm/)                 |
|   Backend Development   |     Rider     |     Desarrollo del RESTful API en C# (.NET) siguiendo arquitectura orientada a servicios.    |                [https://www.jetbrains.com/rider/](https://www.jetbrains.com/rider/)               |
|       API Testing       |        Postman        |                           Pruebas y validación de endpoints del API RESTful.                          |                        [https://www.postman.com](https://www.postman.com)                       |
|     Version Control     |         GitHub        | Control de versiones del código fuente y documentación colaborativa (GitFlow + Conventional Commits). |                             [https://github.com](https://github.com)                            |
|  Software Documentation |        Markdown       |                     Redacción del informe del proyecto bajo enfoque Docs-as-Code.                     |                            Compatible con GitHub / editores de texto                            |


### 5.1.2. Source Code Management. 
Los repositorios utilizados para el desarrollo de código fuente son los siguientes:

<div align="center">

| Producto Digital | URL del Repositorio | 
|:----------------:|:-------------------:|
| Landing Page | https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page | 
| Web Services (Backend API) | https://github.com/Aurora-AplicacionesWeb/SupplyWok-BackEnd  |
| Frontend Web Application | https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd |

</div>

---

**Modelos de Ramificación**

Se implementará GitFlow, un modelo de ramificación estructurado, el cual permite separar de manera clara las etapas de desarrollo, pruebas, liberación y mantenimiento.

**La estructura de ramas en GitFlow será:**

- _Main_: Contiene el código en estado estable y listo para producción.
- _Develop_: Rama de integración para desarrollo activo.
- _Feature branches_: Para nuevas funcionalidades.
    - Convención: `feature/nombre-descriptivo`  
    - Ejemplo: `feature/US007-business-profiles`
- _Release branches_: Para preparar versiones antes de pasar a producción.
    - Convención: `release/X.Y.Z`  
    - Ejemplo: `release/1.0.0`
- _Hotfix branches_: Para correcciones urgentes.
    - Convención: `hotfix/X.Y.Z`  
    - Ejemplo: `hotfix/1.0.1`        

**Versionado Semántico (Semantic Versioning)**

- Se utiliza Semantic Versioning 2.0.0, con el esquema MAJOR.MINOR.PATCH:

    - **MAJOR:** Cambios incompatibles.
    - **MINOR:** Funcionalidades nuevas retrocompatibles.
    - **PATCH:** Correcciones retrocompatibles.

    **Ejemplos de versiones:**  
    `v1.0.0`, `v1.1.0`, `v1.1.1`.

**Convenciones para Commits**

El equipo sigue el estándar de Conventional Commits para los mensajes de commits, lo que permite claridad en el historial y facilita la generación automática de changelogs:

`<type>[optional scope]: <description>`

Tipos comunes:

- `feat`: Nueva funcionalidad.
- `fix`: Corrección de errores.
- `docs`: Cambios en documentación.
- `style`: Cambios de formato sin impacto funcional.
- `refactor`: Reestructuración del código.
- `test`: Relacionados con pruebas.
- `chore`: Tareas de mantenimiento.

Ejemplo:
```
  feat(auth): implement login via OAuth
  fix(api): handle null user tokens
```
### 5.1.3. Source Code Style Guide & Conventions. 

El equipo ha adoptado guías de estilo y convenciones de codificación para cada uno de los lenguajes utilizados. Estas convenciones permiten que todos los miembros del equipo desarrollen bajo un estándar común y que el código sea comprensible tanto para desarrolladores actuales como futuros.

Todos los identificadores, comentarios y documentación del código se escribirán en inglés.

---

**Backend: C# con .NET Framework**

Para el desarrollo del backend, se utilizará **C#** junto con el framework **.NET 10**. Se adoptan las siguientes convenciones:

- **Guía de estilo base:**  
  [Microsoft C# Coding Conventions](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)

- **Estructura de carpetas basada en Domain-Driven Design (DDD):**  
  - `Domain`: Contiene las entidades, agregados y lógica de negocio.  
  - `Application`: Contiene los casos de uso y servicios de aplicación.  
  - `Infrastructure`: Contiene la implementación de repositorios, acceso a datos y servicios externos.  
  - `API`: Contiene los controladores y configuraciones específicas de la API.

- **Nomenclatura:**  
  - Clases nombradas en **PascalCase**:  
    Ejemplo: `UserService`, `MealPlanRepository`  
  - Métodos y variables en **camelCase**:  
    Ejemplo: `getAllUsers()`, `userEmail`  

- **Documentación:**  
  - Uso obligatorio de **XML Documentation Comments** para describir métodos y clases públicas.

- **Separación lógica del código:**  
  - Cada capa debe tener responsabilidades claras:  
    - Controladores (`[ApiController]`)  
    - Servicios (`Scoped` o `Singleton`)  
    - Repositorios (`IRepository`)  
    - Modelos  

- **Anotaciones de .NET:**  
  - Uso de atributos como `[HttpGet]`, `[HttpPost]`, `[FromBody]` para mantener claridad en los controladores.

---

**Frontend: Vue.js Framework (JavaScript, HTML, CSS)**

Para el desarrollo del frontend, el equipo utilizará **Vue 3**, basado en **JavaScript** junto con **HTML** y **CSS**. Las convenciones son:

- **Guías de estilo base:**  
  - [Vue.js Style Guide (Oficial)](https://vuejs.org/style-guide/)  
  - [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

- **Estructura modular y escalable:**  
  - Cada componente tendrá su propio directorio con los archivos `.vue`, `.js` y `.css` correspondientes.

- **Nomenclatura de archivos:**  
  - Archivos nombrados con **kebab-case**:  
    - Componentes: `user-profile.vue`  
    - Servicios: `auth-service.js`  
    - CSS asociados seguirán el mismo nombre base.

- **Nomenclatura de clases y componentes:**  
  - Componentes y clases en **PascalCase**:  
    Ejemplo: `UserProfile`, `MealPlanCard`  
  - Variables, métodos y propiedades en **camelCase**.

- **Modelos de datos:**  
  - Uso de **TypeScript interfaces** o **JavaScript objects** para definir modelos de datos (e.g., `User`, `MealPlan`, `Recipe`) y asegurar consistencia.

- **HTML:**  
  - Buenas prácticas semánticas y accesibles:  
    Uso de etiquetas apropiadas (`<main>`, `<section>`, `<button>`, etc.).

- **CSS:**  
  - Convenciones basadas en el [BEM (Block Element Modifier)](http://getbem.com/):  
    - Nombres de clase descriptivos en inglés:  
      Ejemplo: `.user-profile__header`  
    - Agrupación por tipo de selector.  
    - Estilos reutilizables mediante clases utilitarias.

---

Estas guías aseguran que el código sea limpio, mantenible y fácil de entender para todos los miembros del equipo.

### 5.1.4. Software Deployment Configuration.
La configuración de despliegue contempla mecanismos organizados para publicar correctamente cada uno de los productos digitales del sistema: **Landing Page**, **Web Services (Backend)** y **Frontend Web Application**. Esta configuración garantiza que el equipo pueda replicar y mantener el proceso de despliegue con consistencia y trazabilidad.

---

**Despliegue del Landing Page**

- **Tecnología:**  
  HTML5, CSS3, JavaScript (Vanilla), diseño responsivo.

- **Repositorio GitHub:**  
  [https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page](https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page)

- **Plataforma de despliegue:**  
  GitHub Pages

- **Método de despliegue:**  
  - La rama `main` contiene la versión estable y publicada del sitio.  
  - El contenido del directorio raíz se mantiene como fuente para GitHub Pages.  
  - Los cambios aprobados en `develop` son fusionados a `main` mediante pull request.  
  - GitHub Pages actualiza automáticamente la publicación al detectar cambios en `main`.

---

**Despliegue del Backend (Web Services)**

- **Tecnología:**  
  C# con .NET 10.

- **Repositorio GitHub:**  
  [https://github.com/Aurora-AplicacionesWeb/SupplyWok-BackEnd](https://github.com/Aurora-AplicacionesWeb/SupplyWok-BackEnd)

- **Plataforma de despliegue:**  
  Azure App Service.

- **Método de despliegue:**  
  - El backend se empaqueta como un archivo ejecutable o se publica directamente desde Visual Studio.  
  - Se configura un pipeline de despliegue automático en Azure DevOps para integrar los cambios desde el repositorio.  
  - Las variables de entorno (como credenciales de base de datos) se configuran en Azure App Service de forma segura.  
  - El servicio se expone mediante una URL pública que el frontend puede consumir vía HTTP/REST.

---

**Despliegue del Frontend Web Application**

- **Tecnología:**  
  Vue.js 3 (JavaScript, HTML, CSS).

- **Repositorio GitHub:**  
  [https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd](https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd)

- **Plataforma de despliegue:**  
  Firebase.

- **Método de despliegue:**  
  - Vue.js se compila con `npm run build` para generar los archivos estáticos de producción.  
  - La rama `main` sirve como fuente para el despliegue.  
  - Firebase debe crearse con cada modificación para que esté actualizado con el repositorio.  

---

**Consideraciones Finales**

- Se documentará el procedimiento de despliegue paso a paso en la wiki del repositorio principal.  
- Los entornos de desarrollo y producción estarán claramente separados mediante archivos de configuración.  
- Se establecerán pruebas manuales básicas post-despliegue para verificar la disponibilidad y funcionalidad de los servicios.  
- Se evaluará la incorporación de **GitHub Actions** o **Azure Pipelines** para automatizar los flujos de despliegue continuo (CI/CD).
  
## 5.2. Landing Page, Services & Applications Implementation.
### 5.2.1. Sprint 1 
#### 5.2.1.1. Sprint Planning 1

En el sprint 1 como equipo nos centramos en la creación de la Landing Page de SupplyWok, que será la cara visible de nuestra plataforma ante los usuarios. Definiendo las secciones claves de la página para informar y convencer a los visitantes que se interesen.

**Sprint Planning 1**

| **Sprint #** | 1 |
|---|---|
| **Date** | 20-04-2026 |
| **Time** | 15:00 |
| **Location** | Virtual, Discord |
| **Prepared by** | Zayd Ayasta, Juan Wang |
| **Attendees** | Marcelo Cuadros, Mathias Sanchez, Miguel Jara, Juan Wang, Zayd Ayasta |
| **Sprint 0 Review Summary** | *No aplica por ser el primer sprint.* |
| **Sprint 0 Retrospective Summary** | *No aplica por ser el primer sprint.* |
| **Sprint 1 Goal** | Nuestro enfoque en este sprint es la Landing Page que informará de nuestra plataforma, por lo que la desarrollaremos e implementaremos para que sea accesible y responsiva. Con la información que brindamos sobre nuestro producto esperamos ganarnos la confianza de los que visiten la página y que empiecen a usar nuestro sistema. Se confirmará cuando esté en producción y se pueda usar el enlace de la página. |
| **Sprint 1 Velocity** | Límite de **35 SP** |
| **Sum of Story Points** | **30 SP** |

#### 5.2.1.2. Aspect Leaders and Collaborators.

| Team Member | GitHub username | Estructure HTML | Design UI & responsive | Scripts and UX | SEO and Accessibility | Content and Assets |
|---|---|---|---|---|---|---|
| Cuadros, Marcelo | Marcelo-alt-lab | L | C | L | C | C |
| Sanchez, Mathias | Nounz27 | C | L | C | - | - |
| Jara, Miguel | MiguelJara2 | C | C | C| - | - |
| Ayasta, Zayd | ZaydAyasta | C | C | C | - | C |
| Wang, Juan | jwd3t | C | C | C | L | C |

#### 5.2.1.3. Sprint Backlog 1.

**Sprint 1 Backlog**

| US Id | US Title | Task Id | Task Title | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---|---|
| US44 | Página de inicio con hero section | T01 | Crear estructura HTML de la Hero Section | Maquetar la sección principal (Hero) usando etiquetas semánticas de HTML5. | 2 | Marcelo Cuadros | Done |
| US44 | Página de inicio con hero section | T02 | Implementar estilos CSS de la Hero Section | Aplicar la hoja de estilos base para definir colores, tipografía y disposición. | 2 | Mathias Sanchez | Done |
| US44 | Página de inicio con hero section | T03 | Implementar CTAs y enlace al formulario de registro | Añadir botones llamativos que redirijan al usuario al proceso de registro. | 1 | Marcelo Cuadros | Done |
| US44 | Página de inicio con hero section | T04 | Adaptar Hero Section a diseño responsive | Asegurar que la sección principal se visualice correctamente en dispositivos móviles. | 2 | Marcelo Cuadros | Done |
| US45 | Sección de características principales | T05 | Crear estructura HTML de la sección de características | Construir la grilla o layout para mostrar los beneficios principales de la plataforma. | 1 | Juan Wang | Done |
| US45 | Sección de características principales | T06 | Agregar iconos y estilos visuales a cada característica | Incorporar elementos gráficos y CSS para hacer cada característica visualmente atractiva. | 2 | Mathias Sanchez | Done |
| US46 | Sección de planes y precios | T07 | Crear estructura HTML de la sección de planes | Maquetar el área donde se mostrarán las opciones de precios y suscripciones. | 1 | Zayd Ayasta | Done |
| US46 | Sección de planes y precios | T08 | Implementar estilos de tarjetas de planes y precios | Diseñar visualmente las tarjetas de precios para facilitar la comparación de planes. | 2 | Zayd Ayasta | Done |
| US46 | Sección de planes y precios | T09 | Agregar CTA de selección de plan con redirección al registro | Vincular cada tarjeta de precio con el flujo de creación de cuenta. | 1 | Marcelo Cuadros | Done |
| US47 | Sección de preguntas frecuentes | T10 | Crear estructura HTML del acordeón FAQ | Maquetar el contenedor base para las preguntas frecuentes de los usuarios. | 1 | Marcelo Cuadros | Done |
| US47 | Sección de preguntas frecuentes | T11 | Implementar lógica de expansión y colapso de preguntas | Programar la interactividad para mostrar u ocultar respuestas al hacer clic. | 2 | Marcelo Cuadros | Done |
| US48 | Navegación y menú principal | T12 | Crear navbar sticky con enlaces de navegación | Implementar un menú de navegación fijo en la parte superior con scroll suave. | 2 | Zayd Ayasta | Done |
| US48 | Navegación y menú principal | T13 | Implementar menú hamburguesa para dispositivos móviles | Desarrollar un menú lateral desplegable para resoluciones de pantalla pequeñas. | 2 | Zayd Ayasta | Done |
| US49 | Responsividad total y optimización mobile | T14 | Definir e implementar breakpoints responsive globales | Establecer las reglas CSS de diseño adaptable para toda la página de aterrizaje. | 2 | Zayd Ayasta | Done |
| US49 | Responsividad total y optimización mobile | T15 | Verificar tamaño mínimo de elementos interactivos | Validar que botones y enlaces tengan al menos 44px para facilitar el toque en móviles. | 1 | Miguel Jara | Done |
| US49 | Responsividad total y optimización mobile | T16 | Validar que las imágenes no generen scroll horizontal | Asegurar que ningún recurso visual exceda el ancho máximo de la pantalla. | 1 | Miguel Jara | Done |
| US50 | SEO y accesibilidad web | T17 | Configurar meta tags de SEO (título, descripción, keywords) | Añadir metadatos clave para mejorar la indexación y visibilidad en buscadores. | 1 | Miguel Jara | Done |
| US50 | SEO y accesibilidad web | T18 | Agregar atributos alt, roles ARIA y estructura semántica HTML5 | Mejorar la accesibilidad para usuarios que dependen de lectores de pantalla. | 2 | Miguel Jara | Done |
| US50 | SEO y accesibilidad web | T19 | Verificar navegación por teclado y visibilidad del foco | Asegurar que se pueda interactuar con la página usando únicamente el teclado. | 1 | Miguel Jara | Done |
| US51 | Footer con información adicional | T20 | Crear estructura HTML del footer | Maquetar la sección final de la página para enlaces secundarios y legales. | 1 | Miguel Jara | Done |
| US51 | Footer con información adicional | T21 | Implementar enlaces a redes sociales y páginas legales | Conectar los iconos sociales y los textos de términos y condiciones. | 1 | Zayd Ayasta | Done |
| US52 | Impacto apoyado en cifras | T22 | Crear sección de métricas e impacto con estadísticas | Diseñar un bloque visual que resalte los números clave para generar confianza. | 2 | Juan Wang | Done |
| US53 | Muestra del producto | T23 | Integrar galería de imágenes del producto con texto alternativo | Mostrar capturas de la plataforma asegurando que sean accesibles para todos. | 1 | Mathias Sanchez | Done |
| US53 | Muestra del producto | T24 | Integrar video del producto con fallback de texto alternativo | Incrustar un video demostrativo con opciones de texto para quienes no puedan verlo. | 2 | Mathias Sanchez | Done |
| US54 | Calls to action | T25 | Distribuir CTAs secundarios en secciones clave de la Landing Page | Añadir llamadas a la acción adicionales a lo largo del recorrido del usuario. | 1 | Marcelo Cuadros | Done |
| US55 | Scripts para ocultar contenido | T26 | Implementar scripts de show/hide para contenido condicional | Añadir lógica JavaScript para controlar elementos que se muestran bajo ciertas acciones. | 1 | Marcelo Cuadros | Done |
| US56 | Comentarios y nombres de variables | T27 | Agregar comentarios de código y estandarizar nombres de variables | Limpiar y documentar el código fuente para facilitar futuros mantenimientos. | 1 | Marcelo Cuadros | Done |
| US57 | Sobre el equipo detrás de SupplyWok | T28 | Crear sección del equipo con video y texto alternativo | Maquetar la presentación de los creadores de SupplyWok con soporte multimedia. | 2 | Marcelo Cuadros | Done |
| US58 | Prioridad en mostrar las funcionalidades a los Restaurantes | T29 | Ordenar sección de funcionalidades priorizando beneficios para restaurantes | Estructurar visualmente el contenido para destacar el valor aportado a los restaurantes. | 1 | Marcelo Cuadros | Done |

#### 5.2.1.4. Development Evidence for Sprint Review.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|---|---|---|---|---|---|
| SupplyWok-Landing-Page | develop | 1eca1eb | feat: css hero section and CTA. | 25 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | e7cfb4d | fix: Readme with wrong text. | 25 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 0a4749c | feat: responsive for hero sections. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 6f65577 | feat: add features section and update HTML structure; include new icons and license files. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | main | 0a1e1cc | feat(landing-page): add css and html for hero section and features section. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | main | d9651aa | feat(landing-page): add css and html for hero section and features section. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 62ce603 | feat(landing-page): add text information for plans. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 8967aeb | feat: add styles on plans. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 85fecd0 | docs(readme): fix README.md | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 5bcaa5e | Merge remote-tracking branch 'origin/develop' into develop. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 5ba9214 | feat: add FAQ seccion. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 16d8090 | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page into develop | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | ae2af7a | feat: add header. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | - | feat: add uses you want, about our team and impact | 27 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 68c9d1d | feat: add footer. | 26 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 25283da | feat: add i18n al fixes to the footer. | 27 de Abril, 2026 |
| SupplyWok-Landing-Page | develop | 3452838 | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page into develop | 27 de Abril, 2026 |

Destacar que el commit sin commit id es debido a que es un PR que se hace desde un fork del repositorio.
También se añadirá evidencia del Figma como pruebas de colaboración en el sprint.

Esta sería la captura antes de empezar el sprint con las task creadas en jira y listas para asignarse a los miembros respectivos:
![jira-prove-1](../assets/images/jira-evidence.png)

Esta seria la captura de como quedo el board de jira al finalizar el sprint:
![jira-prove-2](../assets/images/jira-evidence-2.png)

#### 5.2.1.5. Execution Evidence for Sprint Review.

Se presentarán las capturas que muestran el despliegue de la Landing Page en GitHub Pages. La interfaz es responsiva y soporta múltiples idiomas, asegurando accesibilidad para diversos perfiles de usuario.

![hero-section](../assets/images/deploy-steps/prove-1.png)
*Figura: Hero Section de la Landing Page con propuesta de valor clara.*

![features-section](../assets/images/deploy-steps/prove-2.png)
*Figura: Sección de características principales resaltando beneficios para restaurantes.*

![i18n-support](../assets/images/deploy-steps/prove-3.png)
*Figura: Funcionamiento del sistema de internacionalización (i18n) en idioma chino.*

![plans-section](../assets/images/deploy-steps/prove-4.png)
*Figura: Visualización de planes de suscripción y botones de acción (CTA).*

![footer-section](../assets/images/deploy-steps/prove-5.png)
*Figura: Footer con información de contacto, redes sociales y navegación secundaria.*

Aquí está el enlace a la página desplegada: [SupplyWok landing page](https://aurora-aplicacionesweb.github.io/SupplyWok-Landing-Page/)

#### 5.2.1.6. Services Documentation Evidence for Sprint Review.

Como la Landing Page es una página estática, no fue necesario durante el Sprint el uso de servicios externos ni conexiones a API's, por lo cual no hay generación ni evidencia de documentación técnica relacionada.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review.

La evidencia del despliegue de la Landing Page durante el Sprint se mostrará a continuación, el despliegue se realizará en GitHub Pages.

![first-step](../assets/images/deploy-steps/step-1.png)

Revisamos que el repositorio esté en público:

![second-step](../assets/images/deploy-steps/step-2.png)

Nos dirigimos a la seccion de deploy, y selecionamos la rama main:

![third-step](../assets/images/deploy-steps/step-3.png)

Luego de unos minutos, el deploy se realizara correctamente:

![fourth-step](../assets/images/deploy-steps/step-4.png)

#### 5.2.1.8. Team Collaboration Insights during Sprint.

Se anexa evidencia de la participación activa del equipo en el desarrollo de la Landing Page. Durante el Sprint 1, el equipo utilizó una metodología colaborativa mediante Pull Requests y revisiones de código, asegurando que cada sección cumpliera con los estándares de calidad definidos. El gráfico de contribuciones muestra una distribución equitativa de tareas entre maquetación, estilos, lógica de i18n y despliegue.

![Team Collaboration](../assets/images/deploy-steps/participation.png)
*Figura: Reporte de contribuciones y commits del equipo Aurora en el repositorio de la Landing Page.*

### 5.2.2. Sprint 2 
#### 5.2.2.1. Sprint Planning 2

En el Sprint 2, como equipo nos centramos en el desarrollo del frontend de SupplyWok, el cual será la interfaz principal de nuestra plataforma mediante la cual los usuarios podrán administrar sus servicios. Se implementaron diferentes dashboards para que tanto los dueños como los proveedores puedan gestionar las necesidades de sus respectivos negocios.

**Sprint Planning 2**

| **Sprint #** | 2 |
|---|---|
| **Date** | 10-05-2026 |
| **Time** | 13:00 |
| **Location** | Virtual, Discord |
| **Prepared by** | Zayd Ayasta, Juan Wang |
| **Attendees** | Marcelo Cuadros, Mathias Sanchez, Miguel Jara |
| **Sprint 1 Review Summary** | En el Sprint 1, el equipo se enfocó en el desarrollo del Landing Page de SupplyWok. Con ello, se logró configurar el entorno de trabajo, establecer los requerimientos principales del sistema, así como el diseño preliminar de la interfaz y la estructura de navegación de la plataforma. Por otro lado, el profesor a cargo brindó feedback positivo respecto al diseño inicial del sistema y sugirió corregir ciertos aspectos de la documentación del proyecto. |
| **Sprint 1 Retrospective Summary** | Durante el Sprint 1, surgieron dificultades relacionadas con la comunicación, la distribución de tareas y el cumplimiento de algunos entregables de la plataforma, afectando principalmente la documentación del proyecto. Sin embargo, a pesar de estas dificultades, se logró entregar un sprint casi completo y con una calidad aceptable. |
| **Sprint 2 Goal** | Nuestro enfoque en este sprint es desarrollar e implementar la interfaz principal de SupplyWok mediante dashboards funcionales para dueños y proveedores, permitiendo la visualización y gestión básica de la información del negocio. Además, se espera implementar la interfaz base de cada dashboard junto con las funcionalidades principales de cada bounded context. |
| **Sprint 2 Velocity** | Límite de **35 SP** |
| **Sum of Story Points** | **30 SP** |

#### 5.2.2.2. Aspect Leaders and Collaborators.

Durante el Sprint 2, el equipo se enfocó principalmente en el desarrollo del frontend de SupplyWok, priorizando las interfaz y funcionalidades principales de la plataforma. Los principales aspectos considerados en este sprint incluyen el desarrollo de los todos los bounded context.

- **Inventory Management Bounded Context**: Es el encargado de gestionar la informacion de los recursos de inventario de cada restaurante.

- **Supply and Purchasing Bounded Context**: Es el encargado de gestionar las órdenes de suplementos realizadas por cada restaurante.

- **Restaurant Management Bounded Context**: Es el encargado de gestionar todo lo relacionado con la operación del establecimiento.

- **Operational Monitoring and IoT Alerts Bounded Context**: Es el encargado de gestionar la información recopilada por los sensores del restaurante.

- **Supplier Management & Operations Bounded Context**: Es el encargado de gestionar la información de los proveedores y sus pedidos.

- **Identity & Access Bounded Context**: Es el encargado de gestionar todo lo relacionado con la autenticación y administración de cuentas.

- **Shared Bounded Context**: Contiene Value Objects y componenetes visuales comunes que son reutilizados por múltiples bounded contexts del sistema.

| Team Member | GitHub username | Inventory Management Bounded BC | Supply and Purchasing BC / Shared BC | Restaurant Management BC | Supplier Management & Operations BC | Operational Monitoring and IoT Alerts BC / Identity & Access BC  |
|---|---|---|---|---|---|---|
| Cuadros, Marcelo | Marcelo-alt-lab | C | C | C | - | L |
| Sanchez, Mathias | Nounz27             | - | C | L | C | C |
| Jara, Miguel | MiguelJara2     | L | C | - | C | C |
| Ayasta, Zayd | Zayd Ayasta         | C | L | C | C | - |
| Wang, Juan | jwd3t                 | C | - | C | L | C |

#### 5.2.2.3. Sprint Backlog 2.

**Sprint 2 Backlog**

| US Id | US Title | Task Id | Task Title | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---|---|
| US11 | Proyección de demanda basada en historial | T30 | Diseño de interfaz de proyección | Diseñar la interfaz para visualizar la proyección de consumo de insumos. | 3 | Mathias Sanchez | Done |
| US11 | Proyección de demanda basada en historial | T31 | Implementación de gráficos estadísticos | Implementar gráficos y métricas de proyección de demanda. | 4 | Marcelo Cuadros | Done |
| US11 | Proyección de demanda basada en historial | T32 | Integración de datos históricos | Conectar la vista con los datos históricos de consumo. | 3 | Juan Wang | Done |
| US14 | Monitoreo de temperatura en almacén | T33 | Diseño del dashboard IoT | Diseñar el panel de monitoreo de sensores IoT. | 2 | Marcelo Cuadros | Done |
| US14 | Monitoreo de temperatura en almacén | T34 | Integración de datos de sensores | Implementar la recepción y visualización de temperatura en tiempo real. | 4 | Zayd Ayasta | Done |
| US15 | Alertas de riesgo en cocina | T35 | Sistema de alertas automáticas | Implementar alertas visuales ante condiciones peligrosas. | 3 | Miguel Jara | Done |
| US15 | Alertas de riesgo en cocina | T36 | Configuración de umbrales | Configurar parámetros de temperatura y humedad para activar alertas. | 2 | Marcelo Cuadros | Done |
| US17 | Control de ocupación de mesas | T37 | Diseño de estado de mesas | Crear componentes visuales para representar el estado de las mesas. | 2 | Juan Wang | Done |
| US17 | Control de ocupación de mesas | T38 | Actualización en tiempo real | Implementar actualización dinámica de ocupación de mesas. | 3 | Mathias Sanchez | Done |
| US18 | Historial de alertas e incidencias operativas | T39 | Registro de incidencias | Implementar almacenamiento de eventos y alertas. | 3 | Zayd Ayasta | Done |
| US18 | Historial de alertas e incidencias operativas | T40 | Vista histórica de alertas | Crear interfaz para consultar incidencias registradas. | 3 | Marcelo Cuadros | Done |
| US19 | Exportar reporte de monitoreo y alertas | T41 | Generación de reportes PDF | Implementar exportación de reportes en PDF. | 3 | Marcelo Cuadros | Done |
| US19 | Exportar reporte de monitoreo y alertas | T42 | Exportación CSV | Implementar exportación de datos en formato CSV. | 2 | Juan Wang | Done |
| US20 | Registro y perfil del proveedor | T43 | Formulario de registro | Implementar formulario para registro de proveedores. | 3 | Miguel Jara | Done |
| US20 | Registro y perfil del proveedor | T44 | Vista de perfil del proveedor | Crear pantalla de perfil y edición de datos. | 3 | Zayd Ayasta | Done |
| US21 | Recepción y gestión de órdenes de compra | T45 | Panel de órdenes recibidas | Implementar listado de órdenes de compra recibidas. | 4 | Mathias Sanchez | Done |
| US21 | Recepción y gestión de órdenes de compra | T46 | Gestión de estado de pedidos | Permitir actualizar estados de órdenes de compra. | 3 | Marcelo Cuadros | Done |
| US24 | Confirmación y seguimiento de entregas | T47 | Registro de entregas | Implementar formulario para confirmar entregas realizadas. | 3 | Juan Wang | Done |
| US24 | Confirmación y seguimiento de entregas | T48 | Seguimiento de despachos | Implementar visualización del estado de entregas. | 3 | Miguel Jara | Done |
| US25 | Panel de rendimiento por cliente | T49 | Dashboard de clientes frecuentes | Implementar métricas de pedidos por cliente. | 4 | Zayd Ayasta | Done |
| US25 | Panel de rendimiento por cliente | T50 | Estadísticas comerciales | Mostrar estadísticas y tendencias de consumo. | 3 | Miguel Jara | Done |
| US27 | Selección y gestión del plan de suscripción | T51 | Vista de planes disponibles | Diseñar pantalla de planes y beneficios. | 2 | Marcelo Cuadros | Done |
| US27 | Selección y gestión del plan de suscripción | T52 | Gestión de suscripción | Implementar selección y activación de planes. | 2 | Juan Wang | Done |
| US28 | Notificaciones en tiempo real | T53 | Sistema de notificaciones | Implementar notificaciones dinámicas en la plataforma. | 4 | Mathias Sanchez | Done |
| US28 | Notificaciones en tiempo real | T54 | Alertas en tiempo real | Mostrar alertas instantáneas relacionadas al sistema. | 3 | Zayd Ayasta | Done |
| US29 | Inicio de sesión y registro de cuenta | T55 | Formulario de login | Implementar formulario de inicio de sesión con validación. | 3 | Marcelo Cuadros | Done |
| US29 | Inicio de sesión y registro de cuenta | T56 | Formulario de registro | Implementar formulario de registro de nueva cuenta con validación. | 3 | Marcelo Cuadros | Done |

#### 5.2.2.4. Development Evidence for Sprint Review.

![Tabla en Trello 1](../assets/images/deploy-steps/trello_1.png)

![Tabla en Trello 2](../assets/images/deploy-steps/trello_2.png)

[Sprint en Trello](https://trello.com/b/07LRT0At/sprint-2)

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|---|---|---|---|---|---|
| SupplyWok-FrontEnd | feature | 66c85df | feat: setup project architecture and shared modules | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | 6039b3b | feat: configure application routing | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | 4cd7752 | feat: add purchase order domain entities | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | fab4097 | feat: implement purchase order api integration | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | d6f5221 | feat: add purchase order store management | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | bb8db44 | feat: configure supply and purchasing routes | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | 546855e | feat: create purchase order reusable components | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | 4e2fcff | feat: implement supply and purchasing pages | - | 10/05/2026 |
| SupplyWok-FrontEnd | feature | f34ffae | refactor: reorganize shared layout and state management | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 21f4bff | feat: implement supply and purchasing bounded context | - | 11/05/2026 |
| SupplyWok-FrontEnd | develop | 2dc2096 | Merge pull request #5 from Aurora-AplicacionesWeb/develop | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 752abc5 | feat(iot-monitoring): add IoT monitoring components and alerts, update environment variables | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 0e1b7e3 | feat(entities): add initial entities for restaurant management bounded context | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 9e705a8 | feat(restaurant-management/infrastructure): implement assemblers for restaurant management entities. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 9f17ee0 | feat(restaurant-management): implement base API and endpoint classes for restaurant management. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 2e948ec | feat(restaurant-management/application): add Pinia store for managing restaurant operations. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 9f72302 | feat(restaurant-management/locales): update translations for restaurant management pages in English, Spanish, and Chinese. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 7375fba | feat(restaurant-management/presentation): add components for dish menu, kitchen tickets, and tables occupancy management. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 45892cb | feat(shared/presentation): implement layout components and add language switcher component. | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 4c4bf96 | feat: rename restaurant-management.json to db.json and update table structure and routing | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 6ca5639 | chore: add new SVG icons for alerts, configuration, dashboard, inventory, kitchen tickets, orders, reports, subscription, and suppliers | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | 0fa27a0 | feat: add environment configuration for development and production with API endpoints | - | 11/05/2026 |
| SupplyWok-FrontEnd | feature | efe9e7f | feat: initialize supplier management module with the sidebar for suppliers and update translations | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 22a5d5f | fix: correct syntax and an typing error in zh.json | - | 12/05/2026 |
| SupplyWok-FrontEnd | develop | 92f7703 | Merge branch 'feature/restaurant-management-bc' into develop | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | c22a4df | fix: fix some errors in sidebar-menu | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 5e4e350 | refactor: update method names for consistency and improve layout styling | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 3915b4f | feat: integrate pinia store and vue router, initialize router with supplier routes | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 3bafae0 | fix: correct API URL typo, and adjust app title | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | a5a54a5 | Merge branch 'develop' into feature/operational-monitoring-and-iot-alerts-bc | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | a295c25 | feat(operational-monitoring-and-iot-alerts-bc): add iot and alerts bc to the main branch for develop. | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 064a209 | chore: update package-lock.json to reflect dependency version changes | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | d91f6b3 | feat: add orders entities and assembler for transforming purchase orders resources | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 74a02aa | feat(iot-monitoring): change IoT monitoring components and alerts, update environment variables. | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | e201320 | fix: update OrdersAssembler to use correct Orders entity | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | a7257bd | feat: add supply management api and initialize json server setup | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 7bd9292 | feat(supply-and-purchasing): add mock backend with db.json | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | bcf87fa | feat: add supplier management store with state, getters, and fetch logic | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 739b84d | feat(supply-and-purchasing): add orders summary card | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 78e1edd | Merge remote-tracking branch 'origin/develop' into feature/supply-and-purchasing-bc | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | c0b77d3 | feat: add mock api fallback and dashboard enhancements | - | 12/05/2026 |
| SupplyWok-FrontEnd | feature | 0694d59 | feat(supply-and-purchasing): enhance dashboard integration and mock api support | - | 12/05/2026 |
| SupplyWok-FrontEnd | develop | 1232115 | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd into develop | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | c77d755 | feat: implement inventory item and stock movement entities | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 405c216 | feat: implement inventory management API with mock data fallback | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | ee58105 | feat: implement inventory management API with mock data fallback | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 274c281 | feat: add inventory management page and data table component | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 87c6730 | feat: add internationalization support for inventory management | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 2dc4f94 | feat: add delete confirmation dialog and functionality to inventory management | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | b2cb7d1 | feat: add inventory API configuration and update stock percentage calculation | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 8ec5d44 | feat: integrate confirmation dialog into inventory data table component | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 40c3912 | feat: refactor inventory and stock movement entities to use public properties | - | 13/05/2026 |
| SupplyWok-FrontEnd | develop | d663118 | Merge remote-tracking branch 'origin/develop' into develop | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 90b902b | feat(iam): add user validation and notifies in header. | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 6f68afb | feat(alerts): enhance alert management with status and source properties, add acknowledgment functionality | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 30b0f7c | feat: finish supplier management store with CRUD methods and documentation | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 7e1145c | feat(supply-management): add catalog entity and assembler | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 3885462 | feat(supply-management): update store and api | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 547bcf2 | feat(supply-management): update db.json to include catalog items | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | ab5066d | feat(supply-management): add routing in sidebar menu for supplier and restaurant and switching roles | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | cf1fc68 | feat(supply-management): add catalog supplier components and functionality | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | f1569f9 | feat(supply-management): add supplier management orders view | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 0dc1f27 | . | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 5e25a4f | Merge remote-tracking branch 'origin/develop' into feature/supplier-management-and-operations-bc | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | e10ad29 | . | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 25d7752 | refactor: improve restaurant management bc and styling consistency across components | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 8965e0a | feat: add active commands and kitchen tickets cards to restaurant management dashboard | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | a71db21 | feat: enhance restaurant management dashboard with kitchen tickets and active commands functionality | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | d243b6b | feat: add pending orders card to dashboard with dynamic count | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | cc267ea | delete: App.vue | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 661ac88 | feat: add below minimum stock card component with internationalization support | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 21227b6 | feat: add Chinese localization for below minimum stock component | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | 71d72db | fix: update role routing | - | 13/05/2026 |
| SupplyWok-FrontEnd | feature | dbef84e | fix: update route routing and dashboard view | - | 13/05/2026 |
| SupplyWok-FrontEnd | develop | 1bec258 | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd into develop | - | 13/05/2026 |
| SupplyWok-FrontEnd | develop | f7e8c05 | feat(supply-management): add client view | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | ceebb76 | fix: remove unnecessary endpoint paths | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | b876bf0 | feat(supply-management): add alert endpoint and assembler and api | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 45d7066 | feat(supply-management): add endpoins for alerts and store for alerts | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 329deb7 | Merge branch 'feature/supplier-management-and-operations-bc' into develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | edfce1d | fix(restaurant-management): fix routing for create kitchen ticket | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 601aedb | fix: unify purchase orders data source | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 0e01c56 | feat: add inventory, configuration, reports page | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 7a31adf | Merge remote-tracking branch 'origin/develop' into feature/supply-and-purchasing-bc | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 7d2759f | fix: delete app.vue | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | aee254d | fix: repair routing and orders api fallbacks | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | f50f699 | feature: add views and fix routes errors | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 2fe0640 | feat(supply-management): add client entity and assembler and endpoint and store | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 7684ba8 | feat(supply-management): add supplier alerts view | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 553e723 | feat(supply-management): add demand forecast endpoint and assembler and entity | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | b5b11b1 | feat(supply-management): add data for demand forecast and install chart.js dependency | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | adb9344 | feat(supply-management): add demand forecast view and internationalization | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | c4ed789 | Merge remote-tracking branch 'origin/feature/supplier-management-and-operations-bc' into develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | a001a24 | fix: inventory management api and iam | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 6bb63fa | refactor: align inventory data flow | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | f944122 | feat(supply-management): add delivery route endpoint and assembler and entity and update store and data | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | aa2b8e2 | feat(supply-management): add delivery planning view | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | d97eace | refactor: adjust layout styling for IoT panel and placeholder page | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 35afb4a | feat: implement add table functionality in tables and occupancy page | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 6802e29 | fix: fix route for views | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | abbc374 | fix(supply-management): update delivery status filter | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 5aeeedf | fix(supply-management): add supplier settings and subscription endpoints and assemblers entity stores and data | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 84727b4 | fix(supply-management): add supplier settings and subscription views | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | d0ad0f5 | fix(supply-management): add dashboard components and view | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 83bbae1 | refactor: rename files to "-view" | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 0e8b291 | feat: add table deletion functionality and enhance table details view | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | bfd7a0a | Merge remote-tracking branch 'origin/feature/supplier-management-and-operations-bc' into develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 77f8271 | feat(i18n): implement internationalization for various components and routes | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | d228610 | refactor: update supplier API endpoints for supply management and purchase order | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | fe76c7f | feat(subscription): integrate subscription plan management and update UI components | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 245b495 | feat: update environment variables and enhance restaurant management api with new endpoints | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 736f77a | feat(alerts): enhance alert display logic and add supplier notification messages | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | e2fe602 | Merge remote-tracking branch 'origin/develop' into develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 1fb79dc | fix(supplier-api.js): connect suppliers page to mock api | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 1f0a08e | Merge branch from develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 0541dca | fix(supplier-api.js): connect suppliers page to mock api | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | e5af4fe | Merge pull request #14 from Aurora-AplicacionesWeb/develop | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | 66c71ce | Dejar de rastrear archivos de entorno (manteniendo copias locales) | - | 14/05/2026 |
| SupplyWok-FrontEnd | develop | ea24093 | chore(app): complete bounded-context architecture migration, routing normalization, and i18n fixes | - | 14/05/2026 |


#### 5.2.2.5. Execution Evidence for Sprint Review.

En este Sprint se logró desarrollar gran parte del frontend de la plataforma SupplyWok. Se integraron funcionalidades como el inicio de sesión, el dashboard general, los módulos de inventario, pedidos, comandas, sensores y alertas, junto con sus funcionalidades básicas principales.

Link de la plataforma de SupplyWok: https://supplywok.web.app/

![first](../assets/images/execution-evidence/ec-login.png)

![first](../assets/images/execution-evidence/ec-dashboard.png)

![first](../assets/images/execution-evidence/ec-inventory.png)

![first](../assets/images/execution-evidence/ec-orders.png)

![first](../assets/images/execution-evidence/ec-kitchen-tickets.png)

![first](../assets/images/execution-evidence/ec-create-kitchen-tickets.png)

![first](../assets/images/execution-evidence/ec-suppliers.png)

![first](../assets/images/execution-evidence/ec-tables-and-occupancy.png)

![first](../assets/images/execution-evidence/ec-add-table.png)

![first](../assets/images/execution-evidence/ec-alerts.png)

![first](../assets/images/execution-evidence/ec-reports.png)

![first](../assets/images/execution-evidence/ec-configuration.png)

![first](../assets/images/execution-evidence/ec-subscription.png)

![first](../assets/images/execution-evidence/ec-suppliers-dashboard.png)

![first](../assets/images/execution-evidence/ec-supplier-orders.png)

![first](../assets/images/execution-evidence/ec-supplier-my-clients.png)

![first](../assets/images/execution-evidence/ec-delivery-planning.png)

![first](../assets/images/execution-evidence/ec-demand-forecast.png)

![first](../assets/images/execution-evidence/ec-product-catalog.png)

![first](../assets/images/execution-evidence/ec-new-product-catalog.png)

![first](../assets/images/execution-evidence/ec-supplier-alerts.png)

![first](../assets/images/execution-evidence/ec-supplier-configuration.png)

![first](../assets/images/execution-evidence/ec-supplier-subscription.png)

#### 5.2.2.6. Services Documentation Evidence for Sprint Review.

Para esta sección se dirán los servicios que se utilizaron para simular los json que devolvería nuestro backend, los cuales se implementaron en dos servicios, en mockapi y en my json server.

![](../assets/images/mockapi-evidence.png)

![Mathias](../assets/images/mathias-myjson.png)

![Mathias](../assets/images/mathias-myjson2.png)

Estos implementaron endpoints para manejar los datos y mostrarlos en nuestros componentes que permiten utilizar nuestro sistema sin necesidad de tener un backend por el momento.

#### 5.2.2.7. Software Deployment Evidence for Sprint Review.

En esta sección mostramos como se realizó el deploy de la plataforma junto con el json server.

**Deploy del Json Server**

1. Accedemos a https://my-json-server.typicode.com/ y seguimos los pasos para publicar el Json Server

![](../assets/images/deploy-steps/deploy_db.png)

2. Creamos un nuevo repositorio y subimos el archivo Json.

![](../assets/images/deploy-steps/deploy_db_1.png)

3. Accedemos al enlace de nuestro Json server de forma  https://my-json-server.typicode.com/< your-username >/< your-repo >. 

![](../assets/images/deploy-steps/myjsonserver-evidence.png)

**Deploy de la Plataforma en Firebase**

1. Accedemos a https://firebase.google.com/ y accedemos con nuestra cuenta. Después creamos nuestro proyecto.

![](../assets/images/deploy-steps/deploy_firebase.png)

2. Luego de instalar e iniciar sesión en firebase la terminal de Jetbrains para construir, inicializar y deployar nuestro proyecto, para posteriormente acceder al enlace publico.

![](../assets/images/deploy-steps/deploy_firebase_1.png)

![](../assets/images/deploy-steps/deploy_firebase_2.png)

![](../assets/images/deploy-steps/deploy_firebase_3.png)

![](../assets/images/deploy-steps/deploy_firebase_4.png)

![](../assets/images/deploy-steps/deploy_firebase_build.png)

Estos implementarion endpoints para majenar los datos y mostrarlos en nuestros componentes que permiten utilizar nuestro sistema sin necesidad de tener un backend por el momento.
[https://supplywok.web.app/](https://supplywok.web.app/)

#### 5.2.2.8. Team Collaboration Insights during Sprint.

En este apartado se visualiza todos los gráficos que representan la participación de cada integrante en el repositorio del fronted.

![Team Collaboration](../assets/images/deploy-steps/participation_2.png)

![Team Contribution 1](../assets/images/deploy-steps/contributions_1_2.png)

![Team Contribution 2](../assets/images/deploy-steps/contributions_2_2.png)

### 5.2.3. Sprint 3

En esta sección se registra y explica el avance realizado durante el Sprint 3 en términos de producto y trabajo colaborativo. El enfoque principal de este Sprint es el desarrollo e implementación de los servicios backend mediante C# y Entity Framework Core para los bounded context priorizados, así como la validación y correcto funcionamiento de sus endpoints REST.

#### 5.2.3.1. Sprint Planning 3

Durante la reunión de Sprint Planning del Sprint 3, se estableció como objetivo principal avanzar significativamente en el desarrollo backend de la plataforma SupplyWok, planteando alcanzar aproximadamente el 70% de implementación de los servicios backend del sistema. Para ello, se priorizó el desarrollo de los bounded contexts correspondientes al núcleo del negocio, incluyendo  . Asimismo, el equipo revisó los resultados obtenidos durante el sprint anterior e identificó oportunidades de mejora con el fin de corregir errores, optimizar el proceso de desarrollo y garantizar una base sólida para las siguientes etapas del proyecto.

**Sprint Planning 3**

| **Sprint #**                       | 3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Date**                           | 2026-06-06                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Time**                           | 17:00                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Location**                       | Virtual, Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Prepared by**                    | Mathias Sanchez, Juan Wang                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Attendees**                      | Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Sprint 2 Review Summary**        | Durante el Sprint 3 se completó el desarrollo de la aplicación frontend utilizando una Fake API para simular la comunicación con los servicios backend. Se implementaron las principales interfaces y flujos de usuario previstos para la plataforma, obteniendo resultados satisfactorios en términos de funcionalidad, organización del código y experiencia de usuario. Como parte del feedback recibido, se destacó la calidad de la implementación realizada; sin embargo, se recomendó fortalecer la documentación técnica del proyecto para facilitar su comprensión, mantenimiento y futura integración con los servicios backend reales. |
| **Sprint 2 Retrospective Summary** | El equipo consideró que la distribución de tareas y la colaboración durante el Sprint 2 fueron adecuadas, permitiendo cumplir los objetivos establecidos dentro del plazo previsto. Asimismo, se identificó como principal oportunidad de mejora la elaboración de una documentación más completa y detallada, tanto del proceso de desarrollo como de los componentes implementados, con el fin de mejorar la comunicación interna y facilitar el trabajo en las siguientes iteraciones.                                                                                                                                                         |
| **Sprint 3 Goal**                  | Habilitar la comunicación centralizada de datos en la plataforma SupplyWok mediante la implementación del Web Service principal, garantizando que los sistemas externos puedan consultar a los bounded context Inventory Management, Procurement & Purchasing, Operations, IoT Operational Monitoring & Alerts, Supplier Panel, Identity And Access Management, Profiles y Analytics de manera segura y eficiente al cierre del sprint.                                                                                                                                                                                                           |
| **Sprint 3 Velocity**              | Límite de **35 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Sum of Story Points**            | **35 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

#### 5.2.3.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración correspondiente al Sprint 3. Dado que el objetivo principal de esta iteración es avanzar en el desarrollo backend de SupplyWok, los aspectos considerados corresponden a los bounded contexts de negocio. Para cada aspecto se asigna un líder responsable de coordinar el desarrollo y uno o más colaboradores encargados de apoyar en la implementación, validación y pruebas de los servicios y endpoints asociados.

**Link del Sprint 3 Board:** [Trello](https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3)

**Consider Aspects**

- **Inventory Management Bounded Context**: Es el encargado de gestionar la información de los recursos de inventario del restaurante. 
- **Procurement & Purchasing Bounded Context**: Es el encargado de gestionar las órdenes de productos realizadas por el restaurante. 
- **Operations Bounded Context**: Es el encargado de gestionar las comandas, tickets de cocina y mesas dentro del restaurante. 
- **IoT Operational Monitoring & Alerts Bounded Context**: Es el encargado de monitorear y alertar sobre los dispositivos IoT del restaurante.
- **Supplier Panel Bounded Context**: Es el encargado de gestionar los datos de los proveedores y sus clientes. 
- **Identity And Access Management Bounded Context**: Es el encargado de gestionar todo lo relacionado con la autenticación y administración de cuentas.
- **Profiles Bounded Context**: Es el encargado de gestionar los perfiles de los usuarios del sistema.
- **Analytics Bounded Context**: Es el encargado de gestionar los diferentes gráficos que se pueden visualizar en la plataforma.
- **Shared Bounded Context**: Es el encargado de gestionar los datos compartidos que son reutilizados entre los diferentes bounded contexts del sistema.

| Team Member| Github Username | Inventory Management Bounded Context | Procurement & Purchasing Bounded Context | Operations Bounded Context | IoT Operational Monitoring & Alerts Bounded Context | Supplier Panel Bounded Context | Identity And Access Management Bounded Context | Profiles Bounded Context | Analytics Bounded Context |
|-----------|-----------------|--------------------------------------|------------------------------------------|----------------------------|-----------------------------------------------------|--------------------------------|------------------------------------------------|--------------------------|---------------------------|
| Cuadros, Macelo| Marcelo-alt-lab | -                                    | -                                        | -                          | L                                                   | C                              | L                                              | C                        | L                         | 
| Ayasta, Zayd | Zayd Ayasta     | -                                    | L                                        | -                          | -                                                   | C                              | -                                              | -                        | C                         |
| Wang, Juan | jwd3t           | -                                    | C                                        | -                          | -                                                   | L                              | -                                              | C                        | -                         | 
| Sánchez, Mathias | Nounz27         | L                                    | -                                        | L                          | -                                                   | -                              | -                                              | -                        | -                         |
| Cayanchi, Milenko | MaxghZZ         | -                                    | -                                        | -                          | -                                                   | C                              | -                                              | L                        | -                         |

#### 5.2.3.3. Sprint Backlog 3

En esta sección se presenta el Sprint Backlog correspondiente al Sprint 3. Los elementos incluidos fueron seleccionados en función del Sprint Goal establecido para esta iteración, el cual busca habilitar la comunicación centralizada de datos en la plataforma SupplyWok mediante la implementación del Web Service principal, garantizando que los sistemas externos puedan consultar inventario, pedidos, usuarios, reportes, monitoreo operativo, órdenes de cocina de SupplyWok mediante servicios backend funcionales. Para elo, se definieron las historias de usuario y tareas necesarias para implementar, validar y documentar los endpoints REST de los bounded contexts priorizados, asegurando su correcto funcionamiento antes de la integración con los componentes frontend de la plataforma.

**Link del Sprint 3 Board:** [Trello](https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3)

**Sprint 3 Backlog**

| US Id | US Title                                                   | Task Id | Task Title                                | Description                                                                                                      | Estimation (Hours) | Assigned To     | Status |
| ----- | ---------------------------------------------------------- | ------- | ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------ | --------------- | ------ |
| US34  | Obtener los datos del inventario vía API                   | T-01    | Implement Inventory GET Endpoint          | Desarrollar endpoint GET para consultar inventario de un restaurante y exponer la información mediante API REST. | 8                  | Alexandra Meza  | Done   |
| US01  | Registro de inventario inicial                             | T-02    | Implement Inventory Registration Services | Implementar entidades, repositorios y servicios para registrar insumos en inventario.                            | 6                  | Alexandra Meza  | Done   |
| US09  | Creación de orden de compra                                | T-03    | Implement Purchase Order Endpoint         | Desarrollar endpoint POST para registrar órdenes de compra.                                                      | 6                  | Zayd Ayasta     | Done   |
| US37  | Crear una orden de insumos vía API                         | T-04    | Implement Purchasing API Services         | Implementar servicios de aplicación, validaciones y persistencia para órdenes de compra.                         | 6                  | Zayd Ayasta     | Done   |
| US38  | Obtener datos relevantes de proveedores vía API            | T-05    | Implement Supplier Query Endpoints        | Desarrollar endpoints para consulta de proveedores y catálogos asociados.                                        | 6                  | Juan Wang       | Done   |
| US12  | Gestión de proveedores vinculados                          | T-06    | Implement Supplier Management Services    | Implementar entidades y lógica de negocio para gestión de proveedores.                                           | 5                  | Juan Wang       | Done   |
| US42  | Endpoint para recibir información de componentes IoT       | T-07    | Implement IoT Data Reception Endpoint     | Implementar endpoint para recepción de información proveniente de sensores IoT.                                  | 8                  | Marcelo Cuadros | Done   |
| US18  | Historial de alertas e incidencias operativas              | T-08    | Implement Alerts Management Services      | Implementar servicios y endpoints para consulta de alertas operativas registradas.                               | 6                  | Marcelo Cuadros | Done   |
| US26  | Registro e inicio de sesión para usuarios de la plataforma | T-09    | Implement Identity and Access Services    | Implementar servicios base de autenticación y gestión de usuarios.                                               | 5                  | Marcelo Cuadros | Done   |
| US17  | Control de ocupación de mesas                              | T-10    | Implement Restaurant Management Endpoints | Implementar endpoints relacionados con la gestión operativa del restaurante.                                     | 5                  | Joan Payano     | Done   |
| US36  | Manejo estándar de errores                                 | T-11    | Configure Global Exception Handling       | Implementar manejo centralizado de excepciones y respuestas HTTP estandarizadas.                                 | 4                  | Zayd Ayasta     | Done   |
| US39  | Evitar almacenamientos en errores                          | T-12    | Configure Transaction Management          | Configurar validaciones y transacciones para evitar persistencia de datos inválidos.                             | 3                  | Zayd Ayasta     | Done   |

#### 5.2.3.4. Development Evidence for Sprint Review

En esta sección se presentan los avances realizados durante el Sprint 3 en la implementación de los componentes backend de SupplyWok. El trabajo desarrollado se centró en la construcción de los bounded contexts priorizados del núcleo del negocio, incluyendo la implementación de entidades de dominio, repositorios, servicios de aplicación y endpoints REST mediante C# y Entity Framework Core.

| Repository                       | Branch                        | Commit Id | Commit Message                                                                          | Commit Message Body                                                                             | Commited on (Date) |
| -------------------------------- | ----------------------------- | --------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------ |
| Aurora-startup/SupplyWok-backend | feature/shared                | 9e50ab7   | feat(shared): implement shared layer                                                    | Implementación de la capa compartida utilizada por los diferentes bounded contexts del sistema. | 2026-06-10         |
| Aurora-startup/SupplyWok-backend | develop                       | 32c9e97   | chore: configure application properties and add dependencies for PostgreSQL and OpenAPI | Configuración inicial del proyecto, dependencias de PostgreSQL y documentación OpenAPI.         | 2026-06-10         |
| Aurora-startup/SupplyWok-backend | feature/iot                   | d9c9842   | feat(iot): implement iot layer with sensor aggregate                                    | Implementación del bounded context de monitoreo IoT y agregado Sensor.                          | 2026-06-10         |
| Aurora-startup/SupplyWok-backend | feature/restaurant-management | 8b85738   | feat(restaurant-management): implement restaurant management bounded context            | Desarrollo del bounded context Restaurant Management.                                           | 2026-06-11         |
| Aurora-startup/SupplyWok-backend | feature/inventory-management  | 27c933e   | Add value objects for inventory management bounded context                              | Implementación de value objects para Inventory Management.                                      | 2026-06-12         |
| Aurora-startup/SupplyWok-backend | feature/inventory-management  | dcfa1ef   | Add aggregates and entities                                                             | Incorporación de agregados y entidades del dominio para Inventory Management.                   | 2026-06-12         |
| Aurora-startup/SupplyWok-backend | feature/inventory-management  | 4f8aef7   | Finish domain package of inventory management bounded context                           | Finalización de la estructura del dominio para Inventory Management.                            | 2026-06-13         |
| Aurora-startup/SupplyWok-backend | feature/suppliers             | 48967ca   | feat(suppliers): add clients endpoint                                                   | Implementación del endpoint para consulta de clientes asociados a proveedores.                  | 2026-06-17         |
| Aurora-startup/SupplyWok-backend | feature/suppliers             | 30598b0   | feat(suppliers): add catalog endpoint by supplier id                                    | Implementación del endpoint para consulta de catálogo por proveedor.                            | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/purchasing            | e25f995   | feat: add purchase order management endpoints and domain                                | Desarrollo del dominio y endpoints para la gestión de órdenes de compra.                        | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/purchasing            | 00bef77   | feat: align inventory persistence and activity endpoints                                | Ajuste de persistencia y endpoints relacionados con actividades de inventario.                  | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/purchasing            | 4a31215   | feat: add supplier identity acl contract                                                | Implementación del contrato ACL para integración con el contexto de proveedores.                | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/alerts                | 427701d   | feat(alerts): add alerts aggregate and controllers                                      | Implementación de agregados y controladores para el módulo de alertas operativas.               | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/alerts                | 7e87e5    | refactor(alerts): replace external services with IoT and inventory context facades      | Refactorización para integrar el módulo de alertas con los contextos IoT e Inventory.           | 2026-06-18         |
| Aurora-startup/SupplyWok-backend | feature/restaurant-management | c4ba83c   | fix: add CrossOrigin and clean imports in restaurant management controllers             | Corrección de configuración CORS y limpieza de imports en los controladores.                    | 2026-06-18         |
| | | | | | | 


#### 5.2.3.5. Execution Evidence for Sprint Review

Durante el Sprint 3 se completó la implementación y validación de los principales servicios backend de SupplyWok correspondientes a los bounded contexts priorizados del núcleo del negocio. Como parte de la revisión del sprint, se verificó el correcto funcionamiento de los endpoints REST desarrollados mediante pruebas realizadas en Swagger, comprobando la ejecución satisfactoria de las operaciones expuestas por la API. Además, se validó la persistencia de la información en la base de datos MySql mediante MySql Workbench.

![Trello Sprint 3 Board]()
![Trello Sprint 3 Board]()
![Trello Sprint 3 Board]()

**Link del vídeo de explicación del Sprint** [Vídeo del Sprint](https://youtu.be/olHC8_y3YLo)

#### 5.2.3.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 3 se documentaron los servicios web desarrollados para los bounded contexts priorizados de SupplyWok utilizando Swagger. La documentación generada permite visualizar y comprender la estructura de los endpoints implementados, incluyendo los métodos HTTP soportados, parámetros de entrada, cuerpos de solicitud, respuestas esperadas y códigos de estado asociados. A continuación, se presenta el detalle de los endpoints documentados, los enlaces correspondientes a la documentación generada y evidencias de interacción utilizando datos de prueba.

**Repository URL:** https://github.com/Aurora-AplicacionesWeb/supply-wok-platform
**Swagger URL:** https://supply-wok-platform-cgbs.onrender.com/swagger/index.html

| Endpoint | Action | HTTP Verb | Parameters | Response Example | Documentation URL |
|----------|--------|------------|------------|-------------------|------------------|


#### 5.2.3.7. Software Deployment Evidence for Sprint Review

En esta sección se muestra los deploy de los componentes backend de SupplyWok implementados en la plataforma Aurora-AplicacionesWeb en la plataforma Render.

**Backend Deployment URL:** [Backend Deployment](https://supply-wok-platform-cgbs.onrender.com/swagger/index.html)

#### 5.2.3.8. Team Collaboration Insights during Sprint

Durante el Sprint 3, el equipo trabajó de manera colaborativa en el desarrollo de los servicios backend de SupplyWok utilizando una estrategia basada en ramas de Git y GitHub. Las tareas fueron distribuidas entre los integrantes de acuerdo con los bounded contexts priorizados, permitiendo que cada miembro asumiera la responsabilidad principal de un área específica del negocio. En este sprint, todos los integrantes contribuyeron activamente mediante commits, revisiones e integración de cambios en el repositorio del proyecto. A continuación, se presentan evidencias de colaboración obtenidas a partir de los analíticos de GitHub, incluyendo contribuciones, historial de commits y actividad realizada durante el sprint.

![Sprint 3 Insight Graphic 1](../assets/images/deploy-steps/contributions_22.png) 

Como se observa en la sección Contributors del repositorio backend, durante el Sprint 3 se realizaron un total de 169 commits, reflejando una participación activa por parte de los miembros del equipo en el desarrollo de los servicios y endpoints de la plataforma.

![Sprint 3 Insight Graphic 2](../assets/images/deploy-steps/contributions_23.png)

Como se observa en el detalle de la sección Contributors, todos los integrantes realizaron contribuciones al repositorio. En promedio, cada miembro efectuó aproximadamente 20 commits y contribuyó con alrededor de 28040 líneas de código agregadas, evidenciando una distribución equilibrada del trabajo durante el sprint.

![Sprint 3 Insight Graphic 3](../assets/images/deploy-steps/pulse_11.png)

Como se observa en la sección Pulse del repositorio backend, durante la última semana se integraron 4 Pull Requests y se registraron 60 commits excluyendo merges. Asimismo, la rama principal del proyecto acumuló 10195 líneas agregadas y 1641 líneas eliminadas, reflejando el avance significativo realizado en la implementación de los bounded contexts y servicios backend planificados para este sprint.

## 5.3. Validation Interviews.

En esta sección se presentan las actividades de validación realizadas con usuarios pertenecientes a los segmentos objetivos de SupplyWok. El objetivo de estas entrevistas fue recopilar retroalimentación sobre la propuesta de valor, la experiencia de navegación en la Landing Page y el uso de las funcionalidades implementadas en la plataforma. Los resultados obtenidos permitieron identificar fortalezas, oportunidades de mejora y validar los principales supuestos planteados durante el desarrollo del proyecto.

### 5.3.1. Diseño de Entrevistas.
En esta sección se presenta el diseño de las sesiones de validación realizadas sobre la Landing Page y la Web Application de SupplyWok. A diferencia de las entrevistas de descubrimiento desarrolladas durante el needfinding, estas sesiones tuvieron como objetivo evaluar el comportamiento de usuarios representativos al interactuar con la propuesta de valor del producto y con los principales flujos de la solución digital implementada.

Las sesiones de validación se diseñaron para observar si los participantes comprendían el propósito del producto, si podían navegar por las vistas principales sin asistencia excesiva y si lograban completar tareas representativas del core business. Asimismo, se buscó recopilar comentarios espontáneos de los participantes sobre claridad, utilidad, confianza, facilidad de uso y valor percibido de la solución.

Para ello, se trabajó con usuarios correspondientes a los dos segmentos objetivos del proyecto: dueños o administradores de restaurantes chifa y proveedores de insumos para restaurantes. Cada sesión fue moderada por un integrante del equipo y registrada en video como evidencia de validación.

**Objetivo general de validación**

- Verificar si los usuarios comprenden la propuesta de valor de SupplyWok al interactuar con la Landing Page.
- Evaluar si los usuarios pueden navegar por la Web Application y completar tareas clave sin fricción significativa.
- Identificar problemas de usabilidad, arquitectura de información y diseño inclusivo en los flujos implementados.
- Recoger observaciones cualitativas que permitan priorizar mejoras para las siguientes iteraciones del producto.

**Segmentos validados**

- **Segmento 1:** Dueños o administradores de restaurantes chifa.
- **Segmento 2:** Proveedores de insumos para restaurantes.

**Escenarios y tareas de validación**

Las sesiones se estructuraron alrededor de tareas concretas, alineadas con los flujos principales del producto.

**Para el segmento de restaurantes**

- Identificar, a partir de la Landing Page, cuál es la propuesta de valor principal de SupplyWok.
- Navegar desde la Landing Page hacia la aplicación.
- Iniciar sesión y reconocer el propósito general del dashboard.
- Ubicar módulos clave como inventario, pedidos, alertas o mesas.
- Interpretar la información presentada en una vista principal del sistema.

**Para el segmento de proveedores**

- Identificar, a partir de la Landing Page, cómo SupplyWok puede aportar valor al proveedor.
- Navegar desde la Landing Page hacia la aplicación.
- Iniciar sesión en la vista de proveedor.
- Ubicar funcionalidades principales como clientes, catálogo, órdenes o demanda proyectada.
- Interpretar la información mostrada en una vista principal del panel del proveedor.

**Preguntas de validación posteriores a la demostración**

Después de mostrar la Landing Page y los principales flujos de la Web Application, el moderador realizó preguntas orientadas a recoger la percepción del participante sobre la utilidad, claridad y aplicabilidad real de la solución.

- Después de ver la aplicación, ¿te parece útil para tu trabajo o negocio?
- ¿Qué parte de la aplicación te gustó más?
- ¿Hubo algo que no entendiste o que te confundió?
- ¿Usarías una aplicación como esta en la vida real? ¿Por qué?
- ¿Qué cambiarías o mejorarías?

### 5.3.2. Registro de Entrevistas.
En esta sección se presenta el registro de las sesiones de validación realizadas con representantes de los segmentos objetivo. Cada sesión permitió observar cómo los usuarios interactuaron con el Landing Page y con la Web Application, así como registrar comentarios, dudas y observaciones generadas durante la navegación.

Las entrevistas de validación fueron registradas en video y consolidadas en un único material de evidencia, siguiendo las indicaciones del project statement. En cada caso se documenta la información del participante, el segmento representado, la fecha de la sesión y un resumen de los principales hallazgos obtenidos.

**Video consolidado de validación**
- **Enlace en Microsoft Stream:** [Vídeo de Validación](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6)
- **Captura de evidencia:**  
  ![captura](../assets/images/valincap.png)

### Segmento Objetivo Restaurantes

#### Entrevista de validación #1
![alt text](../assets/images/validation/entrevista1.png)

**Resumen de la sesión:**

El primer entrevistado Weiquan Wang, un dueño de restaurante de 55 años ubicado en el Callao, logró comprender la idea general de la landing page y también el flujo principal de la aplicación, especialmente las pantallas de inventario, pedidos, comandas, mesas y alertas. Su percepción general fue positiva, ya que consideró que el sistema era fácil de usar y que podría manejarlo sin demasiada dificultad; sin embargo, aportó una observación importante sobre el módulo de pedidos, indicando que sería más práctico no agregar productos uno por uno, sino contar con una forma más rápida de seleccionar varios insumos en una sola acción.

| Detalle | Información |
|---|---|
| **Entrevistador** | Juan Sung Jau Wang Chen |
| **Entrevistado** | Weiquan Wang |
| **Segmento objetivo** | Restaurante  |
| **Edad** | 55 |
| **Ubicación** | La Perla, Callao |
| **Duración / Empieza en** | [14:18 minutos] / [0:00] |
| **Enlace** | [Ver entrevista](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 1*




#### Entrevista de validación #2
![alt text](../assets/images/validation/entrevista2.png)

**Resumen de la sesión:**

La segunda entrevistada Ana Chen, una dueña de restaurante de 50 años de Callao, entendió de forma clara las funciones principales de la aplicación, sobre todo el inventario, la creación de órdenes a proveedores, los tickets de cocina, la gestión de mesas y las alertas. Comentó que el sistema le parecía sencillo y fácil de seguir, sin encontrar grandes dificultades en su uso; no obstante, brindó una sugerencia bastante valiosa al señalar que, en la sección de pedidos, sería más útil manejar horarios de entrega además de la prioridad, ya que en la práctica casi todos los pedidos se consideran importantes y lo realmente decisivo suele ser el momento en que deben recibirse.

| Detalle | Información |
|---|---|
| **Entrevistador** | Juan Sung Jau Wang Chen |
| **Entrevistado** | Ana Chen |
| **Segmento objetivo** | Restaurante |
| **Edad** | 50 |
| **Ubicación** | La Perla, Callao |
| **Duración / Empieza en** | [12 minutos] / [14:20] |
| **Enlace** | [Ver entrevista](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 2*

#### Entrevista de validación #3

![alt text](../assets/images/validation/entrevista3.png)

**Resumen de la sesión:**

La tercera entrevistada, Lili, de 54 años y dueña de un restaurante chifa en La Perla, mostró una validación claramente favorable tanto de la landing page como de la aplicación. Después de revisar las pantallas principales, afirmó que la plataforma le parecía útil para su trabajo diario, que el flujo era entendible y que no percibía confusión importante en el uso de las funciones. Entre todos los módulos presentados, destacó especialmente el de alertas como la parte que más le interesó, señalando además que sí utilizaría la aplicación en un contexto real y que, al menos en esta etapa, no veía cambios urgentes que realizar.

| Detalle | Información |
|---|---|
| **Entrevistador** | Juan Sung Jau Wang Chen |
| **Entrevistado** | Lily 蔡 |
| **Segmento objetivo** | Restaurante  |
| **Edad** | 54 |
| **Ubicación** | La Perla, Callao |
| **Duración / Empieza en** | [8 minutos] / [26:18] |
| **Enlace** | [Ver entrevista](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 3*


### Segmento Objetivo Proveedores

#### Entrevista de validación #4
![alt text](../assets/images/validation/entrevista4.png)

**Resumen de la sesión:**

El cuarto entrevistado, Alberto Copa Villa, de 37 años, trabajador de una carnicería en La Perla y representante del perfil proveedor, valoró de manera positiva la propuesta para este segundo segmento de usuarios, especialmente en las pantallas de órdenes, clientes, delivery planning, alertas, demanda y catálogo. Indicó que las funcionalidades que más le llamaron la atención fueron las alertas, el control del stock y la planificación de rutas, ya que las percibió como herramientas útiles para el trabajo real de un proveedor. Además, propuso dos mejoras importantes: reemplazar o complementar la prioridad de las órdenes con horarios de entrega más concretos, y añadir dentro de la misma aplicación una función de mensajería o chat tipo WhatsApp para comunicarse con los restaurantes sin depender de otros medios externos.

| Detalle | Información |
|---|---|
| **Entrevistador** | Juan Sung Jau Wang Chen |
| **Entrevistado** | Alberto Copa Villa |
| **Segmento objetivo** | Proveedor |
| **Edad** | 37 |
| **Ubicación** | La Perla, Callao |
| **Duración / Empieza en** | [8 minutos] / [34:00] |
| **Enlace** | [Ver entrevista](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 3*


### 5.3.3. Evaluaciones según heurísticas.
Como complemento a la observación de las sesiones de validación, el equipo realizó una evaluación de experiencia de usuario basada en heurísticas. Esta revisión tomó como referencia los criterios de usabilidad, diseño inclusivo y arquitectura de información indicados en el project statement del curso.

El objetivo de esta evaluación fue sistematizar los principales problemas detectados durante la interacción de los usuarios con el Landing Page y la Web Application, asignándoles un nivel de severidad y relacionándolos con la heurística o principio incumplido. De este modo, los hallazgos cualitativos obtenidos en las entrevistas de validación pudieron complementarse con una revisión experta centrada en identificar oportunidades concretas de mejora para la siguiente iteración del producto.

**Aplicación evaluada**

- **Site o app a evaluar:** SupplyWok
- **Auditor:** Aurora
- **Clientes participantes:** Usuarios de los segmentos restaurante y proveedor entrevistados durante la validación

**Tareas evaluadas**

- Comprender la propuesta de valor del Landing Page.
- Navegar hacia la Web Application desde los call to action.
- Reconocer el propósito del dashboard según el rol del usuario.
- Ubicar funcionalidades principales del sistema.
- Interpretar información clave en vistas como inventario, pedidos, clientes o catálogo.

**Escala de severidad utilizada**

| Nivel | Descripción |
|---|---|
| 1 | Problema superficial que no afecta significativamente la experiencia. |
| 2 | Problema menor que genera fricción, pero puede ser superado por el usuario. |
| 3 | Problema mayor que ocurre con frecuencia o dificulta seriamente completar la tarea. |
| 4 | Problema muy grave que impide continuar con el uso de la herramienta. |

**Tabla resumen de hallazgos**

| # | Problema | Escala de severidad | Heurística o principio violado |
|---|---|---|---|
| 1 | La aplicación no ofrece una guía inicial ni ayuda contextual para usuarios nuevos. | 3 | Ayuda y documentación |
| 2 | No existen diálogos de confirmación antes de ejecutar acciones destructivas como eliminar registros. | 4 | Prevención de errores |
| 3 | Se identificaron inconsistencias visuales entre pantallas, componentes y estilos del sistema. | 2 | Consistencia y estándares |

**Descripción de problemas**

**Problema #1: Ausencia de guía de uso o acompañamiento inicial**

- **Severidad:** 3
- **Heurística violada:** Ayuda y documentación
- **Problema:** Durante la evaluación se observó que la aplicación no brinda una orientación inicial para usuarios nuevos. No se encontraron mensajes introductorios, explicaciones contextuales ni elementos que indiquen con claridad cómo iniciar el uso de los módulos principales. Esto puede dificultar la adopción de la plataforma, especialmente para usuarios que ingresan por primera vez y aún no conocen la lógica del sistema ni el propósito de cada sección.
- **Recomendación:** Incorporar una breve guía de bienvenida, textos de apoyo o mensajes contextuales que orienten al usuario sobre el propósito de cada módulo y las acciones principales que puede realizar.

![heuristic-problem-1](../assets/images/[agregar-captura-problema-1].png)

**Problema #2: Falta de confirmación antes de eliminar información**

- **Severidad:** 4
- **Heurística violada:** Prevención de errores
- **Problema:** Se identificó que la aplicación no presenta un cuadro de confirmación antes de ejecutar acciones irreversibles como la eliminación de registros. Esta situación representa un riesgo importante, ya que el usuario puede borrar información por equivocación sin una oportunidad previa para cancelar la acción. La ausencia de esta validación reduce la sensación de control y puede ocasionar pérdida accidental de datos.
- **Recomendación:** Implementar diálogos de confirmación antes de eliminar elementos, con mensajes claros sobre la acción que se va a realizar y opciones visibles para confirmar o cancelar.

![heuristic-problem-2](../assets/images/[agregar-captura-problema-2].png)

**Problema #3: Inconsistencias visuales en el diseño de la interfaz**

- **Severidad:** 2
- **Heurística violada:** Consistencia y estándares
- **Problema:** Durante la revisión se detectaron diferencias visuales entre pantallas y componentes, como variaciones en estilos, jerarquías visuales, tamaños o distribución de elementos. Aunque estas diferencias no impiden por completo el uso del sistema, sí afectan la percepción de uniformidad y profesionalismo de la plataforma, y obligan al usuario a reinterpretar cada pantalla en lugar de reconocer patrones consistentes.
- **Recomendación:** Definir y aplicar criterios visuales uniformes para componentes, botones, tablas, encabezados, colores, espaciados y estilos tipográficos en todas las vistas del sistema.

![heuristic-problem-3](../assets/images/[agregar-captura-problema-3].png)

**Conclusión de la evaluación heurística**

La evaluación heurística permitió identificar problemas relevantes que complementan los hallazgos obtenidos en las entrevistas de validación. En particular, se evidenció la necesidad de mejorar el acompañamiento al usuario, reforzar la prevención de errores en acciones sensibles y unificar la experiencia visual del sistema. Estos aspectos no siempre son mencionados de forma explícita por los entrevistados, pero sí impactan de manera significativa en la usabilidad general de la plataforma.

La incorporación de estas mejoras contribuirá a que SupplyWok ofrezca una experiencia más clara, confiable y consistente, alineada con los principios de diseño centrado en el usuario y con los criterios de calidad esperados para una aplicación web funcional.

## 5.4. Video About-the-Product.

![](../assets/images/abtproduct.png)

* Microsoft Stream: [URL del video](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQDqz9uEXx01RIo8CM6xXsP8AaC6OZqd2Gy9L5aeXz3yxoU?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=OCLJI9)
* YouTube: [Url del video en YouTube](https://youtu.be/AzOyy7Oak_w)


# Conclusiones
