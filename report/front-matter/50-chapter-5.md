# Capítulo V: Product Implementation, Validation & Deployment.

## 5.1. Software Configuration Management. 
Para tener consistencia y seguimiento del desarrollo de la plataforma, se ha definido una serie de herramientas y estrategias de desarrollo. El método cubre la configuración del entorno de desarrollo, la gestion del código y el despliegue, alineado a las buenas prácticas de ingeniería de software y metodologías ágiles.
### 5.1.1. Software Development Environment Configuration. 
Para facilitar la colaboración del equipo en todas las actividades del ciclo de vida de desarrollo de SupplyWok, se ha definido un entorno de desarrollo común. Este entorno está compuesto por herramientas especializadas para la gestión del proyecto, diseño UX/UI, modelado, desarrollo, pruebas, documentación y despliegue. La selección de estas herramientas se basa en criterios de eficiencia, compatibilidad con tecnologías open-source (Vue + C#), y alineación con prácticas recomendadas de la industria.

|        Categoría        |           Herramienta           |                                               Propósito                                               |                                                                     Tipo de acceso/enlace                                                                      |
|:-----------------------:|:-------------------------------:|:-----------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|   Project Management    |              Jira               |           Gestión del backlog, tareas y sprints del equipo usando metodología ágil (Scrum).           |                                       [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira)                                       |
| Requirements Management |            UXPressia            |                 Creación de User Personas, Journey Maps y artefactos de needfinding.                  |                                                         [https://uxpressia.com](https://uxpressia.com)                                                         |
|  Product UX/UI Design   |              Figma              |               Diseño de wireframes, mockups y prototipos de la aplicación web y móvil.                |                                                             [https://figma.com](https://figma.com)                                                             |
|  Modelado de Software   | LucidChart / Miro / Structurizr |                 Modelado de arquitectura (UML, C4, Event Storming, Bounded Contexts).                 | [https://www.lucidchart.com/](https://www.lucidchart.com/)     / [https://miro.com/](https://miro.com/) / [https://structurizr.com/](https://structurizr.com/) |
|  Frontend Development   |  Visual Studio Code / WebStorm  |                Desarrollo del Landing Page y Web Application (HTML, CSS, JavaScript).                 |          [https://code.visualstudio.com](https://code.visualstudio.com) / [https://www.jetbrains.com/webstorm/](https://www.jetbrains.com/webstorm/)           |
|   Backend Development   |              Rider              |         Desarrollo del RESTful API en C# (.NET) siguiendo arquitectura orientada a servicios.         |                                              [https://www.jetbrains.com/rider/](https://www.jetbrains.com/rider/)                                              |
|       API Testing       |             Postman             |                          Pruebas y validación de endpoints del API RESTful.                           |                                                       [https://www.postman.com](https://www.postman.com)                                                       |
|     Version Control     |             GitHub              | Control de versiones del código fuente y documentación colaborativa (GitFlow + Conventional Commits). |                                                            [https://github.com](https://github.com)                                                            |
| Software Documentation  |            Markdown             |                     Redacción del informe del proyecto bajo enfoque Docs-as-Code.                     |                                                           Compatible con GitHub / editores de texto                                                            |


### 5.1.2. Source Code Management. 
Los repositorios utilizados para el desarrollo de código fuente son los siguientes:

<div align="center">

|      Producto Digital      |                       URL del Repositorio                        | 
|:--------------------------:|:----------------------------------------------------------------:|
|        Landing Page        | https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page | 
| Web Services (Backend API) |   https://github.com/Aurora-AplicacionesWeb/SupplyWok-BackEnd    |
|  Frontend Web Application  |   https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd   |

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

**Despliegue de la Landing Page**

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

| **Sprint #**                        | 1                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Date**                            | 20-04-2026                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Time**                            | 15:00                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Location**                        | Virtual, Discord                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Prepared by**                     | Zayd Ayasta, Juan Wang                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Attendees**                       | Marcelo Cuadros, Mathias Sanchez, Miguel Jara, Juan Wang, Zayd Ayasta                                                                                                                                                                                                                                                                                                                                                    |
| **Sprint 0 Review Summary**         | *No aplica por ser el primer sprint.*                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sprint 0 Retrospective Summary**  | *No aplica por ser el primer sprint.*                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sprint 1 Goal**                   | Nuestro enfoque en este sprint es la Landing Page que informará de nuestra plataforma, por lo que la desarrollaremos e implementaremos para que sea accesible y responsiva. Con la información que brindamos sobre nuestro producto esperamos ganarnos la confianza de los que visiten la página y que empiecen a usar nuestro sistema. Se confirmará cuando esté en producción y se pueda usar el enlace de la página.  |
| **Sprint 1 Velocity**               | Límite de **35 SP**                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Sum of Story Points**             | **30 SP**                                                                                                                                                                                                                                                                                                                                                                                                                |

#### 5.2.1.2. Aspect Leaders and Collaborators.

|    Team Member     |  GitHub username  |  Estructure HTML  |  Design UI & responsive  |  Scripts and UX  |  SEO and Accessibility  |  Content and Assets  |
|:------------------:|:-----------------:|:-----------------:|:------------------------:|:----------------:|:-----------------------:|:--------------------:|
|  Cuadros, Marcelo  |  Marcelo-alt-lab  |         L         |            C             |        L         |            C            |          C           |
|  Sanchez, Mathias  |      Nounz27      |         C         |            L             |        C         |            -            |          -           |
|    Jara, Miguel    |    MiguelJara2    |         C         |            C             |        C         |            -            |          -           |
|    Ayasta, Zayd    |    ZaydAyasta     |         C         |            C             |        C         |            -            |          C           |
|     Wang, Juan     |       jwd3t       |         C         |            C             |        C         |            L            |          C           |

#### 5.2.1.3. Sprint Backlog 1.

**Sprint 1 Backlog**

| US Id | US Title                                                    | Task Id | Task Title                                                                  | Description                                                                                                                                                                      | Estimation (Hours) |   Assigned To   | Status |
|:-----:|:------------------------------------------------------------|:-------:|:----------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------:|:---------------:|:------:|
| US37  | Página de inicio con hero section                           |   T01   | Crear estructura HTML de la Hero Section                                    | Maquetar la sección principal (Hero) usando etiquetas semánticas de HTML5.                                                                                                       |         2          | Marcelo Cuadros |  Done  |
| US37  | Página de inicio con hero section                           |   T02   | Implementar estilos CSS de la Hero Section                                  | Aplicar la hoja de estilos base para definir colores, tipografía y disposición.                                                                                                  |         2          | Mathias Sanchez |  Done  |
| US37  | Página de inicio con hero section                           |   T03   | Implementar CTAs y enlace al formulario de registro                         | Añadir botones llamativos que redirijan al usuario al proceso de registro.                                                                                                       |         1          | Marcelo Cuadros |  Done  |
| US37  | Página de inicio con hero section                           |   T04   | Adaptar Hero Section a diseño responsive                                    | Asegurar que la sección principal se visualice correctamente en dispositivos móviles.                                                                                            |         2          | Marcelo Cuadros |  Done  |
| US38  | Sección de características principales                      |   T05   | Crear estructura HTML de la sección de características                      | Construir la grilla o layout para mostrar los beneficios principales de la plataforma.                                                                                           |         1          |    Juan Wang    |  Done  |
| US38  | Sección de características principales                      |   T06   | Agregar iconos y estilos visuales a cada característica                     | Incorporar elementos gráficos y CSS para hacer cada característica visualmente atractiva.                                                                                        |         2          | Mathias Sanchez |  Done  |
| US39  | Sección de planes y precios                                 |   T07   | Crear estructura HTML de la sección de planes                               | Maquetar el área donde se mostrarán las opciones de precios y suscripciones.                                                                                                     |         1          |   Zayd Ayasta   |  Done  |
| US39  | Sección de planes y precios                                 |   T08   | Implementar estilos de tarjetas de planes y precios                         | Diseñar visualmente las tarjetas de precios para facilitar la comparación de planes.                                                                                             |         2          |   Zayd Ayasta   |  Done  |
| US39  | Sección de planes y precios                                 |   T09   | Agregar CTA de selección de plan con redirección al registro                | Vincular cada tarjeta de precio con el flujo de creación de cuenta.                                                                                                              |         1          | Marcelo Cuadros |  Done  |
| US40  | Sección de preguntas frecuentes                             |   T10   | Crear estructura HTML del acordeón FAQ                                      | Maquetar el contenedor base para las preguntas frecuentes de los usuarios.                                                                                                       |         1          | Marcelo Cuadros |  Done  |
| US40  | Sección de preguntas frecuentes                             |   T11   | Implementar lógica de expansión y colapso de preguntas                      | Programar la interactividad para mostrar u ocultar respuestas al hacer clic.                                                                                                     |         2          | Marcelo Cuadros |  Done  |
| US41  | Navegación y menú principal                                 |   T12   | Crear navbar sticky con enlaces de navegación                               | Implementar un menú de navegación fijo en la parte superior con scroll suave.                                                                                                    |         2          |   Zayd Ayasta   |  Done  |
| US41  | Navegación y menú principal                                 |   T13   | Implementar menú hamburguesa para dispositivos móviles                      | Desarrollar un menú lateral desplegable para resoluciones de pantalla pequeñas.                                                                                                  |         2          |   Zayd Ayasta   |  Done  |
| US42  | Responsividad total y optimización mobile                   |   T14   | Definir e implementar breakpoints responsive globales                       | Establecer las reglas CSS de diseño adaptable para toda la página de aterrizaje.                                                                                                 |         2          |   Zayd Ayasta   |  Done  |
| US42  | Responsividad total y optimización mobile                   |   T15   | Verificar tamaño mínimo de elementos interactivos                           | Validar que botones y enlaces tengan al menos 44px para facilitar el toque en móviles.                                                                                           |         1          |   Miguel Jara   |  Done  |
| US42  | Responsividad total y optimización mobile                   |   T16   | Validar que las imágenes no generen scroll horizontal                       | Asegurar que ningún recurso visual exceda el ancho máximo de la pantalla.                                                                                                        |         1          |   Miguel Jara   |  Done  |
| US43  | SEO y accesibilidad web                                     |   T17   | Configurar meta tags de SEO (título, descripción, keywords)                 | Añadir metadatos clave para mejorar la indexación y visibilidad en buscadores.                                                                                                   |         1          |   Miguel Jara   |  Done  |
| US43  | SEO y accesibilidad web                                     |   T18   | Agregar atributos alt, roles ARIA y estructura semántica HTML5              | Mejorar la accesibilidad para usuarios que dependen de lectores de pantalla.                                                                                                     |         2          |   Miguel Jara   |  Done  |
| US43  | SEO y accesibilidad web                                     |   T19   | Verificar navegación por teclado y visibilidad del foco                     | Asegurar que se pueda interactuar con la página usando únicamente el teclado.                                                                                                    |         1          |   Miguel Jara   |  Done  |
| US44  | Footer con información adicional                            |   T20   | Crear estructura HTML del footer                                            | Maquetar la sección final de la página para enlaces secundarios y legales.                                                                                                       |         1          |   Miguel Jara   |  Done  |
| US44  | Footer con información adicional                            |   T21   | Implementar enlaces a redes sociales y páginas legales                      | Conectar los iconos sociales y los textos de términos y condiciones.                                                                                                             |         1          |   Zayd Ayasta   |  Done  |
| US45  | Visualizar métricas de impacto                              |   T22   | Crear sección de métricas e impacto con estadísticas                        | Diseñar un bloque visual que resalte los números clave para generar confianza.                                                                                                   |         2          |    Juan Wang    |  Done  |
| US46  | Muestra del producto                                        |   T23   | Integrar galería de imágenes del producto con texto alternativo             | Mostrar capturas de la plataforma asegurando que sean accesibles para todos.                                                                                                     |         1          | Mathias Sanchez |  Done  |
| US46  | Muestra del producto                                        |   T24   | Integrar video del producto con fallback de texto alternativo               | Incrustar un video demostrativo con opciones de texto para quienes no puedan verlo.                                                                                              |         2          | Mathias Sanchez |  Done  |
| US47  | Calls to action                                             |   T25   | Distribuir CTAs secundarios en secciones clave de la Landing Page           | Añadir llamadas a la acción adicionales a lo largo del recorrido del usuario.                                                                                                    |         1          | Marcelo Cuadros |  Done  |
| US48  | Secciones interactivas con contenido expandible             |   T26   | Implementar scripts de show/hide para contenido condicional                 | Añadir lógica JavaScript para controlar elementos que se muestran bajo ciertas acciones.                                                                                         |         1          | Marcelo Cuadros |  Done  |
| US49  | Sobre el equipo detrás de SupplyWok                         |   T28   | Crear sección del equipo con video y texto alternativo                      | Maquetar la presentación de los creadores de SupplyWok con soporte multimedia.                                                                                                   |         2          | Marcelo Cuadros |  Done  |
| US50  | Prioridad en mostrar las funcionalidades a los Restaurantes |   T29   | Ordenar sección de funcionalidades priorizando beneficios para restaurantes | Estructurar visualmente el contenido para destacar el valor aportado a los restaurantes.                                                                                         |         1          | Marcelo Cuadros |  Done  |
| US51  | Soporte multiidioma                                         |   T30   | Agregar atributos `data-i18n` a los elementos HTML de la landing page       | Etiquetar todos los elementos textuales HTML con el atributo `data-i18n="clave"` para que sean traducibles por el motor de i18n.                                                 |         1          | Mathias Sanchez |  Done  |
| US51  | Soporte multiidioma                                         |   T31   | Implementar selector de idiomas y lógica de cambio                          | Crear los botones de cambio de idioma en el header con estilos `active/inactive`y la función `updateLanguage()` que recora los elementos `[data-i18n]` y actualice su contenido. |         1          | Mathias Sanchez |  Done  |


#### 5.2.1.4. Development Evidence for Sprint Review.

|        Repository        |  Branch   |  Commit Id  | Commit Message                                                                                           |  Commit Message Body  |  Commited on (Date)  |
|:------------------------:|:---------:|:-----------:|:---------------------------------------------------------------------------------------------------------|:---------------------:|:--------------------:|
|  SupplyWok-Landing-Page  |  develop  |   1eca1eb   | feat: css hero section and CTA.                                                                          |           -           |  25 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   e7cfb4d   | fix: Readme with wrong text.                                                                             |           -           |  25 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   0a4749c   | feat: responsive for hero sections.                                                                      |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   6f65577   | feat: add features section and update HTML structure; include new icons and license files.               |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |   main    |   0a1e1cc   | feat(landing-page): add css and html for hero section and features section.                              |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |   main    |   d9651aa   | feat(landing-page): add css and html for hero section and features section.                              |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   62ce603   | feat(landing-page): add text information for plans.                                                      |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   8967aeb   | feat: add styles on plans.                                                                               |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   85fecd0   | docs(readme): fix README.md                                                                              |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   5bcaa5e   | Merge remote-tracking branch 'origin/develop' into develop.                                              |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   5ba9214   | feat: add FAQ seccion.                                                                                   |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   16d8090   | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page into develop  |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   ae2af7a   | feat: add header.                                                                                        |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |      -      | feat: add uses you want, about our team and impact                                                       |           -           |  27 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   68c9d1d   | feat: add footer.                                                                                        |           -           |  26 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   25283da   | feat: add i18n al fixes to the footer.                                                                   |           -           |  27 de Abril, 2026   |
|  SupplyWok-Landing-Page  |  develop  |   3452838   | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-Landing-Page into develop  |           -           |  27 de Abril, 2026   |

Destacar que el commit sin commit id es debido a que es un PR que se hace desde un fork del repositorio. También se añadirá evidencia del Figma como pruebas de colaboración en el sprint.

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

Aquí está el enlace a la página desplegada: [https://aurora-aplicacionesweb.github.io/SupplyWok-Landing-Page/](https://aurora-aplicacionesweb.github.io/SupplyWok-Landing-Page/)

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

| **Sprint #**                        | 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|:------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Date**                            | 10-05-2026                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Time**                            | 13:00                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Location**                        | Virtual, Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Prepared by**                     | Zayd Ayasta, Juan Wang                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Attendees**                       | Marcelo Cuadros, Mathias Sanchez, Miguel Jara                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Sprint 1 Review Summary**         | En el Sprint 1, el equipo se enfocó en el desarrollo del Landing Page de SupplyWok. Con ello, se logró configurar el entorno de trabajo, establecer los requerimientos principales del sistema, así como el diseño preliminar de la interfaz y la estructura de navegación de la plataforma. Por otro lado, el profesor a cargo brindó feedback positivo respecto al diseño inicial del sistema y sugirió corregir ciertos aspectos de la documentación del proyecto.  |
| **Sprint 1 Retrospective Summary**  | Durante el Sprint 1, surgieron dificultades relacionadas con la comunicación, la distribución de tareas y el cumplimiento de algunos entregables de la plataforma, afectando principalmente la documentación del proyecto. Sin embargo, a pesar de estas dificultades, se logró entregar un sprint casi completo y con una calidad aceptable.                                                                                                                          |
| **Sprint 2 Goal**                   | Nuestro enfoque en este sprint es desarrollar e implementar la interfaz principal de SupplyWok mediante dashboards funcionales para dueños y proveedores, permitiendo la visualización y gestión básica de la información del negocio. Además, se espera implementar la interfaz base de cada dashboard junto con las funcionalidades principales de cada bounded context.                                                                                             |
| **Sprint 2 Velocity**               | Límite de **35 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sum of Story Points**             | **30 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

#### 5.2.2.2. Aspect Leaders and Collaborators.

Durante el Sprint 2, el equipo se enfocó principalmente en el desarrollo del frontend de SupplyWok, priorizando la interfaz y las funcionalidades principales de la plataforma. Los principales aspectos considerados en este sprint incluyen el desarrollo de los todos los bounded context.

- **Inventory Management Bounded Context**: Es el encargado de gestionar la información de los recursos de inventario de cada restaurante.

- **Supply and Purchasing Bounded Context**: Es el encargado de gestionar las órdenes de suplementos realizadas por cada restaurante.

- **Restaurant Management Bounded Context**: Es el encargado de gestionar todo lo relacionado con la operación del establecimiento.

- **Operational Monitoring and IoT Alerts Bounded Context**: Es el encargado de gestionar la información recopilada por los sensores del restaurante.

- **Supplier Management & Operations Bounded Context**: Es el encargado de gestionar la información de los proveedores y sus pedidos.

- **Identity & Access Bounded Context**: Es el encargado de gestionar todo lo relacionado con la autenticación y administración de cuentas.

- **Shared Bounded Context**: Contiene Value Objects y componentes visuales comunes que son reutilizados por múltiples bounded contexts del sistema.

|    Team Member     |  GitHub username  |  Inventory Management Bounded BC  |  Supply and Purchasing BC / Shared BC  |  Restaurant Management BC  |  Supplier Management & Operations BC  |  Operational Monitoring and IoT Alerts BC / Identity & Access BC  |
|:------------------:|:-----------------:|:---------------------------------:|:--------------------------------------:|:--------------------------:|:-------------------------------------:|:-----------------------------------------------------------------:|
|  Cuadros, Marcelo  |  Marcelo-alt-lab  |                 C                 |                   C                    |             C              |                   -                   |                                 L                                 |
|  Sanchez, Mathias  |      Nounz27      |                 -                 |                   C                    |             L              |                   C                   |                                 C                                 |
|    Jara, Miguel    |    MiguelJara2    |                 L                 |                   C                    |             -              |                   C                   |                                 C                                 |
|    Ayasta, Zayd    |    Zayd Ayasta    |                 C                 |                   L                    |             C              |                   C                   |                                 -                                 |
|     Wang, Juan     |       jwd3t       |                 C                 |                   -                    |             C              |                   L                   |                                 C                                 |

#### 5.2.2.3. Sprint Backlog 2.

**Sprint 2 Backlog**

|  US Id  | US Title                                      |  Task Id  | Task Title                               | Description                                                               |  Estimation (Hours)  |    Assigned To    |  Status  |
|:-------:|:----------------------------------------------|:---------:|:-----------------------------------------|:--------------------------------------------------------------------------|:--------------------:|:-----------------:|:--------:|
|  US11   | Proyección de demanda basada en historial     |    T30    | Diseño de interfaz de proyección         | Diseñar la interfaz para visualizar la proyección de consumo de insumos.  |          3           |  Mathias Sanchez  |   Done   |
|  US11   | Proyección de demanda basada en historial     |    T31    | Implementación de gráficos estadísticos  | Implementar gráficos y métricas de proyección de demanda.                 |          4           |  Marcelo Cuadros  |   Done   |
|  US11   | Proyección de demanda basada en historial     |    T32    | Integración de datos históricos          | Conectar la vista con los datos históricos de consumo.                    |          3           |     Juan Wang     |   Done   |
|  US14   | Monitoreo de temperatura en almacén           |    T33    | Diseño del dashboard IoT                 | Diseñar el panel de monitoreo de sensores IoT.                            |          2           |  Marcelo Cuadros  |   Done   |
|  US14   | Monitoreo de temperatura en almacén           |    T34    | Integración de datos de sensores         | Implementar la recepción y visualización de temperatura en tiempo real.   |          4           |    Zayd Ayasta    |   Done   |
|  US15   | Alertas de riesgo en cocina                   |    T35    | Sistema de alertas automáticas           | Implementar alertas visuales ante condiciones peligrosas.                 |          3           |    Miguel Jara    |   Done   |
|  US15   | Alertas de riesgo en cocina                   |    T36    | Configuración de umbrales                | Configurar parámetros de temperatura y humedad para activar alertas.      |          2           |  Marcelo Cuadros  |   Done   |
|  US17   | Control de ocupación de mesas                 |    T37    | Diseño de estado de mesas                | Crear componentes visuales para representar el estado de las mesas.       |          2           |     Juan Wang     |   Done   |
|  US17   | Control de ocupación de mesas                 |    T38    | Actualización en tiempo real             | Implementar actualización dinámica de ocupación de mesas.                 |          3           |  Mathias Sanchez  |   Done   |
|  US18   | Historial de alertas e incidencias operativas |    T39    | Registro de incidencias                  | Implementar almacenamiento de eventos y alertas.                          |          3           |    Zayd Ayasta    |   Done   |
|  US18   | Historial de alertas e incidencias operativas |    T40    | Vista histórica de alertas               | Crear interfaz para consultar incidencias registradas.                    |          3           |  Marcelo Cuadros  |   Done   |
|  US19   | Exportar reporte de monitoreo y alertas       |    T41    | Generación de reportes PDF               | Implementar exportación de reportes en PDF.                               |          3           |  Marcelo Cuadros  |   Done   |
|  US19   | Exportar reporte de monitoreo y alertas       |    T42    | Exportación CSV                          | Implementar exportación de datos en formato CSV.                          |          2           |     Juan Wang     |   Done   |
|  US20   | Registro y perfil del proveedor               |    T43    | Formulario de registro                   | Implementar formulario para registro de proveedores.                      |          3           |    Miguel Jara    |   Done   |
|  US20   | Registro y perfil del proveedor               |    T44    | Vista de perfil del proveedor            | Crear pantalla de perfil y edición de datos.                              |          3           |    Zayd Ayasta    |   Done   |
|  US21   | Recepción y gestión de órdenes de compra      |    T45    | Panel de órdenes recibidas               | Implementar listado de órdenes de compra recibidas.                       |          4           |  Mathias Sanchez  |   Done   |
|  US21   | Recepción y gestión de órdenes de compra      |    T46    | Gestión de estado de pedidos             | Permitir actualizar estados de órdenes de compra.                         |          3           |  Marcelo Cuadros  |   Done   |
|  US24   | Confirmación y seguimiento de entregas        |    T47    | Registro de entregas                     | Implementar formulario para confirmar entregas realizadas.                |          3           |     Juan Wang     |   Done   |
|  US24   | Confirmación y seguimiento de entregas        |    T48    | Seguimiento de despachos                 | Implementar visualización del estado de entregas.                         |          3           |    Miguel Jara    |   Done   |
|  US25   | Panel de rendimiento por cliente              |    T49    | Dashboard de clientes frecuentes         | Implementar métricas de pedidos por cliente.                              |          4           |    Zayd Ayasta    |   Done   |
|  US25   | Panel de rendimiento por cliente              |    T50    | Estadísticas comerciales                 | Mostrar estadísticas y tendencias de consumo.                             |          3           |    Miguel Jara    |   Done   |
|  US27   | Selección y gestión del plan de suscripción   |    T51    | Vista de planes disponibles              | Diseñar pantalla de planes y beneficios.                                  |          2           |  Marcelo Cuadros  |   Done   |
|  US27   | Selección y gestión del plan de suscripción   |    T52    | Gestión de suscripción                   | Implementar selección y activación de planes.                             |          2           |     Juan Wang     |   Done   |
|  US28   | Notificaciones en tiempo real                 |    T53    | Sistema de notificaciones                | Implementar notificaciones dinámicas en la plataforma.                    |          4           |  Mathias Sanchez  |   Done   |
|  US28   | Notificaciones en tiempo real                 |    T54    | Alertas en tiempo real                   | Mostrar alertas instantáneas relacionadas al sistema.                     |          3           |    Zayd Ayasta    |   Done   |
|  US26   | Inicio de sesión y registro de cuenta         |    T55    | Formulario de login                      | Implementar formulario de inicio de sesión con validación.                |          3           |  Marcelo Cuadros  |   Done   |
|  US26   | Inicio de sesión y registro de cuenta         |    T56    | Formulario de registro                   | Implementar formulario de registro de nueva cuenta con validación.        |          3           |  Marcelo Cuadros  |   Done   |

#### 5.2.2.4. Development Evidence for Sprint Review.

![Tabla en Trello 1](../assets/images/deploy-steps/trello_1.png)

![Tabla en Trello 2](../assets/images/deploy-steps/trello_2.png)

[https://trello.com/b/07LRT0At/sprint-2](https://trello.com/b/07LRT0At/sprint-2)

|      Repository      |  Branch   |  Commit Id  | Commit Message                                                                                                                           |  Commit Message Body  |  Commited on (Date)  |
|:--------------------:|:---------:|:-----------:|:-----------------------------------------------------------------------------------------------------------------------------------------|:---------------------:|:--------------------:|
|  SupplyWok-FrontEnd  |  feature  |   66c85df   | feat: setup project architecture and shared modules                                                                                      |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   6039b3b   | feat: configure application routing                                                                                                      |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   4cd7752   | feat: add purchase order domain entities                                                                                                 |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   fab4097   | feat: implement purchase order api integration                                                                                           |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   d6f5221   | feat: add purchase order store management                                                                                                |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   bb8db44   | feat: configure supply and purchasing routes                                                                                             |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   546855e   | feat: create purchase order reusable components                                                                                          |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   4e2fcff   | feat: implement supply and purchasing pages                                                                                              |           -           |      10/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   f34ffae   | refactor: reorganize shared layout and state management                                                                                  |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   21f4bff   | feat: implement supply and purchasing bounded context                                                                                    |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   2dc2096   | Merge pull request #5 from Aurora-AplicacionesWeb/develop                                                                                |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   752abc5   | feat(iot-monitoring): add IoT monitoring components and alerts, update environment variables                                             |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   0e1b7e3   | feat(entities): add initial entities for restaurant management bounded context                                                           |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   9e705a8   | feat(restaurant-management/infrastructure): implement assemblers for restaurant management entities.                                     |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   9f17ee0   | feat(restaurant-management): implement base API and endpoint classes for restaurant management.                                          |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   2e948ec   | feat(restaurant-management/application): add Pinia store for managing restaurant operations.                                             |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   9f72302   | feat(restaurant-management/locales): update translations for restaurant management pages in English, Spanish, and Chinese.               |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   7375fba   | feat(restaurant-management/presentation): add components for dish menu, kitchen tickets, and tables occupancy management.                |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   45892cb   | feat(shared/presentation): implement layout components and add language switcher component.                                              |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   4c4bf96   | feat: rename restaurant-management.json to db.json and update table structure and routing                                                |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   6ca5639   | chore: add new SVG icons for alerts, configuration, dashboard, inventory, kitchen tickets, orders, reports, subscription, and suppliers  |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   0fa27a0   | feat: add environment configuration for development and production with API endpoints                                                    |           -           |      11/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   efe9e7f   | feat: initialize supplier management module with the sidebar for suppliers and update translations                                       |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   22a5d5f   | fix: correct syntax and an typing error in zh.json                                                                                       |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   92f7703   | Merge branch 'feature/restaurant-management-bc' into develop                                                                             |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   c22a4df   | fix: fix some errors in sidebar-menu                                                                                                     |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   5e4e350   | refactor: update method names for consistency and improve layout styling                                                                 |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   3915b4f   | feat: integrate pinia store and vue router, initialize router with supplier routes                                                       |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   3bafae0   | fix: correct API URL typo, and adjust app title                                                                                          |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   a5a54a5   | Merge branch 'develop' into feature/operational-monitoring-and-iot-alerts-bc                                                             |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   a295c25   | feat(operational-monitoring-and-iot-alerts-bc): add iot and alerts bc to the main branch for develop.                                    |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   064a209   | chore: update package-lock.json to reflect dependency version changes                                                                    |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   d91f6b3   | feat: add orders entities and assembler for transforming purchase orders resources                                                       |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   74a02aa   | feat(iot-monitoring): change IoT monitoring components and alerts, update environment variables.                                         |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   e201320   | fix: update OrdersAssembler to use correct Orders entity                                                                                 |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   a7257bd   | feat: add supply management api and initialize json server setup                                                                         |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   7bd9292   | feat(supply-and-purchasing): add mock backend with db.json                                                                               |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   bcf87fa   | feat: add supplier management store with state, getters, and fetch logic                                                                 |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   739b84d   | feat(supply-and-purchasing): add orders summary card                                                                                     |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   78e1edd   | Merge remote-tracking branch 'origin/develop' into feature/supply-and-purchasing-bc                                                      |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   c0b77d3   | feat: add mock api fallback and dashboard enhancements                                                                                   |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   0694d59   | feat(supply-and-purchasing): enhance dashboard integration and mock api support                                                          |           -           |      12/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   1232115   | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd into develop                                      |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   c77d755   | feat: implement inventory item and stock movement entities                                                                               |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   405c216   | feat: implement inventory management API with mock data fallback                                                                         |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   ee58105   | feat: implement inventory management API with mock data fallback                                                                         |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   274c281   | feat: add inventory management page and data table component                                                                             |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   87c6730   | feat: add internationalization support for inventory management                                                                          |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   2dc4f94   | feat: add delete confirmation dialog and functionality to inventory management                                                           |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   b2cb7d1   | feat: add inventory API configuration and update stock percentage calculation                                                            |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   8ec5d44   | feat: integrate confirmation dialog into inventory data table component                                                                  |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   40c3912   | feat: refactor inventory and stock movement entities to use public properties                                                            |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   d663118   | Merge remote-tracking branch 'origin/develop' into develop                                                                               |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   90b902b   | feat(iam): add user validation and notifies in header.                                                                                   |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   6f68afb   | feat(alerts): enhance alert management with status and source properties, add acknowledgment functionality                               |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   30b0f7c   | feat: finish supplier management store with CRUD methods and documentation                                                               |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   7e1145c   | feat(supply-management): add catalog entity and assembler                                                                                |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   3885462   | feat(supply-management): update store and api                                                                                            |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   547bcf2   | feat(supply-management): update db.json to include catalog items                                                                         |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   ab5066d   | feat(supply-management): add routing in sidebar menu for supplier and restaurant and switching roles                                     |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   cf1fc68   | feat(supply-management): add catalog supplier components and functionality                                                               |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   f1569f9   | feat(supply-management): add supplier management orders view                                                                             |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   0dc1f27   | .                                                                                                                                        |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   5e25a4f   | Merge remote-tracking branch 'origin/develop' into feature/supplier-management-and-operations-bc                                         |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   e10ad29   | .                                                                                                                                        |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   25d7752   | refactor: improve restaurant management bc and styling consistency across components                                                     |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   8965e0a   | feat: add active commands and kitchen tickets cards to restaurant management dashboard                                                   |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   a71db21   | feat: enhance restaurant management dashboard with kitchen tickets and active commands functionality                                     |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   d243b6b   | feat: add pending orders card to dashboard with dynamic count                                                                            |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   cc267ea   | delete: App.vue                                                                                                                          |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   661ac88   | feat: add below minimum stock card component with internationalization support                                                           |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   21227b6   | feat: add Chinese localization for below minimum stock component                                                                         |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   71d72db   | fix: update role routing                                                                                                                 |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  feature  |   dbef84e   | fix: update route routing and dashboard view                                                                                             |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   1bec258   | Merge branch 'develop' of https://github.com/Aurora-AplicacionesWeb/SupplyWok-FrontEnd into develop                                      |           -           |      13/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   f7e8c05   | feat(supply-management): add client view                                                                                                 |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   ceebb76   | fix: remove unnecessary endpoint paths                                                                                                   |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   b876bf0   | feat(supply-management): add alert endpoint and assembler and api                                                                        |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   45d7066   | feat(supply-management): add endpoins for alerts and store for alerts                                                                    |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   329deb7   | Merge branch 'feature/supplier-management-and-operations-bc' into develop                                                                |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   edfce1d   | fix(restaurant-management): fix routing for create kitchen ticket                                                                        |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   601aedb   | fix: unify purchase orders data source                                                                                                   |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   0e01c56   | feat: add inventory, configuration, reports page                                                                                         |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   7a31adf   | Merge remote-tracking branch 'origin/develop' into feature/supply-and-purchasing-bc                                                      |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   7d2759f   | fix: delete app.vue                                                                                                                      |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   aee254d   | fix: repair routing and orders api fallbacks                                                                                             |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   f50f699   | feature: add views and fix routes errors                                                                                                 |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   2fe0640   | feat(supply-management): add client entity and assembler and endpoint and store                                                          |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   7684ba8   | feat(supply-management): add supplier alerts view                                                                                        |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   553e723   | feat(supply-management): add demand forecast endpoint and assembler and entity                                                           |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   b5b11b1   | feat(supply-management): add data for demand forecast and install chart.js dependency                                                    |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   adb9344   | feat(supply-management): add demand forecast view and internationalization                                                               |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   c4ed789   | Merge remote-tracking branch 'origin/feature/supplier-management-and-operations-bc' into develop                                         |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   a001a24   | fix: inventory management api and iam                                                                                                    |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   6bb63fa   | refactor: align inventory data flow                                                                                                      |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   f944122   | feat(supply-management): add delivery route endpoint and assembler and entity and update store and data                                  |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   aa2b8e2   | feat(supply-management): add delivery planning view                                                                                      |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   d97eace   | refactor: adjust layout styling for IoT panel and placeholder page                                                                       |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   35afb4a   | feat: implement add table functionality in tables and occupancy page                                                                     |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   6802e29   | fix: fix route for views                                                                                                                 |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   abbc374   | fix(supply-management): update delivery status filter                                                                                    |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   5aeeedf   | fix(supply-management): add supplier settings and subscription endpoints and assemblers entity stores and data                           |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   84727b4   | fix(supply-management): add supplier settings and subscription views                                                                     |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   d0ad0f5   | fix(supply-management): add dashboard components and view                                                                                |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   83bbae1   | refactor: rename files to "-view"                                                                                                        |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   0e8b291   | feat: add table deletion functionality and enhance table details view                                                                    |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   bfd7a0a   | Merge remote-tracking branch 'origin/feature/supplier-management-and-operations-bc' into develop                                         |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   77f8271   | feat(i18n): implement internationalization for various components and routes                                                             |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   d228610   | refactor: update supplier API endpoints for supply management and purchase order                                                         |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   fe76c7f   | feat(subscription): integrate subscription plan management and update UI components                                                      |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   245b495   | feat: update environment variables and enhance restaurant management api with new endpoints                                              |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   736f77a   | feat(alerts): enhance alert display logic and add supplier notification messages                                                         |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   e2fe602   | Merge remote-tracking branch 'origin/develop' into develop                                                                               |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   1fb79dc   | fix(supplier-api.js): connect suppliers page to mock api                                                                                 |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   1f0a08e   | Merge branch from develop                                                                                                                |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   0541dca   | fix(supplier-api.js): connect suppliers page to mock api                                                                                 |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   e5af4fe   | Merge pull request #14 from Aurora-AplicacionesWeb/develop                                                                               |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   66c71ce   | Dejar de rastrear archivos de entorno (manteniendo copias locales)                                                                       |           -           |      14/05/2026      |
|  SupplyWok-FrontEnd  |  develop  |   ea24093   | chore(app): complete bounded-context architecture migration, routing normalization, and i18n fixes                                       |           -           |      14/05/2026      |


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

3. Accedemos al enlace de nuestro Json server de forma https://my-json-server.typicode.com/< your-username >/< your-repo >. 

![](../assets/images/deploy-steps/myjsonserver-evidence.png)

**Deploy de la Plataforma en Firebase**

1. Accedemos a https://firebase.google.com/ y accedemos con nuestra cuenta. Después creamos nuestro proyecto.

![](../assets/images/deploy-steps/deploy_firebase.png)

2. Luego de instalar e iniciar sesión en firebase la terminal de JetBrains para construir, inicializar y deployar nuestro proyecto, para posteriormente acceder al enlace público.

![](../assets/images/deploy-steps/deploy_firebase_1.png)

![](../assets/images/deploy-steps/deploy_firebase_2.png)

![](../assets/images/deploy-steps/deploy_firebase_3.png)

![](../assets/images/deploy-steps/deploy_firebase_4.png)

![](../assets/images/deploy-steps/deploy_firebase_build.png)

Estos implementaron endpoints para manejar los datos y mostrarlos en nuestros componentes que permiten utilizar nuestro sistema sin necesidad de tener un backend por el momento.
[https://supplywok.web.app/](https://supplywok.web.app/)

#### 5.2.2.8. Team Collaboration Insights during Sprint.

En este apartado se visualiza todos los gráficos que representan la participación de cada integrante en el repositorio del fronted.

![Team Collaboration](../assets/images/deploy-steps/participation_2.png)

![Team Contribution 1](../assets/images/deploy-steps/contributions_1_2.png)

![Team Contribution 2](../assets/images/deploy-steps/contributions_2_2.png)

### 5.2.3. Sprint 3

En esta sección se registra y explica el avance realizado durante el Sprint 3 en términos de producto y trabajo colaborativo. El enfoque principal de este Sprint es el desarrollo e implementación de los servicios backend mediante C# y Entity Framework Core para los bounded context priorizados, así como la validación y correcto funcionamiento de sus endpoints REST.

#### 5.2.3.1. Sprint Planning 3

Durante la reunión de Sprint Planning del Sprint 3, se estableció como objetivo principal avanzar significativamente en el desarrollo backend de la plataforma SupplyWok, planteando alcanzar aproximadamente el 70% de implementación de los servicios backend del sistema. Para ello, se priorizó el desarrollo de los bounded contexts correspondientes al núcleo del negocio, incluyendo. Asimismo, el equipo revisó los resultados obtenidos durante el sprint anterior e identificó oportunidades de mejora con el fin de corregir errores, optimizar el proceso de desarrollo y garantizar una base sólida para las siguientes etapas del proyecto.

**Sprint Planning 3**

| **Sprint #**                       | 3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Date**                           | 2026-06-18                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Time**                           | 17:00                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Location**                       | Virtual, Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Prepared by**                    | Mathias Sanchez, Juan Wang                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Attendees**                      | Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Sprint 2 Review Summary**        | Durante el Sprint 2 se completó el desarrollo de la aplicación frontend utilizando una Fake API para simular la comunicación con los servicios backend. Se implementaron las principales interfaces y flujos de usuario previstos para la plataforma, obteniendo resultados satisfactorios en términos de funcionalidad, organización del código y experiencia de usuario. Como parte del feedback recibido, se destacó la calidad de la implementación realizada; sin embargo, se recomendó fortalecer la documentación técnica del proyecto para facilitar su comprensión, mantenimiento y futura integración con los servicios backend reales. |
| **Sprint 2 Retrospective Summary** | El equipo consideró que la distribución de tareas y la colaboración durante el Sprint 2 fueron adecuadas, permitiendo cumplir los objetivos establecidos dentro del plazo previsto. Asimismo, se identificó como principal oportunidad de mejora la elaboración de una documentación más completa y detallada, tanto del proceso de desarrollo como de los componentes implementados, con el fin de mejorar la comunicación interna y facilitar el trabajo en las siguientes iteraciones.                                                                                                                                                         |
| **Sprint 3 Goal**                  | Habilitar la comunicación centralizada de datos en la plataforma SupplyWok mediante la implementación del Web Service principal, garantizando que los sistemas externos puedan consultar a los bounded context Inventory Management, Procurement & Purchasing, Operations, IoT Operational Monitoring & Alerts, Supplier Panel, Identity And Access Management, Profiles y Analytics de manera segura y eficiente al cierre del sprint.                                                                                                                                                                                                           |
| **Sprint 3 Velocity**              | Límite de **45 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Sum of Story Points**            | **26 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Link del Sprint 3 Board:** [https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3](https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3)

#### 5.2.3.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración correspondiente al Sprint 3. Dado que el objetivo principal de esta iteración es avanzar en el desarrollo backend de SupplyWok, los aspectos considerados corresponden a los bounded contexts de negocio. Para cada aspecto se asigna un líder responsable de coordinar el desarrollo y uno o más colaboradores encargados de apoyar en la implementación, validación y pruebas de los servicios y endpoints asociados.

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

|     Team Member     |  Github Username  |  Inventory Management Bounded Context  |  Procurement & Purchasing Bounded Context  |  Operations Bounded Context  |  IoT Operational Monitoring & Alerts Bounded Context  |  Supplier Panel Bounded Context  |  Identity And Access Management Bounded Context  |  Profiles Bounded Context  |  Analytics Bounded Context  |
|:-------------------:|:-----------------:|:--------------------------------------:|:------------------------------------------:|:----------------------------:|:-----------------------------------------------------:|:--------------------------------:|:------------------------------------------------:|:--------------------------:|:---------------------------:|
|   Cuadros, Macelo   |  Marcelo-alt-lab  |                   -                    |                     -                      |              -               |                           L                           |                C                 |                        L                         |             C              |              L              | 
|    Ayasta, Zayd     |    Zayd Ayasta    |                   -                    |                     L                      |              -               |                           -                           |                C                 |                        -                         |             -              |              C              |
|     Wang, Juan      |       jwd3t       |                   -                    |                     C                      |              -               |                           -                           |                L                 |                        -                         |             C              |              -              | 
|  Sánchez, Mathias   |      Nounz27      |                   L                    |                     -                      |              L               |                           -                           |                -                 |                        -                         |             -              |              -              |
|  Cayanchi, Milenko  |      MaxghZZ      |                   -                    |                     -                      |              -               |                           -                           |                C                 |                        -                         |             L              |              -              |

#### 5.2.3.3. Sprint Backlog 3

En esta sección se presenta el Sprint Backlog correspondiente al Sprint 3. Los elementos incluidos fueron seleccionados en función del Sprint Goal establecido para esta iteración, el cual busca habilitar la comunicación centralizada de datos en la plataforma SupplyWok mediante la implementación del Web Service principal, garantizando que los sistemas externos puedan consultar inventario, pedidos, usuarios, reportes, monitoreo operativo, órdenes de cocina de SupplyWok mediante servicios backend funcionales. Para elo, se definieron las historias de usuario y tareas necesarias para implementar, validar y documentar los endpoints REST de los bounded contexts priorizados, asegurando su correcto funcionamiento antes de la integración con los componentes frontend de la plataforma.

**Link del Sprint 3 Board:** [https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3](https://trello.com/b/vRbx1S2v/supplywok-sprint-backlog-3)

**Sprint 3 Backlog** Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi

|    US ID     | US Title                                                                                                                                                        |     Task Id      | Task Title                                                         | Description                                                                                                                                                          |                                 Assigned To                                  |  Estimation (Hours)  |   Status    |
|:------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------:|:-------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------:|:--------------------:|:-----------:|
|  TS-SHR-001  | Como Arquitecto de Software, Quiero que el proyecto siga las convenciones de diseño, Para mantener una escalabilidad y mantenibilidad en el desarrollo.         |  TS-SHR-001-001  | Create Shared directory                                            | Create `Shared` directory within `Domain`, `Infrastructure` and `Application`.                                                                                       |  Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi  |          1           |    Done     |
|  TS-SHR-001  | Como Arquitecto de Software, Quiero que el proyecto siga las convenciones de diseño, Para mantener una escalabilidad y mantenibilidad en el desarrollo.         |  TS-SHR-001-002  | Add Base content in the directories.                               | Create file `Result` in `Application`; `IAuditableEntity`, `IBaseRepository`, and `IUnitOfWork` in `Domain`; `StringExtensions` and extensions in `Infrastructure`.  |  Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi  |          2           |    Done     |
|  TS-SHR-001  | Como Arquitecto de Software, Quiero que el proyecto siga las convenciones de diseño, Para mantener una escalabilidad y mantenibilidad en el desarrollo.         |  TS-SHR-001-003  | Create Files for the DataBase conexion                             | N/A                                                                                                                                                                  |  Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi  |          2           |    Done     |
|  TS-INM-001  | Como desarrollador backend, quiero gestionar supplies y consultar el stock consolidado, para mantener actualizado el inventario del restaurante.                |  TS-INM-001-001  | Implement Supply Query Endpoints                                   | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          4           |    Done     |
|  TS-INM-001  | Como desarrollador backend, quiero gestionar supplies y consultar el stock consolidado, para mantener actualizado el inventario del restaurante.                |  TS-INM-001-002  | Implement Supply Command Endpoints                                 | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          5           |    Done     |
|  TS-INM-001  | Como desarrollador backend, quiero gestionar supplies y consultar el stock consolidado, para mantener actualizado el inventario del restaurante.                |  TS-INM-001-003  | Define Supply Resources and Assemblers                             | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          2           |    Done     |
|  TS-INM-001  | Como desarrollador backend, quiero gestionar supplies y consultar el stock consolidado, para mantener actualizado el inventario del restaurante.                |  TS-INM-001-004  | Implement Total Stock Endpoint and Missing Supply Handling         | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          5           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-001  | Implement Purchase Order Query Service                             | Create `PurchaseOrderQueryService` with `GetAllPurchaseOrdersAsync()` to retrieve purchase order data from `IPurchaseOrderRepository` without side effects.          |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-002  | Implement Supplier Query Service                                   | Create `SupplierQueryService` with `GetAllSuppliersAsync()` to retrieve supplier data from `ISupplierRepository` without side effects.                               |                                 Zayd Ayasta                                  |          3           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-003  | Implement Purchase Order Command Service                           | Create `PurchaseOrderCommandService` with `CreatePurchaseOrderAsync(CreatePurchaseOrderCommand command)` to validate and persist new purchase orders.                |                                 Zayd Ayasta                                  |          6           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-004  | Define PurchaseOrderResource                                       | Define `PurchaseOrderResource` as an immutable record containing the fields required to represent a purchase order in the public REST API contract.                  |                                 Zayd Ayasta                                  |          1           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-005  | Define SupplierResource                                            | Define `SupplierResource` as an immutable record containing the fields required to represent a supplier in the public REST API contract.                             |                                 Zayd Ayasta                                  |          1           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-006  | Define CreatePurchaseOrderRequest                                  | Define `CreatePurchaseOrderRequest` as an immutable record containing `supplierId`, `orderDate`, `priority`, and `items` as the request contract.                    |                                 Zayd Ayasta                                  |          1           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-007  | Implement PurchaseOrderResource Assembler                          | Create `PurchaseOrderResourceAssembler` with mapping methods to transform `PurchaseOrder` entities into `PurchaseOrderResource` instances.                           |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-008  | Implement SupplierResource Assembler                               | Create `SupplierResourceAssembler` with mapping methods to transform `Supplier` entities into `SupplierResource` instances.                                          |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-009  | Implement Purchase Orders Controller Endpoints                     | Create controller endpoints for `GET /api/v1/purchase-orders` and `POST /api/v1/purchase-orders`, delegating query and command execution.                            |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-001  | Como desarrollador backend, quiero gestionar órdenes de compra y obtener datos de proveedores para soportar el flujo de abastecimiento en el sistema.           |  TS-ORD-001-010  | Implement Suppliers Controller Endpoint                            | Create controller endpoint for `GET /api/v1/suppliers`, delegating supplier retrieval through `SupplierQueryService`.                                                |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-001  | Validate Purchase Order Creation Command                           | Implement validation rules in `CreatePurchaseOrderCommand` or its validator to ensure `supplierId`, `orderDate`, `priority`, and `items` are present and valid.      |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-002  | Validate Purchase Order Item Structure                             | Implement validation rules for each purchase order item to ensure valid product data, quantity, unit type, and unit price before persistence.                        |                                 Zayd Ayasta                                  |          3           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-003  | Validate Supplier Existence                                        | Implement supplier existence verification in `PurchaseOrderCommandService` before creating a purchase order, using `ISupplierRepository`.                            |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-004  | Define Validation Error Response Contract                          | Define a response contract for validation failures that includes invalid fields and their corresponding error messages.                                              |                                 Zayd Ayasta                                  |          1           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-005  | Handle Invalid Purchase Order Requests                             | Implement application-layer handling for invalid purchase order requests, returning `400 Bad Request` when required data is missing or malformed.                    |                                 Zayd Ayasta                                  |          3           |    Done     |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-006  | Handle Missing Supplier in Purchase Order Creation                 | Implement application-layer handling to return `404 Not Found` when the supplier referenced by `supplierId` does not exist.                                          |                                 Zayd Ayasta                                  |          2           |   To-Fix    |
|  TS-ORD-002  | Como desarrollador backend, quiero validar la información de órdenes de compra para garantizar consistencia en el registro y seguimiento del abastecimiento.    |  TS-ORD-002-007  | Add Purchase Order Validation Tests                                | Create unit tests covering valid and invalid purchase order creation scenarios, including missing fields, invalid items, and nonexistent suppliers.                  |                                 Zayd Ayasta                                  |          6           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-002  | Implement Purchase Order Status Command Service                    | Create `PurchaseOrderStatusCommandService` with `UpdatePurchaseOrderStatusAsync()` to validate and persist order status updates.                                     |                                 Zayd Ayasta                                  |          5           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-003  | Define Purchase Order Status Transition Rules                      | Implement the allowed purchase order status transition rules in the application or domain layer to prevent invalid state changes.                                    |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-004  | Implement Purchase Order Lookup for Status Updates                 | Add repository lookup logic to retrieve purchase orders by identifier before attempting a status update.                                                             |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-005  | Handle Missing Purchase Order on Status Update                     | Implement application-layer handling to return `404 Not Found` when the target purchase order does not exist.                                                        |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-006  | Handle Invalid Status Transitions                                  | Implement application-layer handling to return `400 Bad Request` when the requested purchase order status transition is invalid.                                     |                                 Zayd Ayasta                                  |          3           |    Done     |
|  TS-ORD-003  | Como desarrollador backend, quiero actualizar el estado de las órdenes de compra para soportar su seguimiento dentro del flujo de abastecimiento.               |  TS-ORD-003-007  | Implement Purchase Order Status Update Endpoint                    | Create controller endpoint for `PUT` or `PATCH /api/v1/purchase-orders/{purchaseOrderId}` to delegate status updates.                                                |                                 Zayd Ayasta                                  |          3           |    Done     |
|  TS-ORD-004  | Como desarrollador backend, quiero actualizar y eliminar ordenes de compra, para mantener vigente la informacion del flujo de abastecimiento.                   |  TS-ORD-004-001  | Implement Purchase Order Update Command Handling                   | N/A                                                                                                                                                                  |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-004  | Como desarrollador backend, quiero actualizar y eliminar ordenes de compra, para mantener vigente la informacion del flujo de abastecimiento.                   |  TS-ORD-004-002  | Define UpdatePurchaseOrderResource and Assembler                   | N/A                                                                                                                                                                  |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-ORD-004  | Como desarrollador backend, quiero actualizar y eliminar ordenes de compra, para mantener vigente la informacion del flujo de abastecimiento.                   |  TS-ORD-004-003  | Implement Purchase Order Update and Delete Endpoints               | N/A                                                                                                                                                                  |                                 Zayd Ayasta                                  |          4           |    Done     |
|  TS-ORD-004  | Como desarrollador backend, quiero actualizar y eliminar ordenes de compra, para mantener vigente la informacion del flujo de abastecimiento.                   |  TS-ORD-004-004  | Handle Missing Purchase Order on Update or Delete                  | N/A                                                                                                                                                                  |                                 Zayd Ayasta                                  |          2           |    Done     |
|  TS-SUP-001  | Como desarrollador frontend, Quiero obtener los datos relevantes de los clientes mediante una solicitud GET, Para poder mostrarlo en la vista de mis clientes.  |  TS-SUP-001-01   | Implement Supplier Clients Listing Endpoint                        | Expose GET /api/v1/suppliers/{supplierId}/clients to return the ClientResource list linked to a supplier and respond 404 Not Found when no linked clients.           |                         Milenko Cayanchi, Juan Wang                          |          4           |    Done     |
|  TS-SUP-002  | Como desarrollador backend, quiero administrar el catalogo de proveedores, para consultar y mantener catalog items por proveedor desde la API.                  |  TS-SUP-002-001  | Implement Supplier and Client Query Endpoints                      | N/A                                                                                                                                                                  |                         Milenko Cayanchi, Juan Wang                          |          4           |    Done     |
|  TS-SUP-002  | Como desarrollador backend, quiero administrar el catalogo de proveedores, para consultar y mantener catalog items por proveedor desde la API.                  |  TS-SUP-002-002  | Implement Catalog Item Query Endpoints                             | N/A                                                                                                                                                                  |                         Milenko Cayanchi, Juan Wang                          |          3           |    Done     |
|  TS-SUP-002  | Como desarrollador backend, quiero administrar el catalogo de proveedores, para consultar y mantener catalog items por proveedor desde la API.                  |  TS-SUP-002-003  | Implement Catalog Item Command Endpoints                           | N/A                                                                                                                                                                  |                         Milenko Cayanchi, Juan Wang                          |          5           |    Done     |
|  TS-SUP-002  | Como desarrollador backend, quiero administrar el catalogo de proveedores, para consultar y mantener catalog items por proveedor desde la API.                  |  TS-SUP-002-004  | Define Supplier, Client and Catalog Item Resources and Assemblers  | N/A                                                                                                                                                                  |                         Milenko Cayanchi, Juan Wang                          |          3           |    Done     |
|  TS-AIM-003  | Como desarrollador backend, quiero administrar sensores IoT desde la API, para registrar, consultar, actualizar y eliminar sensores.                            |  TS-AIM-003-001  | Implement Sensor Query Endpoints                                   | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          3           |    Done     |
|  TS-AIM-003  | Como desarrollador backend, quiero administrar sensores IoT desde la API, para registrar, consultar, actualizar y eliminar sensores.                            |  TS-AIM-003-002  | Implement Sensor Command Endpoints                                 | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          4           |    Done     |
|  TS-AIM-003  | Como desarrollador backend, quiero administrar sensores IoT desde la API, para registrar, consultar, actualizar y eliminar sensores.                            |  TS-AIM-003-003  | Define Sensor Resources and Assembler                              | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          2           |    Done     |
|  TS-AIM-003  | Como desarrollador backend, quiero administrar sensores IoT desde la API, para registrar, consultar, actualizar y eliminar sensores.                            |  TS-AIM-003-004  | Handle Invalid or Missing Sensor Requests                          | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          3           |  To-Review  |
|  TS-AIM-004  | Como desarrollador backend, quiero administrar alertas operativas de proveedores y restaurantes, para registrar, consultar y reconocer incidentes.              |  TS-AIM-004-001  | Implement Supplier Alert Endpoints                                 | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          4           |    Done     |
|  TS-AIM-004  | Como desarrollador backend, quiero administrar alertas operativas de proveedores y restaurantes, para registrar, consultar y reconocer incidentes.              |  TS-AIM-004-002  | Implement Restaurant Alert Endpoints                               | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          4           |    Done     |
|  TS-AIM-004  | Como desarrollador backend, quiero administrar alertas operativas de proveedores y restaurantes, para registrar, consultar y reconocer incidentes.              |  TS-AIM-004-003  | Implement Inventory-based Restaurant Alert Endpoint                | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          6           |    Done     |
|  TS-AIM-004  | Como desarrollador backend, quiero administrar alertas operativas de proveedores y restaurantes, para registrar, consultar y reconocer incidentes.              |  TS-AIM-004-004  | Define Alert Resources, Assemblers and Acknowledge Handling        | N/A                                                                                                                                                                  |                               Marcelo Cuadros                                |          3           |    Done     |
|  TS-OPR-003  | Como desarrollador backend, quiero gestionar comandas desde la API, para crear, consultar, actualizar estado, agregar items y eliminar comandas.                |  TS-OPR-003-001  | Implement Comanda Query Endpoints                                  | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          4           |    Done     |
|  TS-OPR-003  | Como desarrollador backend, quiero gestionar comandas desde la API, para crear, consultar, actualizar estado, agregar items y eliminar comandas.                |  TS-OPR-003-002  | Implement Comanda Command Endpoints                                | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          5           |    Done     |
|  TS-OPR-003  | Como desarrollador backend, quiero gestionar comandas desde la API, para crear, consultar, actualizar estado, agregar items y eliminar comandas.                |  TS-OPR-003-003  | Define Comanda Resources and Assembler                             | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          2           |    Done     |
|  TS-OPR-003  | Como desarrollador backend, quiero gestionar comandas desde la API, para crear, consultar, actualizar estado, agregar items y eliminar comandas.                |  TS-OPR-003-004  | Implement Comanda Status and Item Endpoints                        | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          5           |  To-Review  |
|  TS-OPR-004  | Como desarrollador backend, quiero gestionar mesas desde la API, para crear, consultar, actualizar estado y eliminar mesas.                                     |  TS-OPR-004-001  | Implement Table Query Endpoints                                    | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          3           |    Done     |
|  TS-OPR-004  | Como desarrollador backend, quiero gestionar mesas desde la API, para crear, consultar, actualizar estado y eliminar mesas.                                     |  TS-OPR-004-002  | Implement Table Command Endpoints                                  | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          4           |    Done     |
|  TS-OPR-004  | Como desarrollador backend, quiero gestionar mesas desde la API, para crear, consultar, actualizar estado y eliminar mesas.                                     |  TS-OPR-004-003  | Define Table Resources and Assembler                               | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          2           |    Done     |
|  TS-OPR-004  | Como desarrollador backend, quiero gestionar mesas desde la API, para crear, consultar, actualizar estado y eliminar mesas.                                     |  TS-OPR-004-004  | Implement Table Status and Delete Endpoints                        | N/A                                                                                                                                                                  |                               Mathias Sanchez                                |          4           |    Done     |

#### 5.2.3.4. Development Evidence for Sprint Review

En esta sección se presentan los avances realizados durante el Sprint 3 en la implementación de los componentes backend de SupplyWok. El trabajo desarrollado se centró en la construcción de los bounded contexts priorizados del núcleo del negocio, incluyendo la implementación de entidades de dominio, repositorios, servicios de aplicación y endpoints REST mediante C# y Entity Framework Core.

|      Repository       |             Branch              |  Commit Id  | Commit Message                                                                                                                                  | Commit Message Body                                               |  Committed on (Date)  |
|:---------------------:|:-------------------------------:|:-----------:|:------------------------------------------------------------------------------------------------------------------------------------------------|:------------------------------------------------------------------|:---------------------:|
|  supply-wok-platform  |         feature/shared          |   8360eca   | feat(shared): add domain layer                                                                                                                  |                                                                   |  2026-06-04 23:02:58  |
|  supply-wok-platform  |         feature/shared          |   c51af55   | feat(shared): add Infrastructure Layer and related components.                                                                                  |                                                                   |  2026-06-05 04:16:25  |
|  supply-wok-platform  |         feature/shared          |   b8ed23d   | feat(shared): update .gitignore and add Application Layer.                                                                                      |                                                                   |  2026-06-05 01:27:09  |
|  supply-wok-platform  |         feature/shared          |   2962552   | feat(shared): add problem details factory and shared resource files                                                                             |                                                                   |  2026-06-05 06:58:16  |
|  supply-wok-platform  |         feature/shared          |   bd075fd   | feat(shared): update project file with new package references and configurations.                                                               |                                                                   |  2026-06-05 22:04:51  |
|  supply-wok-platform  |         feature/shared          |   9fdf8ad   | feat(shared): correct namespace casing and update access modifiers in iauditable-entity.                                                        |                                                                   |  2026-06-05 22:09:54  |
|  supply-wok-platform  |         feature/shared          |   a307fa2   | fix(shared): refactor imports and update namespaces                                                                                             |                                                                   |  2026-06-05 23:14:49  |
|  supply-wok-platform  |         feature/shared          |   e2b7120   | fix(shared): fix class to interface                                                                                                             |                                                                   |  2026-06-05 23:15:38  |
|  supply-wok-platform  |         feature/shared          |   fccc994   | feat(shared): update project file with new package references and configurations                                                                |                                                                   |  2026-06-05 23:16:20  |
|  supply-wok-platform  |             develop             |   386fb48   | Merge branch 'feature/shared' into develop                                                                                                      |                                                                   |  2026-06-05 23:25:09  |
|  supply-wok-platform  |             develop             |   916076f   | fix:  correct name format convention                                                                                                            |                                                                   |  2026-06-05 21:21:24  |
|  supply-wok-platform  |             develop             |   7a274d9   | fix:  update gitignore                                                                                                                          |                                                                   |  2026-06-05 23:15:08  |
|  supply-wok-platform  |             develop             |   c5f3939   | chore: initial commit                                                                                                                           |                                                                   |  2026-05-29 23:06:14  |
|  supply-wok-platform  |           feature/iot           |   800da01   | feat(Sensor): add sensor definition.                                                                                                            |                                                                   |  2026-06-06 22:58:50  |
|  supply-wok-platform  |           feature/iot           |   988c2b6   | feat(Sensor): finish the Domain Layer for the moment.                                                                                           |                                                                   |  2026-06-06 23:24:02  |
|  supply-wok-platform  |           feature/iot           |   0f34884   | feat(Sensor): add Infrastructure Layer and related components.                                                                                  |                                                                   |  2026-06-07 00:30:00  |
|  supply-wok-platform  |           feature/iot           |   e35fa82   | feat(Sensor): integrate IoT context and add sensor-related services                                                                             |                                                                   |  2026-06-07 04:51:01  |
|  supply-wok-platform  |           feature/iot           |   8bc8c91   | feat(Sensor): implement interfaces layer for REST API.                                                                                          |                                                                   |  2026-06-07 04:21:27  |
|  supply-wok-platform  |           feature/iot           |   d02cc8f   | feat(Sensor): add Resources Layer and related components                                                                                        |                                                                   |  2026-06-07 04:37:07  |
|  supply-wok-platform  |             develop             |   2ccb027   | Merge branch 'feature/sensors' into develop                                                                                                     |                                                                   |  2026-06-07 04:54:08  |
|  supply-wok-platform  |             develop             |   20e983f   | Merge pull request #1 from Aurora-AplicacionesWeb/release/0.2.0                                                                                 | Release/0.2.0                                                     |  2026-06-07 04:55:48  |
|  supply-wok-platform  |       feature/purchasing        |   cbca652   | feat(purchasing): add purchase order domain model                                                                                               |                                                                   |  2026-06-08 04:54:50  |
|  supply-wok-platform  |       feature/purchasing        |   3fd812c   | feat(purchasing): add purchase order application services                                                                                       |                                                                   |  2026-06-08 04:56:06  |
|  supply-wok-platform  |       feature/purchasing        |   0b000fd   | feat(purchasing): add persistence configuration and repositories                                                                                |                                                                   |  2026-06-08 04:57:09  |
|  supply-wok-platform  |       feature/purchasing        |   ddf9ff9   | feat(purchasing): add purchase order rest endpoints                                                                                             |                                                                   |  2026-06-08 04:57:44  |
|  supply-wok-platform  |       feature/purchasing        |   1f04c5e   | feat(purchasing): register purchasing dependencies                                                                                              |                                                                   |  2026-06-08 04:57:58  |
|  supply-wok-platform  |             develop             |   666a88d   | Merge branch 'feature/purchase-orders' into develop                                                                                             |                                                                   |  2026-06-08 05:35:20  |
|  supply-wok-platform  |             develop             |   7d30e0d   | Merge branch 'release/0.3.0'                                                                                                                    |                                                                   |  2026-06-08 05:48:15  |
|  supply-wok-platform  |             develop             |   59fb5ef   | Merge tag '0.3.0' into develop                                                                                                                  | Release v0.3.0 - Purchase Orders 0.3.0                            |  2026-06-08 05:48:16  |
|  supply-wok-platform  |             develop             |   0f7c9bb   | Merge pull request #3 from Aurora-AplicacionesWeb/release/0.3.0                                                                                 | Merge tag '0.3.0' into develop                                    |  2026-06-08 06:00:35  |
|  supply-wok-platform  |  feature/restaurant-management  |   80b55d9   | feat(tables): add commands, queries and status enumeration for table management                                                                 |                                                                   |  2026-06-08 17:06:30  |
|  supply-wok-platform  |  feature/restaurant-management  |   1f2e851   | feat(tables): add operations context and repository for table management                                                                        |                                                                   |  2026-06-08 17:07:25  |
|  supply-wok-platform  |  feature/restaurant-management  |   d0d7bc6   | feat(tables): add resource and command assemblers for table creation and updates                                                                |                                                                   |  2026-06-08 17:08:27  |
|  supply-wok-platform  |  feature/restaurant-management  |   7aa7ac9   | feat(tables): implement command and query services for table management                                                                         |                                                                   |  2026-06-08 17:10:23  |
|  supply-wok-platform  |  feature/restaurant-management  |   080d896   | feat(tables): add localized operation messages for table management                                                                             |                                                                   |  2026-06-08 17:10:38  |
|  supply-wok-platform  |  feature/restaurant-management  |   b1de2d2   | feat(operations): add operations bounded context with repositories and services                                                                 |                                                                   |  2026-06-08 17:11:01  |
|  supply-wok-platform  |             develop             |   919385c   | Conflicts resolved from feature/tables to develop                                                                                               |                                                                   |  2026-06-08 17:19:10  |
|  supply-wok-platform  |             develop             |   71a025f   | feat(settings): add user-specific settings for resource editor                                                                                  |                                                                   |  2026-06-08 17:27:34  |
|  supply-wok-platform  |             master              |   3faa38d   | Merge branch 'release/0.4.0' into master                                                                                                        |                                                                   |  2026-06-08 17:33:20  |
|  supply-wok-platform  |       feature/purchasing        |   426e307   | refactor(purchasing): align purchase order architecture with context patterns                                                                   |                                                                   |  2026-06-09 06:22:45  |
|  supply-wok-platform  |             develop             |   366721e   | Merge branch 'feature/purchase-order-architecture-alignment' into develop                                                                       |                                                                   |  2026-06-09 06:32:40  |
|  supply-wok-platform  |             develop             |   13a453c   | Merge branch 'release/0.3.1'                                                                                                                    |                                                                   |  2026-06-09 06:36:56  |
|  supply-wok-platform  |             develop             |   21813b3   | Merge pull request #4 from Aurora-AplicacionesWeb/master                                                                                        | feat(merge): updating commits for prevent errors.                 |  2026-06-09 23:09:28  |
|  supply-wok-platform  |         feature/alerts          |   29e8fd0   | feat(alerts): create intefaces for command,queries; add ValueObjects and entities.                                                              |                                                                   |  2026-06-09 23:57:15  |
|  supply-wok-platform  |         feature/alerts          |   22fe8ba   | feat(alerts): implement alert context with commands, queries, and REST resources                                                                |                                                                   |  2026-06-09 23:58:07  |
|  supply-wok-platform  |         feature/alerts          |   21390e4   | feat(alerts): add resources for alert messages.                                                                                                 |                                                                   |  2026-06-09 23:58:26  |
|  supply-wok-platform  |             develop             |   7591b51   | Merge pull request #5 from Aurora-AplicacionesWeb/release/0.4.0                                                                                 | Release/0.4.0                                                     |  2026-06-10 00:00:48  |
|  supply-wok-platform  |        feature/suppliers        |   cd164e0   | feat(suppliers): add client domain and query service                                                                                            |                                                                   |  2026-06-11 07:50:58  |
|  supply-wok-platform  |        feature/suppliers        |   709d42d   | feat(suppliers): add client persistence and register context                                                                                    |                                                                   |  2026-06-11 07:52:35  |
|  supply-wok-platform  |        feature/suppliers        |   1f47b8d   | feat(suppliers): add clients interface layer                                                                                                    |                                                                   |  2026-06-11 07:53:11  |
|  supply-wok-platform  |             develop             |   c7142b2   | feat(database): create connection string for development environment database                                                                   |                                                                   |  2026-06-11 20:55:40  |
|  supply-wok-platform  |             develop             |   ff08982   | Merge pull request #8 from Aurora-AplicacionesWeb/release/0.5.0                                                                                 | Release/0.5.0                                                     |  2026-06-11 20:59:55  |
|  supply-wok-platform  |             develop             |   afa8e31   | Merge pull request #6 from Aurora-AplicacionesWeb/master                                                                                        | Merge pull request #5 from Aurora-AplicacionesWeb/release/0.4.0   |  2026-06-11 20:29:36  |
|  supply-wok-platform  |             develop             |   1817395   | Merge pull request #7 from Aurora-AplicacionesWeb/develop                                                                                       | Develop                                                           |  2026-06-11 20:29:36  |
|  supply-wok-platform  |             develop             |   c9d9321   | fix(swagger): fix swagger ui to show it                                                                                                         |                                                                   |  2026-06-11 21:26:42  |
|  supply-wok-platform  |             master              |   c80bf59   | Merge branch 'release/0.5.0' into master                                                                                                        |                                                                   |  2026-06-11 21:56:46  |
|  supply-wok-platform  |             develop             |   e1f7dbd   | Merge pull request #10 from Aurora-AplicacionesWeb/release/0.5.0                                                                                | Release/0.5.0                                                     |  2026-06-11 22:00:08  |
|  supply-wok-platform  |             develop             |   9a5b84a   | Merge pull request #11 from Aurora-AplicacionesWeb/master                                                                                       | Merge pull request #10 from Aurora-AplicacionesWeb/release/0.5.0  |  2026-06-11 22:01:18  |
|  supply-wok-platform  |             develop             |   422bec7   | Merge pull request #9 from Aurora-AplicacionesWeb/release/0.5.0                                                                                 | fix(swagger): fix swagger ui to show it                           |  2026-06-11 21:29:32  |
|  supply-wok-platform  |  feature/inventory-management   |   abded98   | feat(inventory): add folder structure for inventory application and domain layers                                                               |                                                                   |  2026-06-12 20:53:37  |
|  supply-wok-platform  |        feature/suppliers        |   ef4cb30   | feat(suppliers): implement supplier aggregate and related query services                                                                        |                                                                   |  2026-06-12 21:12:35  |
|  supply-wok-platform  |             develop             |   af73e64   | Merge branch 'release/0.6.0'                                                                                                                    |                                                                   |  2026-06-12 23:06:25  |
|  supply-wok-platform  |             develop             |   3562393   | Merge branch 'master' of https://github.com/Aurora-AplicacionesWeb/supply-wok-platform                                                          |                                                                   |  2026-06-12 23:05:49  |
|  supply-wok-platform  |             develop             |   eb647fe   | Merge branch 'feature/supplier-orders-facade' into develop. Related to Ts-SHR-001-003, TS-ORD-001-002, TS-ORD-001-001                           |                                                                   |  2026-06-12 23:44:30  |
|  supply-wok-platform  |             develop             |   dbd74be   | fix: update namespace.                                                                                                                          |                                                                   |  2026-06-12 23:53:09  |
|  supply-wok-platform  |             develop             |   fbd12d5   | Merge branch 'feature/supplier-orders-acl' into develop                                                                                         |                                                                   |  2026-06-12 23:53:44  |
|  supply-wok-platform  |             develop             |   92e3998   | Merge pull request #12 from Aurora-AplicacionesWeb/master                                                                                       | Merge branch 'release/0.6.0'                                      |  2026-06-12 23:34:33  |
|  supply-wok-platform  |             master              |   68bc4bc   | Merge branch 'release/0.6.1' into master                                                                                                        |                                                                   |  2026-06-12 23:54:40  |
|  supply-wok-platform  |  feature/inventory-management   |   d19dd90   | feat(supply): implement Supply aggregate with queries and auditing                                                                              |                                                                   |  2026-06-13 21:00:57  |
|  supply-wok-platform  |  feature/inventory-management   |   1a5ff2b   | feat(supply): add supply commands and unit of measure enumeration                                                                               |                                                                   |  2026-06-13 20:55:16  |
|  supply-wok-platform  |  feature/inventory-management   |   8b917e4   | feat(inventory): add stock movement entity, commands and queries.                                                                               |                                                                   |  2026-06-13 21:02:23  |
|  supply-wok-platform  |  feature/inventory-management   |   be5f3f1   | feat(inventory): implement command and query services for supply and stock movement.                                                            |                                                                   |  2026-06-13 21:02:58  |
|  supply-wok-platform  |  feature/inventory-management   |   d008cee   | feat(stock-movement): refactor StockMovement and Supply command services to use SupplyRepository for stock movements                            |                                                                   |  2026-06-13 22:27:14  |
|  supply-wok-platform  |  feature/inventory-management   |   21d7cb8   | feat(supply): update CreateSupplyCommand and UpdateSupplyCommand to use 'Category' parameter                                                    |                                                                   |  2026-06-13 22:26:38  |
|  supply-wok-platform  |  feature/inventory-management   |   4e86a7d   | feat(supply): add CreateSupply and UpdateSupply resources and their corresponding command assemblers                                            |                                                                   |  2026-06-13 22:28:40  |
|  supply-wok-platform  |  feature/inventory-management   |   6a977df   | feat(inventory): implement ISupplyRepository and SupplyRepository for managing supplies and stock movements                                     |                                                                   |  2026-06-13 22:29:02  |
|  supply-wok-platform  |  feature/inventory-management   |   6ce0afc   | feat(inventory): integrate Inventory context into application services and configuration                                                        |                                                                   |  2026-06-13 22:29:33  |
|  supply-wok-platform  |  feature/inventory-management   |   fb46024   | feat(inventory): implement InventoryContextFacade and GetTotalSupplyStockQuery for stock retrieval                                              |                                                                   |  2026-06-13 23:12:30  |
|  supply-wok-platform  |  feature/inventory-management   |   8d055b0   | refactor(inventory): rename namespace from Ad to Acl in InventoryContextFacade and update references                                            |                                                                   |  2026-06-14 00:34:33  |
|  supply-wok-platform  |             develop             |   9011893   | Merge branch 'feature/stock' into develop                                                                                                       |                                                                   |  2026-06-14 00:39:34  |
|  supply-wok-platform  |             master              |   5cbb494   | Merge branch 'release/0.7.0' into master                                                                                                        |                                                                   |  2026-06-14 00:52:24  |
|  supply-wok-platform  |  feature/restaurant-management  |   7db6668   | feat(dish): add dish, dish-category entities, commands, and queries for dish management in operations bounded context.                          |                                                                   |  2026-06-17 17:47:55  |
|  supply-wok-platform  |        feature/suppliers        |   59437d9   | feat(suppliers): get clients by supplier id                                                                                                     |                                                                   |  2026-06-17 23:15:29  |
|  supply-wok-platform  |           feature/iot           |   2cffd69   | refactor(iot): split alert controllers and add inventory alert flow                                                                             |                                                                   |  2026-06-17 23:31:46  |
|  supply-wok-platform  |             develop             |   92d076c   | fix: rename application ad facades to acl                                                                                                       |                                                                   |  2026-06-17 20:54:07  |
|  supply-wok-platform  |             develop             |   18177c6   | Merge remote-tracking branch 'origin/develop' into develop                                                                                      |                                                                   |  2026-06-17 20:55:07  |
|  supply-wok-platform  |  feature/restaurant-management  |   e5266ed   | feat(operations): add repositories, services, and EF configurations for dish and dish-category management                                       |                                                                   |  2026-06-18 01:58:48  |
|  supply-wok-platform  |  feature/restaurant-management  |   d9c16f3   | feat(operations): implement controllers and resource assemblers for dish and dish category management                                           |                                                                   |  2026-06-18 01:59:16  |
|  supply-wok-platform  |  feature/restaurant-management  |   6b57268   | feat(operations): add query services and extend error handling for dish category management in operations context.                              |                                                                   |  2026-06-18 01:57:56  |
|  supply-wok-platform  |             develop             |   0bde108   | chore: update migration and model definitions for initial create.                                                                               |                                                                   |  2026-06-18 02:00:20  |
|  supply-wok-platform  |             develop             |   2b147e9   | chore: update user settings and remove unused Operations domain folder in project file                                                          |                                                                   |  2026-06-18 02:00:28  |
|  supply-wok-platform  |             develop             |   31361e0   | Merge remote-tracking branch 'origin/develop' into feature/alert_controllers                                                                    |                                                                   |  2026-06-18 02:00:49  |
|  supply-wok-platform  |             develop             |   b43dcd8   | Merge branch 'feature/dish' into develop                                                                                                        |                                                                   |  2026-06-18 02:10:33  |
|  supply-wok-platform  |             master              |   bdd8336   | Merge branch 'release/0.9.0' into master                                                                                                        |                                                                   |  2026-06-18 02:15:15  |
|  supply-wok-platform  |             develop             |   22610ee   | Merge remote-tracking branch 'origin/develop' into feature/alert_controllers                                                                    |                                                                   |  2026-06-18 02:30:44  |
|  supply-wok-platform  |             develop             |   5fcd5c5   | Merge branch 'feature/alert_controllers' into develop                                                                                           |                                                                   |  2026-06-18 02:36:51  |
|  supply-wok-platform  |             master              |   abea41d   | Merge branch 'release/0.10.0' into master                                                                                                       |                                                                   |  2026-06-18 02:40:56  |
|  supply-wok-platform  |           feature/iot           |   5d37281   | feat(iot): seed alerts and expose restaurant alert sensor details                                                                               |                                                                   |  2026-06-18 06:01:21  |
|  supply-wok-platform  |             develop             |   c1de080   | Merge branch 'feature/iot-alerts' into develop                                                                                                  |                                                                   |  2026-06-18 06:02:17  |
|  supply-wok-platform  |             master              |   5e1de89   | Merge branch 'release/0.10.1' into master                                                                                                       |                                                                   |  2026-06-18 06:05:28  |
|  supply-wok-platform  |        feature/suppliers        |   8e55d7e   | feat(suppliers): add supplier catalog crud and catalog acl facade                                                                               |                                                                   |  2026-06-18 01:11:51  |
|  supply-wok-platform  |             develop             |   0c24dc5   | Merge branch 'feature/catalog' into develop                                                                                                     |                                                                   |  2026-06-18 01:14:00  |
|  supply-wok-platform  |             master              |   56e5b83   | Merge branch 'release/0.8.0' into master                                                                                                        |                                                                   |  2026-06-18 01:15:02  |
|  supply-wok-platform  |  feature/restaurant-management  |   4894e79   | feat(kitchen-order): add KitchenOrder aggregate with entities, commands, queries, and value objects for kitchen order management.               |                                                                   |  2026-06-18 17:02:09  |
|  supply-wok-platform  |  feature/restaurant-management  |   1e97476   | feat(kitchen-order): implement command and query services for KitchenOrder management.                                                          |                                                                   |  2026-06-18 17:03:28  |
|  supply-wok-platform  |  feature/restaurant-management  |   37fbffa   | feat(kitchen-order): add repository, EF configurations, and entity mappings for KitchenOrder and related items management                       |                                                                   |  2026-06-18 17:05:51  |
|  supply-wok-platform  |  feature/restaurant-management  |   cde1953   | feat(kitchen-order): implement REST controllers, resources, and assemblers for KitchenOrder management.                                         |                                                                   |  2026-06-18 17:06:14  |
|  supply-wok-platform  |  feature/restaurant-management  |   9171072   | feat(operations): add localization messages, repository, and services registration for KitchenOrder management.                                 |                                                                   |  2026-06-18 17:06:44  |
|  supply-wok-platform  |             develop             |   3a99fd8   | Merge branch 'feature/kitchen-orders' into develop                                                                                              |                                                                   |  2026-06-18 17:07:51  |
|  supply-wok-platform  |             master              |   7a79d00   | Merge branch 'release/0.11.0' into master                                                                                                       |                                                                   |  2026-06-18 17:11:08  |
|  supply-wok-platform  |             develop             |   cc46700   | Add MIT License to the project                                                                                                                  |                                                                   |  2026-06-19 08:46:36  |
|  supply-wok-platform  |             develop             |   840e091   | Merge pull request #13 from Aurora-AplicacionesWeb/license                                                                                      | Add MIT License to the project                                    |  2026-06-19 08:47:05  |
|  supply-wok-platform  |             develop             |   2db75c6   | Merge pull request #14 from Aurora-AplicacionesWeb/develop                                                                                      | Add MIT License to the project                                    |  2026-06-19 08:50:33  |
|  supply-wok-platform  |             develop             |   653b114   | feat(profile): add restaurant and supplier profile queries and commands.                                                                        |                                                                   |  2026-06-19 10:48:01  |
|  supply-wok-platform  |             develop             |   ac11497   | feat(profile): add restaurant and supplier profile command and query services.                                                                  |                                                                   |  2026-06-19 11:00:57  |
|  supply-wok-platform  |             develop             |   c2e8841   | feat(profile): add supplier profile command and query services.                                                                                 |                                                                   |  2026-06-19 11:01:32  |
|  supply-wok-platform  |             develop             |   e5e0181   | feat(profile): implement ProfilesContextFacade with command and query services for restaurant and supplier profiles.                            |                                                                   |  2026-06-19 11:02:18  |
|  supply-wok-platform  |             develop             |   f2d5783   | feat(profile): implement restaurant and supplier profile command and query services.                                                            |                                                                   |  2026-06-19 11:03:52  |
|  supply-wok-platform  |             develop             |   9c65b86   | feat(profile): update query parameters to match new user id types.                                                                              |                                                                   |  2026-06-19 11:03:20  |
|  supply-wok-platform  |             develop             |   a1a5476   | feat(profile): implement restaurant and supplier profile query services.                                                                        |                                                                   |  2026-06-19 11:04:37  |
|  supply-wok-platform  |             develop             |   faab6d1   | feat(profile): add entity framework model configuration extensions for profiles.                                                                |                                                                   |  2026-06-19 11:16:14  |
|  supply-wok-platform  |             develop             |   34e4aa7   | feat(profile): implement restaurant and supplier profile repository implementations and query services.                                         |                                                                   |  2026-06-19 11:16:35  |
|  supply-wok-platform  |         feature/shared          |   2be9cd5   | feat(shared): update query parameters to match new user id types.                                                                               |                                                                   |  2026-06-19 11:18:06  |
|  supply-wok-platform  |             develop             |   3985ad6   | feat(profile): implement restaurant and supplier profile context facade and query services.                                                     |                                                                   |  2026-06-19 11:27:38  |
|  supply-wok-platform  |             develop             |   690255a   | feat(profile): implement restaurant and supplier profile resource and command assemblers.                                                       |                                                                   |  2026-06-19 11:28:46  |
|  supply-wok-platform  |             develop             |   85ec80e   | feat(profile): implement restaurant and supplier profile resource models and record types.                                                      |                                                                   |  2026-06-19 11:28:23  |
|  supply-wok-platform  |             develop             |   b92b96e   | feat(profile): implement restaurant and supplier profile rest controllers and query services.                                                   |                                                                   |  2026-06-19 11:29:00  |
|  supply-wok-platform  |             develop             |   803ea04   | chore: ignore Rider DotSettings.user file                                                                                                       |                                                                   |  2026-06-19 11:45:30  |
|  supply-wok-platform  |             develop             |   3ab3c36   | feat: update profile bounded context services and repositories.                                                                                 |                                                                   |  2026-06-19 11:46:25  |
|  supply-wok-platform  |             develop             |   d7ba99d   | Merge branch 'feature/profile' into develop                                                                                                     |                                                                   |  2026-06-19 13:16:11  |
|  supply-wok-platform  |             master              |   80deb3a   | Merge branch 'release/0.12.0' into master                                                                                                       |                                                                   |  2026-06-19 13:23:24  |
|  supply-wok-platform  |  feature/inventory-management   |   e1aa7c6   | feat(inventory): refactor stock movement into inventory transaction with extended operations and queries.                                       |                                                                   |  2026-06-19 18:04:54  |
|  supply-wok-platform  |  feature/inventory-management   |   ec38e3c   | feat(inventory): replace stock movement with inventory transaction, adding new services, extended operations, and queries.                      |                                                                   |  2026-06-19 18:06:41  |
|  supply-wok-platform  |  feature/inventory-management   |   deff419   | feat(inventory): finalize migration from stock movement to inventory transaction with updated models, repositories, and EF configurations.      |                                                                   |  2026-06-19 18:08:12  |
|  supply-wok-platform  |  feature/inventory-management   |   f552426   | feat(inventory): implement InventoryTransaction REST controllers, resources, and assemblers with extended operations and localization support.  |                                                                   |  2026-06-19 18:09:19  |
|  supply-wok-platform  |  feature/inventory-management   |   1a2189c   | feat(inventory): add multilingual localization resources for inventory messages.                                                                |                                                                   |  2026-06-19 18:09:52  |
|  supply-wok-platform  |  feature/inventory-management   |   c5fb27e   | feat(inventory): register InventoryMessages localization and add services for InventoryTransaction operations.                                  |                                                                   |  2026-06-19 18:10:47  |
|  supply-wok-platform  |             develop             |   7dc4ebb   | chore: remove outdated migrations for aligning IoT alerts and inventory schema                                                                  |                                                                   |  2026-06-19 18:10:15  |
|  supply-wok-platform  |             develop             |   92adcc9   | chore: update EF configurations to set `longtext` mapping for string-converted enums across multiple modules.                                   |                                                                   |  2026-06-19 18:10:34  |
|  supply-wok-platform  |             develop             |   885a6df   | chore(settings): enable `InventoryMessages` localization in .DotSettings user file                                                              |                                                                   |  2026-06-19 18:16:57  |
|  supply-wok-platform  |             develop             |   6ae88d8   | Merge branch 'feature/stock-movement' into develop                                                                                              |                                                                   |  2026-06-19 18:21:55  |
|  supply-wok-platform  |             develop             |   d3733c7   | chore: update EF configurations to include `CreatedAt` and `UpdatedAt` for seed data and map `Id` in owned entities.                            |                                                                   |  2026-06-19 18:41:10  |
|  supply-wok-platform  |             develop             |   8852cf6   | feat: add migration for restaurant and supplier profiles module                                                                                 |                                                                   |  2026-06-19 18:41:45  |
|  supply-wok-platform  |             master              |   72599bd   | Merge branch 'release/0.13.0' into master                                                                                                       |                                                                   |  2026-06-19 18:43:54  |
|  supply-wok-platform  |             master              |   ba54410   | Merge branch 'release/0.13.0' into master                                                                                                       |                                                                   |  2026-06-19 18:43:53  |
|  supply-wok-platform  |             develop             |   8d2bf13   | Merge branch 'master' into develop                                                                                                              |                                                                   |  2026-06-19 18:58:49  |
|  supply-wok-platform  |             develop             |   35c3a5e   | ci(configuration): assign parameters for development and production environments.                                                               |                                                                   |  2026-06-19 19:52:19  |
|  supply-wok-platform  |             develop             |   f3cbe1f   | chore(docker): add Dockerfile to build and run Aurora.SupplyWok.Platform.                                                                       |                                                                   |  2026-06-19 20:06:05  |
|  supply-wok-platform  |             develop             |   1ef23a8   | feat(profile): add street address, email address, and person name value objects.                                                                |                                                                   |  2026-06-19 10:29:55  |
|  supply-wok-platform  |             develop             |   59bdd97   | feat(profile): add restaurant and supplier profile aggregates.                                                                                  |                                                                   |  2026-06-19 10:33:49  |
|  supply-wok-platform  |             develop             |   59dde6d   | feat(profile): add create restaurant and supplier profile commands.                                                                             |                                                                   |  2026-06-19 10:34:22  |
|  supply-wok-platform  |             develop             |   d071e53   | feat(profile): add restaurant and supplier profile queries.                                                                                     |                                                                   |  2026-06-19 10:35:17  |
|  supply-wok-platform  |             develop             |   902e8b8   | feat(profile): add supplier and restaurant profile repositories.                                                                                |                                                                   |  2026-06-19 10:35:50  |
|  supply-wok-platform  |             develop             |   846fe82   | chore: update project folders for new profiles modules.                                                                                         |                                                                   |  2026-06-19 10:36:05  |
|  supply-wok-platform  |             develop             |   a0fab97   | feat(profile): add profiles error enum and enum values.                                                                                         |                                                                   |  2026-06-19 10:36:22  |
|  supply-wok-platform  |             develop             |   436cbe8   | Merge branch 'release/0.13.1' into master                                                                                                       |                                                                   |  2026-06-19 23:19:22  |
|  supply-wok-platform  |             master              |   2cb2d58   | Merge branch 'release/0.13.1' into master                                                                                                       |                                                                   |  2026-06-19 23:19:23  |
|  supply-wok-platform  |             develop             |   c783443   | Merge branch 'master' into develop                                                                                                              |                                                                   |  2026-06-19 23:20:46  |
|  supply-wok-platform  |             develop             |   e672962   | chore(migrations): remove initial database migration file.                                                                                      |                                                                   |  2026-06-19 23:18:08  |
|  supply-wok-platform  |             develop             |   ca747f6   | feat(migrations): create initial database schema with multiple tables                                                                           |                                                                   |  2026-06-19 23:40:20  |
|  supply-wok-platform  |             develop             |   54250c2   | Merge branch 'release/0.13.2' into master                                                                                                       |                                                                   |  2026-06-19 23:40:44  |
|  supply-wok-platform  |             master              |   3ee0203   | Merge branch 'release/0.13.2' into master                                                                                                       |                                                                   |  2026-06-19 23:40:43  |
|  supply-wok-platform  |        feature/analytics        |   c4478c5   | feat(analytics): add analytics context with migration for restaurant and supplier analytics tables                                              |                                                                   |  2026-06-20 05:41:03  |
|  supply-wok-platform  |         feature/alerts          |   69d79e8   | refactor(alerts): remove unused alert assemblers and resources; streamline alert handling logic                                                 |                                                                   |  2026-06-20 05:00:18  |
|  supply-wok-platform  |             develop             |   9130f0c   | Merge pull request #15 from Aurora-AplicacionesWeb/feature/analytics                                                                            | Feature/analytics                                                 |  2026-06-20 05:44:27  |
|  supply-wok-platform  |             develop             |   3a3d33a   | Merge pull request #16 from Aurora-AplicacionesWeb/develop                                                                                      | Develop                                                           |  2026-06-20 06:48:32  |
|  supply-wok-platform  |  feature/restaurant-management  |   7205064   | feat(kitchen-orders): add support for listing kitchen orders with items included.                                                               |                                                                   |  2026-06-20 21:29:30  |
|  supply-wok-platform  |  feature/inventory-management   |   73bf618   | feat(inventory): improve validation and error handling for supply commands, add logging, and configure JSON enum serialization.                 |                                                                   |  2026-06-20 21:29:43  |
|  supply-wok-platform  |             develop             |   01eae3b   | Merge branch 'release/0.13.3' into master                                                                                                       |                                                                   |  2026-06-20 21:33:04  |
|  supply-wok-platform  |             master              |   09ca317   | Merge branch 'release/0.13.3' into master                                                                                                       |                                                                   |  2026-06-20 21:33:03  | 


#### 5.2.3.5. Execution Evidence for Sprint Review

Durante el Sprint 3 se completó la implementación y validación de los principales servicios backend de SupplyWok correspondientes a los bounded contexts priorizados del núcleo del negocio. Como parte de la revisión del sprint, se verificó el correcto funcionamiento de los endpoints REST desarrollados mediante pruebas realizadas en Swagger, comprobando la ejecución satisfactoria de las operaciones expuestas por la API. Además, se validó la persistencia de la información en la base de datos MySql mediante MySql Workbench.

![Trello Sprint 3 Board 1](../assets/images/trello_11.png)
![Trello Sprint 3 Board 2](../assets/images/trello_22.png)
![Trello Sprint 3 Board 3](../assets/images/trello_33.png)
![Backend Swagger](../assets/images/deploy-steps/swagger_1.png)

**Link del vídeo de explicación del Execution:** [Vídeo del Sprint](https://youtu.be/olHC8_y3YLo)

#### 5.2.3.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 3 se documentaron los servicios web desarrollados para los bounded contexts priorizados de SupplyWok utilizando Swagger. La documentación generada permite visualizar y comprender la estructura de los endpoints implementados, incluyendo los métodos HTTP soportados, parámetros de entrada, cuerpos de solicitud, respuestas esperadas y códigos de estado asociados. A continuación, se presenta el detalle de los endpoints documentados, los enlaces correspondientes a la documentación generada y evidencias de interacción utilizando datos de prueba.

- **Repository URL:** https://github.com/Aurora-AplicacionesWeb/supply-wok-platform
- **Swagger URL:** https://supply-wok-platform-cgbs.onrender.com/swagger/index.html

|                            Endpoint                            |                Action                |  HTTP Verb  |                                              Parameters                                              |                       Response Example                       |                         Documentation URL                          |
|:--------------------------------------------------------------:|:------------------------------------:|:-----------:|:----------------------------------------------------------------------------------------------------:|:------------------------------------------------------------:|:------------------------------------------------------------------:|
|          /api/v1/suppliers/{supplierId}/catalog-items          |  Create catalog item for a supplier  |    POST     |                   supplierId (integer, Required), body: CreateCatalogItemResource                    |       201: The catalog item was created successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|          /api/v1/suppliers/{supplierId}/catalog-items          |    Get catalog items by supplier     |     GET     |                                    supplierId (integer, Required)                                    |          200: Catalog items retrieved successfully.          |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|  /api/v1/suppliers/{supplierId}/catalog-items/{catalogItemId}  |        Get catalog item by ID        |     GET     |                  supplierId (integer, Required), catalogItemId (integer, Required)                   |        200: The catalog item was found and returned.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|  /api/v1/suppliers/{supplierId}/catalog-items/{catalogItemId}  |         Update catalog item          |     PUT     |  supplierId (integer, Required), catalogItemId (integer, Required), body: UpdateCatalogItemResource  |       200: The catalog item was updated successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|  /api/v1/suppliers/{supplierId}/catalog-items/{catalogItemId}  |         Delete catalog item          |   DELETE    |                  supplierId (integer, Required), catalogItemId (integer, Required)                   |       204: The catalog item was deleted successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|             /api/v1/suppliers/{supplierId}/clients             |       Get clients by supplier        |     GET     |                                    supplierId (integer, Required)                                    |             200: Clients retrieved successfully.             |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/dish-categories                     |         Get dish categories          |     GET     |                                                  -                                                   |         200: Dish categories retrieved successfully.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                         /api/v1/dishes                         |              Get dishes              |     GET     |                                                  -                                                   |             200: Dishes retrieved successfully.              |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                 /api/v1/inventory-transactions                 |     Create inventory transaction     |    POST     |                               body: CreateInventoryTransactionResource                               |   201: The inventory transaction was created successfully.   |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                 /api/v1/inventory-transactions                 |      Get inventory transactions      |     GET     |                                                  -                                                   |     200: Inventory transactions retrieved successfully.      |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|    /api/v1/inventory-transactions/{inventoryTransactionId}     |   Get inventory transaction by ID    |     GET     |                              inventoryTransactionId (integer, Required)                              |    200: The inventory transaction was found and returned.    |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|      /api/v1/inventory-transactions/by-supply/{supplyId}       |      Get transactions by supply      |     GET     |                                     supplyId (integer, Required)                                     |     200: Inventory transactions retrieved successfully.      |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                     /api/v1/kitchen-orders                     |         Create kitchen order         |    POST     |                                   body: CreateKitchenOrderResource                                   |       201: The kitchen order was created successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                     /api/v1/kitchen-orders                     |          Get kitchen orders          |     GET     |                                                  -                                                   |         200: Kitchen orders retrieved successfully.          |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/kitchen-orders/{id}                   |       Get kitchen order by ID        |     GET     |                                        id (integer, Required)                                        |        200: The kitchen order was found and returned.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/kitchen-orders/{id}                   |         Update kitchen order         |     PUT     |                       id (integer, Required), body: CreateKitchenOrderResource                       |       200: The kitchen order was updated successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/kitchen-orders/{id}                   |         Delete kitchen order         |   DELETE    |                                        id (integer, Required)                                        |       204: The kitchen order was deleted successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|               /api/v1/kitchen-orders/{id}/status               |     Update kitchen order status      |     PUT     |                    id (integer, Required), body: UpdateKitchenOrderStatusResource                    |   200: The kitchen order status was updated successfully.    |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|               /api/v1/kitchen-orders/{id}/dishes               |      Add dish to kitchen order       |    POST     |                     id (integer, Required), body: AddDishToKitchenOrderResource                      |  200: The dish was added to the kitchen order successfully.  |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/purchase-orders                     |        Create purchase order         |    POST     |                                  body: CreatePurchaseOrderResource                                   |      201: The purchase order was created successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/purchase-orders                     |         Get purchase orders          |     GET     |                                                  -                                                   |         200: Purchase orders retrieved successfully.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|           /api/v1/purchase-orders/{purchaseOrderId}            |       Get purchase order by ID       |     GET     |                                 purchaseOrderId (integer, Required)                                  |       200: The purchase order was found and returned.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|           /api/v1/purchase-orders/{purchaseOrderId}            |        Update purchase order         |     PUT     |                purchaseOrderId (integer, Required), body: UpdatePurchaseOrderResource                |      200: The purchase order was updated successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|           /api/v1/purchase-orders/{purchaseOrderId}            |        Delete purchase order         |   DELETE    |                                 purchaseOrderId (integer, Required)                                  |      204: The purchase order was deleted successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|        /api/v1/purchase-orders/{purchaseOrderId}/status        |     Update purchase order status     |     PUT     |             purchaseOrderId (integer, Required), body: UpdatePurchaseOrderStatusResource             |   200: The purchase order status was updated successfully.   |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/restaurant/alerts                    |        Get restaurant alerts         |     GET     |                                                  -                                                   |        200: Restaurant alerts retrieved successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|              /api/v1/restaurant/alerts/{alertId}               |      Get restaurant alert by ID      |     GET     |                                     alertId (integer, Required)                                      |            200: The alert was found and returned.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|        /api/v1/restaurant/alerts/{alertId}/acknowledge         |     Acknowledge restaurant alert     |    POST     |                                     alertId (integer, Required)                                      |        200: The alert was acknowledged successfully.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/analytics/restaurant                  |       Get restaurant analytics       |     GET     |                                                  -                                                   |      200: Restaurant analytics retrieved successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/restaurant-profiles                   |      Create restaurant profile       |    POST     |                                body: CreateRestaurantProfileResource                                 |    201: The restaurant profile was created successfully.     |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/restaurant-profiles                   |       Get restaurant profiles        |     GET     |                                                  -                                                   |       200: Restaurant profiles retrieved successfully.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|       /api/v1/restaurant-profiles/{restaurantProfileId}        |     Get restaurant profile by ID     |     GET     |                               restaurantProfileId (integer, Required)                                |     200: The restaurant profile was found and returned.      |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|          /api/v1/restaurant-profiles/by-user/{userId}          |    Get restaurant profile by user    |     GET     |                                      userId (integer, Required)                                      |     200: The restaurant profile was found and returned.      |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                        /api/v1/sensors                         |            Create sensor             |    POST     |                                      body: CreateSensorResource                                      |          201: The sensor was created successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                        /api/v1/sensors                         |             Get sensors              |     GET     |                                                  -                                                   |             200: Sensors retrieved successfully.             |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/sensors/{sensorId}                   |           Get sensor by ID           |     GET     |                                     sensorId (integer, Required)                                     |           200: The sensor was found and returned.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/sensors/{sensorId}                   |            Update sensor             |     PUT     |                       sensorId (integer, Required), body: UpdateSensorResource                       |          200: The sensor was updated successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/sensors/{sensorId}                   |            Delete sensor             |   DELETE    |                                     sensorId (integer, Required)                                     |          204: The sensor was deleted successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/supplier/alerts                     |         Get supplier alerts          |     GET     |                                                  -                                                   |         200: Supplier alerts retrieved successfully.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|               /api/v1/supplier/alerts/{alertId}                |       Get supplier alert by ID       |     GET     |                                     alertId (integer, Required)                                      |            200: The alert was found and returned.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|         /api/v1/supplier/alerts/{alertId}/acknowledge          |      Acknowledge supplier alert      |    POST     |                                     alertId (integer, Required)                                      |        200: The alert was acknowledged successfully.         |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/analytics/supplier                   |        Get supplier analytics        |     GET     |                                                  -                                                   |       200: Supplier analytics retrieved successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/supplier-profiles                    |       Create supplier profile        |    POST     |                                 body: CreateSupplierProfileResource                                  |     201: The supplier profile was created successfully.      |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                   /api/v1/supplier-profiles                    |        Get supplier profiles         |     GET     |                                                  -                                                   |        200: Supplier profiles retrieved successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|         /api/v1/supplier-profiles/{supplierProfileId}          |      Get supplier profile by ID      |     GET     |                                supplierProfileId (integer, Required)                                 |      200: The supplier profile was found and returned.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|           /api/v1/supplier-profiles/by-user/{userId}           |     Get supplier profile by user     |     GET     |                                      userId (integer, Required)                                      |      200: The supplier profile was found and returned.       |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                       /api/v1/suppliers                        |            Get suppliers             |     GET     |                                                  -                                                   |            200: Suppliers retrieved successfully.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                        /api/v1/supplies                        |            Create supply             |    POST     |                                      body: CreateSupplyResource                                      |          201: The supply was created successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                        /api/v1/supplies                        |             Get supplies             |     GET     |                                                  -                                                   |            200: Supplies retrieved successfully.             |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/supplies/total-stock                  |           Get total stock            |     GET     |                                                  -                                                   |           200: Total stock retrieved successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/supplies/{supplyId}                   |           Get supply by ID           |     GET     |                                     supplyId (integer, Required)                                     |           200: The supply was found and returned.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/supplies/{supplyId}                   |            Update supply             |     PUT     |                       supplyId (integer, Required), body: UpdateSupplyResource                       |          200: The supply was updated successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                  /api/v1/supplies/{supplyId}                   |            Delete supply             |   DELETE    |                                     supplyId (integer, Required)                                     |          204: The supply was deleted successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                         /api/v1/tables                         |             Create table             |    POST     |                                      body: CreateTableResource                                       |           201: The table was created successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                         /api/v1/tables                         |              Get tables              |     GET     |                                                  -                                                   |             200: Tables retrieved successfully.              |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/tables/{tableId}                    |           Get table by ID            |     GET     |                                     tableId (integer, Required)                                      |            200: The table was found and returned.            |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/tables/{tableId}                    |             Update table             |     PUT     |                        tableId (integer, Required), body: UpdateTableResource                        |           200: The table was updated successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|                    /api/v1/tables/{tableId}                    |             Delete table             |   DELETE    |                                     tableId (integer, Required)                                      |           204: The table was deleted successfully.           |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |

#### 5.2.3.7. Software Deployment Evidence for Sprint Review

En esta sección se muestra el deploy de los componentes backend de SupplyWok implementados en la plataforma Aurora-AplicacionesWeb en la plataforma Render junto con el deploy de la base de datos en la plataforma Filess.

**Backend Deployment:**

1. Entramos a la página de Render: https://render.com/. Iniciamos sesión con cualquier cuenta (Google, Github, Microsoft, etc.). Nos dirigimos a la sección "Projects" y damos clics al botón "New" y escogemos la opción "Web Service".
![Backend Deploy 1](../assets/images/deploy-steps/deploy_backend_2.png)

2. Después de rellenar todos los campos, empezamos a realizar el deploy y saldrá la siguiente vista, donde se tendrá que esperar hasta que termine el proceso de deploy.
![Backend Deploy 2](../assets/images/deploy-steps/deploy_backend_1.png)

**Backend Deployment URL:** [https://supply-wok-platform-cgbs.onrender.com/swagger/index.html](https://supply-wok-platform-cgbs.onrender.com/swagger/index.html)

**Database Deployment:**
![Database Deploy](../assets/images/deploy-steps/database_deploy.png)

**Frontend Deployment:**

**Link del Deploy del Frontend:** [https://supplywok.web.app/](https://supplywok.web.app/)

#### 5.2.3.8. Team Collaboration Insights during Sprint

Durante el Sprint 3, el equipo trabajó de manera colaborativa en el desarrollo de los servicios backend de SupplyWok utilizando una estrategia basada en ramas de Git y GitHub. Las tareas fueron distribuidas entre los integrantes de acuerdo con los bounded contexts priorizados, permitiendo que cada miembro asumiera la responsabilidad principal de un área específica del negocio. En este sprint, todos los integrantes contribuyeron activamente mediante commits, revisiones e integración de cambios en el repositorio del proyecto. A continuación, se presentan evidencias de colaboración obtenidas a partir de los analíticos de GitHub, incluyendo contribuciones, historial de commits y actividad realizada durante el sprint.

![Sprint 3 Insight Graphic 1](../assets/images/deploy-steps/contributions_22.png) 

Como se observa en la sección Contributors del repositorio backend, durante el Sprint 3 se realizaron un total de 169 commits, reflejando una participación activa por parte de los miembros del equipo en el desarrollo de los servicios y endpoints de la plataforma.

![Sprint 3 Insight Graphic 2](../assets/images/deploy-steps/contributions_23.png)

Como se observa en el detalle de la sección Contributors, todos los integrantes realizaron contribuciones al repositorio. En promedio, cada miembro efectuó aproximadamente 20 commits y contribuyó con alrededor de 28040 líneas de código agregadas, evidenciando una distribución equilibrada del trabajo durante el sprint.

![Sprint 3 Insight Graphic 3](../assets/images/deploy-steps/pulse_11.png)

Como se observa en la sección Pulse del repositorio backend, durante la última semana se integraron 4 Pull Requests y se registraron 60 commits excluyendo merges. Asimismo, la rama principal del proyecto acumuló 10195 líneas agregadas y 1641 líneas eliminadas, reflejando el avance significativo realizado en la implementación de los bounded contexts y servicios backend planificados para este sprint.

### 5.2.4. Sprint 4: 

En esta sección se explicará y registrará el desarrollo del Sprint 4, se estableció como objetivo terminar y arreglar los defectos identificados tras la entrega del sprint anterior, esto incluye al web service, web application y landing page.

#### 5.2.4.1. Sprint Planning 4

Durante la reunion del Sprint Planning referente al Sprint 4, se estableció terminar el 30% restante del web service y conectarlo con la vista del cliente que seria el web application de la plataforma.

**Sprint Planning 4**


| **Sprint #**                       | 4                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Date**                           | 2026-06-28                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Time**                           | 19:00                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Location**                       | Virtual, Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Prepared by**                    | Marcelo Cuadros, Juan Wang                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Attendees**                      | Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Sprint 3 Review Summary**        | Durante el Sprint 2 se completó el desarrollo de la aplicación frontend utilizando una Fake API para simular la comunicación con los servicios backend. Se implementaron las principales interfaces y flujos de usuario previstos para la plataforma, obteniendo resultados satisfactorios en términos de funcionalidad, organización del código y experiencia de usuario. Como parte del feedback recibido, se destacó la calidad de la implementación realizada; sin embargo, se recomendó fortalecer la documentación técnica del proyecto para facilitar su comprensión, mantenimiento y futura integración con los servicios backend reales.                                                                                                                                                                                                                      |
| **Sprint 3 Retrospective Summary** | El equipo considero ordenar mejor los tiempos de entrega para cada miembro del equipo con el fin de no resulte en un trabajo apresurado que pueda llamar a errores, asimismo se notificó mejorar la documentación de la plataforma para mantener la construccion de la plataforma detallada y correcta para su lectura, esto con el fin de mejorar la comunicaion en el proyecto para nuevos y viejos integrantes que quieran modificar o revisar la plataforma realizada.                                                                                                                                                                                                                                                                                                                                                                                             |
| **Sprint 4 Goal**                  | Nuestro enfoque se centra en implementar un sistema de autenticación robusto y habilitar la facturación automatizada, proporcionando a los usuarios de Supply Wok un acceso seguro a la plataforma y control total sobre sus planes de suscripción. Creemos que esto proporciona a los clientes una experiencia de incorporación confiable junto con total autonomía en el manejo de su información financiera, y establece para el equipo de desarrollo la infraestructura crítica de seguridad y monetización requerida para la viabilidad comercial del producto. Esto se confirmará cuando los usuarios puedan registrarse e iniciar sesión exitosamente validando su identidad, puedan suscribirse o actualizar planes de pago; y la aplicación web actualice estos estados de acceso y facturación en tiempo real comunicándose correctamente con el Web Service |
| **Sprint 4 Velocity**              | Límite de **45 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sum of Story Points**            | **26 SP**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

**Link del Sprint 4 Board:** [https://tinyurl.com/yvj3y3bj](https://tinyurl.com/yvj3y3bj)

#### 5.2.4.2. Aspect Leaders and Collaborators.

En esta sección se presenta la matriz de liderazgo y colaboración correspondiente al Sprint 3. Dado que el objetivo principal de esta iteración es avanzar en el desarrollo backend de SupplyWok, los aspectos considerados corresponden a los bounded contexts de negocio. Para cada aspecto se asigna un líder responsable de coordinar el desarrollo y uno o más colaboradores encargados de apoyar en la implementación, validación y pruebas de los servicios y endpoints asociados.

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

|     Team Member     |  Github Username  |  Inventory Management Bounded Context  | Procurement & Purchasing Bounded Context |  Operations Bounded Context  |  IoT Operational Monitoring & Alerts Bounded Context  | Supplier Panel Bounded Context | Identity And Access Management Bounded Context | Profiles Bounded Context | Analytics Bounded Context |
|:-------------------:|:-----------------:|:--------------------------------------:|:----------------------------------------:|:----------------------------:|:-----------------------------------------------------:|:------------------------------:|:----------------------------------------------:|:------------------------:|:-------------------------:|
|   Cuadros, Macelo   |  Marcelo-alt-lab  |                   -                    |                    -                     |              -               |                           L                           |               -                |                       L                        |            -             |             L             | 
|    Ayasta, Zayd     |    Zayd Ayasta    |                   -                    |                    L                     |              -               |                           -                           |               -                |                       -                        |            -             |             -             |
|     Wang, Juan      |       jwd3t       |                   -                    |                    -                     |              -               |                           -                           |               L                |                       C                        |            C             |             -             | 
|  Sánchez, Mathias   |      Nounz27      |                   L                    |                    -                     |              L               |                           -                           |               -                |                       -                        |            -             |             C             |
|  Cayanchi, Milenko  |      MaxghZZ      |                   -                    |                    -                     |              -               |                           -                           |               C                |                       C                        |            L             |             -             |


#### 5.2.4.3. Sprint Backlog 4

|    US ID     | US Title                                                                                                                                |     Task Id      | Task Title                                                         | Description                                                                                                                                                          |                                 Assigned To                                  |  Estimation (Hours)  |   Status    |
|:------------:|:----------------------------------------------------------------------------------------------------------------------------------------|:----------------:|:-------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------:|:--------------------:|:-----------:|
|  TS-IAM-001  | Como desarrollador frontend, Quiero que el acceso de los usuarios sea seguro, Para asegurar los procesos de los usuarios segun el rol.  |  TS-SHR-001-001  | Create Shared directory                                            | Create `Shared` directory within `Domain`, `Infrastructure` and `Application`.                                                                                       |  Marcelo Cuadros, Zayd Ayasta, Juan Wang, Mathias Sanchez, Milenko Cayanchi  |          1           |    Done     |

#### 5.2.4.4. Development Evidence for Sprint Review.

#### 5.2.4.5. Execution Evidence for Sprint Review.

Durante el Sprint 4 se finalizó los servicios web backend de SupplyWok, ádemas de modificar y corregir el frontend de la plataforma para que no halla errores entre al aplicacion y el servicio web de Supply Wok, esto añadiendo nuevos endpoints y métodos REST corregidos con respecto al sprint anterior que se detallaran a continuación.

- **Repository URL:** https://github.com/Aurora-AplicacionesWeb/supply-wok-platform
- **Swagger URL:** https://supply-wok-platform-cgbs.onrender.com/swagger/index.html

|                            Endpoint                            |                Action                |  HTTP Verb  |                                              Parameters                                              |                       Response Example                       |                         Documentation URL                          |
|:--------------------------------------------------------------:|:------------------------------------:|:-----------:|:----------------------------------------------------------------------------------------------------:|:------------------------------------------------------------:|:------------------------------------------------------------------:|
|          /api/v1/suppliers/{supplierId}/catalog-items          |  Create catalog item for a supplier  |    POST     |                   supplierId (integer, Required), body: CreateCatalogItemResource                    |       201: The catalog item was created successfully.        |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |
|          /api/v1/suppliers/{supplierId}/catalog-items          |    Get catalog items by supplier     |     GET     |                                    supplierId (integer, Required)                                    |          200: Catalog items retrieved successfully.          |  https://supply-wok-platform-cgbs.onrender.com/swagger/index.html  |


#### 5.2.4.6. Services Documentation Evidence for Sprint Review.

#### 5.2.4.7. Software Deployment Evidence for Sprint Review.

#### 5.2.4.8. Team Collaboration Insights during Sprint.

En esta sección se presentarán las versiones actualizadas de los aportes a la plataforma Supply Wok, lo cual incluira los aportes en Landing Page, Frontend y Backend. La forma para mostrar este avance será usando las analiticas por commits del repositorio respectivo de Github.

##### Landing Page

Durante el Sprint 4 el equipo hizo cambios en la Landing Page de Supply Wok enfocado en ajustes visuales y léxicos para mantener un enfoque claro respecto a la plataforma.

![Sprint 4 Landing Page](../assets/images/insights/sprint-4-lpi.png)

![Sprint 4 Landing Page](../assets/images/insights/sprint-4-lpi-2.png)

##### Frontend

Los cambios aplicados en el Frontend de Supply Wok durante este sprint son en consecuencia de la construcción del web service, para que emitan y reciban el mismo esquema de información en formato json.

![Sprint 4 Frontend](../assets/images/insights/sprint-4-fi.png)

![Sprint 4 Frontend](../assets/images/insights/sprint-4-fi-2.png)

##### Backend

El enfoque del Sprint 4 ya fue explicado anteriormente, por lo que se mostrara directamente la evidencia de la participación del equipo en el desarrollo del web service.

![Sprint 4 Backend](../assets/images/insights/sprint-4-bi.png)

![Sprint 4 Backend](../assets/images/insights/sprint-4-bi-2.png)

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
- ¿Usarías una aplicación como está en la vida real? ¿Por qué?
- ¿Qué cambiarías o mejorarías?

### 5.3.2. Registro de Entrevistas.
En esta sección se presenta el registro de las sesiones de validación realizadas con representantes de los segmentos objetivo. Cada sesión permitió observar cómo los usuarios interactuaron con la Landing Page y con la Web Application, así como registrar comentarios, dudas y observaciones generadas durante la navegación.

Las entrevistas de validación fueron registradas en video y consolidadas en un único material de evidencia, siguiendo las indicaciones del project statement. En cada caso se documenta la información del participante, el segmento representado, la fecha de la sesión y un resumen de los principales hallazgos obtenidos.

**Video consolidado de validación**
- **Enlace en Microsoft Stream:** [Vídeo de Validación](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6)
- **Captura de evidencia:**  
  ![captura](../assets/images/validation/entrevista1.png)

### Segmento Objetivo Restaurantes

#### Entrevista de validación #1
![alt text](../assets/images/validation/entrevista1.png)

**Resumen de la sesión:**

El primer entrevistado Weiquan Wang, un dueño de restaurante de 55 años ubicado en el Callao, logró comprender la idea general de la landing page y también el flujo principal de la aplicación, especialmente las pantallas de inventario, pedidos, comandas, mesas y alertas. Su percepción general fue positiva, ya que consideró que el sistema era fácil de usar y que podría manejarlo sin demasiada dificultad; sin embargo, aportó una observación importante sobre el módulo de pedidos, indicando que sería más práctico no agregar productos uno por uno, sino contar con una forma más rápida de seleccionar varios insumos en una sola acción.

|           Detalle           | Información                                                  |
|:---------------------------:|:-------------------------------------------------------------|
|      **Entrevistador**      | Juan Sung Jau Wang Chen                                      |
|      **Entrevistado**       | Weiquan Wang                                                 |
|    **Segmento objetivo**    | Restaurante                                                  |
|          **Edad**           | 55                                                           |
|        **Ubicación**        | La Perla, Callao                                             |
|  **Duración / Empieza en**  | [14:18 minutos] / [0:00]                                     |
|         **Enlace**          | [https://tinyurl.com/53azn8f8](https://tinyurl.com/53azn8f8) |

*Tabla. Registro de validación 1*

#### Entrevista de validación #2
![alt text](../assets/images/validation/entrevista2.png)

**Resumen de la sesión:**

La segunda entrevistada Ana Chen, una dueña de restaurante de 50 años de Callao, entendió de forma clara las funciones principales de la aplicación, sobre todo el inventario, la creación de órdenes a proveedores, los tickets de cocina, la gestión de mesas y las alertas. Comentó que el sistema le parecía sencillo y fácil de seguir, sin encontrar grandes dificultades en su uso; no obstante, brindó una sugerencia bastante valiosa al señalar que, en la sección de pedidos, sería más útil manejar horarios de entrega además de la prioridad, ya que en la práctica casi todos los pedidos se consideran importantes y lo realmente decisivo suele ser el momento en que deben recibirse.

|           Detalle           | Información                                                                                                                                                      |
|:---------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **Entrevistador**      | Juan Sung Jau Wang Chen                                                                                                                                          |
|      **Entrevistado**       | Ana Chen                                                                                                                                                         |
|    **Segmento objetivo**    | Restaurante                                                                                                                                                      |
|          **Edad**           | 50                                                                                                                                                               |
|        **Ubicación**        | La Perla, Callao                                                                                                                                                 |
|  **Duración / Empieza en**  | [12 minutos] / [14:20]                                                                                                                                           |
|         **Enlace**          | [https://tinyurl.com/53azn8f8](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 2*

#### Entrevista de validación #3

![alt text](../assets/images/validation/entrevista3.png)

**Resumen de la sesión:**

La tercera entrevistada, Lili, de 54 años y dueña de un restaurante chifa en La Perla, mostró una validación claramente favorable tanto de la landing page como de la aplicación. Después de revisar las pantallas principales, afirmó que la plataforma le parecía útil para su trabajo diario, que el flujo era entendible y que no percibía confusión importante en el uso de las funciones. Entre todos los módulos presentados, destacó especialmente el de alertas como la parte que más le interesó, señalando además que sí utilizaría la aplicación en un contexto real y que, al menos en esta etapa, no veía cambios urgentes que realizar.

|           Detalle           | Información                                                                                                                                                      |
|:---------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **Entrevistador**      | Juan Sung Jau Wang Chen                                                                                                                                          |
|      **Entrevistado**       | Lily 蔡                                                                                                                                                           |
|    **Segmento objetivo**    | Restaurante                                                                                                                                                      |
|          **Edad**           | 54                                                                                                                                                               |
|        **Ubicación**        | La Perla, Callao                                                                                                                                                 |
|  **Duración / Empieza en**  | [8 minutos] / [26:18]                                                                                                                                            |
|         **Enlace**          | [https://tinyurl.com/53azn8f8](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 3*


### Segmento Objetivo Proveedores

#### Entrevista de validación #4
![alt text](../assets/images/validation/entrevista4.png)

**Resumen de la sesión:**

El cuarto entrevistado, Alberto Copa Villa, de 37 años, trabajador de una carnicería en La Perla y representante del perfil proveedor, valoró de manera positiva la propuesta para este segundo segmento de usuarios, especialmente en las pantallas de órdenes, clientes, delivery planning, alertas, demanda y catálogo. Indicó que las funcionalidades que más le llamaron la atención fueron las alertas, el control del stock y la planificación de rutas, ya que las percibió como herramientas útiles para el trabajo real de un proveedor. Además, propuso dos mejoras importantes: reemplazar o complementar la prioridad de las órdenes con horarios de entrega más concretos, y añadir dentro de la misma aplicación una función de mensajería o chat tipo WhatsApp para comunicarse con los restaurantes sin depender de otros medios externos.

|           Detalle           | Información                                                                                                                                                      |
|:---------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **Entrevistador**      | Juan Sung Jau Wang Chen                                                                                                                                          |
|      **Entrevistado**       | Alberto Copa Villa                                                                                                                                               |
|    **Segmento objetivo**    | Proveedor                                                                                                                                                        |
|          **Edad**           | 37                                                                                                                                                               |
|        **Ubicación**        | La Perla, Callao                                                                                                                                                 |
|  **Duración / Empieza en**  | [8 minutos] / [34:00]                                                                                                                                            |
|         **Enlace**          | [https://tinyurl.com/53azn8f8](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202318609_upc_edu_pe/IQBNPmcdTVCFRIyAVH7xDnAtAXWfSILtxJUzz8KwcBEKa64?e=iLzLn6) |

*Tabla. Registro de validación 3*


### 5.3.3. Evaluaciones según heurísticas.
Como complemento a la observación de las sesiones de validación, el equipo realizó una evaluación de experiencia de usuario basada en heurísticas. Esta revisión tomó como referencia los criterios de usabilidad, diseño inclusivo y arquitectura de información indicados en el project statement del curso.

El objetivo de esta evaluación fue sistematizar los principales problemas detectados durante la interacción de los usuarios con la Landing Page y la Web Application, asignándoles un nivel de severidad y relacionándolos con la heurística o principio incumplido. De este modo, los hallazgos cualitativos obtenidos en las entrevistas de validación pudieron complementarse con una revisión experta centrada en identificar oportunidades concretas de mejora para la siguiente iteración del producto.

**Aplicación evaluada**

- **Site o app a evaluar:** SupplyWok
- **Auditor:** Aurora
- **Clientes participantes:** Usuarios de los segmentos restaurante y proveedor entrevistados durante la validación

**Tareas evaluadas**

- Comprender la propuesta de valor de la Landing Page.
- Navegar hacia la Web Application desde los Call To Action.
- Reconocer el propósito del dashboard según el rol del usuario.
- Ubicar funcionalidades principales del sistema.
- Interpretar información clave en vistas como inventario, pedidos, clientes o catálogo.

**Escala de severidad utilizada**

|  Nivel  | Descripción                                                                          |
|:-------:|:-------------------------------------------------------------------------------------|
|    1    | Problema superficial que no afecta significativamente la experiencia.                |
|    2    | Problema menor que genera fricción, pero puede ser superado por el usuario.          |
|    3    | Problema mayor que ocurre con frecuencia o dificulta seriamente completar la tarea.  |
|    4    | Problema muy grave que impide continuar con el uso de la herramienta.                |

**Tabla resumen de hallazgos**

|  #  | Problema                                                                                              |  Escala de severidad  |  Heurística o principio violado  |
|:---:|:------------------------------------------------------------------------------------------------------|:---------------------:|:--------------------------------:|
|  1  | La aplicación no ofrece una guía inicial ni ayuda contextual para usuarios nuevos.                    |           3           |      Ayuda y documentación       |
|  2  | No existen diálogos de confirmación antes de ejecutar acciones destructivas como eliminar registros.  |           4           |      Prevención de errores       |
|  3  | Se identificaron inconsistencias visuales entre pantallas, componentes y estilos del sistema.         |           2           |    Consistencia y estándares     |

**Descripción de problemas**

**Problema #1: Ausencia de guía de uso o acompañamiento inicial**

- **Severidad:** 3
- **Heurística violada:** Ayuda y documentación
- **Problema:** Durante la evaluación se observó que la aplicación no brinda una orientación inicial para usuarios nuevos. No se encontraron mensajes introductorios, explicaciones contextuales ni elementos que indiquen con claridad cómo iniciar el uso de los módulos principales. Esto puede dificultar la adopción de la plataforma, especialmente para usuarios que ingresan por primera vez y aún no conocen la lógica del sistema ni el propósito de cada sección.
- **Recomendación:** Incorporar una breve guía de bienvenida, textos de apoyo o mensajes contextuales que orienten al usuario sobre el propósito de cada módulo y las acciones principales que puede realizar.

![heuristic-problem-1](../assets/images/heuristic1.png)

**Problema #2: Falta de confirmación antes de eliminar información**

- **Severidad:** 4
- **Heurística violada:** Prevención de errores
- **Problema:** Se identificó que la aplicación no presenta un cuadro de confirmación antes de ejecutar acciones irreversibles como la eliminación de registros. Esta situación representa un riesgo importante, ya que el usuario puede borrar información por equivocación sin una oportunidad previa para cancelar la acción. La ausencia de esta validación reduce la sensación de control y puede ocasionar pérdida accidental de datos.
- **Recomendación:** Implementar diálogos de confirmación antes de eliminar elementos, con mensajes claros sobre la acción que se va a realizar y opciones visibles para confirmar o cancelar.

![heuristic-problem-2](../assets/images/heuristic21.png)
![heuristic-problem-22](../assets/images/heuristic22.png)
**Problema #3: Inconsistencias visuales en el diseño de la interfaz**

- **Severidad:** 2
- **Heurística violada:** Consistencia y estándares
- **Problema:** Durante la revisión se detectaron diferencias visuales entre pantallas y componentes, como variaciones en estilos, jerarquías visuales, tamaños o distribución de elementos. Aunque estas diferencias no impiden por completo el uso del sistema, sí afectan la percepción de uniformidad y profesionalismo de la plataforma, y obligan al usuario a reinterpretar cada pantalla en lugar de reconocer patrones consistentes.
- **Recomendación:** Definir y aplicar criterios visuales uniformes para componentes, botones, tablas, encabezados, colores, espaciados y estilos tipográficos en todas las vistas del sistema.

![heuristic-problem-3](../assets/images/heuristic3.png)

**Conclusión de la evaluación heurística**

La evaluación heurística permitió identificar problemas relevantes que complementan los hallazgos obtenidos en las entrevistas de validación. En particular, se evidenció la necesidad de mejorar el acompañamiento al usuario, reforzar la prevención de errores en acciones sensibles y unificar la experiencia visual del sistema. Estos aspectos no siempre son mencionados de forma explícita por los entrevistados, pero sí impactan de manera significativa en la usabilidad general de la plataforma.

La incorporación de estas mejoras contribuirá a que SupplyWok ofrezca una experiencia más clara, confiable y consistente, alineada con los principios de diseño centrado en el usuario y con los criterios de calidad esperados para una aplicación web funcional.

## 5.4. Video About-the-Product.

![](../assets/images/abtproduct.png)

* Microsoft Stream: [https://tinyurl.com/4a9ucufx](https://tinyurl.com/4a9ucufx)
* YouTube: [https://youtu.be/AzOyy7Oak_w](https://youtu.be/AzOyy7Oak_w)


# Conclusiones

## Conclusiones y recomendaciones

El proceso de desarrollo de SupplyWok mostró una evolución progresiva y coherente a lo largo de los sprints documentados en este capítulo. En el Sprint 1, el equipo logró construir y desplegar la Landing Page del producto, estableciendo una base sólida de comunicación de propuesta de valor, navegación inicial, diseño responsivo e internacionalización. Esta primera iteración permitió consolidar el entorno de trabajo, definir convenciones de desarrollo y demostrar la capacidad del equipo para entregar una primera versión visible del producto en producción.

Durante el Sprint 2, el avance se concentró en la construcción del frontend de la Web Application, organizando la solución en bounded contexts y desarrollando dashboards diferenciados para restaurantes y proveedores. En esta etapa se implementaron las principales vistas funcionales del sistema, así como la estructura compartida de navegación, componentes reutilizables, manejo de estado y configuración de entornos. Aunque el frontend aún se apoyaba en una Fake API para simular datos, este sprint fue importante porque permitió validar la arquitectura de la aplicación, aterrizar los user flows principales y preparar la plataforma para la integración posterior con servicios reales.

El Sprint 3 representó el avance técnico más importante del ciclo actual, ya que permitió trasladar la solución hacia una capa real de servicios backend mediante C#, Entity Framework Core, persistencia en MySql y documentación de endpoints en Swagger. En esta iteración se implementaron los bounded contexts priorizados del núcleo del negocio y se habilitaron operaciones REST funcionales para módulos como inventario, órdenes de compra, comandas, alertas, perfiles, analytics y supplier management. Además, el despliegue del backend en Render y la verificación de persistencia en MySql Workbench evidencian que el proyecto ya no se mantiene solo en nivel prototípico, sino que cuenta con una base técnica operativa y desplegada.

Desde una perspectiva de desarrollo, uno de los principales logros del equipo fue haber construido el producto por capas y en etapas claras: primero la presencia pública del producto, luego la experiencia de usuario en frontend y finalmente la infraestructura de servicios que soporta la lógica de negocio. Esta secuencia permitió reducir complejidad, distribuir mejor el trabajo entre los integrantes y mantener continuidad entre diseño, implementación y validación. Asimismo, la evidencia de commits, Pull Requests, boards de sprint, despliegues y documentación técnica muestra que el trabajo no solo avanzó en funcionalidad, sino también en prácticas colaborativas y de ingeniería de software.

No obstante, el propio desarrollo también dejó en evidencia aspectos que todavía deben fortalecerse. En el frontend aún existen oportunidades de mejora en consistencia visual, acompañamiento al usuario y algunos flujos operativos, mientras que en backend todavía queda pendiente seguir ampliando cobertura funcional, consolidar integraciones completas entre cliente y servidor, y profundizar pruebas con escenarios más cercanos al uso real. Del mismo modo, varias métricas de éxito definidas en Lean UX todavía no pueden validarse cuantitativamente, pues requieren una etapa posterior de uso continuo con usuarios reales sobre la versión integrada del sistema.

Como recomendación para la siguiente etapa del roadmap, el equipo debería priorizar la integración completa entre el frontend y los Web Services ya desplegados, reemplazando definitivamente dependencias simuladas donde aún existan. Junto con ello, conviene continuar refinando los bounded contexts ya implementados, reforzar validaciones y manejo de errores, completar evidencias visuales faltantes del sprint y ejecutar pruebas funcionales integrales por flujo de negocio. En paralelo, resulta recomendable mantener el mismo nivel de documentación técnica y colaboración evidenciado en este capítulo, ya que ha sido una de las fortalezas más claras del proceso de desarrollo.

En conjunto, el trabajo realizado demuestra que SupplyWok alcanzó un nivel importante de madurez para esta etapa del curso: existe una propuesta validada, una interfaz funcional, un backend desplegado y una arquitectura organizada que permite seguir creciendo el producto. Más allá de las mejoras pendientes, el desarrollo documentado en los sprints confirma que el equipo logró transformar una idea inicial en una solución web estructurada, técnicamente consistente y preparada para una integración y validación más profunda en las siguientes entregas.

## Video About-The-Team


### Enlaces del Video

* Microsoft Stream: [https://tinyurl.com/2acmmayx](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202422890_upc_edu_pe/IQDySsjWzeU3QJIfvb_8FEj8AQdXLUYVA6erYiIsj7Xe7eU?e=qVnNMj&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)
* YouTube: [https://www.youtube.com/watch?v=V8HEQALGMGo](https://www.youtube.com/watch?v=V8HEQALGMGo)

![About the Team](../assets/images/about-the-team.png)
