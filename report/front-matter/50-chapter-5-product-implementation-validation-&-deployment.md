# Capítulo V: Product Implementation, Validation & Deployment.

## 5.1. Software Configuration Management. 
Para tener consistencia y seguimiento de el desarrollo de la plataforma, se ha definido una serie de herramientas y estrategias de desarrollo. El metodo cubre la configuracion del entorno de desarrollo, la gestion del codigo y el despliegue, alineado a las buenas prácticas de ingenieria de software y metodologias ágiles.
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
  [https://github.com/G4-Aplicaciones-Web/backend](https://github.com/G4-Aplicaciones-Web/backend)

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
  Vercel.

- **Método de despliegue:**  
  - Vue.js se compila con `npm run build` para generar los archivos estáticos de producción.  
  - La rama `main` sirve como fuente para el despliegue.  
  - Vercel detecta automáticamente los cambios en `main` y publica la nueva versión del frontend.  
  - El archivo de configuración de producción incluirá la URL pública del backend para permitir integración total.

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

| Atributo | Valor |
|---|---|
| **Sprint #** | 1 |
| **Date** | 20-04-2026 |
| **Time** | 15:00 |
| **Location** | Virtual, Discord |
| **Prepared by** | Zayd Ayasta, Juan Wang |
| **Attendees** | Marcelo Cuadros, Alexandra Meza, Joan Payano |
| **Sprint n-1 Retrospective Summary** | *Siendo el primer sprint, este campo no es aplicable.* |
| **Sprint 1 Goal** | Nuestro enfoque en este sprint es la Landing Page que informará de nuestra plataforma, por lo que la desarrollaremos e implementaremos para que sea accesible y responsiva. Con la información que brindamos sobre nuestro producto esperamos ganarnos la confianza de los que visiten la página y que empiecen a usar nuestro sistema. Se confirmará cuando esté en producción y se pueda usar el enlace de la página. |
| **Sprint n Velocity** | Límite de **35 SP** |
| **Sum of Story Points** | **30 SP** |

#### 5.2.1.2. Aspect Leaders and Collaborators.

| Team Member {Last Name, First Name} | GitHub username | Estructure HTML | Design UI & responsive | Scripts and UX | SEO and Accessibility | Content and Assets |
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

Se presentaran las capturas que muestran el despliegue de la Landing Page en GitHub Pages en el navegador, en este caso en el navegador de Microsoft Edge.

![first](../assets/images/deploy-steps/prove-1.png)

Aqui se puede diferenciar el funcionamiento de los distintos idiomas en los que se encuentra disponible la Landing Page, en este caso chino.

![second](../assets/images/deploy-steps/prove-2.png)

Aqui esta el enlace a la pagina desplegada: [SupplyWok landing page](https://aurora-aplicacionesweb.github.io/SupplyWok-Landing-Page/)

#### 5.2.1.5. Execution Evidence for Sprint Review.


#### 5.2.1.6. Services Documentation Evidence for Sprint Review.

Como la Landing Page es una página estática, no fue necesario durante el Sprint el uso de servicios externos ni conexiones a APIs, por lo cual no hay generación ni evidencia de documentación técnica relacionada.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review.

La evidencia del despliegue de la Landing Page durante el Sprint se mostrara a continuación, el despliegue se realizara en GitHub Pages.

![first-step](../assets/images/deploy-steps/step-1.png)

Revisamos que el repositorio este en publico:

![second-step](../assets/images/deploy-steps/step-2.png)

Nos dirigimos a la seccion de deploy, y selecionamos la rama main:

![third-step](../assets/images/deploy-steps/step-3.png)

Luego de unos minutos, el deploy se realizara correctamente:

![fourth-step](../assets/images/deploy-steps/step-4.png)

#### 5.2.1.8. Team Collaboration Insights during Sprint.

Se anexa evidencia de la participación del equipo en el desarrollo de la Landing Page segun el report de commits que da el repositorio de GitHub.

![Team Collaboration](../assets/images/deploy-steps/participation.png)