# Estructura de Presentación: Informe 01 de Proyecto de Tesis

Esta estructura está diseñada para una presentación (tipo PowerPoint, Beamer o Canva) basándose en el Informe 01 del proyecto de tesis. Cada "Diapositiva" resume los puntos clave de cada capítulo para una exposición verbal fluida, clara y orientada al rigor matemático.

---

## Diapositiva 1: Portada
*   **Título:** Formulación y análisis de un modelo de programación no lineal para la optimización de costos en redes logísticas interregionales
*   **Presentado por:** Miguel Angel Luna Ttacca
*   **Asignatura:** Seminario de Tesis I
*   **Lugar y Año:** Tacna - Perú, 2026

---

## Diapositiva 2: I. Preparación y Revisión Bibliográfica
*   **Búsqueda Dual:** Se abordó desde dos ejes: los fundamentos matemáticos de la optimización (teoría axiomática) y la aplicación empírica a redes de transporte.
*   **Brecha Identificada:** La ingeniería logística actual suele linealizar los problemas (asumiendo proporcionalidad estricta) o emplea heurísticas sin garantía de convergencia global. 
*   **El Problema:** La realidad física del transporte posee dinámicas intrínsecamente no lineales (economías de escala que son cóncavas y congestión que es convexa). Falta un puente matemático formal que estructure rigurosamente esta topología.

---

## Diapositiva 3: Formulación del Problema
*   **Definición Axiomática:** Modelamiento sobre un grafo dirigido $G = (V, E)$, donde se minimiza la función objetivo multivariable no lineal $F(X)$ (costos de transporte y almacenamiento).
*   **Restricciones:** Sujeto a la región factible $\Omega$, regida por leyes estandarizadas de conservación de flujo y capacidades de arcos.
*   **Pregunta Principal de Investigación:** *¿Cuáles son las propiedades estructurales (topológicas y geométricas) y el rendimiento computacional de un modelo de programación no lineal formulado para minimizar costos en redes logísticas interregionales?*

---

## Diapositiva 4: II. Antecedentes del Problema
*   **Evolución:** Históricamente sustentado en la teoría clásica de flujos en redes (Ahuja, Magnanti & Orlin).
*   **Estado Actual:** Literatura aplicada reciente recurre masivamente a la Programación Lineal (PL) o Entera Mixta (PLEM).
*   **Necesidad Teórica:** Los trabajos previos esquivan las complicaciones del Análisis Convexo al no introducir funciones logísticas continuas de orden superior, abriendo la puerta a la contribución de la presente investigación.

---

## Diapositiva 5: III. Objetivos de la Investigación
*   **Objetivo Principal:** Formular y analizar rigurosamente un modelo de Programación No Lineal para redes logísticas interregionales, demostrando sus propiedades topológicas y evaluando asintóticamente la convergencia de algoritmos de optimización diferenciable.
*   **Objetivos Específicos:**
    1.  *Construcción Axiomática:* Definir funciones de costo multivariables y sus restricciones.
    2.  *Análisis Topológico:* Demostrar convexidad, compacidad y formular las condiciones de Karush-Kuhn-Tucker (KKT).
    3.  *Análisis Numérico:* Implementar in-silico y evaluar métodos numéricos continuos (Puntos Interiores, SQP).

---

## Diapositiva 6: Hipótesis de Trabajo
*   **Hipótesis Principal:**
    > "La formulación de la red logística utilizando funciones de costo de clase $C^2$ (dos veces diferenciables) y no estrictamente convexas, genera un espacio topológico donde algoritmos de Punto Interior o gradiente conjugado convergen hacia óptimos estacionarios con un menor error analítico que los modelos lineales clásicos (PLEM), asumiendo un incremento en la complejidad temporal acotado polinomialmente."

---

## Diapositiva 7: IV. Justificación del Problema
*   **Relevancia:** Cierra la brecha entre la simplificación académica y la realidad física, evitando "óptimos artificiales" por la linealización excesiva.
*   **Impacto Teórico (Matemática Pura):** Aporta a la Optimización Continua evaluando cómo funciones de costo reales sobre grafos desafían los teoremas de unicidad.
*   **Impacto Práctico:** Deriva algoritmos que minimizan el costo económico real, previenen la congestión estructural de vías y reducen indirectamente la huella de carbono logística.

---

## Diapositiva 8: V. Alcance y Limitaciones
*   **Alcance Teórico y Numérico:** La tesis prioriza la abstracción y el análisis matemático por sobre un simple caso de estudio. Se enfoca en simulaciones sobre instancias generadas matemáticamente (*in-silico*).
*   **Limitaciones / Delimitación:** No busca desarrollar software comercial para una empresa "X", sino proveer la estructura teórica algorítmica generalizable para topologías interregionales variadas.

---

## Diapositiva 9: VI. Metodología
*   **Fase Analítico-Deductiva:** Basada en el formalismo de la matemática pura. Incluye cálculo diferencial multivariable para derivadas y matrices Hessianas, análisis topológico para los teoremas de Weierstrass, y derivación analítica de dualidad (KKT).
*   **Fase Numérico-Experimental:** Implementación matricial computacional usando herramientas de alto nivel (Julia / Python).
*   **Justificación:** Se descartan las metaheurísticas (cajas negras) a favor de algoritmos matriciales continuos para poder garantizar pruebas rigurosas de convergencia según el rigor matemático exigido.

---

## Diapositiva 10: VII. Relevancia del Estudio y Conclusiones
*   **Impacto Sintetizado:** Demostrar que el rigor de la matemática pura puede traducirse en una herramienta de cálculo algorítmico superior a los atajos de la industria tradicional.
*   **Conexión Final:** Al responder nuestras preguntas de investigación, el modelo permitirá a la academia logística entender matemáticamente el comportamiento marginal de los costos y mejorar sistémicamente la toma de decisiones.

---

## Diapositiva 11: Referencias Bibliográficas Principales
*   **Fundamentos Matemáticos y de Optimización:**
    *   Bazaraa, M. S., Sherali, H. D., & Shetty, C. M. (2006). *Nonlinear Programming: Theory and Algorithms*.
    *   Nocedal, J., & Wright, S. J. (2006). *Numerical Optimization*.
    *   Boyd, S., & Vandenberghe, L. (2004). *Convex Optimization*.
*   **Teoría de Flujos en Redes Logísticas:**
    *   Ahuja, R. K., Magnanti, T. L., & Orlin, J. B. (1993). *Network Flows: Theory, Algorithms, and Applications*.
    *   Ravindran, A. R., & Warsing, D. P. (2012). *Supply Chain Engineering: Models and Applications*.
*   **Estado del Arte (Artículos de Referencia):**
    *   Investigaciones recientes en modelado de redes inversas, redes logísticas de alimentos (ej. caso Colombia) e integración de plantas, distribuidores y detallistas.
