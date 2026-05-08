# Guion de Exposición: Informe 01 de Proyecto de Tesis

**Tema:** Formulación y análisis de un modelo matemático para optimizar costos en redes logísticas
**Expositor:** Miguel Angel Luna Ttacca
**Tiempo estimado:** 10 minutos

---

## Diapositiva 1 y 2: Presentación y Contenido (0.5 minutos)
*   "Buenos días, señores del jurado y Dr. Rolando Vásquez. Soy Miguel Angel Luna Ttacca, estudiante de ciencias, y hoy presentaré el primer informe de mi proyecto de tesis, el cual busca optimizar los costos en redes logísticas utilizando modelos matemáticos rigurosos."

## Diapositiva 3: Introducción - ¿De qué trata esta tesis? (1.5 minutos)
*   "Para entender el panorama general, debemos ver el escenario: la logística interregional mueve bienes a gran escala. El problema radica en que los modelos clásicos asumen que los costos de transporte crecen como una línea recta (lineales). Es decir, suponen que llevar 100 cajas cuesta el doble que llevar 50."
*   "Sin embargo, la realidad es *no lineal*: existen economías de escala (enviar más volumen hace más barato el flete) y congestión (saturar una ruta dispara los costos). Por ello, nuestra propuesta es crear un modelo de Programación No Lineal que capture esta realidad en un grafo, evaluando su geometría y sus métodos de solución."

## Diapositivas 4 y 5: Problema y Preguntas de Investigación (1.5 minutos)
*   "Como detallamos aquí, las industrias suelen simplificar demasiado la realidad ignorando estas curvas de costo complejas."
*   "Al formular este problema matemáticamente, surge nuestra **Pregunta Central**: ¿De qué manera este modelo no lineal nos permite optimizar los costos de manera real en las redes logísticas interregionales?"
*   "Para responderla, nos planteamos tres preguntas secundarias: 1) ¿Cómo formulamos las ecuaciones de manera axiomática en el grafo? 2) ¿Qué propiedades topológicas rigen nuestra región de soluciones y bajo qué condiciones (KKT) encontramos el óptimo? y 3) ¿Qué tan rápido y complejo es para una computadora resolver este modelo?"

## Diapositiva 6: Antecedentes (1 minuto)
*   "Históricamente, se ha usado la Programación Lineal por ser fácil de calcular. Hoy en día en ingeniería se usan algoritmos heurísticos o 'cajas negras' que adivinan la solución, pero que carecen de rigor y no garantizan encontrar la mejor."
*   "Nuestra propuesta, como ven en el diagrama, actúa como puente: emplea el rigor matemático de la optimización continua para encontrar la solución exacta de las curvas."

## Diapositivas 7 y 8: Objetivos e Hipótesis (1.5 minutos)
*   "Nuestro **Objetivo Principal** es formular y analizar este modelo no lineal. Esto se desglosa en tres objetivos específicos: la construcción axiomática del modelo, el análisis geométrico y topológico derivando las condiciones KKT, y el análisis numérico computacional."
*   "Nuestra **Hipótesis** plantea que, al emplear funciones de clase $C^2$ (curvas continuas y suaves), el espacio topológico permitirá que algoritmos matriciales iterativos encuentren la solución óptima con menor error y a un costo de cálculo polinomial estable en comparación con los modelos lineales."

## Diapositivas 9 y 10: Justificación y Alcance (1 minuto)
*   "**¿Por qué es relevante?** Para la matemática pura, aporta conocimientos sobre Análisis Convexo y flujos no lineales. En la práctica, fundamenta la creación de sistemas que ahorren combustible y prevengan el colapso de las rutas."
*   "Es importante precisar nuestras **Limitaciones y Alcance**: Nos mantenemos en el ámbito teórico-computacional sobre flujos macro y continuos, excluyendo el ruteo urbano o las variables de incertidumbre."

## Diapositiva 11: Metodología (1.5 minutos)
*   "Trabajaremos este problema en dos grandes fases. Una fase analítico-deductiva, en la cual aplicaremos herramientas como el **Teorema de Weierstrass** (para garantizar que sí existe una ruta óptima) y las **Condiciones KKT** (para confirmarla matemáticamente)."
*   "La segunda fase será experimental, programando algoritmos iterativos. *Para dar un ejemplo rápido:* Si queremos mandar camiones a la sierra de Tacna, un modelo clásico dará una tarifa estática. Nuestro modelo analizará el punto exacto de equilibrio donde meter más camiones dejaría de ser rentable por la congestión, usando el cálculo diferencial avanzado."

## Diapositivas 12, 13 y 14: Relevancia y Conclusiones (1.5 minutos)
*   "Lo fascinante de estos modelos topológicos es que sus ecuaciones sirven también para otras ramas, como el flujo de datos en telecomunicaciones o mecánicas de fluidos."
*   "En conclusión: no podemos seguir simplificando la realidad si queremos optimizar de verdad. Modelar las curvas no lineales con rigor de ciencias puras nos brinda soluciones confiables, robustas y aplicables. Muchas gracias por su atención, quedo abierto a sus preguntas."

---

### Consejos Clave para la Exposición
1.  **Sencillez con Rigor:** El texto está diseñado para ser entendido por cualquier profesional, pero cuando menciones términos como **"Grafo $G=(V,E)$"**, **"Matriz Hessiana"**, **"Teorema de Weierstrass"** o **"Condiciones KKT"**, pronúncialos con seguridad, porque demuestran tu nivel como estudiante de ciencias puras.
2.  **El Ejemplo de Tacna:** Si te notan nervioso o si ves caras de confusión en el jurado al hablar de matemáticas, detente un segundo y apóyate en el ejemplo del camión desde Tacna (Diapositiva 11). Las historias o ejemplos tangibles conectan inmediatamente a la audiencia con las fórmulas.
3.  **Defensa de tu Método:** Si te preguntan por qué no usas algoritmos genéticos o de inteligencia artificial (muy de moda hoy), responde con tu enfoque analítico: *"Esos métodos son buenos para aproximar, pero matemáticamente no te pueden garantizar que han encontrado el mínimo costo real. Nuestro enfoque con derivadas nos permite garantizar analíticamente la convergencia"*.
