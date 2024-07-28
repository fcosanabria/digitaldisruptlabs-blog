---
title: Introducción a Kubernetes
description: Aprende los fundamentos de Kubernetes
date: 2024-07-27
categories: [Learning]
tags: [kubernetes, devops]
---

# Kubernetes: La revolución en la orquestación de contenedores

## Introducción

En el dinamico mundo del desarrollo de software y la infraestructura de IT, pocas tecnologias han tenido un impacto tan significativo como Kubernetes. Este articulo explora que es Kubernetes, por que es tan importante y como esta tranformando la forman en la que desarrolamos y desplegamos aplicaciones.

> **Nota:** Este articulo es una introducción a Kubernetes y no requiere conocimientos previos sobre la tecnologia per se, pero asumo que tienes un conocimiento basico sobre contenedores. Si quieres saber más sobre contenedores, puedes leer este [articulo](https://www.ibm.com/mx-es/topics/containers) sobre contenedores y [Docker](https://www.ibm.com/mx-es/topics/docker).

## ¿Qué es Kubernetes?

Ahora, hablemos de lo que es Kubernetes. Que por cierto, ahora le llamaremos K8s.

K8s es una [plaforma de código abierto](https://kubernetes.io/es/) diseñada para automatizar la implementación, el escalado y la gestión de aplicaciones en contenedores. Actúa como un sistema de orquestación, coordinando un clúster de computadoras para que funcionen como una sola unidad.

Imagina a K8s como un director de orquesta. K8s se encarga de coordinar contenedores para asegurar que las aplicaciones funciones de manera eficiente y sin problemas. A esto se le conoce como orquestación de contenedores o un sistema de orquestación, como ya lo mencionamos.

## Historia y Evolución de Kubernetes

Comenzamos con la parte aburrida, y usualmente con la que nos encontramos en la mayoría de los artículos, y este, obviamente, no será la excepción.

Kubernetes fue originalmente diseñado de la experiecia de Google. Para aquel momento AWS estaba dominando el mercado de la nube, y Google de alguna manera necesitaba ponerse al corte, no solamente para competir, si no para mejorar su infraestructura interna.

Usualmente lo que nos encontramos en línea es que Borg fue el precursor de Kubernetes, pero en realidad, *Borg* y *Omega* fue el sistema que Google utilizó para orquestar contenedores y manejar aplicaciones en su infraestructura interna.

Sin embargo, Kubernetes NO es una versión de código abierto de Borg y Omega. Kubernetes fue diseñado desde cero, y aunque se inspiró en Borg y Omega, no es una copia de estos sistemas. Es más que K8s su comparte ADN e historia.

Con eso dicho, ahora K8s es un proyecto mantenido por la CNCF, y se encuentra licenciado bajo Apache 2.0.

Ahora hablemos sobre Kubernetes y Docker, como parte de la historia. En la primeras versiones de Kubernetes estas venian configuradas para usar Docker como container runtime. Esto significa que Kubernetes usaba Docker para el manejo de tareas de bajo nivel, como crear, iniciar y detener contenedores. Sin embargo con esto, varias cosas pasaban:

1. Docker se sobrecargó.
2. Empezarón a desarrollarse alternativas a Docker.

Debido a esto Kubernetes creó un proyecto llamado CRI o Container Runtime Interface para hacer la capa del runtime modular. Esto significa que puedes escoger el runtime que más te funcione, por ejemplo hay runtimes que ofrecen mejor aislamiento mientras que otros proveen un mejor desempeño.

Para la versión 1.24, Kubernetes decidió quitar Docker como runtime, ya que era considerado overkill para las necesidades de Kubernetes. Ahora se usa Containerd por defecto.

> Existe un estandar llamado OCI (Open Container Initiative) que hace que las aplicaciones diseñadas para Docker puedan funcionar con cualquier otro runtime que cumpla con el OCI también.

Ok, mucha historia.

## Importancia de Kubernetes

Ahora que ya sabemos qué es Kubernetes y de dónde viene, vamos a lo interesante: ¿por qué todo el mundo está hablando de K8s? ¿Es solo otra moda tecnológica o realmente vale la pena?

Spoiler alert: Kubernetes es definitivamente mucho más que una moda pasajera. Ha ganado una importancia crucial en el mundo tecnológico actual por varias razones. Vamos a verlas una por una:

### Gestión de microservicios

¿Recuerdas cuando las aplicaciones eran monolíticas y todos teníamos dolor de cabeza cada vez que había que hacer un cambio? Bueno, los microservicios llegaron para solucionar eso, pero trajeron sus propios desafíos. Aquí es donde K8s brilla:

- **Orquestación magistral**: Kubernetes puede manejar cientos o incluso miles de microservicios simultáneamente. Es como tener un director de orquesta que puede dirigir una sinfonía con mil instrumentos diferentes, y que de paso suene bien.

- **Descubrimiento de servicios**: Imagina que tus microservicios son como personas en una fiesta. K8s es el anfitrión que se asegura de que todos se conozcan y sepan cómo hablar entre sí. No más servicios perdidos o desconectados.

- **Balanceo de carga**: A esto también se le conoce como *Load Balancing*. Kubernetes distribuye el tráfico entre las diferentes instancias de un microservicio para evitar sobre cargas de un mismo recurso.

### Portabilidad entre nubes

¿Alguna vez has sentido que estás "casado" con un proveedor de nube y que mudarte sería un dolor de cabeza? Kubernetes viene al rescate:

- **Abstracción de la infraestructura**: K8s proporciona una capa de abstracción sobre la infraestructura subyacente. Es como tener un adaptador universal para tus aplicaciones.

- **Compatibilidad multi-nube**: ¿AWS hoy, Google Cloud mañana y Azure la próxima semana? No hay problema. Kubernetes te permite mover tus aplicaciones de una nube a otra sin tener que reescribir todo. Como el punto anterior, la abstración que hace que su migración o adaptación sea mucho más sencilla. Esto también permite la adaptación de la nube hibrida.

### Escalabilidad y alta disponibilidad

En el mundo digital de hoy, donde un tweet puede hacer que tu aplicación pase de 100 a 1 millón de usuarios en cuestión de minutos, la escalabilidad es crucial:

- **Escalado horizontal automático**: Kubernetes puede aumentar o disminuir automáticamente el número de instancias de tu aplicación basándose en la demanda.

- **Auto-reparación**: Si un nodo o un pod falla, Kubernetes puede automáticamente reiniciarlo o reemplazarlo.

- **Actualizaciones sin tiempo de inactividad**: K8s permite realizar actualizaciones graduales sin interrumpir el servicio. Esto permite poder rollear nuevas versiones de manera deliberada, sin necesidad de detener el servicio. Esto se puede controlar de manera granular y con varias estrategias, pero eso es tema para otro entry.

### Eficiencia operativa: Automatización al rescate

Por último, pero no menos importante, Kubernetes es un maestro de la automatización:

- **Reducción de errores humanos**: Al automatizar tareas repetitivas, se minimizan los errores causados por la intervención manual.

- **Optimización de recursos**: Kubernetes empaqueta eficientemente las aplicaciones en los nodos del clúster. Es como jugar al Tetris con tus recursos, pero Kubernetes siempre gana.

- **Gestión declarativa**: Los administradores pueden declarar el estado deseado del sistema, y Kubernetes se encarga de mantener ese estado. No tienes que preocuparte por el "cómo", solo por el "qué".

## Conclusión

En resumen, Kubernetes no es solo otra herramienta más en el vasto mundo de la tecnología. Es un cambio de paradigma en la forma en que desarrollamos, desplegamos y gestionamos aplicaciones.

Ya sea que estés comenzando tu viaje en el desarrollo de software o buscando optimizar tus operaciones de TI, comprender Kubernetes es esencial en el panorama tecnológico actual. Es como aprender a conducir en un mundo donde los coches son cada vez más autónomos: puede parecer abrumador al principio, pero una vez que lo dominas, te preguntas cómo vivías sin ello.

En los próximos entries, voy a tocar más sobre la arquitectura de Kubernetes, para después pasar a realizar laboratorios y demás ejercicios prácticos.

Gracias por leer. ;)
