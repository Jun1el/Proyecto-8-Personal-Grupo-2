## 3. `test_notificar_retrasos.py`

### Descripción
Archivo de pruebas unitarias creado con `pytest` para asegurar el correcto funcionamiento del modulo `notificar_retrasos.py` encargado de generar archivos de alerta (`emails`) cuando un issue supera un umbral de horas en su lead time.

Estas pruebas aseguran que el script maneje correctamente distintos escenarios: archivos inexistentes, CSVs mal formateados y generacion de correos simulada.

---

### Funcionalidad Probada

- Verifica la existencia de archivos requeridos (`lead_time.csv`, `issues.json`).
- Detecta errores en archivos con formato incorrecto (como CSV sin cabeceras).
- Evalua que solo se generen correos para issues con `lead_time > umbral` (por defecto 72 horas).
- Utiliza `mock` para evitar efectos secundarios como la creacion real de directorios.

---

### 🧪 Casos de prueba implementados

1. **Archivo `lead_time.csv` no existe**  
   - Entrada: archivo inexistente.  
   - Salida esperada: mensaje de error `"error: inexistente.csv no encontrado"`.

2. **Archivo `issues.json` no existe**  
   - Entrada: JSON faltante.  
   - Salida esperada: mensaje `"error: falso.json no encontrado"`.

3. **CSV malformado (sin cabecera `issue_id`)**  
   - Entrada: archivo `.csv` con datos incorrectos.  
   - Salida esperada: mensaje `"error: formato csv erroneo"`.

4. **Generación simulada de emails**  
   - Entrada: CSV con issues (algunos sobre el umbral).  
   - Salida esperada:
     ```
     email generado: reports/emails/issue_3_delay.txt
     email generado: reports/emails/issue_4_delay.txt
     ```

---

### Entradas

- **CSV (`lead_time.csv`)**
  ```csv
  issue_id,lead_time_hours
  1,1.2
  2,2.2
  3,80.5
  4,100.1
  ```

- **JSON(issues.json)**
    ```
    [
        {"id": 1, "owner": "junal"},
        {"id": 2, "owner": "janio"},
        {"id": 3, "owner": "andres"},
        {"id": 4, "owner": "desconocido"}
    ]
    ```

### Ejecucion en el proyecto 

```python 
# Asumiendo que ya tenemos el entorno virtual con las dependencias instaladas en el doc anterior ejecutamos el test
pytest tests/test_notificar_retrasos.py
# Vemos la cobertura del codigo 
pytest --cov=src tests/test_notificar_retrasos.py
```
