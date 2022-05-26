# Technical challenge - Developer Experience Engineer

![logo](logo_oficial_enviame.png "Title")

## Introducción

¡Felicitaciones por llegar hasta aquí! El siguiente desafío busca evaluar tus conocimientos y habilidades en el mundo del desarrollo de software para ocupar el cargo de Developer Experience Engineer. El desafío está dividido en dos partes: API de tarifas y página de consulta.

**Importante: leer el challenge completo antes de comenzar a realizarlo.**

---

## Parte I: API de tarifas

Son múltiples los carriers o empresas de transportes que en Chile ofrecen sus servicios entre distintas localidades a lo largo del país. Cada carrier ofrece además una serie de servicios en donde se compromete a entregar tu paquete en una cantidad de N días de tránsito (DDT, de ahora en adelante). Se entiende que a mayor rapidez, más costoso es el servicio.

Las tarifas que estos carriers cobran y los DDT que prometen por transportar tus paquetes varían de acuerdo a los siguientes parámetros: localidad de origen, localidad de destino, peso del paquete y servicio contratado.

#### Requerimiento y consideraciones:

- Una API REST desarrollada en **NodeJS o Python** que permita guardar, editar, eliminar y consultar tarifas usando una base de datos **MySQL**.
- Te proveemos 2 templates con una estructura de Clean Architecture que puedes utilizar como base para tu aplicación. NodeJS y Python, elige el que gustes.
- Los endpoints que debes realizar serán relacionados SÓLO a tarifas: crear, leer, modificar y eliminar. Los carriers, servicios y localidades deben estar precargados en la base de datos. Cantidades recomendadas para precargar:
  - Carriers: 10.
  - Servicios: entre 2 y 3 por cada carrier.
  - Localidades: 50.
  - La carga de tarifas (la C de CRUD) se debe hacer indicando carrier, servicio, origen, destino, límite de peso y precios. Se debe indicar un precio para paquetes sobre el límite de peso, y un precio para paquetes bajo el límite.
- La consulta de tarifas (la R de CRUD) sólo debe recibir origen, destino y peso del paquete, ya que es todo lo que sabe el cliente. La respuesta de este endpoint debe entregar la información necesaria para que el cliente pueda tomar la mejor decisión, basándose en las tarifas y días de tránsito de cada servicio.
- El proyecto debe estar **dockerizado** y contar con un archivo **docker-compose.yml**. Esto nos facilitará enormemente la revisión exitosa de tu proyecto.

---

## Parte II: página de consulta de tarifas

¿Cómo toma la decisión el dueño de una tienda sobre qué carrier y servicio utilizar para enviar sus paquetes hacia sus clientes? Como se mencionó anteriormente, tanto el precio como los días de tránsito son fundamentales para tomar dicha decisión.

#### Requerimiento y consideraciones:

- Construir una página con un simple formulario donde el cliente pueda ingresar la localidad de origen, el destino y el peso del paquete en kilogramos.
- Con los datos ingresados, se debe hacer un request a la consulta de tarifas de la API construida en la parte I.
- Los resultados del request deben desplegarse en una tabla bajo el formulario y cada fila debe mostrar **Carrier, Servicio, Días de tránsito y Precio**.
- Si utilizaste algún framework para la parte I que te permita incluir vistas, lo puedes usar sin problema. En caso contrario, si realizas un proyecto diferente para la parte II debes dockerizarlo de la misma manera que la API, y preocuparte que la comunicación entre ambos contenedores se pueda efectuar.

---

## Entrega de tu prueba

- Incluir un archivo readme.md con las instrucciones para levantar tu proyecto.
- Si usas variables de ambiente, recuerda incluir un archivo .env.example.
- Adjuntar una colección de Postman con requests de ejemplo para probar tus endpoints de la parte I.
- El proyecto debe ser subido a un repositorio privado en GitHub y compartirlo a los siguientes usuarios: @rsebjara, @vham, @rolivagon, @vmolina-enviame, @rcarrascop, @psepulvedav.

## Aspectos a evaluar

- Funcionalidad (36 pts).
- Unit tests (12 pts).
- Documentación (6 pts).
  - Readme.md con instrucciones sobre cómo levantar tu proyecto.
  - Colección de Postman con requests de ejemplo para probar todos los endpoints de tu servicio.
  - Diagrama de estructura de base de datos.
- Estilo de programación (6 pts).
- Manejo de errores y excepciones (2 pts).
- Uso correcto de códigos de respuesta HTTP (2 pts).
- Uso adecuado del template de Clean Architecture (6 pts).
