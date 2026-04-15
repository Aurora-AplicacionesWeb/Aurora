# Capítulo V: Product Implementation, Validation & Deployment.

## 5.1. Software Configuration Management. 
Para tener consistencia y seguimiento de el desarrollo de la plataforma, se ha definido una serie de herramientas y estrategias de desarrollo. El metodo cubre la configuracion del entorno de desarrollo, la gestion del codigo y el despliegue, alineado a las buenas prácticas de ingenieria de software y metodologias ágiles.
### 5.1.1. Software Development Environment Configuration. 
Para facilitar la colaboración del equipo en todas las actividades del ciclo de vida de desarrollo de Urban Safe, se ha definido un entorno de desarrollo común. Este entorno está compuesto por herramientas especializadas para la gestión del proyecto, diseño UX/UI, modelado, desarrollo, pruebas, documentación y despliegue. La selección de estas herramientas se basa en criterios de eficiencia, compatibilidad con tecnologías open-source (Java + web), y alineación con prácticas recomendadas de la industria.
|        Categoría        |      Herramienta      |                                               Propósito                                               |                                      Tipo de acceso/enlace                                      |
| :---------------------: | :-------------------: | :---------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
|    Project Management   |         Trello        |           Gestión del backlog, tareas y sprints del equipo usando metodología ágil (Scrum).           |                             [https://trello.com](https://trello.com)                            |
| Requirements Management |       UXPressia       |                  Creación de User Personas, Journey Maps y artefactos de needfinding.                 |                          [https://uxpressia.com](https://uxpressia.com)                         |
|   Product UX/UI Design  |         Figma         |                Diseño de wireframes, mockups y prototipos de la aplicación web y móvil.               |                              [https://figma.com](https://figma.com)                             |
|   Modelado de Software  |    LucidChart / Miro / Structurizr     |                 Modelado de arquitectura (UML, C4, Event Storming, Bounded Contexts).                 |               [https://www.lucidchart.com/](https://www.lucidchart.com/)     / [https://miro.com/](https://miro.com/) / [https://structurizr.com/](https://structurizr.com/)               |
|   Frontend Development  |   Visual Studio Code  |                 Desarrollo del Landing Page y Web Application (HTML, CSS, JavaScript).                |                  [https://code.visualstudio.com](https://code.visualstudio.com)                 |
|   Backend Development   |     IntelliJ IDEA     |     Desarrollo del RESTful API en Java (Spring Boot) siguiendo arquitectura orientada a servicios.    |                [https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/)               |
|       API Testing       |        Postman        |                           Pruebas y validación de endpoints del API RESTful.                          |                        [https://www.postman.com](https://www.postman.com)                       |
|     Version Control     |         GitHub        | Control de versiones del código fuente y documentación colaborativa (GitFlow + Conventional Commits). |                             [https://github.com](https://github.com)                            |
|  Software Documentation |        Markdown       |                     Redacción del informe del proyecto bajo enfoque Docs-as-Code.                     |                            Compatible con GitHub / editores de texto                            |


### 5.1.2. Source Code Management. 
Los repositorios utilizados para el desarrollo de código fuente son los siguientes:

<div align="center">

| Producto Digital | URL del Repositorio | 
|:----------------:|:-------------------:|
| Landing Page | https://github.com/Aurora-startup/urbantrust-landing-page | 
| Web Services (Backend API) |https://github.com/Aurora-startup/urbantrust-backend  |
| Frontend Web Application | https://github.com/Aurora-startup/urbantrust-frontend|

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
### 5.1.4. Software Deployment Configuration.  
## 5.2. Landing Page, Services & Applications Implementation.
| Categoría | Herramienta | Propósito | Tipo de acceso/enlace |
|:----:|:----:|:----:|:----:|
| Project Management | Trello | Gestión del backlog y tareas del equipo mediante tableros Scrum. | https://trello.com |
| Requirements Management | UXPressia | Creación y documentación de User Personas y customer journeys. | https://uxpressia.com |
| Product UX/UI Design | Figma | Creación de wireframes y mockups de la interfaz de usuario. | https://figma.com |
| Modelado de Software | Visual Paradigm | Modelado de arquitectura de software: diagramas de contexto, Bounded Contexts, etc. | https://visual-paradigm.com |
| Frontend Development | Webstorm | Editor de código para el desarrollo del Landing Page y Frontend (Vue). | https://www.jetbrains.com/webstorm/|
| Backend Development | Rider| Entorno de desarrollo para el backend en C# y .NET Framework | https://www.jetbrains.com/rider/ |
| Version Control | GitHub | Repositorio de control de versiones para todos los productos digitales. | https://github.com |
| Software Documentation | Markdown | Redacción de documentación técnica del proyecto. | Compatible con GitHub / editores de texto |
### 5.2.1. Sprint 1 
#### 5.2.1.1. Sprint Planning 1