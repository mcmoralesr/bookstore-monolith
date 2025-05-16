# ST0263 - BookStore Monolítica - Proyecto 2

## Información del curso
- **Materia:** ST0263 - Tópicos Especiales en Telemática
- **Estudiantes:**
  - Manuel Arango Gómez - marangog3@eafit.edu.co
  - Sebastián Cano Rincón - scanor2@eafit.edu.co
  - Maria Camila Morales - mcmorales@eafit.edu.co
- **Profesor:** Alvaro Enrique Ospina Sanjuan - aeospinas@eafit.brightspace.com
- **Video:** https://teams.microsoft.com/l/meetingrecap?driveId=b%216XUses7wc0SIPDAG2T5E3A6yrBq8YolBgI-SkQgnz9EJlUNwCvTLR6z9wXktU5Fj&driveItemId=01TFOAYXUEM7JJKWCNPVFZ6H5CPRF7MH5F&sitePath=https%3A%2F%2Feafit-my.sharepoint.com%2F%3Av%3A%2Fg%2Fpersonal%2Fmarangog3_eafit_edu_co%2FEYRn0pVYTX1Lnx-ifEv2H6UB2aWCxZoSe1jHA-NAyGiq7w&fileUrl=https%3A%2F%2Feafit-my.sharepoint.com%2Fpersonal%2Fmarangog3_eafit_edu_co%2FDocuments%2FGrabaciones%2FLlamada%2520con%2520Maria%2520y%25201%2520m%25C3%25A1s-20250515_213858-Grabaci%25C3%25B3n%2520de%2520la%2520reuni%25C3%25B3n.mp4%3Fweb%3D1&threadId=19%3A579ebe897008492aba5d4ab159f32ac9%40thread.v2&callId=614da91c-bb39-45b8-bdff-bc0fcc98cb33&threadType=GroupChat&meetingType=Unknown&subType=RecapSharingLink_RecapCore

## BookStore Monolítica - Objetivo 1
### 1. Breve descripción de la actividad

Este proyecto consta de tres objetivos escalonados sobre la aplicación BookStore:

#### Objetivo 1 - 20%

Desplegar la aplicación BookStore Monolítica en una Máquina Virtual (VM) en AWS, con dominio propio, certificado SSL y configuración de proxy inverso con NGINX.

#### Objetivo 2 - 30%

Escalamiento en la nube de la aplicación monolítica usando un patrón de arquitectura de escalamiento en AWS. Se usarán múltiples VMs con autoescalamiento, balanceador de carga (ELB), almacenamiento de archivos compartidos (NFS) y una base de datos administrada o en alta disponibilidad.


### 1.1 Aspectos cumplidos de la actividad

✔ Despliegue funcional de la app monolítica  
✔ Docker y Docker Compose configurados  
✔ NGINX como proxy inverso  
✔ Certificado SSL con Let's Encrypt  
✔ Dominio propio: https://bookstoredemo.shop  
✔ ALB (Application Load Balancer) con instancias *healthy*  
✔ NFS configurado correctamente  
✔ Infraestructura montada en AWS  

### Aspectos NO cumplidos

Objetivo 3 - microservicios y SWARM

### Diseño de alto nivel

 Arquitectura monolítica (objetivo 1)
- Arquitectura escalada: múltiples EC2 + ELB + NFS + RDS (objetivo 2)
- Microservicios y Kubernetes (objetivo 3, pendiente)
- Patrón de despliegue clásico: servidor + BD
- Buenas prácticas: uso de .env, Docker Compose, SSL/TLS, separación de lógica por controladores
![image](https://github.com/user-attachments/assets/8a1e674e-049b-4f74-8683-f2962db4ab66)


### 3. Ambiente de desarrollo
- Lenguaje: Python 3.x
- Framework: Flask
- Docker: v24.0+
- Docker Compose: v2.36.0
- Certbot: 2.9.0
- Servidor: Ubuntu 24.04 (EC2)
- NGINX: 1.24.0

## Compilación y ejecución

```
git clone https://github.com/usuario/bookstore-monolith.git
cd bookstore-monolith
sudo docker-compose up -d --build
```

# Clonar repositorio
https://github.com/tuusuario/bookstore-monolith.git
cd bookstore-monolith

# Ejecutar
docker-compose up --build -d

# Sitio Web desplegado

- Dominio: https://bookstoredemo.shop
- Puerto expuesto: 443
- NFS Mount: `/mnt/nfs`
- BD: MySQL en RDS (us-east-1)
- NGINX como proxy inverso a `localhost:5000`
- Certificados en: `/etc/letsencrypt/live/bookstoredemo.shop/`
- Infraestructura: AWS EC2 + ALB + NFS + RDS
- IP NFS Server: 54.84.35.254
- IP pública Bookstore2: 54.205.132.233
- Balanceador de carga: `bookstore-alb` (HTTPS:443)

![image](https://github.com/user-attachments/assets/9603591c-db48-4939-b948-dbf70e14c41c)


![image](https://github.com/user-attachments/assets/c8fce644-3ecc-412d-ad68-9c192108fbdf)

**Estructura de carpetas:**
├── Dockerfile
├── README.md
├── app.py
├── awscliv2.zip
├── config.py
├── controllers
│   ├── _pycache_
│   │   ├── auth_controller.cpython-312.pyc
│   │   ├── book_controller.cpython-312.pyc
│   │   ├── delivery_controller.cpython-312.pyc
│   │   ├── payment_controller.cpython-312.pyc
│   │   └── purchase_controller.cpython-312.pyc
│   ├── admin_controller.py
│   ├── auth_controller.py
│   ├── book_controller.py
│   ├── delivery_controller.py
│   ├── payment_controller.py
│   └── purchase_controller.py
├── docker-compose.yml
├── extensions.py
├── models
│   ├── book.py
│   ├── delivery.py
│   ├── delivery_assignment.py
│   ├── payment.py
│   ├── purchase.py
│   └── user.py
├── requirements.txt
└── templates
    ├── add_book.html
    ├── base.html
    ├── catalog.html
    ├── delivery_options.html
    ├── edit_book.html
    ├── home.html
    ├── list_users.html
    ├── login.html
    ├── my_books.html
    ├── payment.html
    └── register.html

### 5. Otra información relevante

Este despliegue forma parte del Proyecto 2 del curso ST0263. Incluye 2/3 objetivos mandatorios.


![image](https://github.com/user-attachments/assets/a83cdafd-3a51-46ac-b7f2-f2202567eae2)

 - NFS permite compartir archivos entre instancias
- La app responde correctamente a `curl -Ik https://localhost`
- Certificado verificado con `openssl s_client`

![image](https://github.com/user-attachments/assets/4d8ff9b5-39c9-45c3-b249-cfd5c4d73f7b)
![image](https://github.com/user-attachments/assets/a891b80f-b943-46ec-8789-137ed807740d)


Referencias:
------------
- https://docs.docker.com
- https://flask.palletsprojects.com
- https://certbot.eff.org
- https://docs.aws.amazon.com/elasticloadbalancing/

