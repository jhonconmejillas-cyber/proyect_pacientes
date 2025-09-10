# proyect_pacientes
# Proyecto de Gestión y Monitoreo de Pacientes en UCI

Este proyecto en **C++** implementa un sistema para procesar información de pacientes, configuraciones de sensores, mediciones y detección de anomalías en un entorno de **Unidad de Cuidados Intensivos (UCI)**.  
El sistema permite leer archivos de configuración, pacientes y mediciones, detectar anomalías en los datos (incluyendo ECG) y exportar la información organizada.

---

## 📂 Estructura de Archivos

El código principal se encuentra en `main.cpp` y hace uso de múltiples librerías auxiliares:

- `libs/BasicLibs.h`
- `libs/ArchivePatients.h`
- `libs/Config.h`
- `libs/Lectura.h`
- `libs/Maquina.h`
- `libs/Medicion.h`
- `libs/Patient.h`
- `libs/Sala.h`
- `EcgExport.h`

---

## ⚙️ Funcionalidades Probadas en `main.cpp`

1. **Separación de cadenas en tokens**
   - `strToTokensC` → convierte configuración en tokens.
   - `strToTokensP` → convierte información de pacientes en tokens.

2. **Conversión de tokens a estructuras**
   - `tokenToStructC` → genera una estructura `Config` desde tokens.
   - `tokenToStructP` → genera una estructura `Patient` desde tokens.

3. **Comparación de fechas**
   - `comparefech(fecha1, fecha2)` → compara dos fechas en formato `DD/MM/AAAA`.

4. **Lectura de archivos**
   - `readPatient()` → carga pacientes desde archivo.
   - `readConfig()` → carga configuraciones de sensores.
   - `readBinary()` → lee archivos binarios de simulación de mediciones (`.bsf`).

5. **Detección de anomalías**
   - `detectorAnomaly()` → determina si una lectura es anómala según configuración.
   - `detectorEcg()` → detecta anomalías en señales ECG.
   - `anomale()` → genera archivo de anomalías ordenadas cronológicamente.

6. **Reportes**
   - `writeMed()` → escribe una medición en archivo.
   - `exportarPacientesEcgAnomalos()` → exporta pacientes con ECG anómalos.
   - `generarPacientesEcgAnomalos()` → analiza sala completa y genera archivo `pacientes_ecg_anomalos.dat`.

7. **Menú interactivo**
   - Opción 1 → Lectura de sensor individual.
   - Opción 2 → Medición de un paciente.
   - Opción 3 → Una máquina de UCI.
   - Opción 4 → Una sala de UCI.
   - Opción 5 → Información del archivo de configuración.
   - Opción 6 → Información de un paciente.
   - Opción 7 → Información de un archivo de pacientes.
   - Opción 0 → Salir.

---

## ▶️ Ejecución

Compilar con `g++`:

```bash
g++ main.cpp -o uci_monitor
