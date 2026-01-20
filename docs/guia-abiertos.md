# Guía para la publicación de datos en formatos abiertos del Gobierno de la Ciudad Autónoma de Buenos Aires

  <!-- START doctoc generated TOC please keep comment here to allow auto update -->
  <!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

## Indice

  - [Introducción](#introduccion)
  - [Transformación Digital y Transparencia: El Rol del Equipo de Datos Abiertos](#transformacion-digital-y-transparencia-el-rol-del-equipo-de-datos-abiertos)
  - [Buenos Aires Data](#buenos-aires-data)
    - [Composición portal](#composicion-portal)
    - [Actualización y creación de recursos](#actualizacion-y-creacion-de-recursos)
    - [Enlaces y administradores de Datos](#enlaces-y-administradores-de-datos)
    - [Criterios para selección de datos](#criterios-para-seleccion-de-datos)
  - [Esquema de apertura](#esquema-de-apertura)
    - [1. Identificación de apertura](#1-identificacion-de-apertura)
    - [2. Acuerdo con el área](#2.acuerdo-con-el-area)
    - [3. Análisis y Normalización](#3-analisis-y-normalizacion)
    - [4. Publicación y notificación](#4-publicacion-y-notificacion)
    - [5. Monitoreo de Apertura](#5-monitoreo-de-apertura)
  - [Licencia de utilización de datos](#licencia-de-utilizacion-de-datos)
  - [Criterios Técnicos para la Gestión de Recursos en Datos Abiertos](#criterios-tecnicos-para-la-gestion-de-recursos-en-datos-abiertos)
    - [Diccionario de Datos y Metadatos](#diccionario-de-datos-y-metadatos)
    - [Formatos abiertos de archivos](#formatos-abiertos-de-archivos)
  - [CSV](#csv)
  - [JSON](#json)
  - [Fragmentación de archivos](#fragmentacio-de-archivos)
  - [Nomenclatura de archivos](#nomenclatura-de-archivos)
  - [Codificación](#codificacion)
  - [Estructura y características de los datos tabulares](#estructura-y-caracteristicas-de-los-datos-tabulares)
    - [Recomendaciones generales](#recomendaciones-generales)
      - [Nomenclatura de los campos (nombres de las columnas)](#nomenclatura-de-los-campos-nombres-de-las-columnas)
      - [Nivel de granularidad de los datos](#nivel-de-granularidad-de-los-datos)
      - [Usar orientación vertical en lugar de horizontal](#usar-orientacion-vertical-en-lugar-de-horizontal)
      - [Incluir sólo un atributo por campo](#incluir-solo-un-atributo-por-campo)
      - [Valores nulos, desconocidos o no aplicables en los datos](#valores-nulos-desconocidos-o-no-aplicables-en-los-datos)
    - [Recomendaciones para estructurar planillas de cálculo](#recomendaciones-para-estructurar-planillas-de-calculo)
      - [Usar celdas simples](#usar-celdas-simples)
      - [Fila de encabezado](#fila-de-encabezado)
      - [Celdas vacías en filas para agrupar conceptos](#celdas-vacias-en-filas-para-agrupar-conceptos)
      - [Formato de celdas](#formato-de-celdas)
  - [Estándares según el tipo de Datos](#estandares-segun-el-tipo-de-datos)
    - [Texto](#texto)
      - [Entidades](#entidades)
      - [Nombres propios](#nombres-propios)
      - [Instituciones del Gobierno de la Ciudad de Buenos Aires](#instituciones-del-gobierno-de-la-ciudad-de-buenos-aires)
      - [Siglas](#siglas)
    - [Número](#numero)
      - [Moneda](#moneda)
      - [Porcentaje](#porcentaje)
      - [Números telefónicos](#numeros-telefonicos)
      - [Coordenadas](#coordenadas)
    - [Tiempo](#tiempo)
      - [Fecha](#fecha)
      - [Rangos horarios](#rangos-horarios)
    -  [Otros estándares sectoriales](#otros-estandares-sectoriales)
    - [Booleano](#booleano)

  <!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Introducción

  Esta sección tiene como objetivo establecer criterios técnicos y pautas operativas para la generación, estructuración y publicación de datos en formatos abiertos, con el fin de facilitar su acceso, reutilización y comprensión por parte de la ciudadanía y otros actores.

  El contenido de este documento se apoya en marcos normativos y guías técnicas utilizados a nivel internacional, nacional y también la regulación local, incluyendo la [Guía de buenas prácticas para la publicación de datos en formatos abiertos](https://datosgobar.github.io/paquete-apertura-datos/guia-subnacionales/), creada al amparo del Decreto Nº 117/2016 por el cual el Poder Ejecutivo Nacional instruye la implementación de un “Plan de Apertura de Datos”, los [Lineamientos para la Gobernanza de Datos del Gobierno de la Ciudad de Buenos Aires](https://buenosaires.gob.ar/innovacionytransformaciondigital/lineamientos-para-la-gobernanza-de-datos), [la Guía para la Identificación y Uso de Entidades Interoperables](https://datosgcba.github.io/guia-datos/guia-interoperables/) y las especificaciones técnicas del portal “datos.gob.ar” -estas últimas en el ámbito local-, entre otras. 

  También esta guía incorpora normativa definida por el Gobierno de la Ciudad de Buenos Aires y la experiencia operativa de la Dirección General de Gobernanza de Datos (DGGDA) dependiente de la Subsecretaría de Innovación Administrativa de la Secretaría de Innovación y Transformación Digital.

  Dado que se trata de una guía sujeta a actualización, se contempla la posibilidad de incorporar sugerencias y observaciones por parte de equipos técnicos y funcionales, áreas de gobierno, organizaciones y ciudadanos interesados.

## Transformación Digital y Transparencia: El Rol del Equipo de Datos Abiertos

  El equipo de Datos Abiertos es el encargado de la administración y gobernanza del portal de datos abiertos, garantizando la disponibilidad, accesibilidad y calidad de la información publicada. 

  Su labor se orienta hacia la actualización, mantenimiento y mejora continua del portal de datos abiertos, en conformidad con los principios de transparencia y acceso a la información pública.

  Entre sus competencias principales se encuentra la gestión integral de los conjuntos de datos, lo que incluye su actualización periódica, la publicación de nuevos datasets y el monitoreo de la frecuencia con la que deben ser revisados y mantenidos. Asimismo, el equipo se encarga de asegurar que los conjuntos de datos permanezcan accesibles y comprensibles para los usuarios, optimizando su calidad y usabilidad mediante la normalización de formatos y la implementación de estándares técnicos.

  En cuanto a la articulación con las áreas generadoras de datos, el equipo de Datos Abiertos actúa como intermediario entre las distintas dependencias gubernamentales, promoviendo el flujo de información y aunando por la coherencia en la publicación de los datos. 

  Por otro lado, el equipo mantiene un contacto permanente con la comunidad de usuarios del portal, atendiendo sus demandas y requerimientos, con el fin de mejorar la pertinencia y el impacto de los datos abiertos en la ciudad.

  El equipo también se encarga de actualizar y mejorar continuamente las tecnologías utilizadas en el portal, con el objetivo de optimizar la experiencia del usuario y facilitar la explotación de los datos.

  Además, impulsa la automatización de los procesos de publicación y monitoreo, permitiendo una mayor eficiencia en la gestión y reduciendo la posibilidad de errores en la actualización de los conjuntos de datos.

## Buenos Aires Data

  [BA Data](https://data.buenosaires.gob.ar/) es la plataforma oficial de datos abiertos de la Ciudad implementada por el Gobierno de la Ciudad Autónoma de Buenos Aires a través del Decreto N° 156/2012. 

  La misma se creó con el objetivo de facilitar la búsqueda, descubrimiento y acceso a conjuntos de datos del sector público, que contribuyan a promover la transparencia, a incentivar la participación y colaboración de los ciudadanos, a fomentar la reutilización de la información para generar conocimiento, y a estimular la innovación y el desarrollo social, económico y cultural en el ámbito de la Ciudad de Buenos Aires. 

  A lo largo de todo el portal se encuentran centralizados los activos de información de todas las áreas de gobierno. La unidad mínima del portal son los recursos, los cuales están agrupados por conjuntos de datos o datasets y a su vez pertenecen a categorías macro que facilitan su descubrimiento y acceso por parte del usuario.

  El Portal está basado en la herramienta [CKAN](https://ckan.org/), una plataforma de código abierto muy utilizada a nivel global para la gestión y publicación de datos abiertos. Si bien, comparte una base tecnológica común con otras iniciativas de apertura de datos -como el portal de datos de Nación- BA Data ha evolucionado, con el tiempo, hacia una plataforma adaptada a las particularidades y demandas de la Ciudad de Buenos Aires.

  La arquitectura del portal está orientada a garantizar el acceso estable, eficiente y seguro a la información pública, alineándose con los principios de apertura, interoperabilidad y escalabilidad.

### Composición portal

  La estructura digital se organiza entorno a conjuntos de datos, grupos temáticos y organizaciones, y se complementa con diversas herramientas orientadas a facilitar el acceso, la exploración y la reutilización de la información disponible.

  El portal se organiza de la siguiente manera: 

  * Datasets: conjunto principal de datos disponibles para su consulta y descarga. El portal alberga más de 430 conjuntos de datos que abarcan diversas temáticas, incluyendo salud, educación, transporte, medio ambiente, entre otros. Cada dataset está acompañado de metadatos que describen su contenido, formato, frecuencia de actualización y fuente de origen.

  * Organizaciones: dependencias gubernamentales responsables de la generación y mantenimiento de los datos.  Actualmente, se encuentran registradas 35 organizaciones activas en el portal.

  * Grupos: categorías temáticas que agrupan datasets relacionados, como "Transporte", "Salud" o "Educación", que facilitan la búsqueda por áreas de interés.

  * APIs: interfaz de programación que permite a los desarrolladores interactuar con los datos de forma automatizada. Entre las principales se destacan la API de Transporte Público, los servicios geoespaciales (como el normalizador de direcciones y el geocodificador), y recursos específicos como mapas interactivos, datos catastrales y organigramas institucionales. Estas interfaces están disponibles en formatos estandarizados (como JSON y XML),

  Adicionalmente, los usuarios cuentan con herramientas y funcionalidades que optimizan y agilizan la utilización del portal:

  * Historial de Actualizaciones: cada conjunto de datos cuenta con un historial de actualizaciones que documenta los cambios realizados, incluyendo modificaciones en los datos, actualizaciones de metadatos y ajustes en la descripción, entre otros. Esta funcionalidad permite realizar un seguimiento preciso de las intervenciones efectuadas sobre cada dataset.

  * Filtros Dinámicos: la página de datasets incluye filtros dinámicos, una funcionalidad propia del sistema CKAN, que permite refinar la búsqueda de datos. En el caso del portal BA Data, esta herramienta está disponible para combinar filtros de organización, temas y etiquetas, facilitando la navegación temática dentro del catálogo.

  * Barra de Búsqueda: el portal dispone de una barra de búsqueda general y una específica por dataset permitiendo identificar recursos dentro del conjunto.

  * Menú ordenamiento: permite reorganizar los resultados visualizados en el catálogo general según tres criterios: orden alfabético ascendente, orden alfabético descendente y fecha de última actualización. También se encuentra disponible de manera particular para cada dataset. 

  * Vista Previa de Recursos: antes de descargar un recurso, los usuarios pueden acceder a una vista previa del contenido, donde se plasma una muestra representativa de los registros. 

  * Composición de los Metadatos: cada recurso cuenta con un cuadro donde se detalla la información correspondiente a los campos incluidos en el recurso. Este aspecto se profundiza en la sección dedicada a la guía de metadatos.

  Por último, para mejorar la experiencia del usuario y promover la interacción con la comunidad de datos abiertos, el portal pone a disposición, en la sección “Información adicional” presente en cada dataset, diversos canales de comunicación y espacios de participación:

  * Encuesta de Satisfacción: los usuarios pueden brindar retroalimentación sobre su experiencia de uso del portal, con el fin de identificar oportunidades de mejora.

  * BA Colaborativa: canal habilitado para recibir consultas, sugerencias y observaciones vinculadas al funcionamiento del portal o al contenido de los conjuntos de datos publicados.

  * Correo Institucional: [datosabiertos@buenosaires.gob.ar](mailto:datosabiertos@buenosaires.gob.ar) disponible para atender requerimientos específicos de carácter técnico, operativo o vinculado al uso de los datos.

  Además de estos canales, el portal incorpora un **banner** informativo en su página principal, mediante el cual se difunden noticias relevantes vinculadas a la comunidad de datos abiertos, incluyendo actividades de networking, eventos, talleres y nuevas publicaciones institucionales.

### Actualización y creación de recursos

  La actualización de los conjuntos de datos se realiza conforme a la frecuencia establecida en cada dataset, la cual se encuentra definida en sus respectivos metadatos. Dependiendo del caso, la actualización puede implicar la sobreescritura de un recurso existente o bien la incorporación de un nuevo recurso dentro del conjunto.

  La Dirección General de Gobernanza de Datos(DGGDA), como administradora del portal BA Data, establece mecanismos de transferencia para facilitar la carga de información desde las áreas generadoras. Si bien existen diferentes alternativas para realizar esta transferencia, se prioriza la implementación de procesos automatizados de extracción, transformación y carga (ETL), desarrollados por las áreas responsables de los datos.

  La implementación de mecanismos automáticos de transferencia y carga permite reducir la intervención manual, disminuir el margen de error y garantizar la regularidad de los envíos. Se favorece de esta manera la trazabilidad de las actualizaciones, minimiza la participación de múltiples actores y permite que los datos lleguen al portal en su forma más directa posible, preservando su estructura original y facilitando su disponibilidad conforme a lo planificado.

  El acuerdo sobre la alternativa de transferencia de datos, así como la periodicidad de la actualización de los recursos publicados, se realizará entre el área responsable y la DGGDA. 

  Cualquier cambio experimentado en los procesos mencionados deberá ser informado por las partes en miras de mantener estables los procesos de apertura de datos.

  La DGGDA mantendrá una relación continua con las áreas productoras de datos, proporcionando retroalimentación sobre la calidad de los conjuntos publicados, en base a los estándares establecidos en el presente documento.

### Enlaces y administradores de Datos

  La apertura de datos es una estrategia que por su propia definición involucra la participación de todas las áreas del Gobierno de la Ciudad de Buenos Aires. Para su implementación se adoptará un enfoque mixto, con una coordinación desde la Dirección General de Gobernanza de Datos, la cual es la responsable de poner en práctica las medidas necesarias para implementar la Política de Apertura de Datos.

  Teniendo en cuenta que actualmente dispone de más de 430 conjuntos de datos pertenecientes a diversas áreas del Gobierno, cada área productora de uno o más datasets deberá designar a un agente que estará en calidad de **persona responsable de datos en las unidades organizativas**. Este agente actuará como referente para la gestión y publicación de los datos, y asumirá las responsabilidades que se detallan a continuación:

  El **responsable de datos en las unidades organizativas** será el responsable máximo ante la DGGDA y tendrá las siguientes funciones:

  1. Actuar como vínculo institucional y operativo, entre su unidad organizativa y la DGGDA.

  2. Interactuar con los equipos técnicos de cada repartición bajo su órbita y los responsables de Datos a fin de asegurar la información a publicar.

  3. Comunicar a la DGGDA cualquier modificación de su estructura orgánica que implique un cambio en cuanto a la producción, administración, actualización y/o publicación de algunas de las obligaciones de Transparencia Activa contempladas.

  4. Diseñar junto a la DGGDA un Plan de Apertura de Datos de su unidad en el que se estipule un cronograma de apertura.

  5. Identificar y promover el uso y reúso de datos públicos dentro de su unidad y coordinar acciones con la DGGDA y los Administradores para fomentar una cultura de apertura de datos de calidad.

  6. Coordinar con la DGGDA la realización de mesas de datos con el propósito de intercambiar experiencias, dar seguimiento al plan de apertura, convocar a taller de datos, entre otros.

  Se recomienda que el responsable de datos tenga una visión estratégica respecto a los activos de información que se encuentra bajo tutela o jurisdicción de su área.

  Por otro lado, los Administradores de Datos serán los encargados de operativizar los acuerdos de apertura realizados con las áreas y será la DGGDA quien lleve adelante estas acciones. Entre sus funciones se encuentran:

  1. Coordinar con el responsable de datos, la fuente del dato.

  2. Proveer asistencia para acceder a los datos acordados para su análisis y apertura.

  3. Informar al responsable de datos abiertos del dataset de referencia, cualquier cambio en la estructura de datos.

  4. Inviar los datos o facilitar su acceso para su correcta actualización.

  5. Documentar casos de uso y reutilización de datos públicos de los recursos bajo su órbita.

  6. Aplicar los estándares de calidad definidos en las guías de buenas prácticas de la Ciudad de Buenos Aires en los datos. 

### Criterios para selección de datos

  El Decreto 478/2013 establece la apertura por defecto de todos los datos públicos bajo tutela y/o jurisdicción del Gobierno de la Ciudad de Buenos Aires, quedando excluidos aquellos que estén protegidos por alguna normativa específica (Ley de Protección de Datos Personales, Secreto Fiscal, Estadística, etc.), a fin de de facilitar su descubrimiento, búsqueda, acceso, redistribución y reutilización por parte de los ciudadanos, en el sitio data.buenosaires.gob.ar.

  En este sentido, al momento de seleccionar los datos que serán publicados en [BA Data](https://data.buenosaires.gob.ar/) deberá tenerse en cuenta dicha normativa y luego priorizar según los siguientes criterios:

  * Responda a una demanda ciudadana

  * Impulsa la innovación

  * Incrementa la rendición de cuentas y transparencia

  * Representa los objetivos y funciones del área

  * Crea nuevas oportunidades económicas

  * Genera valor agregado para las entidades públicas y otros actores

  * Tiene alto potencial de uso y reúso para el ecosistema de datos

  * Fomente el diseño de política pública basada en evidencia

  Adicionalmente, la [Ley de Acceso a la Información Pública](https://boletinoficial.buenosaires.gob.ar/normativaba/norma/982)  N° 104 de la Ciudad de Buenos Aires ha establecido una serie de componentes mínimos a ser publicados por las áreas en formato abierto, mientras que propicia que aquellas respuestas a pedidos concretos que se ajusten a los criterios de apertura de datos puedan ser publicadas en formato abierto en [Buenos Aires Data](https://data.buenosaires.gob.ar/).

  Por último, la DGGDA podrá solicitar a las entidades la apertura de un recurso en función de los criterios anteriormente mencionados. Por último, la DGGDA podrá sugerir a las entidades la apertura de un recurso en función de los criterios anteriormente mencionados  

## Esquema de apertura

### 1. Identificación de apertura

  La incorporación de un nuevo conjunto de datos puede surgir de diversas fuentes, entre las que se pueden mencionar:

  * Publicación proactiva del área

  * Respuesta a un pedido de Acceso a la Información Pública por Ley N° 104

  * Información estipulada en el Plan de Transparencia Activa

  * Solicitud por un tercero a través de BA Colaborativa

  * Incluido en Compromisos de Gobierno

  * Publicación establecida por normativa

  * Relevamiento de la web de Gobierno

  * Estipulado por Decreto 478/2013

  * Producto de un proceso de mesas de Estado Abierto.

  * Propuestas de la DGGDA

### 2. Acuerdo con el área

  Una vez identificado el dato, la DGGDA analiza con el área responsable la factibilidad de su apertura. En esta etapa se tiene especial consideración aquellas normativas vigentes que regulan o que podrían alcanzar al conjunto de datos.

  En caso de ser posible su publicación, las partes acuerdan las condiciones de esta apertura (estructura, formato y frecuencia de actualización).

### 3. Análisis y Normalización

  Siguiendo el acuerdo alcanzado, el área responsable disponibiliza en el formato convenido los datos a la DGGDA para un análisis en profundidad previo a su apertura.

  Teniendo en consideración la Guía de Apertura de Datos de la Ciudad de Buenos Aires, la DGGDA analiza exhaustivamente los datos provistos a fin de adecuarlos a los estándares definidos, así como verificar su coherencia. En caso de que sea necesario se aplicarán las transformaciones necesarias a fin de disponer los datos y la estructura en el formato adecuado, sin alterar su representación.

### 4. Publicación y notificación

  La DGGDA disponibiliza el conjunto de datos en BA Data siguiendo los criterios acordados con el área responsable.

### 5. Monitoreo de Apertura

  La DGGDA, en conjunto con el responsable de datos del área, realizarán un monitoreo de la actualización y la calidad de los recursos. Asimismo, realizarán un seguimiento al nivel de usabilidad del dataset e informarán al área correspondiente casos de reúso.

## Licencia de utilización de datos

  La publicación de datos abiertos no solo implica poner información a disposición del público, sino también garantizar que esta pueda ser utilizada de manera libre, segura y conforme a estándares internacionales. 

  Los datos abiertos son un recurso público disponible para que cualquiera los pueda usar, modificar y compartir, en tal sentido se aplicarán siempre Licencia Creative Commons Attribution 4.0 (CC BY 4.0) para todos sus contenidos digitales. 

  Dicha licencia habilita para compartir y redistribuir el material en cualquier medio o formato, así como a adaptar, remezclar y construir a partir del contenido, incluso con fines comerciales. La única condición es cumplir con la atribución correspondiente, es decir, citar adecuadamente la fuente original de los datos y señalar si se han realizado modificaciones sobre el material original. 

## Criterios Técnicos para la Gestión de Recursos en Datos Abiertos

  Esta sección presenta los lineamientos técnicos adoptados por el equipo de Datos Abiertos para la gestión, estructuración, normalización y estandarización de los datos publicados en el portal. Su contenido reúne criterios esenciales para la conformación de recursos y datasets, los cuales permiten garantizar coherencia estructural, interoperabilidad semántica y consistencia técnica entre las distintas publicaciones.

  La consecución de estas prácticas toma como base los Lineamientos para la Gobernanza de Datos del GCBA, así como los estándares internacionales y normativas vigentes adoptadas a nivel local.

  Las principales herramientas técnicas utilizadas para la gestión de datos son las siguientes: 

  * **Diccionario de Datos y Metadatos:** cómo debe estar estructurado cada dato.
  * **Formatos abiertos de archivos:** cuáles son los formatos más usuales en los que se publican datos y cuáles son los más recomendables.
  * **Fragmentación de archivos:** criterios para decidir si un archivo es demasiado grande (y debe fragmentarse) o demasiado pequeño (y debe agruparse con otros).
  * **Nomenclatura de archivos:** cómo nombrar adecuadamente un archivo.
  * **Codificación:** en qué codificación se debe guardar un archivo.
  * **Estructura y características de los datos tabulares.**
    + **Recomendaciones generales:** aplican a todos los casos.
    + **Recomendaciones para estructurar planillas de cálculo:** aplican exclusivamente al trabajo en planillas de cálculo.
    + **Exportación a CSV:** cómo exportar adecuadamente planillas de cálculo a un archivo de formato abierto.
  * **Estándares según el tipo de datos:** cuáles son los estándares recomendados para manejar distintos tipos de datos.

  Estos constituyen los aspectos iniciales clave para la estandarización de datos. En los apartados siguientes, cada uno de ellos se desarrolla en profundidad.

  Para una discusión sobre los estándares recomendados en el manejo de datos básicos y fundamentales, transversales a distintas áreas temáticas, se puede consultar la [Guía para la identificación y uso de entidades interoperables de la Ciudad Autónoma de Buenos Aires](https://datosgcba.github.io/guia-datos/guia-interoperables/).

### Diccionario de Datos y Metadatos

  Como parte del esfuerzo por mejorar la calidad y estandarización de los datos abiertos, el Gobierno de la Ciudad Autónoma de Buenos Aires cuenta con un Diccionario de Datos y Metadatos aprobado por Disposición N° 13-DGGDA/24. Esta herramienta fundamentada en estas directrices proporciona definiciones detalladas sobre los formatos de los datos utilizados en las distintas áreas de gobierno, asegurando un modelo unificado para su denominación y estructuración.

  Su uso facilita la interoperabilidad, mejora la precisión de la información y permite que todas las áreas trabajen con un mismo criterio. Al establecer un lenguaje común para los datos ayuda a optimizar procesos internos y fortalecer la transparencia de la gestión pública.

  El Diccionario se encuentra alojado en el Sistema de Administración Documental Electrónica (SADE), dentro del módulo Registro de Legajo Multipropósito (RLM), y se actualiza en tiempo real para garantizar la vigencia de su contenido. Ante la identificación de una nueva necesidad de datos, la Dirección General de Gobernanza de Datos, o el área que la reemplace, será responsable de analizar y realizar las adecuaciones necesarias en el Diccionario.

  Para obtener más detalles, se recomienda consultar [el manual de uso del Diccionario de Datos y Metadatos del Gobierno de la Ciudad de Buenos Aires](https://cdn2.buenosaires.gob.ar/manual_diccionario_de_datos_metadatos.pdf).

### Formatos abiertos de archivos

  Hay una gran variedad de tecnologías disponibles para producir y almacenar datos (planillas de cálculo, bases de datos, software estadístico más específico, entre otros), algunos de ellos con un nivel bajo de apertura y de difícil reúso. En este cuadro consideramos algunos de los formatos más usados y evaluamos su nivel de apertura:

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <th>Formato</th>
    <th>Descripción</th>
    <th>Tipo de datos</th>
    <th>Nivel de apertura</th>
  </tr>
  <tr>
    <td>PDF</td>
    <td>Los PDF son archivos de texto que no se encuentran en formato estructurado.</td>
    <td>Texto</td>
    <td>Bajo</td>
  </tr>  
  <tr>
    <td>XLS</td>
    <td>Los XLS son archivos de planilla de cálculo. Es un formato propietario de MS Office.</td>
    <td>Tabulares</td>
    <td>Bajo</td>
  </tr>
  <tr>
    <td>XLSX</td>
    <td>Los XLSX son archivos con la estructura de un XML. Es un formato abierto basado en Office Open XML (ISO/IEC 29500:2008), lo que permite que pueda ser utilizado por diversos software de planillas de cálculo. Popularizado por ser el formato por defecto del procesador de planillas de cálculo desde MS Office 2007.</td>
    <td>Tabulares</td>
    <td>Medio</td>
  </tr>
  <tr>
    <td>ODS</td>
    <td>Los ODS son archivos con la estructura de un XML. Es un formato abierto basado en OASIS OpenDocument Format (ISO/IEC 26300). Es el formato por defecto del procesador de planillas de cálculo Open Office.</td>
    <td>Tabulares</td>
    <td>Medio</td>
  </tr>
  <tr>
    <td>CSV</td>
    <td>Los archivos CSV son archivos de texto plano donde las columnas se separan por comas y las filas por saltos de línea. Es un formato abierto para datos tabulares.</td>
    <td>Tabulares</td>
    <td>Alto</td>
  </tr>
  <tr>
    <td>JSON</td>
    <td>Es un formato para el intercambio de datos. En mayor medida que los formatos anteriores, JSON es especialmente útil para datos entre máquinas. Es un formato abierto basado en la especificación RFC 7159.</td>
    <td style="font-size: 12px" >Estructurados</td>
    <td>Alto</td>
  </tr>
  <tr>
    <td>KML</td>
    <td>Es un formato abierto para datos geográficos basado en el estándar XML.</td>
    <td style="font-size: 12px" >Geográficos</td>
    <td>Alto</td>
  </tr>
  <tr>
    <td>GeoJSON</td>
    <td>Es un formato estándar abierto diseñado para representar elementos geográficos sencillos, junto con sus atributos no espaciales.</td>
    <td style="font-size: 12px" >Geográficos</td>
    <td>Alto</td>
  </tr>
  <tr>
    <td>GeoPackage</td>
    <td>Es un formato de datos geoespaciales implementado como un contenedor de base de datos SQLite.</td>
    <td style="font-size: 12px" >Geográficos</td>
    <td>Alto</td>
  </tr>
</tbody>
</table>

  Antes de seguir, introduciremos dos conceptos que se usarán a lo largo de toda la guía:

  * **Distribución o Recurso:** Una distribución o recurso es la unidad mínima en la que se publican datos. Se trata de los archivos que pueden ser descargados y re-utilizados por un usuario. Los recursos pueden tener diversos formatos (.csv, .shp, etc.).

  * **Dataset:** Un conjunto de datos o dataset agrupa recursos referidos a un mismo tema que respetan una estructura de la información. Los recursos que lo componen pueden diferir en el formato en que se los presenta (por ejemplo: .csv, .json, .xls, etc.), la fecha a la que se refieren, el área geográfica cubierta, ser tablas de un mismo esquema de base de datos relacional o estar separados bajo algún otro criterio.

  Un recurso en formato tabular es un archivo plano que se ajusta a un esquema predefinido de columnas, incluyendo el nombre de la columna y el tipo de datos.

  En la mayoría de los casos, corresponde a datos que llegan de bases de datos, reportes y planillas de cálculo en general. A diferencia de los formatos tabulares, los archivos JSON siguen una estructura diferente donde se definen listas de objetos con pares "clave" - “valor”.

  **Recomendamos con énfasis la publicación de los datos en formato CSV, XLSX y/o JSON.** En caso de utilizar formatos propietarios o aún no estandarizados, es útil indicar software, versión y aplicación que permite procesar esos formatos.

## CSV

  El CSV es un formato estándar de archivo de texto plano donde:

  * Los campos (columnas) se separan por comas.

  * Los registros (filas) se separan por saltos de línea \n o \r\n (CRLF - Carriage Return Line Feed)).

  * Los números decimales se utilizan para separar la parte entera de la parte decimal

  * **Durante la exportación a CSV, la codificación (encoding, en inglés) siempre debe ser UTF-8**, garantizando la correcta interpretación de caracteres en distintos sistemas y aplicaciones.

  * Se utilizan las comillas dobles ``` " ``` como caracter de entrecomillado. Los valores en tablas CSV que incluyen dentro de sí caracteres especiales como, o ``` " ```, deben estar encerrados entre ``` " ``` para su correcta interpretación.

  Algunas versiones alternativas de esta forma de publicar datos usan otros separadores como punto y coma (``` ; ```) o pipe (``` | ```), pero la recomendación para todos los organismos del Gobierno de la Ciudad Autónoma de Buenos Aires, siguiendo los lineamientos para la Administración Pública Nacional, se basa en la versión de CSV más estándar, indicada por la especificación [RFC4180](https://datatracker.ietf.org/doc/html/rfc4180) y las pautas de la [W3C](https://www.w3.org/TR/tabular-data-model/).

  Otros elementos a tener en cuenta:

  * La primera fila siempre contiene los nombres de los campos.

  * No se deben repetir nombres entre los campos.

  * No se debe colocar espacios al principio ni al final del nombre de un campo, o de un valor.

  * Tanto los campos como los valores deben estar separados por comas (``` , ```).

  * En el caso de que un valor contenga el caracter separador (``` , ```) o cualquiera de los caracteres que separan las líneas (\r, \n o \r\n), el valor completo debe ser encerrado entre comillas dobles ``` "" ```. Esto indica que el caracter no cumple el rol de separar columnas o filas, sino que es parte de un valor

  Ejemplo:

  ```
  col1,col2\r\n
  "La tasa de Juan, está vacía",La tasa de Pablo está llena\r\n
  "La tasa de Juan\nestá vacía",La tasa de Pablo está llena\r\n
  "La tasa de Juan\r\nestá vacía",La tasa de Pablo está llena\r\n
  ```

  * En el caso de que un valor contenga el caracter comilla doble (``` " ```), el valor debe ser encerrado entre comillas dobles como en el caso anterior (``` "" ```) y, además, los caracteres comilla doble que se encuentren dentro del valor deben escribirse dos veces (``` "" ```).

  Ejemplo:

  ```
  col1,col2\r\n
  "La tasa de ""Juan"" está vacía",La tasa de Pablo está llena\r\n
  ```

  + Para todos los tipos de datos, el valor indefinido se expresará con "NULL" (o "N/A" según corresponda) en lugar de dejar la celda vacía. No se utilizarán otros valores como ".", "none", "CD", etc.

  Ejemplo:

  ```
  col1,col2,col3\r\n
  a,NULL,b\r\n
  a,N/A,b\r\n
  ```

  * En el **Diccionario de Datos y Metadatos**, el atributo Observaciones detalla la forma en que cada tipo de dato debe representar la ausencia de valor.

  Cabe destacar que un archivo csv puede convertirse en un archivo de planilla de cálculo ingresando al formato propietario de MS Office o software similar, donde los campos se separarán en columnas independientes a través de (```,```).

## JSON

  JSON es un formato de texto popular para el intercambio de datos, es un acrónimo de JavaScript Object Notation. Por su característica de ser un formato de tipo estructurado es especialmente útil para el intercambio de datos entre máquina (machine - readable format).

  El formato JSON ha sido definido por la especificación [RFC 7159](https://datatracker.ietf.org/doc/html/rfc7159) y, tal como CSV, también es un estándar abierto.

## Fragmentación de archivos

  Para garantizar la accesibilidad a los datos, es necesario fragmentar los archivos excesivamente grandes, que superen el millón de filas.

  Para esto, recomendamos usar conceptos simples, fragmentando:

  (a) **por períodos** en caso de tratarse de información temporal (Ej. Años, semestres, trimestres, meses, semanas, días),

  (b) **por zonas** en caso de tratarse de información geográfica (Ej. comunas, barrios, secciones, manzanas o parcelas) o

  (c) **por dimensiones temáticas** propias del dominio particular de la información.

  Sin embargo, siempre que se decida fragmentar un archivo para garantizar su accesibilidad, recomendamos publicar también una versión no fragmentada que contenga el conjunto de datos completo (aunque sea muy grande), a los fines de evitar la tarea de consolidación.

  Para eso, sugerimos usar protocolos de compresión, en especial para archivos muy grandes, y altamente compresibles. De hacerlo, aconsejamos protocolos sin pérdida, y abiertos. Sugerimos utilizar el formato de compresión ZIP.


## Nomenclatura de archivos

  Recomendamos estas convenciones para nombrar archivos:

  * Usar palabras siempre en minúsculas.
  * No usar artículos.
  * Usar únicamente letras y números ASCII, siempre en minúsculas, comprendidos en el rango "a-z" y “0-9”.
  * Separar las palabras con guión medio "-".
  * En caso de corresponder, ubicar la referencia temporal o del atributo de fragmentación siempre al final (*).

  Ejemplos:

  ```
  •	procesos-de-compra-pliego.csv: Versión completa del recurso.
  •	procesos-de-compra-pliego-2018.csv: Versión del recurso fragmentada por año.
  •	procesos-de-compra-pliego-2010-al-2013.csv: Versión del recurso fragmentada por período.
  ```
  
  Para la fragmentación temporal, recomendamos el estándar de los ejemplos, ya que es compacto y ordena los recursos por tiempo: YYYYMMDD. Por favor, recordá mantener siempre dos dígitos para el mes y el día, incluso si el número es menor a 10.

  Ejemplo:

  ```
  •	procesos-de-compra-pliego-20240315.csv → Archivo correspondiente al 15 de marzo de 2024.
  •	procesos-de-compra-pliego-202501.csv → Archivo correspondiente a enero de 2025.
  •	procesos-de-compra-pliego-20231005.csv → Archivo correspondiente al 5 de octubre de 2023.
  ```
 **(*) Nota:** La nomenclatura utilizada sigue buenas prácticas reconocidas internacionalmente. Como alternativa, se puede optar por ubicar la fecha al inicio del nombre del archivo para priorizar la ordenación cronológica. 

 Ejemplo:

   ```
  •	20240315-procesos-de-compra-pliego.csv
  •	202501-procesos-de-compra-pliego.csv
  ```
  Para la fragmentación por zonas, consultá la [Guía para la identificación y uso de entidades interoperables de la Ciudad Autónoma de Buenos Aires](https://datosgcba.github.io/guia-datos/guia-interoperables/), y mirá cómo nombrarlas adecuadamente.

  En el caso de usar dimensiones temáticas propias del dominio particular de la información, podés ver esa guía o usar el mejor estándar identificado para esa temática particular.

  En caso de comprimir varios archivos, recomendamos mantener la misma nomenclatura para todos los archivos (con distintos tipos de formato), incluso para el comprimido.

  * En el **Diccionario de Datos y Metadatos**, se encuentra descrito bajo el nombre “Nombre de archivo”.

## Codificación

  De acuerdo con los lineamientos establecidos para la Administración Pública Nacional, todos los recursos de datos, incluyendo los geográficos, deben publicarse usando la codificación UTF-8 siguiendo las [recomendaciones de la W3C](https://www.w3.org/TR/tabular-data-model/#h-encoding).

  Una de las principales razones es que UTF-8 soporta una gran variedad de lenguajes, [según la W3C](https://www.w3.org/International/questions/qa-choosing-encodings) es un "estándar en el que se definen todos los caracteres necesarios para la escritura de la mayoría de los idiomas hablados en la actualidad. Su objetivo es ser, y, en gran medida, ya lo ha logrado, un superconjunto de todos los sets de caracteres que se hayan codificado".

## Estructura y características de los datos tabulares

  En esta sección veremos:

  (a) Recomendaciones generales para el trabajo con datos, y

  (b) Recomendaciones para el trabajo con planillas de cálculo, orientadas tanto a facilitar su exportación a formatos abiertos, como a su propia usabilidad en el contexto de cualquier aplicación de planillas de cálculo.

### Recomendaciones generales

  Muchas de las recomendaciones, tomadas de la Guía de Nación, se encuadran en los principios de [Tidy Data](https://www.jstatsoft.org/article/view/v059i10/v59i10.pdf) delineados por [Hadley Wickham](https://hadley.nz/). Éstos establecen, por ejemplo, que en una tabla de datos "cada variable es una columna, cada observacion es una fila, y cada tipo de unidad observacional es una tabla". Sugerimos complementar la lectura de esta guía con la del trabajo que mencionamos.

####  Nomenclatura de los campos (nombres de las columnas)

  La "nomenclatura de los campos" es el nombre de las columnas en los datos de estructura tabular. Estas recomendaciones aplican a la generalidad de los casos, pero cuando haya convenciones particulares según la temática o rubro de datos de que se trate y éstas entren en conflicto, puede ser conveniente privilegiar primero la convención de la temática específica y luego la convención general.

  Los nombres de los campos deben:

  * Estar en español.

  * Ser lo más explícitos, descriptivos y declarativos como sea posible.

    + Es preferible que el nombre de un campo sea claro antes que corto, pero se recomienda no superar los 50 caracteres.

    + No usar abreviaturas si no es estrictamente necesario o recomendado por una convención ampliamente difundida. En caso de usarlas, incluirlas en el diccionario de datos.

  * Estar en minúsculas, no incluir caracteres especiales, ni estar subrayados.

  *	Usar palabras compuestas únicamente de caracteres en minúsculas comprendidos en el rango a-z (letras sin tildes) y en el rango 0-9 (dígitos).

  *	No contener espacios.

  *	Las palabras deben separarse siempre con guión bajo " _ ", en lugar de no tener separación alguna: fecha_audiencia_solicitada en lugar de fechaaudienciasolicitada.

  *	Referirse a un sólo atributo de los datos, indivisible en más de un campo.

  *	Los campos deben separar los atributos de los datos en la forma más desagregada que sea posible.

  *	Se debe evitar definir campos que contengan más de un tipo de información (por ejemplo: e-mail y sitio web, número de teléfono, etc. bajo "datos_de_contacto").

  *	Si existe una entidad que engloba varias características separadas en campos diferentes, comenzar nombrando los campos con esa entidad y luego con los atributos más específicos (de lo más general a lo más específico).
  Ej.: en los pedidos de acceso a la información pública, “solicitante” es una entidad que puede repetirse en varios campos que corresponden a atributos más específicos:

    + solicitante_id
    + solicitante_tipo

  * Resulta más fácil identificar qué campos están relacionados entre sí porque configuran atributos de una misma entidad, en lugar de parecer campos conceptualmente independientes. Además, el ordenamiento alfabético de los campos los dejaría automáticamente agrupados por su pertenencia a una entidad más importante.

  * Incluso cuando la entidad de un atributo parezca evidente (ej.: un dataset llamado "audiencias" donde todos los campos son atributos de la entidad “audiencia”), se recomienda nombrar el campo incluyendo la entidad a la que hace referencia el atributo.

    + **No recomendado:** “fecha_hora”
    + **Recomendado:** "audiencia_id", “audiencia_fecha_hora”.Los campos que sean identificadores o códigos, deberán incluir el sufijo "_id" en el nombre del campo, salvo casos excepcionales donde un nombre alternativo sea más conveniente porque ofrece información sobre el sistema de identificación usado.

  * En cuanto a los campos que contengan la descripción de ese identificador, se recomienda que incluyan el sufijo "_desc" (por "descripción") en caso de que no exista una forma más conveniente de nombrar el campo.

  **Recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>contracts_item_id</td>
    <td>contracts_items_desc</td>
  </tr>  
  <tr>
    <td>20.01.001.0009.2-10</td>
    <td>TELEVISOR INTELIGENTE (SMART)</td>
  </tr>
  <tr>
    <td>03.02.001.0061.3-2</td>
    <td>SERVICIO DE ARTES GRAFICAS - GRABADO SOBRE BOLIGRAFO</td>
  </tr>
  </tbody>
  </table>

  * En el **Diccionario de Datos y Metadatos**, se encuentra descrito bajo el nombre “Nombre del campo”.


####  Nivel de granularidad de los datos

  Por favor, no incluir totales, subtotales ni agrupamientos de datos. Un dataset debe ser consistente en el nivel de granularidad de los datos que contiene. Está bien tener un dataset con la cantidad de proyectos por comuna y está bien tener un dataset con la cantidad de proyectos firmados por barrio. No está bien tener un dataset que mezcle ambos.

  Dicho esto, el dato agregado "proyectos firmados por comuna" siempre se puede calcular a partir de un proceso del dataset más desagregado, pero esto no es así a la inversa (es imposible recuperar los datos a nivel de barrio desde el dataset comunal).

  **No recomendado** - datos con subtotales y/o totales incluidos (diferentes niveles de granularidad)

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>barrio_caba</td>
    <td>proyectos_anio</td>
    <td>proyectos_numero</td>
  </tr>  
  <tr>
    <td> </td>
    <td>Barrio X</td>
    <td>Barrio W</td>
    <td>2011</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Barrio X</td>
    <td>2011</td>
    <td>15</td>
  </tr>
  <tr> 
    <td>1</td>
    <td>Subtotal</td>
    <td>2011</td>
    <td>25</td>
  </tr>
  <tr>	 
    <td>3</td>
    <td>Barrio Z</td>
    <td>2011</td>
    <td>5</td>
  </tr>
  <tr>	 	 	 
    <td>3</td>
    <td>Subtotal</td>
    <td>2011</td>
    <td>5</td>
  </tr>
  <tr>
    <td> </td>
    <td>TOTAL</td>
    <td>2011</td>
    <td>30</td>
  </tr>
  </tbody>
  </table>

  **Recomendado** - datos de un mismo nivel de granularidad

   <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>1</td>
    <td>Barrio W</td>
    <td>2011</td>
    <td>10</td>
  </tr>
  <tr>	 
    <td>3</td>
    <td>Barrio X</td>
    <td>2011</td>
    <td>15</td>
  </tr>
  <tr>
    <td>15</td>
    <td>Barrio Z</td>
    <td>2011</td>
    <td>5</td>
  </tr>
  </tbody>
  </table>

####  Usar orientación vertical en lugar de horizontal

  Es preferible que la orientación de los datos sea "vertical" en lugar de “horizontal” en los casos en que esto sea posible. La principal razón es que los datos orientados de manera vertical facilitan el tratamiento y análisis de los datos.

  **No recomendado** - Orientación horizontal

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>solicitudes_anio</td>
    <td>solicitudes_poda_y_arbolado_numero</td>
    <td>solicitudes_recoleccion_residuos_numero</td>
  </tr>  
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>340</td>
    <td>198</td>
  </tr>
  </tbody>
  </table>

  **Recomendado** - Orientación vertical

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>solicitudes_anio</td>
    <td>solicitudes_categoria</td>
    <td>solicitudes_numero</td>
  </tr>  
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>Poda y arbolado</td>
    <td>340</td>
  </tr>
    <tr>
    <td>6</td>
    <td>2015</td>
    <td>Recolección de residuos</td>
    <td>198</td>
  </tr>
  </tbody>
  </table>

####  Incluir sólo un atributo por campo

  Se recomienda definir los campos de forma atómica de modo de incluir un sólo atributo por elemento, en lugar de datos múltiples, generando campos adicionales de ser necesario.

  **No recomendado** - múltiples datos en una celda

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>solicitudes_anio</td>
    <td>categoria_solicitudes_numero_y_tipo</td>
  </tr>  
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>Poda y arbolado - 340 Recolección de residuos - 198</td>
  </tr>  
  </tbody>
  </table>

  **Recomendado** - un dato por celda

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td> </td>
    <td>solicitudes_anio</td>
    <td>solicitudes_categoria</td>
    <td>solicitudes_numero </td>
  </tr>  
   <tr>
    <td>6</td>
    <td>2015</td>
    <td>Poda y arbolado</td>
    <td>340</td>
  </tr>  
    <tr>
    <td>6</td>
    <td>2015</td>
    <td>Recolección de residuos</td>
    <td>198</td>
  </tr> 
  </tbody>
  </table>

####  Valores nulos, desconocidos o no aplicables en los datos

  No se permiten celdas vacías. En su lugar, se debe utilizar:

  * **NULL:** cuando el dato no está disponible o no existe.

  * **N/A:** cuando el dato no es aplicable en el contexto del registro.

  En los campos numéricos, un valor nulo o ausente **no debe representarse con "0"**, ya que el **"0"** es un valor válido y debe indicarse explícitamente cuando corresponda.

  Si existen distintas interpretaciones de un "valor ausente", estas deben ser explicitadas en un campo aparte. Si solo hay una interpretación posible, no es necesario agregar una columna adicional.

  **No recomendado** - celdas vacías o valores inconsistentes en los campos

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>solicitudes_numero</td>
    <td>34</td>
    <td>NA</td>
    <td> </td>
    <td>...</td>
    <td> </td>
    <td> </td>
    <td>567</td>
  </tr>  
  </tbody>
  </table>

  **Recomendado** - uso explícito de valores nulos y no aplicables

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>solicitudes_numero</td>
    <td>solicitudes_numero_missing_desc</td>
  </tr>  
  <tr>
    <td>34</td>
    <td> </td>
  </tr>
  <tr>
    <td>NULL</td>
    <td>No disponible</td>
  </tr>
   <tr>
    <td>N/A</td>
    <td>No aplica</td>
  </tr>
    <tr>
    <td>NULL</td>
    <td>Valor ausente</td>
  </tr>
    <tr>
    <td>0</td>
    <td> </td>
  </tr>
  <tr>
  <td>567</td>
  <td> </td>
  </tr>
  </tbody>
  </table>

  * En el **Diccionario de Datos y Metadatos**, el atributo Observaciones detalla la forma en que cada tipo de dato debe representar la ausencia de valor.

### Recomendaciones para estructurar planillas de cálculo

  Las recomendaciones de esta sección aplican exclusivamente al trabajo sobre planillas de cálculo.

#### Usar celdas simples

  Recomendamos usar celdas simples y, en ningún caso, combinar celdas.

  **No recomendado** - celdas combinadas

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>proveedor_nombre</td>
    <td colspan="2">contacto_datos</td>
  </tr>
    <tr>
    <td> </td>
    <td>correo_electronico</td>
    <td>telefono</td>
  </tr>  
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>1143XXXXXX</td>
  </tr>
  </tbody>
  </table>

  **Recomendado** - celdas simples, sin combinar

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>proveedor_nombre</td>
    <td>contacto_correo_electronico</td>
    <td>contacto_telefono</td>
  </tr>  
    <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>1143XXXXXX</td>
  </tr>
  </tbody>
  </table>

#### Fila de encabezado

  Los datos deben contener sólo una fila de encabezado. Desde la segunda fila en adelante, sólo debe haber datos, pero nunca un encabezado.

  **No recomendado** - múltiples filas de encabezado

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>Nombre del</td>
    <td>Dirección de correo</td>
    <td>Teléfono de</td>
  </tr>  
  <tr>
    <td>proveedor</td>
    <td>electrónico de contacto</td>
    <td>contacto</td>
  </tr>  
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>1143XXXXXX</td>
  </tr>
  </tbody>
  </table>

  **Recomendado** - encabezado de una única fila

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>proveedor_nombre</td>
    <td>contacto_correo_electronico</td>
    <td>contacto_telefono</td>
  </tr>  
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>1143XXXXXX</td>
  </tr>    
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>1143XXXXXX</td>
  </tr>
  </tbody>
  </table>


#### Celdas vacías en filas para agrupar conceptos

  Recomendamos no dejar celdas vacías en filas bajo la presunción de que valores en blanco posteriores a un valor positivo contienen implícitamente a ese mismo valor en una suerte de "agrupamiento conceptual".

  Este error es muy común en la construcción de planillas de cálculo y suele generar problemas graves cuando cambia el orden original de las filas. Además, impide el uso de tablas dinámicas y otras formas de analizar los datos.

  **No recomendado** - primera celda de la segunda fila vacía

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>solicitudes_anio</td>
    <td>solicitudes_categoria</td>
    <td>solicitudes_numero</td>
  </tr>  
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>Poda y arbolado</td>
    <td> </td>
  </tr>
  <tr>
    <td> </td>
    <td>2015</td>
    <td>Recolección de residuos </td>
    <td>198</td>
  </tr>
  </tbody>
  </table>

  **Recomendado** - primera celda de la segunda fila completa

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>comuna</td>
    <td>solicitudes_anio</td>
    <td>solicitudes_categoria</td>
    <td>solicitudes_numero</td>
  </tr>  
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>Poda y arbolado</td>
    <td>340</td>
  </tr>
  <tr>
    <td>6</td>
    <td>2015</td>
    <td>Recolección de residuos </td>
    <td>198</td>
  </tr>
  </tbody>
  </table>

#### Formato de celdas

  Las celdas de una planilla de cálculo deben estar formateadas acorde al tipo de datos de que se trate. Específicamente, los **números** siempre deben estar en celdas de formato/tipo "número", **los campos de tipo textual** deben estar en celdas de formato/tipo “texto” y **los campos de tipo fecha** deben estar en celdas de formato/tipo “fecha”.

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>audiencia_fecha_hora</td>
    <td>audiencia_sujeto_obligado_nombre</td>
    <td>audiencia_numero</td>
  </tr>  
  <tr>
    <td>2025-03-01</td>
    <td>Juan</td>
    <td>3456</td>
  </tr>
  <tr>
    <td>(Fecha)</td>
    <td>(Texto)</td>
    <td>(Número)</td>
  </tr>
  </tbody>
  </table>

  Mantener el formato correcto de las celdas según el tipo de datos que contengan:

  * Mejora las las probabilidades de que una exportación a otro formato salga correctamente.

  * Hace que los datos sean más operables en la propia planilla de cálculo, aprovechando mejor sus funcionalidades.


## Estándares según el tipo de Datos

  El formato recomendado para los distintos tipos de datos está mayormente basado en las especificaciones de la W3C. En los otros casos, las recomendaciones surgen de la experiencia de trabajo del equipo de la Dirección Nacional de Datos e Información Pública, de estándares particulares definidos por organismos del Gobierno de la Ciudad Autónoma de Buenos Aires y del esfuerzo realizado en la búsqueda de estándares más adecuados.

  **A continuación, se presentan los formatos más generales y frecuentemente utilizados**, los cuales ya están definidos en el **Diccionario de Datos y Metadatos** con el detalle completo de los distintos tipos de datos y las pautas específicas para estructurar correctamente el formato de cada uno.

### Texto

  * Los campos de texto no deben contener espacios en blanco innecesarios al principio ni al final.
  
  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Cadena de caracteres”


#### Entidades

  Las entidades que aparezcan entre los datos de un campo textual deben tener una descripción única. Es decir, toda mención que se realice a una entidad dada debe hacerse usando exactamente la misma cadena de caracteres cada vez:

  * **Las descripciones de entidades** deberían elegirse siempre de forma tal que cumplan con el estándar específico que las describe, en caso de que este exista.

  * **Cuando este estándar no exista** y hay dudas respecto del criterio a adoptar para elegir la descripción única de una entidad, debe **privilegiarse siempre aquella que sea lo más explícita**, descriptiva y declarativa posible.

  En el caso de la Ciudad Autónoma de Buenos Aires, de acuerdo a los lineamientos establecidos por la Gerencia Operativa de Explotación de Datos (GOED), la Ciudad Autónoma de Buenos Aires debe referenciarse como “CABA”.

  **No recomendado**

    <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>localidad_nombre</td>
    <td>Ciudad Autónoma de Buenos Aires</td>
    <td>CABA</td>
    <td>Capital Federal</td>
    <td>Ciudad de Buenos Aires</td>
  </tr>  
  </tbody>
  </table>

  **Recomendado**

    <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>localidad_nombre</td>
    <td>CABA</td>
    <td>CABA</td>
    <td>CABA</td>
    <td>CABA</td>
  </tr>  
  </tbody>
  </table>

  En el ejemplo anterior, los cuatro valores de texto refieren a la misma entidad. Debe elegirse una única forma de referirse a la misma y usarla en todos los casos.

  Siempre que sea posible, la elección deberá fundamentarse en el estándar establecido para ese tipo de entidad (para más información ver la **Guía para la identificación y uso de entidades interoperables de la Ciudad Autónoma de Buenos Aires**). En el caso de no existir un estándar, deberá adecuarse a las pautas generales contexto del dataset que se trate.

  Por ejemplo, para el caso de localidades que conforman el Área Metropolitana de Buenos Aires (AMBA) se recomienda utilizar los nombres definidos por la Gerencia Operativa de Explotación de Datos (GOED) en IDECABA.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Localidad” y en “Localidad de AMBA”

#### Nombres propios

  **Se capitalizan** (primera letra de cada palabra es mayúscula, el resto de las letras son minúsculas) **todas las palabras significativas**, salvo las siglas. Las palabras significativas son aquellas que no cumplen la función de artículos o preposiciones.

  + En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo los nombres: “Apellidos y nombres completos de la persona”, “Nombres de la persona”, “Apellidos de la persona”

#### Instituciones del Gobierno de la Ciudad de Buenos Aires

  El nombre y las siglas de las instituciones del Gobierno de la Ciudad Autónoma de Buenos Aires serán los establecidos en la estructura de gobierno que surja del Decreto de Estructura que se dicta al efecto por el Jefe de Gobierno de la Ciudad Autónoma de Buenos Aires.  Se recomienda revisar la Guía para el uso y la publicación de metadatos del Gobierno de la Ciudad Autónoma de Buenos Aires.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Nombre formal capitalizado”

#### Siglas

  Todas las siglas se escriben en mayúsculas, sin usar puntos ni espacios intermedios.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Siglas”.


### Número

  *	El separador decimal debe ser el caracter ".".

  *	No se usará separador de miles.

  *	No se deberán usar espacios en blanco.

  *	Para los números negativos debe incluirse el símbolo menos "-” inmediatamente antes del número, sin espacio en blanco intermedio.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Siglas”.

#### Moneda

  Los valores numéricos que sean además valores monetarios se consideran números y, por lo tanto, valen las mismas recomendaciones que para ellos. Además, agregamos las siguientes recomendaciones:

  * La cantidad de decimales debe limitarse a dos, salvo que el uso de una mayor cantidad de decimales sea significativo para el caso particular.

  *	En ningún caso se incluirán símbolos o letras en el campo numérico -ya sea "$", “DOL”, “USD”, etc.

  Si en el recurso los valores monetarios están expresados en diferentes monedas, se recomienda indicarlo en un campo aparte (que puede llamarse "moneda_id") usando los códigos alfabéticos definidos en la [ISO 4127](https://www.iso.org/iso-4217-currency-codes.html).

  Ejemplo:

  *	ARS, para el peso argentino.

  *	USD, para el dólar estadounidense.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Siglas”.

#### Porcentaje

  Almacena un valor numérico que representa un porcentaje.

  *	El separador decimal debe ser el caracter punto (".") 

  *	La cantidad de decimales debe limitarse a dos, salvo que el uso de una mayor cantidad de decimales sea significativo para el caso particular. 

  *	En ningún caso se incluirán el símbolo %.

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Siglas”.

#### Números telefónicos

  En este apartado, proponemos una solución para incluir números telefónicos nacionales en los recursos de datos.

  A nivel internacional, el estándar para los números telefónicos fue desarrollado por el "Sector de Normalización de las Telecomunicaciones de la Unión Internacional de Telecomunicaciones" (ITU Telecommunication Standardization Sector) bajo la recomendación [E.164](https://www.itu.int/rec/T-REC-E.164/es).

  Para el caso de los números nacionales, el ENACOM tiene la competencia sobre el sistema de numeración telefónica. Este organismo determina que el número nacional de abonado debe estar compuesto por 10 dígitos. Estos 10 dígitos están conformados por un indicativo interurbano más un número de abonado. Pudiendo el indicativo interurbano tener entre 2 y 4 dígitos, y el número de abonado entre 6 y 8 dígitos.

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>Indicativo interurbano (ámbito geográfico al que corresponde)</td>
    <td>Número de abonado</td>
    <td>Número Nacional interurbano = Indicativo interurbano + Número de abonado </td>
    <td></td>
  </tr>  
  <tr>
    <td>11 (AMBA)</td>
    <td>4343XXXX</td>
    <td>114343XXXX</td>
  </tr>
  <tr>
    <td>351 (Ciudad de Córdoba)</td>
    <td>434XXXX</td>
    <td>351434XXXX</td>
  </tr>
    <tr>
    <td>3837 (Tinogasta)</td>
    <td>43XXXX</td>
    <td>383743XXXX</td>
  </tr>
  </tbody>
  </table>


  Esta numeración es válida para los teléfonos móviles, pero dado que para llamar a un móvil desde un teléfono fijo es necesario anteponer "15" al número de abonado, es necesario que el registro del número telefónico especifique de alguna manera si se trata de un móvil o de un teléfono fijo.


  Al no existir estándares nacionales para la inclusión de números telefónicos en recursos de datos, los números telefónicos suelen indicarse de múltiples maneras. Por ejemplo:

  **No recomendado** - Múltiples formas de indicar un número telefónico

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>proveedor_nombre </td>
    <td>contacto_correo_electronico </td>
    <td>contacto_telefono </td>
  </tr>  
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>01143XXXXXX</td>
  </tr>
  <tr>
    <td>Ejemplo2 Sociedad Anónima</td>
    <td>ejemplo2@ejemplo.com.ar</td>
    <td>011-45XXXXXX </td>
  </tr>
  <tr>
    <td>Ejemplo3 Sociedad Anónima</td>
    <td>ejemplo3@ejemplo.com.ar</td>
    <td>351 434-XXXX </td>
  </tr>
  <tr>
    <td>Ejemplo4 Sociedad Anónima</td>
    <td>ejemplo4@ejemplo.com.ar</td>
    <td>011 15 6344-XXXX</td>
  </tr>
  </tbody>
  </table>

  Para los recursos que contengan números telefónicos nacionales recomendamos como mínimo:

  * Respetar el estándar definido por el Número Nacional Interurbano utilizando la conformación de números mediante 10 dígitos.

  * Asegurarse de indicar si el teléfono es móvil o fijo.

  * Omitir el agregado de dígitos adicionales en el indicativo interurbano. Recomendamos no indicar cero inicial antes del código de área.


  Con las salvedades que comentaremos al final de este apartado, un posible abordaje sería el de la tabla a continuación:

  **Recomendado** - adecuado al estándar del Número Nacional Interurbano

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>proveedor_nombre</td>
    <td>contacto_correo_electronico</td>
    <td>tipo_numero_telefono</td>
    <td>contacto_telefono_indicativo_interurbano</td>
    <td>contacto_telefono_numero_abonado</td>
  </tr>  
  <tr>
    <td>Ejemplo Sociedad Anónima</td>
    <td>ejemplo@ejemplo.com.ar</td>
    <td>Fijo</td>
    <td>11</td>
    <td>43XXXXXX</td>
  </tr>
  <tr>
    <td>Ejemplo2 Sociedad Anónima</td>
    <td>ejemplo2@ejemplo.com.ar</td>
    <td>Fijo</td>
    <td>11</td>
    <td>45XXXXXX</td>
  </tr>
  <tr>
    <td>Ejemplo3 Sociedad Anónima</td>
    <td>ejempl3o@ejemplo.com.ar</td>
    <td>Fijo</td>
    <td>351</td>
    <td>434XXXX</td>
  </tr>
  <tr>
    <td>Ejemplo4 Sociedad Anónima</td>
    <td>ejemplo4@ejemplo.com.ar</td>
    <td>Móvil</td>
    <td>11</td>
    <td>6344XXXX</td>
  </tr>
  
  </tbody>
  </table>

  Esta recomendación no contempla estos casos específicos:

  * No será aplicable a números de uso público, ejemplo: 100, Bomberos; 911, Policía Federal; etc.

  *	Para casos que requieran la inclusión de más de un número telefónico. Deberán agregarse campos o modificar la estructura de la base de datos.

  *	Para teléfonos que requieran la inclusión de un número de interno, y al estar éste definido por la persona u organización específica, deberá considerarse la inclusión de otro campo de tipo texto. Ya que los números de interno pueden incluir texto. Ejemplo: "*86", “#36”, etc.

  *	Para el casos de números internacionales recomendamos contemplar el estándar internacional [E.164](https://www.itu.int/rec/T-REC-E.164/es).


  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo los nombres: “Telefono fijo completo”, “Nro de telefono móvil completo”, “Código de pais para llamada telefónica”, “Código de área para llamada telefónica”, “Número telefónico local o nro de móvil”. 

#### Coordenadas

  El estándar utilizado para la referencia del sistema de coordenadas (Coordinate Reference Systems) es el [EPSG: 4326 - WGS 84](https://spatialreference.org/ref/epsg/4326/).

  Para registrar datos de coordenadas geográficas de puntos, usamos números decimales. Los campos deberán llamarse "lat" y “long”. Cuando sea conveniente especificar el nombre de la entidad de la cual se consignan las coordenadas, se usarán los sufijos “_lat” y “_long”.  

  Para más información contactar a la GOED.

  Los valores latitud y longitud pueden estar en una misma celda (Lat/long) o separadas, ambas opciones son válidas. 

  **No recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>lat</td>
    <td>long</td>
  </tr>  
  <tr>
    <td>34º 11' 30''</td>
    <td>58º 43' 20''</td>
  </tr>
  </tbody>
  </table>

  **Recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>lat</td>
    <td>long</td>
  </tr>  
  <tr>
    <td>-34.6043222</td>
    <td>-58.4134862</td>
  </tr>
  </tbody>
  </table>

  Para datos geográficos que no sean coordenadas/puntos (por ejemplo líneas o polígonos) recomendamos su especificación en WKT (Well Known Text). Los puntos/coordenadas también se pueden representar en WKT, pero en estos casos recomendamos utilizar latitud y longitud para representarlos.

  También para datos geográficos, recomendamos incluir por una parte un CSV con campos geográficos (en WKT o puntos de coordenadas), y por otra parte el archivo en su formato geoespacial (en alguno de los formatos recomendados anteriormente).

  •	En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo los nombres: "Coordenadas geográficas” en una misma celda y por separado “Latitud” y “Longitud”. También se podrán encontrar los datos “Coordenadas Planas/Catersianas” y “Datos geométricos/geográficos”

### Tiempo

#### Fecha

  Se usará el estándar [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601) (YYYY-MM-DDTHH:MM:SS[.mmmmmm][+HH:MM]). 

  A menos que se indique lo contrario, se asumirá que la zona horaria es UTC-03:00 (Argentina).

  *	Fecha: YYYY-MM-DD

  *	Hora: HH:MM:SS[.mmmmmm][+HH:MM]

  *	Fecha y Hora: YYYY-MM-DDTHH:MM:SS[.mmmmmm][+HH:MM]

  *	Duración: P[n]Y[n]M[n]DT[n]H[n]M[n]S 

  +	Donde: P indica el comienzo de la duración, 

  +	Y es el número de años, 

  +	M es el número de meses, 

  +	D es el número de días, 

  +	T indica el inicio de la parte de tiempo, 

  +	H es el número de horas, 

  +	M es el número de minutos, 

  +	S es el número de segundos.

  Ejemplos de duración:

  +	**Duración de 3 años, 2 meses y 10 días:**  ➡ P3Y2M10D

  +	**Duración de 5 horas, 30 minutos y 15 segundos:**  ➡ PT5H30M15S

  * En el **Diccionario de Datos y Metadatos**, estos datos se encuentran bajo los nombres: “Fecha”, “Hora”, “Fecha y hora”, “Duración”. 

#### Rangos horarios

  *	Los rangos estarán divididos en dos partes separadas por un doble guión bajo "__", la primera indica el día y la segunda, la hora.

  *	Se puede omitir la parte del día o bien de la hora pero nunca ambas.

  *	Si se omite la parte que indica el día se asumirá que el rango abarca todo el horario indicado.

  *	Si se omite la parte que indica el horario se asumirá que el rango abarca todo el día indicado.

  *	El día se puede indicar tanto mediante rangos separando los días con guiones medios "-" o bien como particulares con el guión bajo "_".

  Ejemplos de formatos válidos para días:

  DAY: Un solo día

  DAY1-DAY2: Entre entre DAY1 y DAY2

  DAY1_DAY2: DAY1 y DAY2

  DAY1-DAY2_DAY3: DAY1 a DAY2 y DAY3

  * La hora se indica mediante rangos, separando los horarios con guiones medios ("-"). También se pueden indicar varios horarios con el guión bajo "_".

  Ejemplos de formatos válidos para horas:

  HH:MM-HH:MM : Rango simple

  HH:MM-HH:MM_HH:MM-HH:MM : Dos rangos

  Más ejemplos de formatos válidos completos:

  HH:MM-HH:MM para indicar un rango que ocurre todos los días.

  DAY para indicar que el rango ocupa todo el día DAY.

  DAY__HH:MM-HH:MM para indicar un rango que ocurre los días DAY entre HH:MM y HH:MM.

  DAY__HH:MM-HH:MM_HH:MM-HH:MM para indicar mas un rango horario en el mismo día

  DAY1-DAY2__HH:MM-HH:MM para indicar un rango que ocurre los días DAY1 a DAY2 entre HH:MM y HH:MM

  DAY1-DAY2__HH:MM-HH:MM_HH:MM-HH:MM para indicar mas un rango horario en el mismo rango de días

  * En caso de que se necesite cubrir más de una franja horaria y esta sintaxis sea insuficiente, se pueden incluir varias separadas por espacios.

  * Los días se indicarán con sus iniciales en castellano: LUN, MAR, MIE, JUE, VIE, SAB y DOM

  + En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Días de la semana”.

  Ejemplos:

  24hs -> "00:00-23:59" 

  Jueves 24hs -> "JUE" 

  Jueves de 14:30 a 17 hs -> "JUE__14:30-17:00" 

  Jueves de 8 a 12 hs y de 16 a 20 hs -> "JUE__08:00-12:00_16:00-20:00" 

  Jueves de 8 a 15 hs y Viernes de 8 a 15 hs -> "JUE__08:00-15:00 VIE_08:00-15:00" 

  Lunes a Viernes 7:30 a 17 hs y Sábados 8 a 12 hs -> "LUN-VIE__07:30-17:00 SAB__08:00-12:00" 

  Lunes a Viernes 8 a 11 y 14 a 18 hs -> "LUN-VIE__08:00-11:00_14:00-18:00" 

  Lunes y Miercoles 8 a 11 y 14 a 18 hs -> "LUN_MIE__08:00-11:00_14:00-18:00" 

  Lunes a Miercoles y Viernes 8 a 11 y 14 a 18 hs -> "LUN-MIE_VIE__08:00-11:00_14:00-18:00"

  Lunes a Miercoles 8 a 11 y de Viernes a Domingo 9 a 10 -> "LUN-MIE__08:00-11:00 VIE-DOM__09:00-10:00"

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Rangos horarios”.

### Otros estándares sectoriales

  * Se utilizará el estándar de Contrataciones Abiertas (Open Contracting Data Standard) para la publicación de datos vinculados con contrataciones públicas.

  * Siguiendo los lineamientos del Ministerio de Desarrollo Urbano y Transporte, los datos de movilidad se publicarán de acuerdo al estándar abierto GTFS (General Transit Feed Standard).

  * Para datos geográficos se utiliza el estándar WKT (Well-Known Text).

### Booleano

  * A menos que se indique lo contrario, los valores en este campo deben ser TRUE o FALSE.

  * No se permite ningún otro valor, ni representaciones alternativas como Sí, No, 1, 0, Verdadero, Falso, o similares. Tampoco se admiten valores ausentes (NULL o N/A) ni campos completamente vacíos.

  * El tipo de dato booleano es estrictamente binario y sólo admite los dos valores de verdad mencionados. En caso de que se necesite representar valores ausentes o permitir otras convenciones, se debe utilizar un tipo de dato diferente. 

  * En el **Diccionario de Datos y Metadatos**, este dato se encuentra bajo el nombre “Opción Binaria”.