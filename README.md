# Modelo CyTA de Sistemas Expertos Híbridos (CyTA 5.0)

Este repositorio contiene la arquitectura de un sistema experto híbrido diseñado para el análisis financiero avanzado. Combina la precisión del **Cálculo Determinístico** con la flexibilidad de la **Inteligencia Artificial**.

## 🏗️ Arquitectura de Capas

El modelo se divide en tres niveles de orquestación:

1. **Capa de Conocimiento (SQL Database):** - Las reglas de negocio, fórmulas matemáticas y umbrales de alerta residen en tablas de base de datos (`ratios`, `alertas_diagnostico`). 
   - Esto permite actualizar la lógica experta sin modificar el código fuente.

2. **Capa de Inferencia (PHP Engine):**
   - El motor de inferencia (`contabilidad_logic.php`) actúa como mediador. 
   - Extrae los hechos (datos contables), consulta el conocimiento (SQL) y evalúa dinámicamente los resultados.

3. **Capa de Generación (Hybrid AI):**
   - Los resultados estructurados son procesados para generar conocimiento asistido por IA, permitiendo interpretaciones narrativas y recomendaciones estratégicas.

## 🛠️ Especificaciones Técnicas
- **Lenguaje:** PHP 5.6+
- **Base de Datos:** MariaDB / MySQL
- **Estándar:** Documentación bajo PHPDoc y metadatos Schema.org (JSON-LD).
