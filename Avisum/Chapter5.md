## Capítulo V: Product Implementation, Validation & Deployment

### 5.1. Software Configuration Management

El Software Configuration Management (SCM) es un conjunto de actividades y procesos que tiene como objetivo organizar y supervisar los cambios que se realizan en el software durante su desarrollo.

#### 5.1.1. Software Development Environment Configuration

En esta sección referenciamos los productos de software que usamos como equipo para colaborar en la realización de este proyecto.

**Project Management:**

- **WhatsApp:** Utilizado para comunicación rápida mediante un grupo privado donde coordinamos avances, compartimos archivos y establecemos fechas límite.
- **Discord:** Utilizado para reuniones cortas y aclarar dudas en tiempo real mediante llamadas de voz.

**Requirement Management:**

- **OneDrive:** Usado para almacenar archivos audiovisuales del proyecto, como los vídeos requeridos durante las distintas etapas de desarrollo.
- **Git:** Sistema de control de versiones para rastrear los cambios en el código fuente. Usado para registrar los cambios realizados del código dentro de GitHub.

**Product UX/UI Design:**

- **Figma:** Plataforma de diseño de interfaces que permite crear prototipos interactivos de forma colaborativa. Usado para diseñar las pantallas de nuestro producto en versión desktop.

**Software Development:**

- **Visual Studio Code:** Editor de código fuente desarrollado por Microsoft. Empleado para desarrollar el código del proyecto utilizando tecnologías como HTML y CSS.
- **GitHub:** Plataforma de alojamiento de repositorios basada en Git. Empleada para almacenar el proyecto, realizar control de versiones y sincronizar los cambios del equipo.

**Software Testing:**

- **Chrome:** Usado para realizar las pruebas de visualización y comportamiento del prototipo, verificando su correcto funcionamiento en distintos tamaños de pantalla.

**Software Documentation:**

- **Google Docs:** Herramienta de procesamiento de texto en línea usada para redactar la documentación general del proyecto.
- **.MD:** Archivos Markdown usados para guardar toda la documentación del informe realizado.

---

#### 5.1.2. Source Code Management

Para la gestión del código fuente del proyecto, el equipo utilizará **Git** como sistema de control de versiones distribuido y **GitHub** como plataforma central de colaboración.

**Repositorio en GitHub:** https://github.com/DiExpe-Grupo4

**Implementación de Gitflow**

El equipo adoptará el modelo de ramificación GitFlow, propuesto por Vincent Driessen.

**Ramas principales:**

- `main`: Contiene el código estable y listo para producción.
- `develop`: Contiene el código con las últimas funcionalidades integradas, en preparación para la siguiente versión estable.

**Ramas de soporte:**

1. **Feature branches:** Desarrollar nuevas funcionalidades o mejoras.
2. **Release branches:** Denominar una nueva versión estable del proyecto.
3. **Hotfix branches:** Corregir errores críticos detectados en producción.

**Semantic Versioning**

Aplicaremos Semantic Versioning 2.0.0 con el formato `MAJOR.MINOR.PATCH`:
- **MAJOR:** Cambio incompatible con versiones anteriores.
- **MINOR:** Agregado de nuevas funcionalidades.
- **PATCH:** Corrección o mejoras sin afectar su compatibilidad.

Ejemplo: `v1.0.0` → `v1.1.0` → `v1.1.1`

**Conventional Commits**

Los mensajes commit seguirán el formato: `tipo(especificación): descripción`

Tipos: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Ejemplos:
- `feat(formulario): se agregó una validación al correo electrónico`
- `fix(navbar): se corrigió error en la alineación`
- `docs(README): se actualizaron instrucciones`

**Flujo general de trabajo:**

1. Cada integrante clona el repositorio y crea su propia rama `feature/` para trabajar en una nueva tarea.
2. Cuando termina, se realiza un merge hacia `develop` mediante pull request.
3. Una vez integradas todas las funcionalidades planificadas, se crea una rama `release/` para pruebas finales.
4. Si la versión es aprobada, se fusiona a `main`, se etiqueta con su número de versión y se elimina la rama `release/`.
5. En caso de detectar errores en producción, se genera una rama `hotfix/` para resolverlos rápidamente.

---

#### 5.1.3. Source Code Style Guide & Conventions

### Landing Page:

Resumen: Como principales tecnologías, usaremos Tailwind CSS, HTML y TypeScript. Componentes pequeños y tipados, comunicación clara por propósitos, y estilos utilitarios y organizados.

| Tecnología  | Convenciones principales  | Convenciones para código  |
| :---- | :---- | :---- |
| Tailwind CSS  | \- Usar solo clases utilitarias de Tailwind.  | \- Usar @apply para estilos reutilizables. Evitar clases condicionales en el HTML.  |
| HTML  | \- Usar etiquetas semánticas (header, main, section, etc.). Indentación de 2 espacios.  | \- Mantener el HTML limpio y libre de código comentado. Usar data-\* atributos para información adicional.  |
| TypeScript  | \- Variables/funciones en camelCase. Clases/interfaces en PascalCase. Tipado obligatorio.  | \- Usar readonly para propiedades que no deben cambiar. Preferir funciones puras y evitar efectos secundarios.  |

### Front-End:
Resumen: Se utilizarán HTML, TypeScript y CSS como tecnologías principales. Los componentes serán pequeños y tipados, con comunicación clara mediante props/emits y un manejo adecuado del estado y las APIs.

| Tecnología  | Convenciones principales  | Convenciones para código  |
| :---- | :---- | :---- |
| HTML5  | \- Uso semántico de etiquetas (header, main, section, footer). Atributos en comillas dobles.  | \- Mantener el HTML limpio y libre de código comentado. Usar comentarios para secciones complejas o importantes.  |
| CSS3  | \- Estilos modulares y reutilizables. Variables globales para colores/tipografía. Evitar \!important. | \- Usar BEM (Block Element Modifier) para nombrar clases. Mantener la especificidad baja.  |
| TypeScript  | \- Variables/funciones en camelCase. Clases/interfaces en PascalCase. Constantes en UPPER\_SNAKE\_CASE.  | \- Usar desestructuración para extraer valores de objetos y arrays.  |

### Herramientas y configuración :

Estas herramientas están principalmente orientadas a mejorar el flujo de desarrollo y facilitar la gestión de configuraciones y dependencias, pero todas ellas están relacionadas con frontend y el proceso de construcción del proyecto. Vite y Babel se encargan de la construcción del código, Git ayuda con el control de versiones y flujo de trabajo, y Docker puede ser útil para contenedores en entornos de desarrollo o despliegue.

| Tecnología  | Convenciones principales  | Convenciones para código  |
| :---- | :---- | :---- |
| Vite  | \- Herramienta de construcción rápida para el desarrollo en React.  | \- Mantener el archivo [vite.config.js](http://vite.config.js) limpio y organizado. Usar plugins solo cuando sea necesario.  |
| Babel  | \- Uso de Babel para la traducción de código JavaScript moderno (ES6+).  | \- Configuración clara y concisa para la traduccion de código. Mantener las configuraciones mínimas.  |
| Git  | \- Uso de ramas para nuevas características y buenos flujos de trabajo con commits.  | \- Hacer commits frecuentes con mensajes claros. Utilizar flujos de trabajo como Git Flow o feature branching.  |



#### 5.1.4. Software Deployment Configuration

Esta sección detalla los pasos necesarios para desplegar de forma satisfactoria los productos digitales que componen la solución:

**1\. Landing Page \- HTML, CSS y TypeScript**

Para que nuestra landing page esté disponible para todos nuestros usuarios, la publicamos como un sitio web utilizando la plataforma de GitHub. El proceso se llevó a cabo de la siguiente manera:

Registro en GitHub Creamos una cuenta en GitHub para poder gestionar los repositorios del proyecto y almacenar el código de la Landing Page de SafeBus


<img width="841" height="438" alt="image" src="https://github.com/user-attachments/assets/f83df4df-5565-4fd7-8b13-7b722c743a9a" />

* Pantalla de GitHub para crear una organización, donde se ingresan el nombre, correo de contacto y si pertenece a una cuenta personal o institución antes de la verificación.

**2\. Carga de los archivos de la landing page**

Accedimos al repositorio creado. Subimos los archivos generados del proyecto (HTML, TailwindCSS, TypeScript). Verificamos que los cambios se hicieran en la rama principal (main). Finalmente, confirmamos la acción con “Commit changes” para guardar los archivos. Una vez ya configurada y lanzada podremos ingresar desde el repositorio mediante el enlace [safe-bus-lading.vercel.app](https://lading-page-six-psi.vercel.app/) .

<img width="1892" height="932" alt="image" src="https://github.com/user-attachments/assets/12cdff7e-c520-4954-bd3a-4ae5db5401fc" />


**3\. Visualización de la landing page**

 La página principal del landing de SafeBus tiene un diseño limpio y moderno con un menú superior que enlaza las secciones "Características", "Cómo funciona", "Estadística" y "Apoyo", junto con un botón de ingreso. En la sección hero, destaca el eslogan "Protege tu ruta, asegura tu futuro" y una breve descripción del servicio. También se presentan estadísticas clave, como el porcentaje de rutas seguras operativas y la cantidad de conductores protegidos.


<img width="835" height="411" alt="image" src="https://github.com/user-attachments/assets/4fcfe970-4224-48b5-92a1-a537b52c85bf" />
