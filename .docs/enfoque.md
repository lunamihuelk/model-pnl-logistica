# Enfoque Metodológico para Tesis en Matemática Pura y Aplicada

**Tema:** Formulación y análisis de un modelo de programación no lineal para la optimización de costos en redes logísticas interregionales

Para garantizar que la tesis cumpla con los altos estándares de la carrera de Matemática Pura y Aplicada, y evitar que sea evaluada como un proyecto de Ingeniería Industrial, el desarrollo y redacción del documento deben regirse estrictamente por las siguientes directrices:

## 1. El Modelo como Protagonista (Abstracción)
*   **El enfoque incorrecto:** Centrarse en resolver el problema logístico particular de una empresa "X" usando un software comercial (como Excel o LINGO) sin analizar la matemática de fondo.
*   **El enfoque matemático correcto:** El aporte científico de la tesis es el **modelo matemático en sí mismo y su análisis**. La logística interregional solo provee el marco semántico y la motivación de las variables. El trabajo debe centrarse en construir una estructura abstracta rigurosa, generalizable a topologías de grafos similares.

## 2. Equilibrio entre Rigor Teórico (Pura) y Resolución Numérica (Aplicada)
El desarrollo del documento debe reflejar un flujo de trabajo matemático estructurado:

### Fase A: Formulación y Análisis Teórico (El lado de "Matemática Pura")
1.  **Construcción Axiomática:** Definición formal de los espacios vectoriales, la función objetivo $f(x)$ (no lineal) y la topología de la región factible (espacio de restricciones).
2.  **Teoremas de Existencia:** Demostración analítica de que el problema posee al menos una solución óptima (por ejemplo, apoyándose en el Teorema de Weierstrass sobre conjuntos compactos).
3.  **Análisis de Convexidad:** Análisis de la matriz Hessiana para demostrar si la función objetivo es convexa, cóncava o indefinida. Esto es vital para distinguir entre un óptimo local y un óptimo global.
4.  **Condiciones de Optimalidad:** Formulación, derivación y demostración de las condiciones de Karush-Kuhn-Tucker (KKT) aplicadas específicamente a tu modelo.
5.  **Análisis de Sensibilidad (Dualidad):** Estudio matemático de cómo varían las soluciones óptimas ante perturbaciones en los parámetros (qué pasa matemáticamente si cambian los límites de capacidad o los costos base).

### Fase B: Diseño Algorítmico y Computacional (El lado de "Matemática Aplicada")
1.  **Justificación de Métodos Numéricos:** No basta con aplicar un algoritmo; se debe justificar teóricamente la elección de un método de optimización continua (como puntos interiores o gradiente conjugado) o algoritmos metaheurísticos si se demuestra que el problema es NP-Hard.
2.  **Análisis de Convergencia y Complejidad:** Estudio de la velocidad a la que el algoritmo se acerca al óptimo (tasas de convergencia lineal, superlineal o cuadrática) y análisis de complejidad $O(n)$.
3.  **Implementación Computacional:** El código debe ser una traducción directa de la matemática propuesta. Es preferible utilizar lenguajes orientados al cálculo numérico avanzado (Julia, Python/SciPy, MATLAB).
4.  **Validación Matemática:** Realizar simulaciones numéricas (benchmarks) evaluando el comportamiento del algoritmo frente a instancias del problema de diferentes tamaños, analizando su estabilidad y rendimiento computacional.

## 3. Redacción del Problema y Objetivos
Las preguntas de investigación deben interrogar sobre la naturaleza matemática del problema.
*   **Pregunta de investigación tipo:** ¿Cuáles son las propiedades estructurales (convexidad, existencia de soluciones) y el rendimiento computacional de un modelo de programación no lineal formulado para optimizar costos de transporte y almacenamiento en redes logísticas?

## 4. Estrategia de Escalabilidad (Gestión de la Dificultad)
Este enfoque permite gran flexibilidad. Si durante la ejecución te topas con dificultades u oportunidades:
*   **Para reducir dificultad analítica:** Puedes hacer "relajaciones convexas" del modelo, demostrando el error de cota (gap) entre el modelo complejo original y tu versión relajada.
*   **Para aumentar el rigor matemático:** Puedes introducir variables aleatorias en el modelo (por ejemplo, asumiendo que la demanda es una variable con distribución de Poisson o Normal), escalando la investigación a "Programación Estocástica No Lineal".
