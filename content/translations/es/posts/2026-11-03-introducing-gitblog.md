---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Introducción a Gitblog: cómo ser dueño de mis artículos y gestionar mi propio
  blog
description: >-
  Guarda tus artículos en mi repositorio de GitHub, escribe con la ayuda de la
  IA y conecta con más lectores. Te presentamos las cinco filosofías en las que
  se basa Gitblog y cómo empezar a escribir en tu blog.
date: '2026-11-03T19:00:00+09:00'
published: true
category: Manual
tags:
  - gitblog
  - 사용법
locale: es
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: 13c15d5c3b84c5fbdf606fcdc5f7c99e4a899fac4004966fc72874ddfd92c3c7
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-03T16:21:40.133Z'
cover: /uploads/covers/introducing-gitblog-mascot.png
updated: '2026-11-04T01:19:03+09:00'
---
Lo que se acumula en un blog no son solo entradas. También quedan registrados el proceso de resolución de problemas, los momentos en los que he aprendido algo nuevo y mi perspectiva sobre determinados temas. Con el paso del tiempo, esos registros se convierten en un activo que muestra en qué me he estado planteando y cómo he cambiado.

Entonces, ¿dónde debería conservarse este activo? Aunque el servicio en el que escribía cambiara o desapareciera, ¿no debería poder seguir conservándolo y gestionándolo?

**Gitblog es un servicio que permite almacenar entradas públicas y el código del blog en mi repositorio de GitHub, así como redactar entradas a través de la web o de un agente de IA para publicarlas en mi blog.** Partiendo de la base de que uno es el propietario y gestor directo de sus entradas, hemos añadido funciones que facilitan la redacción y permiten llegar a los lectores.

La creación de Gitblog parte de cinco ideas fundamentales.

## 1. Debo poder ser el propietario y gestionar los artículos que escribo

Cuanto más tiempo se escriben entradas, más importante es la confianza en que se podrán seguir consultando. Creemos que el autor debe poder almacenar, modificar y, si es necesario, trasladar sus propios registros a otro lugar.

Las entradas públicas de Gitblog se almacenan como archivos Markdown en mi repositorio de GitHub. También se pueden gestionar conjuntamente los archivos del blog, incluidas las imágenes, y el código. Si descargo el repositorio a mi ordenador, puedo leer, modificar y hacer copias de seguridad de las entradas de forma local, además de consultar el contenido anterior a través del historial de cambios de Git.

**Aunque el servicio de Gitblog dejara de existir, el repositorio de mi cuenta, las entradas guardadas localmente y el código del blog seguirían estando ahí.** Si mantengo el alojamiento y el dominio, podré seguir ofreciendo el blog estático publicado y, si es necesario, trasladar los archivos a otro proveedor de alojamiento. Sin embargo, las funciones integradas que ofrece Gitblog, como la navegación y las suscripciones, dependen del funcionamiento del servicio.

Esta es precisamente la razón por la que hemos optado por basarnos en GitHub. Muchas personas ya lo utilizan y ofrece una base para crear un blog a través de repositorios públicos y GitHub Pages. Incluso con GitHub Free se puede utilizar el alojamiento de Pages para repositorios públicos. El alcance de los servicios y los límites de uso se rigen por [la política de GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Poder tener en mis manos el original de cualquier entrada pública, independientemente de dónde la escriba. Este es el primer principio de Gitblog.

## 2. Debe ser un blog en el que también se pueda utilizar la IA

Escribir con la ayuda de la IA se está convirtiendo en algo habitual. Se crean borradores a partir de notas, se organizan contenidos complejos, se pulen frases y se traducen a otros idiomas. Del mismo modo que los agentes de programación leen y modifican los archivos de un proyecto, creemos que los agentes que ayudan a escribir también deben poder manejar directamente los archivos del blog.

El repositorio del blog de Gitblog incluye directrices y comandos de redacción, traducción y verificación que los agentes de IA pueden consultar. Si designas tu repositorio de blog como entorno de trabajo para un agente capaz de leer y modificar archivos locales y ejecutar comandos, podrás redactar borradores y preparar la publicación en ese entorno. Si dispones de la autenticación y los permisos necesarios, incluso podrás llevar a cabo la publicación.

Por ejemplo, se puede realizar una solicitud como la siguiente:

> Lee el archivo AGENTS.md de este repositorio del blog y sigue las instrucciones de redacción. Redacta el artículo basándote en las notas que he dejado y guárdalo como borrador para que pueda revisarlo.

Una vez finalizada la revisión, puedes solicitar a continuación la traducción, la verificación y la publicación. Las tareas posibles varían en función del alcance de acceso a los archivos y los permisos de ejecución de comandos del agente que utilices. El flujo específico se detalla en la [Guía de redacción y traducción de blogs](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md).

Gitblog no obliga a utilizar un modelo de IA concreto para redactar los artículos. Puedes escribir directamente en la web, utilizar un editor con el que estés familiarizado o trabajar con IA. El objetivo es que el autor pueda elegir la herramienta que mejor se adapte a su forma de trabajar.

## 3. Un buen artículo debe poder descubrirse más allá del idioma y las herramientas

Una vez publicado un artículo, alguien debe encontrarlo y leerlo. Hay quienes buscan respuestas en los motores de búsqueda y quienes encuentran material relevante al plantear preguntas a servicios de IA. También hay lectores que leen en un idioma distinto al que tú utilizas.

Gitblog ofrece una estructura que permite llegar a este tipo de lectores mediante la publicación multilingüe y el acceso a la búsqueda y la IA.

En primer lugar, puedes publicar el texto original, escrito en el idioma que te resulte más cómodo, traducido al idioma seleccionado. Se admite la traducción automática mediante la integración de la API de DeepL, así como la revisión y publicación de traducciones realizadas por personas o por modelos de lenguaje grande (LLM). La traducción automática de DeepL requiere una clave de API independiente. Si gestionas la traducción tú mismo, se ofrece un procedimiento para comprobar que la traducción se mantiene actualizada cuando se modifica el texto original.

Además, las plantillas cuentan con los siguientes elementos básicos para que los motores de búsqueda y las herramientas de IA puedan identificar el contenido y la fuente del texto.

- **Información de la página para la búsqueda:** proporciona el título, la descripción, la URL del texto original, el mapa del sitio y enlaces a las páginas en cada idioma.
- **Estructura que explica el contexto del artículo:** proporciona datos estructurados, como el autor y la fecha de publicación, y permite añadir, según sea necesario, respuestas clave, fuentes, preguntas y respuestas.
- **Vías de acceso directo al texto:** según la configuración, se proporciona la versión en Markdown de los artículos públicos y la lista de artículos `llms.txt`.

Se trata de un diseño que tiene en cuenta la visibilidad en entornos de IA de búsqueda, respuesta y generación, comúnmente denominados SEO, AEO y GEO. El objetivo es presentar el cuerpo del artículo y su contexto de forma fácil de leer. La clasificación en los resultados de búsqueda o las citas en las respuestas de la IA las determina cada servicio, y no se garantizan únicamente mediante la traducción o la configuración técnica. [Guía de búsqueda y acceso a la IA](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

También se pueden encontrar entradas dentro de Gitblog. Las entradas de los blogs que participan en el feed se recopilan y se muestran en las pantallas de exploración, como «Entradas más recientes», «Entradas populares» o «Tendencias». Los lectores pueden buscar las entradas que les interesen y desplazarse al blog del autor para leerlas.

Lo que esperamos es ampliar la posibilidad de que los registros que dejamos lleguen a quienes necesitan ese contenido.

## 4. La resonancia de una entrada se traduce en conexiones en GitHub

Cuando lees una buena entrada, sientes curiosidad por la siguiente del autor. Te animas a averiguar qué tipo de proyectos está creando y qué ideas está compartiendo.

En Gitblog, este interés se traduce también en una relación con GitHub. **La suscripción a un blog se vincula a las estrellas de GitHub de ese repositorio, y seguir al autor se vincula a la opción «Seguir» de su cuenta de GitHub.** El lector puede recopilar las entradas de los blogs o autores que le interesan, y el autor puede conectar con los lectores también a través de GitHub gracias a sus publicaciones.

Aunque pueda parecer algo insignificante, creemos que esta conexión tiene su importancia. Y es que a la imagen que se proyecta a través del código y los proyectos se suman los artículos y las reflexiones. Los artículos en los que se explican las decisiones tomadas en un proyecto, el proceso de resolución de problemas o lo aprendido se convierten en otra vía para comprender el trabajo de esa persona.

El número de estrellas o de seguidores no determina el valor de un artículo. Sin embargo, el hecho de que un lector que se haya identificado con mi artículo pueda llegar a esperar mi próxima publicación puede ser una razón para seguir escribiendo con constancia.

## 5. Escribir sigue siendo importante incluso en la era de la IA

Escribimos cuando hacemos preguntas a la IA. Explicamos el resultado que queremos, organizamos las condiciones y, tras leer la respuesta, volvemos a preguntar. Incluso cuando la IA redacta el prompt y el borrador por nosotros, sigue existiendo el proceso de decidir qué solicitar y qué resultado aceptar.

Escribir es también un proceso de reflexión sobre las propias ideas. Al redactar frases para explicar algo, se detectan lagunas en aspectos que creíamos conocer. Buscamos fundamentos, corregimos argumentos contradictorios y conectamos el contexto para que otras personas puedan entenderlo.

Aunque la IA asuma cada vez más tareas, no queremos olvidar nuestro papel como personas que deciden qué es importante y cómo actuar. **No perder de vista las propias ideas y juicios incluso en los textos escritos junto con la IA**: ese es el tipo de escritura al que aspiramos.

Espero que Gitblog sea un espacio en el que podamos seguir practicando esto. Un espacio en el que explicar lo aprendido con nuestras propias palabras, dejar constancia de nuestras experiencias en un contexto adecuado y desarrollar nuestras ideas al releerlas con el paso del tiempo.

Espero que la tarea de ir acumulando buenos textos se convierta en un proceso de perfeccionamiento de la propia inteligencia.

## Cómo empezar con Gitblog

Gitblog se puede iniciar desde Studio en la web, o bien se puede crear directamente un repositorio de blog en GitHub y gestionarlo desde el ordenador local. En primer lugar, veremos cómo utilizar Studio.

### 1. Registrarse con una cuenta de GitHub

Accede a [Gitblog](https://gitblog.app/ko) y regístrate o inicia sesión con tu cuenta de GitHub. Una vez hayas iniciado sesión, dirígete a Studio, el espacio donde puedes crear y gestionar tu blog.

### 2. Conectar la aplicación de GitHub y crear un blog

Sigue las instrucciones de Studio para instalar la aplicación Gitblog en GitHub y autoriza el acceso al repositorio en el que gestionarás el blog. Echa un vistazo a las plantillas, elige una y, a continuación, establece el título del blog y el nombre del repositorio.

![Pantalla de Gitblog Studio (en inglés) en la que se pueden previsualizar y seleccionar plantillas de blog basadas en Svelte, Astro, React y HTML puro.](/uploads/introducing-gitblog/templates-en.jpg)

*Pantalla de selección de plantillas de Studio en inglés. A fecha de 3 de noviembre de 2026.*

Los archivos del blog se crean en tu repositorio de GitHub. Para el alojamiento, puedes utilizar GitHub Pages o conectar tu cuenta de Cloudflare para usar Cloudflare Pages. Una vez completada la configuración de implementación del método elegido, estarás listo para publicar entradas.

### 3. Escribir y publicar entradas en Markdown

En la pantalla de redacción de Studio, escribe el título, la descripción y el cuerpo del texto en Markdown. También puedes subir una imagen de portada que sirva de miniatura representativa de la entrada, así como imágenes para el cuerpo del texto.

Mientras escribes, guarda el borrador y, tras revisar el contenido, guárdalo como publicado. Una vez guardado, comprueba el progreso de la compilación y la publicación; cuando esta haya finalizado, podrás leer la entrada en tu blog. Si necesitas traducciones, configura los idiomas de traducción del blog y cómo utilizarlos para gestionarlas conjuntamente.

### Cómo empezar en GitHub y en tu ordenador local

Si quieres trabajar con un editor local o un agente de IA, puedes elegir la plantilla oficial de Gitblog que prefieras en GitHub y empezar directamente.

1. **Crea el repositorio de tu blog a partir de una plantilla.** En la página de GitHub de la plantilla oficial que elijas, utiliza la plantilla para crear un nuevo repositorio público en tu cuenta. Se creará un repositorio de blog que gestionarás tú, independiente de la plantilla original.
2. **Clona tu repositorio en tu ordenador local.** Ejecuta `git clone` con la dirección del repositorio creado y abre la carpeta descargada en tu editor o agente de IA para trabajar en ella. Sigue las instrucciones de la plantilla para instalar las herramientas de desarrollo y las dependencias necesarias, y completa la configuración inicial, como la dirección del blog, el idioma y el alojamiento.
3. **Redacta y revisa las entradas de forma local.** Escribe entradas en Markdown en `content/posts/` y añade imágenes. Puedes editarlas directamente o pedirle al agente que lea `AGENTS.md` y siga las instrucciones de redacción. Tras revisar el borrador, cámbialo al estado «publicado» y ejecuta el procedimiento de validación que proporciona la plantilla.
4. **Sube los cambios a GitHub y realiza la implementación.** Cuando comites el artículo y las imágenes y los envías (push) a la rama de implementación, el flujo de trabajo de GitHub Actions configurado compila el blog y lo implementa en el alojamiento seleccionado. Comprueba el resultado de la ejecución de Actions y si los cambios se han reflejado en la página real del blog.

La primera vez, deberá preparar el entorno de distribución siguiendo la [Guía de configuración inicial](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) de la plantilla elegida. A partir de entonces, podrá continuar escribiendo siguiendo el flujo: **redacción local → revisión y validación → commit y push → verificación de la distribución**.

Los blogs creados directamente en GitHub también se pueden gestionar en la aplicación Gitblog, siempre que se permita el acceso a ese repositorio y se utilice la función de conexión con blogs existentes de Studio. Solo tienes que elegir el método que mejor se adapte a tu trabajo: escribir en la web o escribir localmente.

## Empieza por el lugar donde se guardan tus entradas

Gitblog es un blog que te permite guardar tus entradas en tu cuenta, escribir con las herramientas que te resulten más familiares y llegar a lectores de diferentes idiomas y procedencias. En su base se encuentra la convicción de que, a través de la escritura, uno puede comprender mejor sus propios pensamientos.

No hace falta escribir un artículo perfecto desde el principio. Intenta anotar algo que hayas aprendido hoy, una pregunta sobre la que lleves tiempo reflexionando o un problema que hayas resuelto por ti mismo. El proceso de añadir contexto a esa anotación y pulirla te llevará al siguiente artículo.

**Acumula tus ideas en un blog que te pertenece y que gestionas tú mismo.**

[Cómo crear tu propio blog en Gitblog](https://gitblog.app/studio)
