Scripts de gestión — Docker Swarm
Repositorio de scripts desarrollados como parte del TFG Servizos de Rede con Docker e Swarm.
El objetivo es tener una forma rápida y cómoda de gestionar el clúster Swarm desde el NodoManager: consultar el estado de los servicios, arrancarlos, pararlos y gestionar los backups de los volúmenes,
todo con salida en JSON para facilitar su integración.

Requisitos:

- Python 3 instalado en el NodoManager
- Docker Swarm activo y accesible desde el nodo donde se ejecutan los scripts
- Utilizando librerías estándar de Python


Estructura:
      Scripts/
      ├── Listado de Servicios    → listar los servicios activos en el Swarm
      ├── Lanzar Servicios        → desplegar un stack desde un fichero .yml
      ├── Parar Servicios         → parar uno o todos los servicios
      ├── Crear los Backups       → backup de todos los volúmenes Docker
      ├── Restaurar Backups       → restaurar un volumen desde un .tar.gz
      └── Listar Backups          → listar los backups disponibles en una carpeta

Funcionalidad de los Scripts:

1._ Listado de Servicios
    Muestra los servicios activos en el clúster con su estado, réplicas, imagen y puertos.
        
2._ Lanzar Servicios
    Despliega un stack en el Swarm a partir de un fichero docker-compose.yml.

3._ Parar Servicios
    Para un servicio concreto o todos los servicios del Swarm.

4._ Crear los Backups
    Hace un backup de todos los volúmenes Docker existentes en el momento de ejecución y los guarda como .tar.gz en la carpeta indicada.

5._ Restaurar Backups
    Restaura un volumen Docker desde un fichero de backup .tar.gz.

6._ Listar Backups
    Lista todos los backups disponibles en una carpeta, con nombre, tamaño y fecha.

Se prepararon para que los Scripts tengan salida por JSON para facilitar el funcionamiento en caso de querer implementarlos en una API, lo que permite que
todos los scripts generen la salida en formato JSON, tanto por pantalla como en fichero dentro de la carpeta output/.

Autor
Álvaro Cao Fernández — 2ºASIR
