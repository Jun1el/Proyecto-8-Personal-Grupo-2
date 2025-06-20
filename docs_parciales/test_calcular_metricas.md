## 2. `test_calcular_metricas.py`

### Descripción
Archivo de pruebas unitarias desarrollado con `pytest` para verificar el funcionamiento del modulo `calcular_metricas.py`, responsable de procesar el historial de commits y calcular metricas como el lead time.

### Funcionalidad Probada
El script cubre las siguientes funciones:
- `registrar_git_log()`: captura el historial de commits mediante `subprocess`.
- `escribir_csv()`: escribe las metricas en formato CSV.
- `calcular_lead_time()`: calcula el tiempo entre la creación y el cierre de los issues cerrados.

### Casos de Prueba Incluidos
1. **Mock del comando `git log`**  
   Verifica que `registrar_git_log` extraiga correctamente el `commit_hash`, fecha, tipo de issue y días desde el inicio.

2. **Escritura correcta en CSV**  
   Comprueba que `escribir_csv` cree un archivo con la estructura adecuada y datos precisos.

3. **Lead time de un issue cerrado**  
   Evalúa que el cálculo de `lead_time` sea correcto y que el archivo `lead_time.csv` tenga los valores esperados.

4. **Issue abierto es ignorado**  
   Valida que los issues con estado `open` no se incluyan en el cálculo.

5. **Manejo de JSON inválido**  
   Asegura que el script no se rompa si el archivo `issues.json` esta mal formado.

### Entrada
- `issues.json` con atributos: `id`, `state`, `created_at`, `closed_at`.

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

- Simulación de `git log`.


### Ejecucion en el proyecto 
```python
# Creamos entorno virtual
python -m venv .venv
# Activamos el entorno 
cd .venv
cd bin 
source activate
# Instalamos las dependencias de requirements.txt
pip install -r requirements.txt
# Ejecutamos pruebas 
pytest tests/test_calcular_metricas.py
```