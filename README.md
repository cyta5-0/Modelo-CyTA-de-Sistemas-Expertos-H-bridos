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

- 1. Diagrama de Flujo del Sistema (Sequence Flow)Este esquema detalla el proceso desde que el usuario llena el formulario hasta que obtiene el análisis estratégico.Descripción del proceso:INPUT: El usuario provee Balances (Hechos) y Objetivos (Contexto).KNOWLEDGE FETCH: El motor PHP extrae las reglas (Fórmulas/Alertas) de la base de datos SQL.DETERMINISTIC INFERENCE: PHP evalúa las fórmulas. Si un ratio cruza un umbral, se dispara una alerta.PROMPT ORCHESTRATION: Se empaqueta el resultado técnico con el contexto de negocio en un bloque estructurado.GENERATIVE OUTPUT: El usuario entrega el "paquete" a la IA para el informe final.2. Diagrama de Bloques: Arquitectura Híbrida CyTA 5.0Este diagrama es ideal para el README.md de tu GitHub, ya que muestra la jerarquía de las capas.Las 3 Capas de Orquestación:Capa 1 (Base de Conocimiento - SQL): Almacena el "Saber Hacer" contable de forma estática.Capa 2 (Capa Lógica - PHP): El "Cerebro" que procesa y calcula, asegurando que no haya errores matemáticos.Capa 3 (Capa Cognitiva - IA): El "Consultor" que lee los resultados de la Capa 2 y los traduce a lenguaje humano estratégico.3. Resumen Técnico para tu documentación personalPara que recuerdes cómo "conjugar" las funciones en el código, guarda esta tabla:ComponenteArchivoFunción ClaveResponsabilidadRepositorio de Reglasmarcelop_accounting.sqlTablas ratios y alertasDefinir qué es "bueno" o "malo".Calculador Expertocontabilidad_logic.phpejecutar_motor_inferencia()Realizar la matemática pura.Redactor de Promptcontabilidad_logic.phpgenerar_prompt_ia()Unir números con objetivos.Orquestadoranalisis_financiero_completo.phpCarga de $_POSTRecibir datos y mostrar el resultado.
