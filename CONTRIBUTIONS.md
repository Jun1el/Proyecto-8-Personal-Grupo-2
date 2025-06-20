
# Contribucion

## Autor
**Andrés Sebastián La Torre Vásquez (@Jun1el)**  
latorrevasquezandressebastian@gmail.com

### Issues

- Sprint 1:  [3] Crear script generar_kanban.sh inicial #3
- Sprint 2: [8] Mejorar generar_kanban.sh para transiciones de estado #17
- Sprint 2: [9] Agregar pruebas unitarias para calcular_metricas.py #18
- Sprint 3: [13] Optimizar generar_kanban.sh para rendimiento
#29
- Sprint 13: [11] Agregar pruebas unitarias para notificar_retrasos.py #27
 
## Sprint 1

### Issue [#3] Crear script generar_kanban.sh inicial
**Objetivo**: Implementar un script Bash que genere automáticamente un archivo `kanban.md` a partir del archivo `issues.json`, agrupando los issues por estado (`To Do`, `In Progress`, `Done`).

**Commits realizados**:

- `b68afb5` (07-Jun-2025)  
  - `feat[#3]`: Crea el script `scripts/generar_kanban.sh` con verificación de `jq`, estructura básica y lógica para recorrer los issues.

- `351d037` (07-Jun-2025)  
  - `docs[#3]`: Genera archivo inicial `docs/kanban.md` con una primera versión del tablero.

- `94f9001` (08-Jun-2025)  
  - `test[#3]`: Agrega prueba `tests/test_generar_kanban.sh` que valida la generación del Kanban, secciones esperadas y formato correcto.

**Resultado**: Primer tablero funcional y automatizado desde datos en JSON. Validado con pruebas basicas en Bash.

---

## Sprint 2

### Issue [#17] Mejorar generar_kanban.sh para transiciones de estado
**Objetivo**: Incluir información adicional de los issues, como fechas de creación y cierre, para enriquecer el tablero Kanban.

**Commit realizado**:

- `e119f28` (12-Jun-2025)  
  - `update[#17]`: Mejora el script y el `kanban.md` para mostrar campos como `Creado` y `Cerrado`, usando expresiones `jq` más completas.

**Resultado**: El tablero Kanban ahora refleja transiciones temporales más claras para los issues.

---

### Issue [#18] Agregar pruebas unitarias para calcular_metricas.py
**Objetivo**: Implementar pruebas automaticas con `pytest` para asegurar el funcionamiento correcto de las funciones principales del modulo `calcular_metricas.py`.

**Commits realizados**:

- `6382e39` (14-Jun-2025)  
  - `update[#18]`: Se actualiza `.gitignore` y se agregan dependencias necesarias en `requirements.txt` (pytest, pluggy, etc.).

- `4d946e0` (14-Jun-2025)  
  - `test[#18]`: Crea `tests/test_calcular_metricas.py` con 5 pruebas que cubren:
    - Simulación de salida de `git log`
    - Escritura en CSV
    - Calculo correcto de `lead_time`
    - Casos de issues abiertos
    - Manejo de JSON malformado

**Resultado**: Las pruebas garantizan que el calculo de metricas funcione correctamente y maneje errores comunes sin romper el sistema.

---

## Sprint 3

### Issue [#13] Optimizar `generar_kanban.sh` para grandes volumenes  
**Objetivo**: Refactorizar el script para mayor eficiencia y claridad, usando bucles y evitando repeticiones.

**Commit**:
- `e397dad` (18-Jun-2025): `refactor[#29]` — Refactor general con control de errores, bucles para secciones y mejoras de escalabilidad.

**Resultado**: Script robusto que puede manejar grandes archivos de issues con estructura dinámica.

---

### Issue [#9] Adaptar test a version optimizada  
**Commit**:
- `3e15f87` (19-Jun-2025): `test[#18]` — Ajuste de los tests `test_calcular_metricas.py` para soportar nueva estructura de salida (`dia_desde_inicio`, formato ISO 8601).

**Resultado**: Validacion continua tras refactor, manteniendo cobertura y confiabilidad.

---

### Issue [#11] Agregar pruebas unitarias para `notificar_retrasos.py`  
**Objetivo**: Probar errores comunes y generación de alertas de retrasos en la entrega de issues.

**Commit**:
- `5479dab` (19-Jun-2025): `test[#27]` — 4 tests que validan:
  - Archivos faltantes
  - CSV malformado
  - Generación correcta de emails en `reports/emails/`
  - Uso de mocks para rutas y carpetas
  
**Resultado**: Cobertura del componente de alertas, esencial para detectar demoras automaticamente.
## Conceptos y herramientas utilizadas

- Tecnologias utilizadas: `bash`, `jq`, `pytest`, `unittest.mock`, `json`, `subprocess`
- Archivos trabajados:  
  `scripts/generar_kanban.sh`, `docs/kanban.md`, `tests/test_generar_kanban.sh`, `tests/test_calcular_metricas.py`, `requirements.txt`, `.gitignore`
- Automatizacion de reportes, pruebas unitarias robustas usando conceptops como fixtures y mocks asi como  mejora continua del codigo.

---