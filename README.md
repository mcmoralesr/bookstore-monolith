# ST0263 - BookStore Monolítica - Proyecto 2

## Información del curso
- **Materia:** ST0263 - Tópicos Especiales en Telemática
- **Estudiantes:**
  - Manuel Arango Gómez - marangog3@eafit.edu.co
  - Sebastián Cano Rincón - scanor2@eafit.edu.co
  - Maria Camila Morales - mcmorales@eafit.edu.co
- **Profesor:** Alvaro Enrique Ospina Sanjuan - aeospinas@eafit.brightspace.com

## BookStore Monolítica - Objetivo 1
### 1. Breve descripción de la actividad

Este proyecto consta de tres objetivos escalonados sobre la aplicación BookStore:

#### Objetivo 1 - 20%

Desplegar la aplicación BookStore Monolítica en una Máquina Virtual (VM) en AWS, con dominio propio, certificado SSL y configuración de proxy inverso con NGINX.

#### Objetivo 2 - 30%

Escalamiento en la nube de la aplicación monolítica usando un patrón de arquitectura de escalamiento en AWS. Se usarán múltiples VMs con autoescalamiento, balanceador de carga (ELB), almacenamiento de archivos compartidos (NFS) y una base de datos administrada o en alta disponibilidad.

#### Objetivo 3 - 50%

Reingeniería de la aplicación BookStore para separarla en 3 microservicios:

Autenticación (registro, login, logout)

Catálogo de libros

Compra, pago y entrega

Despliegue sobre clúster Kubernetes con reglas de escalabilidad individuales para cada microservicio.


### 1.1 Aspectos cumplidos de la actividad

Despliegue funcional de la aplicación monolítica BookStore.

Uso de Docker y Docker Compose para contenerización.

Configuración de una VM en AWS (EC2).

Instalación de NGINX como proxy inverso.

Configuración de dominio propio y certificación SSL vía Let's Encrypt.

Acceso a la aplicación vía HTTPS desde el navegador usando el dominio configurado.

### Aspectos NO cumplidos

Ninguno - llenar basado en la implementación.

### Diseño de alto nivel

Arquitectura de aplicación monolítica en Objetivo 1.

Arquitectura escalada con múltiples VMs, ELB, RDS, y NFS en Objetivo 2.

Arquitectura basada en microservicios desplegada en Kubernetes en Objetivo 3.

Patrón de despliegue clásico: servidor + base de datos.

Mejores prácticas: uso de Docker Compose, separación de servicios, configuración de variables de entorno.

### 3. Ambiente de desarrollo
Lenguaje: Python 3.x

Framework: Flask

Base de datos: MySQL

Librerías:

Flask 2.x

Flask-Login

SQLAlchemy

docker-compose

## Compilación y ejecución

# Clonar repositorio
https://github.com/tuusuario/bookstore-monolith.git
cd bookstore-monolith

# Ejecutar
docker-compose up --build -d

### 5. Otra información relevante

Este despliegue forma parte del Proyecto 2 del curso ST0263. Incluye los tres objetivos descritos en la guía del proyecto.

Referencias

https://docs.docker.com/

https://certbot.eff.org/

https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-22-04

https://github.com/st0263eafit/st0263-251/blob/main/proyecto2/BookStore.zip

