# Generador de tablero Kanban

**Nombre completo:** Andres Sebastian La Torre Vasquez
**Correo institucional:** andres.latorre.v@uni.pe

**Proyecto grupal:** Integración de métricas ágiles: Burn-Down y lead time con scripts personalizados

**Repositorio grupal:** https://github.com/JunalChowdhuryG/Grupo-2-Practica-Calificada-3/tree/feature-generar-kanban


## Estructura del Repositorio
```
/Proyecto-8-Personal-Grupo-2/
├── README.md
├── CONTRIBUTIONS.md
├── branches/
│   ├── sprint-1-
│   ├── sprint-2-
│   ├── sprint-2-
│   ├── sprint-3-
│   ├── sprint-3-
│   └── sprint-3-test-notificar.patch
├── scripts-personales/
│   ├── generar_kanban.sh
│   ├── kanban.md    
│   └── issues.json
├── tests-personales/
│   ├── test_calcular_metricas.py
│   ├── test_generar_kanban.sh   
│   └── test_notificar_retrasos.py
└── videos.md
```
## Rol en el equipo

**Sprint 1**

Me encargué de implementar el script `generar_kanban.sh` que transforma los datos de `issues.json` en un tablero Kanban en Markdown. Tambien añadi un script de prueba `test_generar_kanban.sh` que verifica la generacion correcta del tablero. Esta funcionalidad fue desarrollada durante el Sprint 1 en el issue [#3](https://github.com/users/JunalChowdhuryG/projects/5/views/1?pane=issue&itemId=114221233&issue=JunalChowdhuryG%7CGrupo-2-Practica-Calificada-3%7C3)

**Sprint 2**

Me encargue de mejorar el script `generar_kanban.sh` para que muestre las fechas de creacion y cierre de los issues haciendo el tablero mas informativo (#17). Ademas desarrolle pruebas unitarias para `calcular_metricas.py`  verificando el registro de commits, la escritura en CSV y el calculo de lead time a partir de las fechas de los issues (#18).

**Sprint 3**

Durante el Sprint 3 optimice el rendimiento del script `generar_kanban.sh` para procesar grandes volumenes de datos usando estructuras más eficientes (#29). También adapte y extendi las pruebas unitarias de `calcular_metricas.py` para incluir una nueva metrica de días desde el inicio. Finalmente implemente pruebas para `notificar_retrasos.py` simulando distintos escenarios de errores y la generación de alertas si un issue supera el umbral de lead time (#27).


## Cómo clonar y ejecutar mi parte 

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

# Primero creamos el entorno virtual para tener las dependencias instaladas 
python -m venv .venv
# Activamos el entorno 
cd .venv
cd bin 
source activate
# Instalamos las dependencias de requirements.txt
pip install -r requirements.txt

# Ahora procedemos a hacer los tests

# Test para calcular metricas 
pytest tests/test_calcular_metricas.py

# Test para notificar emails
pytest tests/test_notificar_retrasos.py

# Verificamos la cobertura del codigo 

pytest --cov=src --cov-report=term-missing
```