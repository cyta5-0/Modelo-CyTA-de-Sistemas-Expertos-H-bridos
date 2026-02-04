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

1\. Diagrama de Flujo del Sistema (Sequence Flow)

Este esquema detalla el proceso desde que el usuario llena el formulario hasta que obtiene el análisis estratégico.

Descripción del proceso:

* INPUT: El usuario provee Balances (Hechos) y Objetivos (Contexto).  
* KNOWLEDGE FETCH: El motor PHP extrae las reglas (Fórmulas/Alertas) de la base de datos SQL.  
* DETERMINISTIC INFERENCE: PHP evalúa las fórmulas. Si un ratio cruza un umbral, se dispara una alerta.  
* PROMPT ORCHESTRATION: Se empaqueta el resultado técnico con el contexto de negocio en un bloque estructurado.  
* GENERATIVE OUTPUT: El usuario entrega el "paquete" a la IA para el informe final.

2\. Diagrama de Bloques: Arquitectura Híbrida CyTA 5.0

Este diagrama es ideal para el README.md de tu GitHub, ya que muestra la jerarquía de las capas.

Las 3 Capas de Orquestación:

1. Capa 1 (Base de Conocimiento \- SQL): Almacena el "Saber Hacer" contable de forma estática.  
2. Capa 2 (Capa Lógica \- PHP): El "Cerebro" que procesa y calcula, asegurando que no haya errores matemáticos.  
3. Capa 3 (Capa Cognitiva \- IA): El "Consultor" que lee los resultados de la Capa 2 y los traduce a lenguaje humano estratégico.

3\. Resumen Técnico para tu documentación personal

Para que recuerdes cómo "conjugar" las funciones en el código, guarda esta tabla:  
Componente  
Componente,Archivo,Función Clave,Responsabilidad  
Repositorio de Reglas,marcelop\_accounting.sql,Tablas ratios y alertas,"Definir qué es ""bueno"" o ""malo""."  
Calculador Experto,contabilidad\_logic.php,ejecutar\_motor\_inferencia(),Realizar la matemática pura.  
Redactor de Prompt,contabilidad\_logic.php,generar\_prompt\_ia(),Unir números con objetivos.  
Orquestador,analisis\_financiero\_completo.php,Carga de $\_POST,Recibir datos y mostrar el resultado.
