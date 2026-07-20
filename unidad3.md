<div align="center">

# 🧩 Modularidad y Arreglos
### Unidad 3 · Fundamentos de Programación

![Lenguaje](https://img.shields.io/badge/Lenguaje-C-blue?style=flat-square)
![Tema](https://img.shields.io/badge/Tema-Funciones%20%26%20Arreglos-orange?style=flat-square)
![Estado](https://img.shields.io/badge/Estado-Completo-brightgreen?style=flat-square)

</div>

---

## 📑 Tabla de contenido

1. [Modularidad](#-modularidad)
   - [Definición](#definición)
   - [Paso de parámetros por valor](#1️⃣-paso-de-parámetros-por-valor)
   - [Paso de parámetros por referencia](#2️⃣-paso-de-parámetros-por-referencia)
2. [Arreglos](#-arreglos)
   - [Arreglos unidimensionales](#1️⃣-arreglos-unidimensionales-vectores)
   - [Arreglos bidimensionales](#2️⃣-arreglos-bidimensionales-matrices)
   - [Arreglos multidimensionales](#3️⃣-arreglos-multidimensionales)
3. [Aplicación de contenido](#-aplicación-de-contenido)

---

## 🧩 Modularidad

### Definición

La **modularidad** es el principio de diseño que consiste en dividir un programa grande en partes más pequeñas, independientes y reutilizables llamadas **módulos** o **funciones**. Cada función se encarga de una tarea específica, recibe datos de entrada (parámetros), procesa esa información y puede devolver un resultado.

| Característica | Detalle |
|---|---|
| 🎯 Propósito | Dividir un problema complejo en subproblemas más simples |
| ♻️ Reutilización | Una función puede usarse varias veces sin reescribir código |
| 🧪 Mantenibilidad | Facilita la depuración, ya que los errores se aíslan por módulo |
| 👥 Trabajo en equipo | Distintas funciones pueden ser desarrolladas por distintas personas |
| 📦 Encapsulamiento | Cada función oculta su lógica interna al resto del programa |

Un aspecto clave de la modularidad en C es la forma en que los datos viajan **entre la función que llama (llamador)** y **la función llamada**. Esto se conoce como **paso de parámetros**, y existen dos mecanismos principales:

| Mecanismo | ¿Qué se copia? | ¿Modifica la variable original? |
|---|---|---|
| **Por valor** | Se copia el *valor* de la variable | ❌ No, la variable original permanece intacta |
| **Por referencia** | Se copia la *dirección de memoria* (`&variable`) | ✅ Sí, la función puede alterar la variable original |

---

### 1️⃣ Paso de parámetros por valor

**Definición**
En el paso por valor, la función recibe una **copia** del dato original. Cualquier cambio que se haga dentro de la función afecta únicamente a esa copia local; la variable original en el programa que hizo la llamada **no se modifica**.

| Característica | Detalle |
|---|---|
| 🔒 Seguridad | Protege la variable original de modificaciones accidentales |
| 🧠 Memoria | Se crea una copia independiente en la memoria (nueva dirección) |
| 🎯 Uso ideal | Cuando la función solo necesita *leer* o *calcular* con el dato, no alterarlo |
| ⚠️ Limitación | No sirve si la función necesita devolver más de un resultado modificado |

**Sintaxis general**

```c
tipo funcion(tipo parametro) {
    // 'parametro' es una copia local
    parametro = parametro + 1; // no afecta a la variable original
}
```

**Ejemplo práctico: Simulación de descenso de un dron** 

Antes de que un dron aterrice, el sistema de vuelo simula cuánta batería consumiría la maniobra de descenso. Esta simulación necesita "probar" el cálculo sin arriesgar el dato real de batería del dron, por si la maniobra resulta insegura y se decide abortar. Por eso se usa paso por valor: la función trabaja sobre una copia.

```c

#include <stdio.h>

// Recibe la bateria POR VALOR: solo "prueba" el descenso
float simularDescenso(float bateria) {
    bateria = bateria - 12.5;   // Consumo estimado de la maniobra
    printf("Simulacion interna -> bateria restante: %.2f%%\n", bateria);
    return bateria;
}

int main() {
    float bateriaDron = 30.0;

    printf("Bateria real antes de simular: %.2f%%\n", bateriaDron);
    float resultadoSimulado = simularDescenso(bateriaDron);
    printf("Bateria real despues de simular: %.2f%%\n", bateriaDron);

    return 0;
}

/* Salida esperada:
Bateria real antes de simular: 30.00%
Simulacion interna -> bateria restante: 17.50%
Bateria real despues de simular: 30.00%   <-- No cambio: fue solo una simulacion
*/
```

---

### 2️⃣ Paso de parámetros por referencia

**Definición**
En el paso por referencia, la función recibe la **dirección de memoria** de la variable original (mediante un puntero, `&`). Esto le permite acceder y **modificar directamente** el valor almacenado en esa dirección, por lo que los cambios sí se reflejan fuera de la función.

| Característica | Detalle |
|---|---|
| 🎯 Uso ideal | Cuando la función necesita modificar la variable original o devolver varios resultados |
| 🧠 Memoria | No se crea una copia; se trabaja sobre la misma dirección de memoria |
| ⚙️ Herramienta en C | Se implementa con **punteros** (`*` y `&`) |
| ⚠️ Riesgo | Mayor cuidado: un mal uso de punteros puede causar errores de memoria |

**Sintaxis general**

```c
tipo funcion(tipo *parametro) {
    // '*parametro' accede al valor real en memoria
    *parametro = *parametro + 1; // SÍ afecta a la variable original
}
```

**Ejemplo práctico:  Consumo real de batería en vuelo**

Una vez confirmado el aterrizaje, el sistema de propulsión sí debe descontar la batería real del dron mientras ejecuta la maniobra.

```c
#include <stdio.h>

// Recibe la bateria POR REFERENCIA: modifica el valor real del dron
void ejecutarDescenso(float *bateria) {
    *bateria = *bateria - 12.5;
    printf("Ejecutando descenso -> bateria real: %.2f%%\n", *bateria);
}

int main() {
    float bateriaDron = 30.0;

    printf("Bateria antes del aterrizaje: %.2f%%\n", bateriaDron);
    ejecutarDescenso(&bateriaDron);   // Se envia la direccion de memoria
    printf("Bateria despues del aterrizaje: %.2f%%\n", bateriaDron);

    return 0;
}

/* Salida esperada:
Bateria antes del aterrizaje: 30.00%
Ejecutando descenso -> bateria real: 17.50%
Bateria despues del aterrizaje: 17.50%   <-- SI cambio: fue una ejecucion real
*/
```

> 💡 **Comparación rápida:** en el primer ejemplo, `saldoCliente` termina en `100.00` porque solo se modificó una copia. En el segundo, termina en `150.00` porque la función trabajó directamente sobre la dirección de memoria de `saldoCliente`.

<br>

## 📦 Arreglos

### Definición general

Un **arreglo** (o *array*) es una estructura de datos que permite almacenar **múltiples valores del mismo tipo** bajo un solo nombre de variable, organizados en posiciones consecutivas de memoria e identificados mediante un **índice** (que en C inicia en `0`).

| Característica | Detalle |
|---|---|
| 📐 Tamaño fijo | Se define al declarar el arreglo y no cambia en tiempo de ejecución |
| 🔢 Indexación | Cada elemento se accede mediante su posición (índice), iniciando en `0` |
| 🧱 Homogéneo | Todos los elementos deben ser del mismo tipo de dato |
| 🚀 Eficiencia | Acceso directo y rápido a cualquier elemento mediante su índice |

---

### 1️⃣ Arreglos unidimensionales (vectores)

**Definición**
Es la forma más simple de arreglo: una **lista lineal** de elementos organizados en una sola fila (una dimensión). Se usa para representar listas de datos como calificaciones, nombres o temperaturas.

| Característica | Detalle |
|---|---|
| 📏 Estructura | Una sola fila de datos, accesible con un único índice `arreglo[i]` |
| 🎯 Uso ideal | Listas simples: notas, precios, temperaturas, edades |
| 🔁 Recorrido | Se recorre típicamente con un solo ciclo `for` |

**Sintaxis en pseudocódigo**

```c
Declarar arreglo[N] de tipo
Para (i = 0; i < N; i = i + 1) hacer
    Leer arreglo[i]
Fin Para
```

**Ejemplo práctico: Flota de drones de reparto**

Durante un vuelo, el dron reporta su altitud cada minuto. Es una sola secuencia de datos en el tiempo, para un único dron: por eso basta un arreglo de una dimensión.

```c
#include <stdio.h>

int main() {
    int altitudes[5];   // Altitud del dron, minuto a minuto (5 minutos de vuelo)
    int altitudMaxima = 0;

    for (int i = 0; i < 5; i++) {
        printf("Altitud minuto %d (m): ", i + 1);
        scanf("%d", &altitudes[i]);
        if (altitudes[i] > altitudMaxima) {
            altitudMaxima = altitudes[i];
        }
    }

    printf("\nBitacora de vuelo: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", altitudes[i]);
    }

    printf("\nAltitud maxima alcanzada: %d m\n", altitudMaxima);

    return 0;
}
```

---

### 2️⃣ Arreglos bidimensionales (matrices)

**Definición**
Es un arreglo que organiza los datos en **filas y columnas**, formando una **matriz**. Se puede visualizar como una tabla, y cada elemento se accede mediante **dos índices**: `matriz[fila][columna]`.

| Característica | Detalle |
|---|---|
| 📏 Estructura | Filas y columnas, accesible con `matriz[i][j]` |
| 🎯 Uso ideal | Tableros, tablas de datos, imágenes en escala de grises, hojas de cálculo |
| 🔁 Recorrido | Requiere **ciclos anidados** (uno para filas, otro para columnas) |

**Sintaxis en pseudocódigo**

```c
Declarar matriz[F][C] de tipo
Para (i = 0; i < F; i = i + 1) hacer
    Para (j = 0; j < C; j = j + 1) hacer
        Leer matriz[i][j]
    Fin Para
Fin Para
```

**Ejemplo práctico**

```c
#include <stdio.h>

int main() {
    // flota[dron][parametro] -> 3 drones, 3 parametros (bateria, altitud, velocidad)
    float flota[3][3];

    for (int d = 0; d < 3; d++) {
        printf("Dron %d - Bateria (%%): ", d + 1);
        scanf("%f", &flota[d][0]);
        printf("Dron %d - Altitud (m): ", d + 1);
        scanf("%f", &flota[d][1]);
        printf("Dron %d - Velocidad (km/h): ", d + 1);
        scanf("%f", &flota[d][2]);
    }

    printf("\nEstado de la flota:\n");
    for (int d = 0; d < 3; d++) {
        printf("Dron %d -> Bateria: %.1f%% | Altitud: %.1fm | Velocidad: %.1fkm/h\n",
               d + 1, flota[d][0], flota[d][1], flota[d][2]);
        if (flota[d][0] < 20.0) {
            printf("  ALERTA: bateria critica en Dron %d\n", d + 1);
        }
    }

    return 0;
}
```

---

### 3️⃣ Arreglos multidimensionales

**Definición**
Son una generalización de los arreglos bidimensionales: agregan una o más dimensiones adicionales (`arreglo[x][y][z]...`). Se usan para representar estructuras de datos más complejas, como cubos de datos, sistemas de coordenadas 3D o conjuntos de matrices.

| Característica | Detalle |
|---|---|
| 📏 Estructura | Tres o más índices, ej. `arreglo[capa][fila][columna]` |
| 🎯 Uso ideal | Datos con múltiples criterios (ej. ventas por sucursal, mes y producto) |
| 🔁 Recorrido | Requiere **tantos ciclos anidados como dimensiones** tenga el arreglo |
| ⚠️ Costo | Consume más memoria y es más difícil de depurar que uno o dos niveles |

**Sintaxis en pseudocódigo**

```c
Declarar arreglo[X][Y][Z] de tipo
Para (i = 0; i < X; i = i + 1) hacer
    Para (j = 0; j < Y; j = j + 1) hacer
        Para (k = 0; k < Z; k = k + 1) hacer
            Leer arreglo[i][j][k]
        Fin Para
    Fin Para
Fin Para
```

**Ejemplo práctico**

```c
#include <stdio.h>

int main() {
    // rutas[dron][waypoint][coordenada] -> 2 drones, 3 waypoints, 3 coordenadas (lat, lon, alt)
    float rutas[2][3][3];

    for (int d = 0; d < 2; d++) {
        for (int w = 0; w < 3; w++) {
            printf("Dron %d, Waypoint %d - lat: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][0]);
            printf("Dron %d, Waypoint %d - lon: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][1]);
            printf("Dron %d, Waypoint %d - alt: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][2]);
        }
    }

    printf("\nRutas de la flota:\n");
    for (int d = 0; d < 2; d++) {
        printf("Dron %d:\n", d + 1);
        for (int w = 0; w < 3; w++) {
            printf("  Waypoint %d -> lat:%.4f lon:%.4f alt:%.1fm\n",
                   w + 1, rutas[d][w][0], rutas[d][w][1], rutas[d][w][2]);
        }
    }

    return 0;
}
```

<br>

## 🧠 Aplicación de contenido
Ejercicio integrador
```
#include <stdio.h>

#define NUM_DRONES 3
#define NUM_MINUTOS 5
#define NUM_PARAMETROS 3
#define NUM_WAYPOINTS 4
#define NUM_COORD 3

/* ---------- MODULARIDAD ---------- */

// Paso POR VALOR: simula el descenso sin comprometer el dato real
float simularDescenso(float bateria) {
    return bateria - 12.5;
}

// Paso POR REFERENCIA: ejecuta el descenso y modifica el dato real
void ejecutarDescenso(float *bateria) {
    *bateria = *bateria - 12.5;
}

/* ---------- ARREGLOS ---------- */

// 1D: bitacora de altitud de un solo vuelo (Dron 1)
void registrarTelemetria(int altitudes[], int minutos) {
    for (int i = 0; i < minutos; i++) {
        printf("  Altitud minuto %d (m): ", i + 1);
        scanf("%d", &altitudes[i]);
    }
}

void mostrarTelemetria(int altitudes[], int minutos) {
    printf("\nBitacora de altitud (Dron 1):\n");
    for (int i = 0; i < minutos; i++) {
        printf("  Min %d -> %d m\n", i + 1, altitudes[i]);
    }
}

// 2D: estado de toda la flota
void cargarFlota(float flota[][NUM_PARAMETROS], int numDrones) {
    for (int d = 0; d < numDrones; d++) {
        printf("  Dron %d - Bateria inicial (%%): ", d + 1);
        scanf("%f", &flota[d][0]);
        printf("  Dron %d - Altitud actual (m): ", d + 1);
        scanf("%f", &flota[d][1]);
        printf("  Dron %d - Velocidad actual (km/h): ", d + 1);
        scanf("%f", &flota[d][2]);
    }
}

void mostrarFlota(float flota[][NUM_PARAMETROS], int numDrones) {
    printf("\nEstado de la flota:\n");
    for (int d = 0; d < numDrones; d++) {
        printf("  Dron %d -> Bateria: %.1f%% | Altitud: %.1fm | Velocidad: %.1fkm/h\n",
               d + 1, flota[d][0], flota[d][1], flota[d][2]);
        if (flota[d][0] < 20.0) {
            printf("     ALERTA: bateria critica, requiere regreso a base.\n");
        }
    }
}

// 3D: rutas de waypoints de toda la flota
void cargarRutas(float rutas[][NUM_WAYPOINTS][NUM_COORD], int numDrones) {
    for (int d = 0; d < numDrones; d++) {
        for (int w = 0; w < NUM_WAYPOINTS; w++) {
            printf("  Dron %d, Waypoint %d - lat: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][0]);
            printf("  Dron %d, Waypoint %d - lon: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][1]);
            printf("  Dron %d, Waypoint %d - alt: ", d + 1, w + 1);
            scanf("%f", &rutas[d][w][2]);
        }
    }
}

void mostrarRutas(float rutas[][NUM_WAYPOINTS][NUM_COORD], int numDrones) {
    printf("\nRutas de la flota:\n");
    for (int d = 0; d < numDrones; d++) {
        printf("  Dron %d:\n", d + 1);
        for (int w = 0; w < NUM_WAYPOINTS; w++) {
            printf("    Waypoint %d -> lat:%.4f lon:%.4f alt:%.1fm\n",
                   w + 1, rutas[d][w][0], rutas[d][w][1], rutas[d][w][2]);
        }
    }
}

/* ---------- PROGRAMA PRINCIPAL ---------- */

int main() {
    // --- Fase 1: Modularidad (valor vs referencia) sobre el Dron 1 ---
    float bateriaDron1 = 30.0;

    printf("=== FASE 1: Aterrizaje del Dron 1 ===\n");
    printf("Bateria real antes de simular: %.2f%%\n", bateriaDron1);

    float resultadoSimulado = simularDescenso(bateriaDron1);
    printf("Simulacion (POR VALOR) -> bateria resultante: %.2f%%\n", resultadoSimulado);
    printf("Bateria real tras la simulacion: %.2f%% (no cambio)\n", bateriaDron1);

    if (resultadoSimulado > 10.0) {
        printf("Simulacion segura. Ejecutando descenso real...\n");
        ejecutarDescenso(&bateriaDron1);   // POR REFERENCIA
        printf("Bateria real tras ejecutar el descenso: %.2f%%\n", bateriaDron1);
    }

    // --- Fase 2: Arreglo 1D - Telemetria del vuelo del Dron 1 ---
    printf("\n=== FASE 2: Telemetria del Dron 1 ===\n");
    int altitudes[NUM_MINUTOS];
    registrarTelemetria(altitudes, NUM_MINUTOS);
    mostrarTelemetria(altitudes, NUM_MINUTOS);

    // --- Fase 3: Arreglo 2D - Estado de toda la flota ---
    printf("\n=== FASE 3: Estado de la flota (%d drones) ===\n", NUM_DRONES);
    float flota[NUM_DRONES][NUM_PARAMETROS];
    cargarFlota(flota, NUM_DRONES);
    mostrarFlota(flota, NUM_DRONES);

    // --- Fase 4: Arreglo 3D - Rutas de toda la flota ---
    printf("\n=== FASE 4: Rutas de la flota (%d waypoints c/u) ===\n", NUM_WAYPOINTS);
    float rutas[NUM_DRONES][NUM_WAYPOINTS][NUM_COORD];
    cargarRutas(rutas, NUM_DRONES);
    mostrarRutas(rutas, NUM_DRONES);

    return 0;
}
```

### ⚠️ Principales dificultades

- **Confusión entre paso por valor y por referencia:** al inicio, resultaba difícil predecir si una función modificaba o no la variable original. La dificultad se resolvió comprendiendo que el paso por valor trabaja sobre una *copia* en una dirección de memoria distinta, mientras que el paso por referencia usa punteros para operar directamente sobre la dirección original.

- **Manejo de punteros:** la sintaxis de `*` y `&` generó errores frecuentes de compilación (por ejemplo, olvidar el operador `&` al enviar el argumento, o el `*` al des-referenciar dentro de la función). Fue necesario practicar varias veces para interiorizar cuándo se usa cada símbolo.

- **Índices fuera de rango en arreglos:** al trabajar con arreglos, uno de los errores más comunes fue intentar acceder a una posición inexistente (por ejemplo, `arreglo[5]` en un arreglo de tamaño 5, cuyo índice máximo válido es `4`). Este tipo de error no siempre es detectado por el compilador y puede causar comportamientos impredecibles en tiempo de ejecución.

- **Ciclos anidados en matrices y arreglos multidimensionales:** llevar el control de qué índice corresponde a fila, columna o capa se volvió confuso a medida que aumentaban las dimensiones, especialmente al recorrer y mostrar los datos en el orden correcto.

### 💡 Reflexión crítica

La modularidad no es solo una práctica de organización, sino una decisión de diseño que impacta directamente la seguridad y la previsibilidad del programa. Elegir entre paso por valor y paso por referencia no debe ser arbitrario: cuando una función solo necesita **consultar** un dato, el paso por valor protege la integridad de la variable original; cuando la función necesita **transformar** ese dato o retornar múltiples resultados, el paso por referencia es indispensable. Ignorar esta distinción puede introducir efectos secundarios difíciles de rastrear en programas más grandes.

De manera similar, los arreglos exigen una planificación cuidadosa del tamaño y la dimensionalidad de la estructura antes de codificar. Un arreglo unidimensional es suficiente para datos lineales, pero forzar una lista compleja de relaciones dentro de una sola dimensión genera código difícil de mantener; en cambio, usar dimensiones adicionales sin necesidad real solo añade complejidad innecesaria. Al igual que con los bucles infinitos estudiados en la unidad anterior, los errores de índice fuera de rango no siempre son señalados por el compilador, lo que refuerza la importancia de las pruebas de escritorio y la verificación manual de los límites de cada arreglo antes de ejecutar el programa. En conjunto, la modularidad bien aplicada y el uso adecuado de arreglos son la base para escribir programas más legibles, reutilizables y fáciles de depurar.

---

<div align="center">
  
  [🏠 **Regresar al inicio**](index.md)

</div>
