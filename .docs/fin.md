# 📦 ¿De qué trata mi tesis? — Explicación para cualquier persona

**Título oficial:**
*"Formulación y análisis de un modelo de programación no lineal para la optimización de costos en redes logísticas interregionales"*

---

## 🌍 El problema del mundo real: mover cosas de un lado al otro cuesta dinero

Imagina que tienes una empresa que produce papas en Puno, y necesitas llevarlas a Lima, pasando por Arequipa. Para eso tienes camiones, rutas, almacenes en el camino, y cada paso te cuesta plata: gasolina, peaje, almacenamiento, tiempo.

Ahora imagina que no es solo papas, ni solo una empresa. Piensa en **todo el país** con decenas de ciudades (nodos), conectadas por carreteras (rutas), con cientos de empresas mandando productos al mismo tiempo.

La pregunta es: **¿cómo mover todo ese flujo de carga de la manera más barata posible?**

Eso es exactamente lo que estudia esta tesis.

---

## 🗺️ La red: ciudades, rutas y flujos

Para entender la tesis, imagina un mapa:

- Cada **ciudad** (o almacén, o fábrica) es un **punto** en la red. En matemáticas se llama **nodo** y se escribe con la letra `V` (de *vértice*).
- Cada **carretera** entre dos ciudades es una **conexión**. En matemáticas se llama **arco** y se escribe como `E` (de *edge*, arista en inglés).
- Todo junto se llama un **grafo dirigido** y se escribe como `G = (V, E)`.

Ejemplo sencillo:

```
[Puno] ——→ [Arequipa] ——→ [Lima]
              ↓
           [Tacna]
```

En cada flecha (arco), pasa una cantidad de carga: eso se llama **flujo** y se representa con `x_ij`, que quiere decir "cuánto mando del nodo `i` al nodo `j`".

---

## ❌ El problema con los modelos tradicionales: "la linealidad miente"

Antes, los matemáticos e ingenieros modelaban este tipo de problemas con algo llamado **Programación Lineal (PL)**. ¿Qué significa eso?

Significa que asumían que si mandas el doble de carga, pagas el doble. Si mandas el triple, pagas el triple. Siempre proporcional. Una línea recta.

Pero eso **no es lo que pasa en la realidad**:

1. **Congestión vehicular:** Si una sola ruta la usan muchos camiones al mismo tiempo, la carretera se satura. Los costos no solo doblan, se disparan exponencialmente. Imagina que hay un embotellamiento y los camiones están parados horas: eso no es lineal, es una curva que sube muy rápido.

2. **Economías de escala:** Si mandas un solo camión con 5 toneladas, el costo por tonelada es alto. Si llenas 10 camiones con 500 toneladas, el costo por tonelada baja (descuentos por volumen, rutas optimizadas, etc.). Esto tampoco es lineal, la curva baja conforme aumenta la cantidad.

> 💡 **Ejemplo fácil:** Si compras 1 botella de agua en una tienda, pagas S/. 2. Si compras una caja de 24 botellas, pagas S/. 30 total (S/. 1.25 por botella). El costo no es proporcional. Eso es una **economía de escala**: mientras más compras, más barato por unidad.

La tesis dice: **"los modelos actuales asumen que el mundo es una línea recta, pero el mundo real es una curva"**. Y esa curva se llama **función no lineal**.

---

## 📐 ¿Qué hace la tesis exactamente?

La tesis **formula un modelo matemático no lineal** para representar este problema de manera fiel a la realidad. En lenguaje matemático, el objetivo es **minimizar** una función llamada `F(X)`:

```
mínimo de: F(X) = Σ f_ij(x_ij) + Σ h_i(y_i)
```

Desglosado en palabras:
- `Σ f_ij(x_ij)` = suma de todos los costos de transporte en cada ruta (curva no lineal por congestión o economía de escala).
- `Σ h_i(y_i)` = suma de todos los costos de almacenamiento en cada nodo/ciudad (también no lineal).
- `X` = el conjunto de todas las decisiones: cuánta carga mando por cada ruta.

**El objetivo:** encontrar los valores de `X` (cuánto mando por cada ruta) que hagan que ese costo total sea lo más pequeño posible.

Pero no se puede hacer cualquier cosa. Hay **restricciones** (reglas que cumplir):

1. **Conservación de flujo:** Lo que entra a una ciudad debe salir (no puede desaparecer mercancía en el camino). Matemáticamente:
   ```
   (lo que sale del nodo i) - (lo que entra al nodo i) = demanda de i
   ```
   Como en un tubo: lo que entra tiene que salir.

2. **Capacidad de las rutas:** Cada carretera tiene un límite de carga que puede soportar:
   ```
   0 ≤ x_ij ≤ u_ij
   ```
   Donde `u_ij` es el máximo de carga que puede pasar por esa ruta.

3. **Otras restricciones complejas** relacionadas con leyes interregionales, horarios, tipos de carga, etc.

---

## 🎯 ¿A dónde quiere llegar la tesis? (Los objetivos)

La tesis tiene **tres grandes metas**:

### Meta 1 — Construir el modelo matemático con rigor

No se trata solo de escribir una ecuación bonita. Se trata de demostrar **desde cero**, con axiomas y demostraciones formales, que el modelo representa correctamente el mundo real y que tiene solución.

Es como construir una casa: primero aseguras que los cimientos son sólidos antes de levantar las paredes.

### Meta 2 — Analizar la "forma" del problema

Aquí entra algo llamado **análisis topológico y convexo**. ¿Qué significa eso?

Cuando buscas el punto más bajo de un valle, es fácil: solo bajas rodando y llegas al fondo. Eso es un **problema convexo** (hay un solo mínimo claro). Pero imagina un terreno con muchos hoyos y colinas: si caes en un hoyo pequeño, puedes pensar que llegaste al mínimo cuando en realidad hay uno más profundo lejos de ahí. Eso es un **problema no convexo**.

Como los costos logísticos son no lineales, la tesis necesita analizar si el "terreno" del problema tiene uno o varios mínimos, y cómo distinguirlos. Para eso se usan herramientas como:

- **La matriz Hessiana** `∇²F(X)`: es una tabla de segundas derivadas que dice si estás en un mínimo real o en uno falso.
- **Las condiciones KKT (Karush-Kuhn-Tucker):** son las reglas matemáticas que debe cumplir cualquier punto que sea una solución óptima con restricciones. Funcionan como un "certificado" de que encontraste el mejor punto.

### Meta 3 — Resolver el modelo con algoritmos y medir qué tan bien funcionan

Finalmente, no basta con tener el modelo teórico. Se necesita **resolverlo en la computadora**. Para eso se usan algoritmos especializados como:

- **Método de Puntos Interiores:** Un método que "navega" por el interior de la región de soluciones válidas, evitando salirse de los límites, y converge al mínimo de forma segura.
- **Programación Cuadrática Secuencial (SQP):** Divide el problema no lineal en una serie de problemas cuadráticos más simples y los resuelve uno a uno hasta llegar a la solución.

Y no solo se ejecutan: se **demuestra matemáticamente** que convergen (que llegan a una respuesta) y se mide la **tasa de convergencia** (qué tan rápido llegan).

---

## 🛤️ ¿Cómo se va a lograr todo esto? (La metodología)

La investigación tiene **dos fases**:

### Fase 1 — Matemática pura: demostrar en papel

Se parte de los principios más básicos de la matemática (axiomas de espacios vectoriales, teoría de grafos) y se construye todo el modelo desde ahí.

Se calcularán:
- El **Gradiente** `∇F(X)`: vector que apunta en la dirección de mayor crecimiento del costo. Sirve para saber hacia dónde "bajar".
- El **Hessiano** `∇²F(X)`: matriz que mide la curvatura de la función. Dice si el punto encontrado es realmente un mínimo.

Se usará el **Teorema de Weierstrass** para demostrar que existe al menos un mínimo en la región de soluciones (no tiene sentido buscar algo si no estás seguro de que existe).

### Fase 2 — Computación: resolver y medir

Se programará el algoritmo (en Python o Julia) y se probará con instancias de prueba (grafos generados artificialmente, ya que datos reales industriales suelen ser confidenciales). Se medirá:
- ¿Cuántas iteraciones necesita para llegar a la respuesta?
- ¿Cuánto tiempo de CPU consume?
- ¿Qué tan pequeño es el error al final?

---

## 🧠 ¿Para qué sirve todo esto? (La finalidad)

### Propósito inmediato — Optimizar costos logísticos reales

Si alguien usa este modelo, puede tomar decisiones más inteligentes sobre:
- ¿Por qué ruta mando mis camiones hoy?
- ¿Cuánta carga acumulo en tal almacén?
- ¿Cómo distribuyo mis recursos para gastar menos?

Todo esto considerando las curvas reales del costo, no suposiciones simplificadas.

### Propósito académico — Llenar un vacío en la literatura matemática

Hoy en día, la mayoría de artículos académicos sobre logística usan modelos lineales o algoritmos "de caja negra" (heurísticas) que no tienen demostración matemática de que funcionen correctamente. Esta tesis **da el rigor que falta**: construye el puente entre la ingeniería aplicada y la matemática pura, demostrando formalmente que el modelo es correcto y que el algoritmo converge.

### Propósito más amplio — Las mismas ecuaciones sirven para otros campos

Porque el modelo está construido sobre una estructura abstracta `G = (V, E)`, las mismas matemáticas aplican a:

- **Redes de internet:** los datos que viajan por servidores también se "congestionan" y el ruteo óptimo de paquetes es el mismo tipo de problema.
- **Redes de agua o gas:** calcular el caudal óptimo en tuberías interconectadas es matemáticamente idéntico.
- **Inteligencia artificial:** el entrenamiento de Redes Neuronales de Grafos (GNN) usa exactamente el mismo descenso por gradiente que se estudia en esta tesis.

---

## 📏 ¿Qué incluye y qué NO incluye?

Para no perderse en un problema demasiado grande, la tesis tiene límites claros:

| ✅ Incluye | ❌ No incluye |
|---|---|
| Flujos continuos (cantidades reales, no enteras) | Variables binarias (abrir/cerrar almacenes) |
| Funciones diferenciables dos veces (`C²`) | Incertidumbre o aleatoriedad en la demanda |
| Redes macro-regionales (ciudades enteras) | Ruteo de camiones dentro de una ciudad |
| Análisis teórico riguroso + simulación computacional | Datos industriales reales (por confidencialidad) |

---

## 🔑 Resumen en una oración

> **La tesis construye, desde cero con rigor matemático, un modelo no lineal para decidir cuánta carga enviar por cada ruta de una red de ciudades, de forma que el costo total sea mínimo — y demuestra que el algoritmo que lo resuelve realmente funciona y llega a la respuesta correcta.**

---

## 📖 Glosario rápido

| Término | Qué significa en lenguaje simple |
|---|---|
| **Grafo** G=(V,E) | Mapa de puntos (ciudades) conectados por flechas (rutas) |
| **Función no lineal** | Una curva (no una línea recta) que relaciona carga con costo |
| **Optimizar** | Encontrar la mejor decisión posible (mínimo costo) |
| **Región factible Ω** | El conjunto de todas las soluciones que no violan las reglas |
| **Gradiente ∇F** | Vector que indica hacia dónde sube más rápido el costo |
| **Hessiana ∇²F** | Matriz que mide la curvatura; confirma si encontramos el mínimo real |
| **KKT** | Condiciones matemáticas que debe cumplir cualquier solución óptima con restricciones |
| **Convergencia** | Que el algoritmo llega a una respuesta (no se pierde en el camino) |
| **Economía de escala** | Mientras más compras/envías, el costo por unidad baja |
| **Congestión** | Mientras más tráfico hay en una ruta, el costo por unidad sube mucho |
| **Programación No Lineal (PNL)** | Área de las matemáticas que estudia optimización con funciones curvas |

---

*Elaborado como guía de comprensión del proyecto de tesis — Miguel Angel Luna Ttacca — Seminario de Tesis I, UNJBG, 2026.*
