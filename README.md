
# info de la materia: ST0263 TOPICOS ESPEC. EN TELEMATICA
#
# Estudiante(s): Carla Sofía Rendón Baliero,Victor Manuel Botero Gómez,Maria Paulina Lopez Salazar 
#
# Profesor: Alvaro Enrique Ospina Sanjuan
#
#  Proyecto 2 - Cluster Kubernetes
#
# 1. Descripción de la actividad
El proyecto consiste en desplegar una aplicación WordPress en un clúster Kubernetes de alta disponibilidad utilizando microk8s. Se configurará un clúster propio en máquinas virtuales en GCP, asegurando alta disponibilidad en las capas de aplicación, base de datos y almacenamiento. Esto incluye el uso de un servidor NFS para volúmenes compartidos y la configuración de un balanceador de cargas. Además, se implementará un dominio con HTTPS y se permitirá la escalabilidad del clúster
#
## 1.1. Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor
- Cluster de kubernetes crado con microk8s
    - Una instancia Master
    - Dos instancias Worker
- Dominio (victorbotero.online)
- Certificado SSL
- Capa de acceso con microk8s Ingress
- Instancias de Wordpress con sus deployment, service, pv y pvc
- Base de datos MySQL con su deployment, service, pv y pvc
- Un servidor NFS para los archivos en una instancia de externa al cluster

# 2. información general de diseño de alto nivel, arquitectura.
### La arquitectura de este proyecto está diseñada para ser una solución robusta y escalable utilizando Kubernetes, con la distribución MicroK8s desplegada en Google Cloud Platform (GCP). El objetivo principal es alojar dos instancias de WordPress junto con una base de datos MySQL, garantizando alta disponibilidad, persistencia de datos y fácil escalabilidad.

### Componentes Principales:

- Google Cloud Platform (GCP): Proveedor de nube donde se despliegan las máquinas virtuales y se gestiona la infraestructura.
- Compute Engine: Se utilizan varias instancias de Compute Engine para desplegar los nodos del clúster y el servidor NFS.
- MicroK8s: Una distribución ligera de Kubernetes utilizada para gestionar el clúster, que incluye:
    - Master: Nodo maestro que gestiona el clúster de Kubernetes.
    - Worker1 y Worker2: Nodos trabajadores que ejecutan las cargas de trabajo (pods).
- Ingress: Controlador que gestiona el acceso externo a los servicios del clúster, dirigiendo el tráfico HTTP/HTTPS a los servicios internos correspondientes.
- Services (svc): Recursos de Kubernetes que exponen los pods y balancean el tráfico entre ellos. Hay servicios específicos para las instancias de WordPress y la base de datos MySQL.
- Pods: Las unidades básicas de ejecución en Kubernetes, que contienen los contenedores con las aplicaciones WordPress y MySQL.
- Deployments: Recursos de Kubernetes que gestionan la creación y actualización de pods, asegurando que siempre haya un número deseado de réplicas en ejecución.
- Persistent Volumes (PV) y Persistent Volume Claims (PVC): Mecanismos de Kubernetes para gestionar el almacenamiento persistente:
    - PV: Representa el almacenamiento físico en el clúster.
    - PVC: Solicita el almacenamiento necesario para los pods.
- NFS: Un servidor NFS externo que proporciona almacenamiento compartido y persistente, accesible por los Persistent Volumes.
## Diagrama Arquitectura
![imagen](https://github.com/csofia1408/Proyecto2TopicosTelematica/assets/72955238/6624c8f9-49c5-4b8e-96ba-eac50fa73f67)

# 3.Detalles del Desarrollo

    


# 4. otra información que considere relevante para esta actividad.
### Glosario de Terminos
- MicroK8s: Una distribución ligera y simplificada de Kubernetes, diseñada para desarrolladores, operadores y entusiastas de Kubernetes que desean ejecutar clústeres Kubernetes en sus propias máquinas.
- Kubernetes (K8s): Plataforma de código abierto para la automatización de la implementación, el escalado y la operación de aplicaciones en contenedores. Kubernetes
- Clúster: Conjunto de máquinas (nodos) que trabajan juntas para proporcionar un entorno de ejecución para las aplicaciones. En Kubernetes, un clúster consiste en un nodo maestro y varios nodos trabajadores. Kubernetes Cluster
- Nodo Maestro (Master): Componente central de un clúster Kubernetes que gestiona el estado del clúster y realiza tareas administrativas como la programación de pods y la gestión de la configuración. Kubernetes Master Node
- Nodo Trabajador (Worker): Máquinas en un clúster Kubernetes que ejecutan las aplicaciones en contenedores. Los nodos trabajadores reciben instrucciones del nodo maestro. Kubernetes Worker Node
- Pod: Unidad más pequeña de ejecución en Kubernetes que puede contener uno o más contenedores. Los pods se despliegan y gestionan como una unidad. Kubernetes Pod
- Deployment: Objeto de Kubernetes que gestiona un conjunto de réplicas de pods, asegurando que un número especificado de instancias del pod estén funcionando en todo momento. Kubernetes Deployment
- Service (SVC): Abstracción de Kubernetes que define un conjunto lógico de pods y una política para acceder a ellos, proporcionando un punto de acceso estable y de red para un grupo de pods. Kubernetes Service
- Ingress: Objeto de Kubernetes que gestiona el acceso externo a los servicios en un clúster, generalmente proporcionando balanceo de carga, terminación SSL y enrutamiento basado en nombres de host. Kubernetes Ingress
- Persistent Volume (PV): Recurso de almacenamiento en Kubernetes que existe independientemente del ciclo de vida de los pods y proporciona almacenamiento persistente. Kubernetes Persistent Volume
- Persistent Volume Claim (PVC): Solicitud de almacenamiento persistente hecha por un usuario que se vincula a un Persistent Volume (PV) específico. Kubernetes Persistent Volume Claim
- NFS (Network File System): Protocolo de red que permite a los usuarios acceder a archivos a través de una red de manera similar a cómo acceden a archivos localmente. NFS
- Alta Disponibilidad (HA): Diseño y configuración de un sistema de manera que sea resistente a fallos y que maximice el tiempo de actividad y la disponibilidad del servicio. High Availability
- Balanceador de Cargas: Dispositivo o servicio que distribuye el tráfico de red entre múltiples servidores para asegurar que ningún servidor se sobrecargue y para mejorar la disponibilidad y capacidad de respuesta del servicio. Load Balancer
- Autoscaling: Capacidad de ajustar automáticamente el número de nodos o la cantidad de recursos disponibles para una aplicación en función de la carga actual, asegurando un rendimiento óptimo y utilización eficiente de recursos. Kubernetes Autoscaling

  
# 5.Referencias:
- MicroK8s.  www.microk8s.io
- Kubernetes Documentation. https://kubernetes.io/docs/home/.
- Network File System. www.wikipedia.org/wiki/Network_File_System.
- MySql Bitnami https://hub.docker.com/r/bitnami/mysql
- Kubernetes Concepts. Kubernetes Concepts.
- MySQL High Availability. www.dev.mysql.com/doc/refman/8.0/en/high-availability.html.
- Autoscaling in Kubernetes. www.github.com/kubernetes/autoscaler.
