# Challenge 1 (Individual): Pipeline de Machine Learning
## Caso B: Infecciones Respiratorias Agudas (IRA) y neumonía en menores de 5 años en el Perú

**Curso:** Machine Learning - Fundamentos de Machine Learning  
**Docente:** Yannick Patrick Carrasco Merma  
**Unidad:** 2  
**Fecha de preparación indicada en la consigna:** 06/10/2026

## 1. Presentación del caso y problema

Esta infografía reporta una reducción de episodios de IRA en menores de cinco años: 1 003 178 (2023), 883 959 (2024) y 824 978 (2025). También reporta una reducción de defunciones por neumonía: 113 (2023), 82 (2024) y 51 (2025). Entre las medidas mencionadas están la vacunación contra neumococo e influenza, lavado de manos, uso de mascarilla ante síntomas, ventilación y atención oportuna.

**Problema propuesto:** ¿Cómo puede un pipeline de análisis de datos explorar escenarios de evolución de los episodios de IRA y estimar un valor de referencia para el siguiente periodo, con el fin de apoyar la planificación preventiva?

**Justificación de IA/ML:** un modelo supervisado de regresión puede aprender una relación entre variables temporales y el número de episodios, y producir estimaciones para periodos no observados. Un pipeline de búsqueda también puede explorar estados de intervención hipotéticos y comparar cuáles cumplen restricciones definidas. El resultado es apoyo analítico, no una recomendación clínica ni prueba de causalidad.

**Limitación importante:** la infografía solo aporta tres observaciones anuales. No son suficientes para entrenar y validar de forma confiable un modelo predictivo. Por ello, el notebook de regresión usa datos mensuales sintéticos, creados únicamente para demostrar el flujo técnico. No representan cifras oficiales ni deben interpretarse como pronóstico sanitario real.


## 2. Espacio de estados

- **Estado:** escenario de planificación descrito por (nivel de cobertura preventiva, intensidad de campaña, capacidad de atención, episodios estimados).
- **Estado inicial:** escenario base ilustrativo con cobertura preventiva baja, campaña baja y capacidad de atención media.
- **Operadores:** aumentar cobertura; intensificar campaña; aumentar capacidad de atención; combinar acciones.
- **Objetivo:** encontrar un escenario factible con menor número estimado de episodios y recursos dentro de los límites definidos.
- **Restricciones:** presupuesto máximo ilustrativo; capacidad de atención no puede superar el nivel máximo; las acciones son niveles discretos; las cifras resultantes son hipotéticas.
- **Criterio de costo:** episodios estimados más una penalización por recursos utilizados. Este costo solo sirve para demostrar búsqueda, no para asignar presupuestos reales.


## 3. Tipo de aprendizaje y tarea

- **Tipo:** aprendizaje supervisado.
- **Tarea:** regresión, porque la variable objetivo (episodios mensuales de IRA) es numérica.
- **Modelo:** regresión lineal como línea base, por ser interpretable y adecuada para enseñar la relación entre variables. El notebook compara el error en un conjunto de prueba temporal.
- **Visualización:** valores observados sintéticos frente a predicciones y estimación ilustrativa para el periodo siguiente.
- **Métricas:** MAE y RMSE. En un análisis real se necesitarían datos oficiales desagregados por mes y región, variables de población, clima, cobertura de vacunación, acceso a servicios y campañas.


## 4. Estructura del repositorio

- `README.md`: descripción y cómo ejecutar.
- `docs/espacio_de_estados.md`: formulación conceptual.
- `notebooks/01_pipeline_razonamiento_busqueda.ipynb`: problema, estados, exploración, búsqueda y resultado.
- `notebooks/02_pipeline_regresion_ira.ipynb`: generación de datos sintéticos, entrenamiento, evaluación y gráfico.
- `data/serie_anual_referencia.csv`: valores que aparecen en la infografía, es solo un ejemplo profesor.


## 5. Google Colab

Colab 1: https://colab.research.google.com/drive/1bw583jyu7j-zZc6XK7lzhYjkHAaTzc79?usp=sharing 

Colab 2: https://colab.research.google.com/drive/1Zien0zPVn7rhmJnMpJe_bxboxnZW6rvY?usp=sharing 


## 6. Interpretación responsable

Las cifras anuales se transcriben de la infografía del caso. Los datos mensuales del modelo y los valores de los escenarios de búsqueda son sintéticos/didácticos. Una asociación temporal no demuestra que una intervención específica haya causado la reducción. El modelo no debe utilizarse para diagnóstico, tratamiento ni decisiones reales de salud pública.
