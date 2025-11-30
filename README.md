## Ejercicio BONUS: Servidor LAMP

Stack completo LAMP implementado:
- **Linux**: Ubuntu 22.04
- **Apache**: 2.4.x
- **MySQL**: 8.x
- **PHP**: 8.1.2

### Páginas implementadas:
- `index.html` - Página principal con diseño moderno
- `info.php` - Información del sistema PHP
- `test_db.php` - Verificación de conexión a MySQL

### Base de datos:
- Base de datos: `tp_final_db`
- Usuario: `alumno`
- Conexión: exitosa

[Capturas disponibles en `lamp/capturas/`]

---

# Trabajo Práctico – Administración de Sistemas Linux con Vagrant

## 📌 Integrantes del Equipo
- **Alumno A – Moran** (Administrador)
- **Alumno B – Cadima** (Desarrollador)
- **Alumno C – Hermann** (Operador)

## 🎯 Objetivos
- Virtualización con Vagrant
- Control de versiones colaborativo con Git
- Administración básica de sistemas Linux
- Gestión de permisos y usuarios
- Administración de volúmenes lógicos con LVM
- Contenedores con Docker y Docker Compose
- Monitoreo con Grafana, Loki y Prometheus
- Ejercicio Bonus: Servidor LAMP (opcional)

---

## 📂 Estructura del Proyecto

## 📂 Estructura del Proyecto

```text
.
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
```

---

## 📑 Entregables por Ejercicio

- **Ejercicio 0 – IP de la VM:** `informacion/ip_vm.txt`
- **Ejercicio 1 – Estructura inicial:** `informacion/estructura_proyecto.txt`
- **Ejercicio 2 – Fastfetch:** `informacion/system_info.txt`
- **Ejercicio 3 – Permisos:** `permisos/usuarios_[apellido].txt`, `permisos/verificacion_permisos.txt`
- **Ejercicio 4 – LVM:** `lvm/lvm-[apellido].txt`
- **Ejercicio 5 – Archivos:** `archivos/verificacion_archivos.txt`
- **Ejercicio 6 – Docker:**  
  - `contenedores/verificacion_contenedores.txt`  
  - `contenedores/testing_hermann.md`  
  - `contenedores/errores_encontrados.md`  
  - `contenedores/logs_completos.txt`  
  - `contenedores/capturas/*.png`
- **Bonus – LAMP:** `lamp/capturas/` (opcional)

---

## 🚀 Cómo levantar el entorno

1. **Levantar la VM con Vagrant:**
   ```bash
   vagrant up
   vagrant ssh
