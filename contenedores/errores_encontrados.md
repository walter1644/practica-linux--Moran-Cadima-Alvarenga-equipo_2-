# Errores Encontrados y Corregidos - Alumno A Cadima

## Error 1: Nombre de volumen incorrecto

**Descripción:**
El volumen estaba declarado como `grafana-data` pero Grafana intentaba usar `grafana-storage`.

**Cómo lo encontré:**
Al ejecutar `docker-compose up -d` apareció el error:
"Named volume grafana-storage is used but no declaration was found"

**Solución:**
Cambié el nombre del volumen de `grafana-data` a `grafana-storage`

**Línea corregida:**
```yaml
volumes:
  grafana-storage:
```

---

## Error 2: Red inconsistente en servicio redis

**Descripción:**
El servicio redis usaba la red `monitoring-network` que no existe. Los demás servicios usan `monitoring`.

**Cómo lo encontré:**
Usando el comando `grep -n "networks:" docker-compose.yml` vi que redis usaba una red diferente.
También al ejecutar `docker-compose config` se veía la inconsistencia.

**Solución:**
Cambié la red de redis de `monitoring-network` a `monitoring`

**Línea corregida:**
```yaml
redis:
  networks:
    - monitoring
```

---

## Comandos utilizados:

- `docker-compose config` - Validar sintaxis
- `docker-compose up -d` - Levantar contenedores
- `docker ps` - Ver estado de contenedores
- `grep -n "networks:" docker-compose.yml` - Buscar inconsistencias
