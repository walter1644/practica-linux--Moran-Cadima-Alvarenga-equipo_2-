 Trabajo Práctico: Administración de Sistemas Linux 

Materia:Arquitectura y Sistemas Operativos
Grupo: Equipo 2
Integrantes:
o
* Cadima, Janneth (Alumno A - Administrador)
* Moran (Alumno B - Desarrollador)
*  “Usuario ficticio”Franz Hermann (Alumno C - Operador)


 Resumen del Proyecto
En este trabajo práctico implementamos un entorno de trabajo colaborativo virtualizado utilizando Vagrant y VirtualBox sobre una distribución Ubuntu 22.04 LTS.
El objetivo principal fue simular un escenario real de administración de servidores, gestionando usuarios, permisos de seguridad, almacenamiento lógico (LVM) y despliegue de servicios mediante contenedores Docker.


Estructura del Proyecto

├── archivos/
│   ├── README.md
│   └── verificacion_archivos.txt
├── contenedores/
│   ├── README.md
│   ├── capturas/
│   ├── docker-compose.yml
│   ├── errores_encontrados.md
│   ├── logs_completos.txt
│   ├── prometheus.yml
│   ├── testing_hermann.md
│   └── verificacion_contenedores.txt
├── informacion/
│   ├── README.md
│   ├── estructura_proyecto.txt
│   ├── ip_vm.txt
│   └── system_info.txt
├── lamp/
│   └── capturas/
├── lvm/
│   ├── README.md
│   ├── lvm-cadima.txt
│   ├── lvm-hermann.txt
│   └── lvm-moran.txt
├── permisos/
│   ├── README.md
│   ├── privado_hermann.txt
│   ├── publico_hermann.txt
│   ├── usuarios_cadima.txt
│   ├── usuarios_hermann.txt
│   ├── usuarios_moran.txt
│   └── verificacion_permisos.txt
├── privado.txt
└── publico.txt


Desarrollo y Tecnologías Implementadas

1. Virtualización y Entorno (Vagrant)
Configuramos un Vagrantfile para automatizar el despliegue de la máquina virtual.
* Provisión: Automatizamos la instalación de paquetes esenciales como git, docker, docker-compose y lvm2 al arrancar la máquina.
 *Red: Configuramos la VM en modo bridge para tener conectividad y una IP accesible dentro de la red local.
 	

2. Trabajo Colaborativo (Git)
Utilizamos Git para el control de versiones.
* Creamos un repositorio central en GitHub.
* Cada integrante trabajó en su propia máquina virtual clonando el proyecto.
* Sincronizamos las tareas individuales (IPs, reportes del sistema con fastfetch) y resolvimos la integración de archivos comunes.


 3. Gestión de Usuarios y Permisos
Como parte de la administración del sistema:
* Creamos usuarios de prueba (estudiante1, 2, 3) para simular un equipo de trabajo.
* Configuramos un grupo equipotrabajo para gestionar el acceso compartido.
*Seguridad: Implementamos permisos:
    * Carpetas personales privadas (600).
    * Carpetas públicas de lectura (644).
    * Directorio colaborativo /tmp/colaborativo con permisos especiales (770) y SetGID para que los archivos hereden el grupo automáticamente.


 4. Administración de Almacenamiento (LVM)
Simulamos el agregado de un disco físico adicional de 2GB (/dev/sdc) y lo administramos con LVM para mayor flexibilidad:
    1.  Creamos los Physical Volumes (PV).
    2.  Agrupamos en Volume Groups (VG) (vg_datos).
    3.  Particionamos en Logical Volumes (LV) de 1.5GB.
    4.  Formateamos en ext4 y configuramos el montaje persistente en /etc/fstab para que el disco no se desconecte al reiniciar la máquina.


 5. Scripting y Gestión de Archivos
Automatizamos la creación masiva de archivos de prueba utilizando bucles en Bash. Realizamos tareas de mantenimiento moviendo logs antiguos a carpetas de "archivados" y generando respaldos de seguridad, verificando la integridad de los datos con reportes de salida.

 6. Contenedores y Monitoreo (Docker)
Desplegamos un stack de servicios interconectados utilizando Docker Compose:
   * Servicios: Nginx (Web), Redis y Postgres (Bases de datos).
   * Monitoreo: Implementamos Prometheus para métricas, Loki para logs y Grafana para la visualización de datos en tiempo real.
   * Solucionamos errores de configuración en los puertos y volúmenes definidos en el docker-compose.yml.

 Conclusión
Este TP nos permitió integrar los conceptos teóricos de la materia en una práctica. Logramos coordinar el trabajo en equipo mediante Git, administrar recursos del sistema operativo (discos y permisos) y desplegar servicios modernos con contenedores, simulando un entorno de producción real.





