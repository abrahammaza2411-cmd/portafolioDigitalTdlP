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

**Ejemplo práctico**

```c
#include <stdio.h>

// Función que recibe el saldo POR VALOR
void aplicarBonoPorValor(float saldo) {
    saldo = saldo + 50;   // Solo modifica la copia local
    printf("Dentro de la función -> saldo: %.2f\n", saldo);
}

int main() {
    float saldoCliente = 100.0;

    printf("Antes de llamar -> saldo: %.2f\n", saldoCliente);
    aplicarBonoPorValor(saldoCliente);
    printf("Despues de llamar -> saldo: %.2f\n", saldoCliente);

    return 0;
}

/* Salida esperada:
Antes de llamar -> saldo: 100.00
Dentro de la función -> saldo: 150.00
Despues de llamar -> saldo: 100.00   <-- La variable original NO cambió
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

**Ejemplo práctico**

```c
#include <stdio.h>

// Función que recibe el saldo POR REFERENCIA (puntero)
void aplicarBonoPorReferencia(float *saldo) {
    *saldo = *saldo + 50;   // Modifica directamente la variable original
    printf("Dentro de la función -> saldo: %.2f\n", *saldo);
}

int main() {
    float saldoCliente = 100.0;

    printf("Antes de llamar -> saldo: %.2f\n", saldoCliente);
    aplicarBonoPorReferencia(&saldoCliente);   // Se envía la dirección de memoria
    printf("Despues de llamar -> saldo: %.2f\n", saldoCliente);

    return 0;
}

/* Salida esperada:
Antes de llamar -> saldo: 100.00
Dentro de la función -> saldo: 150.00
Despues de llamar -> saldo: 150.00   <-- La variable original SÍ cambió
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

**Ejemplo práctico**

```c
#include <stdio.h>

int main() {
    int notas[5];       // Arreglo unidimensional de 5 enteros
    int suma = 0;

    // Llenar el arreglo
    for (int i = 0; i < 5; i++) {
        printf("Ingrese la nota %d: ", i + 1);
        scanf("%d", &notas[i]);
        suma = suma + notas[i];   // Acumulador
    }

    // Mostrar el arreglo y el promedio
    printf("\nNotas ingresadas: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", notas[i]);
    }

    printf("\nPromedio: %.2f\n", suma / 5.0);

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
    int matriz[3][3];   // Matriz de 3 filas x 3 columnas

    // Llenar la matriz
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("Ingrese el valor [%d][%d]: ", i, j);
            scanf("%d", &matriz[i][j]);
        }
    }

    // Mostrar la matriz
    printf("\nMatriz ingresada:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%4d", matriz[i][j]);
        }
        printf("\n");
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
    // Ventas[sucursal][mes][producto] -> 2 sucursales, 3 meses, 2 productos
    int ventas[2][3][2];

    for (int s = 0; s < 2; s++) {
        for (int m = 0; m < 3; m++) {
            for (int p = 0; p < 2; p++) {
                printf("Ventas sucursal %d, mes %d, producto %d: ", s + 1, m + 1, p + 1);
                scanf("%d", &ventas[s][m][p]);
            }
        }
    }

    printf("\nReporte de ventas:\n");
    for (int s = 0; s < 2; s++) {
        printf("Sucursal %d:\n", s + 1);
        for (int m = 0; m < 3; m++) {
            for (int p = 0; p < 2; p++) {
                printf("  Mes %d, Producto %d -> %d unidades\n", m + 1, p + 1, ventas[s][m][p]);
            }
        }
    }

    return 0;
}
```

<br>

## 🧠 Aplicación de contenido

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
