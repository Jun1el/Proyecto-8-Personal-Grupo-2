## 1. `generar_kanban.sh`

### Descripción
Script en Bash que genera automaticamente un tablero Kanban en formato Markdown (`docs/kanban.md`) a partir de los issues definidos en un archivo `issues.json`.

### Funcionalidad
- Clasifica los issues segun su estado (`open`, `in_progress`, `closed`) y los agrupa en secciones:
  - `## To Do`
  - `## In Progress`
  - `## Done`
- Muestra informacion relevante por issue: ID, titulo, owner, fecha de creacion o cierre.
- Optimizado para grandes volumenes de datos mediante uso de bucles y manejo de errores.

### Entrada
- Archivo `issues.json` con el siguiente formato por elemento:
```json
{
  "id": 3,
  "title": "Crear script generar_kanban.sh inicial",
  "owner": "andres",
  "state": "closed",
  "created_at": "2025-06-07T10:00:00",
  "closed_at": "2025-06-08T18:04:00"
}
```

### Ejecucion en el proyecto
```bash
# Dar permisos de ejecucion 
scripts/generar_kanban.sh

# Ejecutamos el script

./scripts/generar_kanban.sh
```
