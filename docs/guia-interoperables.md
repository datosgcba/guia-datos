# Guía para la identificación y uso de entidades interoperables

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

## Indice

- [Objetivo de esta guía](#objetivo-de-esta-guia)
- [Datos de entidades interoperables](#datos-de-entidades-interoperables)
  - [¿Qué son?](#que-son)
  - [¿Por qué es importante estandarizarlos?](#por-que-es-importante-estandarizarlos)
- [Cómo nombrar los campos de las entidades interoperables](#como-nombrar-los-campos-de-las-entidades-interoperables)
    - [Ejemplos y recomendaciones para tipos de entidades](#ejemplos-y-recomendaciones-para-tipos-de-entidades)
      - [GEOGRÁFICOS](#geograficos)
      - [PERSONAS FÍSICAS](#personas-fisicas)
      - [PERSONAS JURÍDICAS](#personas-juridicas)
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Objetivo de esta guía

  Esta es una **guía de buenas prácticas para el uso de entidades interoperables** del Gobierno de la Ciudad de Buenos Aires (GCBA). Se trata de datos básicos y fundamentales cuyo uso se repite frecuentemente entre datasets de distintas temáticas y fuentes.

  Para hacer estas recomendaciones, nos basamos en la [guía del Gobierno Nacional](https://datosgobar.github.io/paquete-apertura-datos/guia-interoperables/), en estándares usados a nivel nacional e internacional y en la experiencia de trabajo del equipo de la Dirección General de Gobernanza de Datos, de la Subsecretaría de Innovación Administrativa, Secretaría de Innovación y Transformación Digital (en adelante, TecBA) del Gobierno de la Ciudad de Buenos Aires.

  Esta es **una guía colaborativa y en progreso**. Valoramos, y alentamos, a organizaciones y ciudadanos a plantear ideas, sugerencias, y comentarios que nos ayuden a crear un mejor documento. 

## Datos de entidades interoperables

### ¿Qué son?

  Una entidad interoperable es un conjunto estructurado de atributos que, combinados, permiten identificar y describir coherentemente un objeto de intercambio de datos. Estas entidades funcionan como ejes comunes que se repiten en distintos conjuntos de datos, permitiendo que puedan relacionarse entre sí de manera significativa.

  Por ejemplo, muchos conjuntos de datos (datasets) incluyen atributos que responden a preguntas como:

  * ¿Dónde? (ubicación geográfica)

  * ¿Quién? (personas u organizaciones)

  * ¿Cuándo? (fechas o períodos)

  * ¿Qué? (categorías, clasificaciones, actividades)

  El uso de estas entidades comunes facilita la **interoperabilidad entre datos**, ya que permite cruzar información de distintas fuentes y temáticas.

  Como, por ejemplo, una matriz origen-destino de pasajeros de transporte urbano que indica cuántos viajes se realizan desde la fracción censal A hacia la fracción censal B puede interoperar con datos del Censo Nacional sobre características de esas fracciones censales (como tasas de desocupación, edad promedio, condiciones de vivienda, etc.).

  En este caso, la **fracción censal** actúa como entidad interoperable porque permite conectar datasets distintos mediante un mismo atributo geográfico.

  Ahora bien, podemos distinguir a las entidades interoperables entre:

  **Entidades transversales** (se utilizan en la mayoría de las áreas temáticas):

  * **¿Dónde?:** unidades geográficas como países, provincias, departamentos, fracciones censales, barrios, comunas, direcciones, códigos postales, espacios públicos.
  * **¿Quién?:** personas físicas, personas jurídicas, entidades gubernamentales, organismos internacionales, sociedad civil.
  * **¿Qué?:** clasificaciones presupuestarias, catálogos de bienes, tipos de servicios, etc.

  **Entidades específicas** (relevantes solo para determinadas áreas temáticas):

  * **¿Qué?:** clasificación de enfermedades (Salud), actividades económicas (Economía), clasificación de unidades educativas (Educación), términos clínicos (Salud), entre otros.

### ¿Por qué es importante estandarizarlos?

  La estandarización es clave para que los datos de distintas fuentes “hablen el mismo idioma” y puedan relacionarse entre sí. Las entidades interoperables permiten que distintos conjuntos de datos se conecten, pero esto solo es posible si están representadas de forma consistente.

  Cuando una misma entidad es nombrada de distintas maneras -por ejemplo, usando identificadores diferentes, con/sin mayúsculas, abreviaturas, artículos, tildes o formas cortas y largas—, se pierde la posibilidad de reconocer que se trata del mismo objeto, y se dificulta su integración.

  Para lograr la interoperabilidad, es necesario:

  * Identificar correctamente todas las entidades interoperables presentes en un conjunto de datos.
  * Asegurarse de que los datos sobre esas entidades sigan un mismo estándar.

  El **Diccionario de Datos y Metadatos del Gobierno de la Ciudad Autónoma de Buenos Aires** aprobado por Disposición N° 13-DGGDA/24 es una herramienta fundamental para alcanzar ese objetivo. Proporciona el conjunto de formatos y nomenclaturas que permiten escribir correctamente cada atributo.

  Pero el diccionario por sí solo no construye entidades interoperables:

  * El **diccionario** es como el “manual de palabras” que define cómo se escriben correctamente cada palabra. 
  * La **entidad interoperable** es la “frase” o “párrafo” formado por esos atributos combinados de manera coherente.

  Por eso, cuando las entidades interoperables se nombran de la misma forma en distintos conjuntos de datos, se facilitan su identificación automática y se evita tener que hacer un trabajo manual de mapeo o reestructuración de datos para saber que se está hablando de lo mismo.

## Cómo nombrar los campos de las entidades interoperables

  La interoperabilidad entre datasets requiere nombrar los campos de forma clara, consistente y estandarizada. Estas recomendaciones ayudan a lograrlo.

  **Reglas generales:**

  * **Usar nombres descriptivos que reflejen el contenido del dato.** 
  Ejemplo:

    + No recomendado: valor

    +	Recomendado: monto_transferencia


  * **Anteponer el nombre de la entidad o categoría al dato.**
  Ejemplo:

    + No recomendado: nombre

    + Recomendado: provincia_nombre

  * **Aplicar sufijos estandarizados como _id (identificador único) o _nombre (nombre descriptivo).** 
  Ejemplo:

    + No recomendado: provincia (no queda claro si es el código o el nombre)

    + Recomendado: provincia_id (para el código) y provincia_nombre (para el nombre)

  * **Ordenar los nombres de los campos de lo general a lo específico.**
  Ejemplo:

    + No recomendado: codigo_origen_pais (desordena la jerarquía y dificulta entender la entidad principal)

    + Recomendado: pais_codigo_origen → primero la entidad (pais), después el atributo (codigo), y por último el contexto (origen)

  * **Evitar abreviaturas ambiguas y usar términos consistentes entre datasets.**
  Ejemplo:

    + No recomendado: muni_id (¿municipio? ¿municipalidad?)

    + Recomendado: municipio_id


### Ejemplos y recomendaciones para tipos de entidades

#### GEOGRÁFICOS

  * **Países o territorios internacionales**

  Recomendamos que el dataset contenga un campo con el código alfabético de 2 dígitos del estándar (Código alfa-2) o el de 3 dígitos del estándar (Código alfa-3) y otro con el nombre completo del país en español.

  **No recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>pais_origen</td>
    <td>pais_destino</td>
    <td>valor_usd</td>
  </tr>  
  <tr>
    <td>Argentina</td>
    <td>China</td>
    <td>1.405.678</td>
  </tr>
  <tr>
    <td>República Popular China</td>
    <td>argentina</td>
    <td>2.456.786</td>
  </tr>
  </tbody>
  </table>

  **Recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>pais_codigo3 _origen</td>
    <td>pais_nombre_origen</td>
    <td>pais_codigo3_destino</td>
    <td>pais_nombre_destino</td>
    <td>valor_usd</td>
  </tr>  
  <tr>
    <td>ARG</td>
    <td>Argentina</td>
    <td>CHN</td>
    <td>China</td>
    <td>1.405.678</td>
  </tr>
  <tr>
    <td>CHN</td>
    <td>China</td>
    <td>ARG</td>
    <td>Argentina</td>
    <td>2.456.786</td>
  </tr>
  </tbody>
  </table>

  * **Divisiones o unidades territoriales internas**

  Al igual que en el caso de los países o territorios internacionales, el dataset debe contener un campo con el código de la división o unidad territorial interna y otro con el nombre o descripción (en caso de que la tenga). Para nombrar estos campos, se recomienda anteponer el nombre del nivel territorial seguido del sufijo correspondiente. 

  Los nombres de los campos identificadores deben ser, respectivamente:

  *	"provincia_id" 

  *	"departamento_id"

  *	"fraccion_id"

  *	"radio_id"

  *	"municipio_id"

  *	"localidad_id"

  *	"aglomerado_id"

  Análogamente, debe reemplazarse "_id" por “_nombre” para nombrar los campos que contiene el nombre de cada entidad, cuando esta lo tiene.

  * “provincia_nombre”

  * “departamento_nombre”

  * **Direcciones o lugares: **

  Si el dataset contiene información sobre direcciones (especialmente en los casos en los que no sea posible proveer coordenadas), recomendamos incluir:

  *	"calle_nombre"

  *	"calle_altura"

  *	"barrio"

  *	"comuna"

  *	"codigo_postal
  "

  *	"codigo_postal_argentino"

  *	"localidad_id"

  *	"localidad_nombre"

  *	"provincia_id"

  *	"provincia_nombre"

  Si el dataset incluye direcciones fuera del territorio argentino, deben además incluirse:

  *	"pais_id"

  *	"pais_nombre"


#### PERSONAS FÍSICAS

  Cuando un dataset contenga más de un campo relacionado con personas, o si la nomenclatura simple como "nombre" pudiera causar ambigüedad, se recomienda utilizar nombres compuestos para los campos. Esto ayuda a identificar claramente el contexto o la relación del dato. Ejemplo de nombres compuestos:

  *	ciudadano_nombres

  *	ciudadano_apellidos

  *	ciudadano_numero_doc

  *	ciudadano_tipo_doc

  *	representante_nombres

  *	representante_apellidos

  *	representante_numero_doc

  *	representante_tipo_doc

  *	ciudadano_pais_id

  *	ciudadano_pais_nombre

  **No recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>ciudadano</td>
    <td>representante</td>
  </tr>  
  <tr>
    <td>José Pérez</td>
    <td>Carlos Gómez</td>
  </tr>
  </tbody>
  </table>


  **Aceptable**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>ciudadano_nombres</td>
    <td>ciudadano_apellidos</td>
    <td>representante_nombres</td>
    <td>representante_apellidos</td>
  </tr>  
  <tr>
    <td>José</td>
    <td>Pérez</td>
    <td>Carlos Jorge</td>
    <td>Gómez</td>
  </tr>
  </tbody>
  </table>

  **Recomendado**

  <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>ciudadano_nombres</td>
    <td>ciudadano_apellidos</td>
    <td>ciudadano_documento_numero</td>
    <td>Ciudadano_documento_tipo</td>
    <td>representante_nombres</td>
    <td>representante_apellidos</td>
    <td>representante_documento_numero</td>
    <td>Representante_documento_tipo</td>
  </tr>  
  <tr>
    <td>José</td>
    <td>Pérez</td>
    <td>11111111</td>
    <td>DNI</td>
    <td>Carlos Jorge</td>
    <td>Gómez</td>
    <td>22222222</td>
    <td>DNI</td>
  </tr>
  </tbody>
  </table>

#### PERSONAS JURÍDICAS

  Las entidades con **personería jurídica local** (Ej.: empresas argentinas, ONGs argentinas, etc.) deben registrarse con su CUIT y razón social (evitar nombres de campo genéricos como “_id” o “_desc”). Por ejemplo:

  * "exportador_cuit"

  * "exportador_razon_social"

  **No recomendado**

   <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>exportador</td>
  </tr>  
  <tr>
    <td>Los Tomates Andinos</td>
    <td>Los Tomates</td>
    <td>Los Tomates Andinos SRL</td>
    <td>Tomates Andinos</td>
  </tr>
  </tbody>
  </table>

  **Recomendado**

   <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>exportador_cuit</td>
    <td>exportador_razon_social</td>
  </tr>  
  <tr>
    <td>33111111117</td>
    <td>Los Tomates Andinos SRL</td>
  </tr>
  <tr>
    <td>33111111117</td>
    <td>Los Tomates Andinos SRL</td>
  </tr>
  </tbody>
  </table>

  En el caso de que el dataset pueda contener **personas jurídicas fuera de la jurisdicción argentina**, recomendamos un enfoque análogo al tratamiento de personas físicas:

  *	"inversor_id"

  *	"inversor_tipo_id" (Ej.: en el caso de una empresa argentina sería “CUIT”)

  *	"inversor_desc"

  *	"inversor_pais_id"

  *	"inversor_pais_nombre"

  **Recomendado**

   <table id="left-align-col-2">
  <tbody>
  <tr>
    <td>inversor_id</td>
    <td>inversor_tipo_id</td>
    <td>inversor_desc</td>
    <td>inversor_pais_id</td>
    <td>inversor_pais_nombre</td>
  </tr>  
  <tr>
    <td>33111111117</td>
    <td>CUIT</td>
    <td>Los Tomates Andinos SRL</td>
    <td>ARG</td>
    <td>Argentina</td>
  </tr>
  <tr>
    <td>33111111117</td>
    <td>CUIT</td>
    <td>Los Tomates Andinos SRL</td>
    <td>ARG</td>
    <td>Argentina</td>
  </tr>
  <tr>
    <td>1234567890</td>
    <td>TIN</td>
    <td>Tomatoes Inc.</td>
    <td>USA</td>
    <td>Estados Unidos</td>
  </tr>
  <tr>
    <td>987654321</td>
    <td>Steuer-Id</td>
    <td>Tomate</td>
    <td>DEU</td>
    <td>Alemania</td>
  </tr>
  </tbody>
  </table>

  Si no se cuenta con el identificador o su tipo para una entidad extranjera, y al no permitir celdas vacias, se debe usar NULL cuando el dato no esté disponible y N/A cuando no sea aplicable. Aun así, se recomienda registrar siempre el nombre (*_desc) y el país (*_pais_id, *_pais_nombre) como referencia mínima para garantizar la interoperabilidad.

  Como ya dijimos, estas recomendaciones se integran con el [Diccionario de Datos y metadatos del GCBA](https://cdn2.buenosaires.gob.ar/manual_diccionario_de_datos_metadatos.pdf), que proporciona definiciones estandarizadas y detalladas sobre los formatos, denominaciones y estructuras de los datos utilizados en las distintas áreas de gobierno.