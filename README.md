
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

## 1.2. Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor 

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
![imagen](https://github.com/csofia1408/Proyecto2TopicosTelematica/assets/72955238/6624c8f9-49c5-4b8e-96ba-eac50fa73f67)



## Arquitectura del Sistema

## Diagrama

# 3.Detalles del Desarrollo

    
# 4. Descripción del ambiente de desarrollo y técnico: lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.


# 5. otra información que considere relevante para esta actividad.
### Glosario de Terminos

  
Referencias:

