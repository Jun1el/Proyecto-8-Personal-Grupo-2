# Generador de tablero Kanban

**Nombre completo:** Andres Sebastian La Torre Vasquez
**Correo institucional:** andres.latorre.v@uni.pe

**Proyecto grupal:** Integración de métricas ágiles: Burn-Down y lead time con scripts personalizados

**Repositorio grupal:** https://github.com/JunalChowdhuryG/Grupo-2-Practica-Calificada-3/tree/feature-generar-kanban
## Rol en el equipo

**Sprint 1**

Me encargué de implementar el script `generar_kanban.sh` que transforma los datos de `issues.json` en un tablero Kanban en Markdown. Tambien añadi un script de prueba `test_generar_kanban.sh` que verifica la generacion correcta del tablero. Esta funcionalidad fue desarrollada durante el Sprint 1 en el issue [#3](https://github.com/users/JunalChowdhuryG/projects/5/views/1?pane=issue&itemId=114221233&issue=JunalChowdhuryG%7CGrupo-2-Practica-Calificada-3%7C3)

## Cómo clonar y ejecutar mi parte 

### SPRINT 1
```bash
## clonamos el repo grupal ya que necesitamos el issues.json para generar el tablero pero ese archivo lo hizo otro integrante del equipo.

git clone git@github.com:JunalChowdhuryG/Grupo-2-Practica-Calificada-3.git

## Primero damos permisos de ejecucion a los scripts

chmod +x ./scripts/generar_kanban.sh
chmod +x ./tests/test_generar_kanban.sh

# Ejecutar el script generar_kanban
./scripts/generar_kanban.sh

# Verificamos resultado
cat docs/kanban.md

# Ejecutar el script del test_generar_kanban
./tests/test_generar_kanban.sh

