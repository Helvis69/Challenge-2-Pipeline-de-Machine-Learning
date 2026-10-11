# Espacio de Estados — Caso B: IRA en menores de 5 años

## Formulación

**Problema:** explorar escenarios preventivos hipotéticos que reduzcan los episodios estimados de IRA, respetando límites didácticos de recursos.

### Componentes
- **Estado** s = (c, i, a), donde:
  - c: nivel de cobertura preventiva (0, 1, 2).
  - i: intensidad de campaña preventiva (0, 1, 2).
  - a: capacidad de atención oportuna (0, 1, 2).
- **Estado inicial:** (0, 0, 1).
- **Acciones/operadores:** subir un nivel de cobertura, campaña o capacidad, si no se supera el nivel 2.
- **Restricción de recursos:** c + i + a <= 4 (presupuesto ficticio).
- **Función ilustrativa de episodios:** parte de una base de 100 unidades normalizadas y aplica reducciones hipotéticas por nivel de intervención. No es una estimación epidemiológica real.
- **Objetivo:** encontrar el estado factible con menor costo objetivo: episodios normalizados estimados + penalización de recursos.

### Representación visual

<p align="center">
  <img src="https://github.com/user-attachments/assets/bf07aae7-3689-41c1-8310-2e3d95d98e20" alt="Representación Visual del Espacio de Estados" width="40%" />
</p>


La búsqueda en anchura (BFS) recorre los estados alcanzables; la búsqueda de mejor costo selecciona el estado con el menor valor de la función objetivo entre los estados factibles. Los pesos y reducciones son inventados para la demostración del algoritmo.
