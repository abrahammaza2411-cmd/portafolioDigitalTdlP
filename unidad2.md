<div align="center">

# 🔀 Estructuras Condicionales y Repetitivas
### Unidad 2 · Fundamentos de Programación

![Lenguaje](https://img.shields.io/badge/Lenguaje-C-blue?style=flat-square)
![Tema](https://img.shields.io/badge/Tema-Control%20de%20flujo-orange?style=flat-square)
![Estado](https://img.shields.io/badge/Estado-Completo-brightgreen?style=flat-square)

</div>

---

## 📑 Tabla de contenido

1. [Estructuras condicionales](#-estructuras-condicionales)
   - [If simple](#1️⃣-estructura-condicional-simple-if)
   - [If-else](#2️⃣-estructura-condicional-doble-if-else)
   - [Switch](#3️⃣-estructura-condicional-múltiple-switch)
   - [Anidamiento condicional](#4️⃣-anidamiento-de-estructuras-condicionales-if---else-if)
2. [Estructuras repetitivas](#-estructuras-repetitivas)
   - [Conceptos previos](#-conceptos-previos-fundamentales)
   - [While](#1️⃣-ciclo-mientras-while)
   - [Do...While](#2️⃣-ciclo-hacermientras-dowhile)
   - [For](#3️⃣-ciclo-para-for)
   - [Anidamiento de ciclos](#4️⃣-anidamiento-de-estructuras-repetitivas)
3. [Ejercicio integrador](#-ejercicio-con-estructura-condicional-y-repetitiva)
4. [Aplicación de contenido](#-aplicación-de-contenido)

---

## 🔀 Estructuras condicionales

> Las estructuras condicionales seleccionan el bloque de código que el programa ejecutará, según se cumpla o no una condición. Existen **3 tipos principales**, más una variante por anidamiento.

### 1️⃣ Estructura condicional simple (`If`)

**Definición**
Es la forma más básica de estructura condicional. Ejecuta un bloque de código **solo si la condición es verdadera**. Si la condición es falsa, el programa continúa con la siguiente instrucción sin ejecutar el bloque interno.

| Característica | Detalle |
|---|---|
| 🎯 Uso ideal | Requisitos únicos, una sola rama de ejecución |
| ⚡ Ventaja | Simplicidad y eficiencia |
| 🔁 Evaluación | Una sola condición, evaluada una vez |

<div align="center">

**Pseudocódigo**

<img width="263" height="143" alt="Pseudocódigo If simple" src="https://github.com/user-attachments/assets/2e90c2c8-516f-4f62-89c7-c59e0551077e" />

**Diagrama de flujo**

<img width="510" height="731" alt="Diagrama de flujo If simple" src="https://github.com/user-attachments/assets/a63f3cea-4eb5-4117-9048-492bcdbb9c03" />

</div>

---

### 2️⃣ Estructura condicional doble (`If-else`)

**Definición**
Añade una alternativa para decisiones binarias. Si la condición es verdadera, se ejecuta el primer bloque de código; si es falsa, se ejecuta un bloque diferente (`else`).

| Característica | Detalle |
|---|---|
| 🎯 Uso ideal | Elegir entre un camino u otro según una condición |
| ⚡ Ventaja | Maneja ambos casos (verdadero/falso) de forma clara |
| 🔁 Evaluación | Una condición, dos ramas mutuamente excluyentes |

<div align="center">

**Pseudocódigo**

<img width="258" height="253" alt="Pseudocódigo If-else" src="https://github.com/user-attachments/assets/c0100f33-fb21-4966-beff-e5d803a4e35b" />

**Diagrama de flujo**

<img width="530" height="380" alt="Diagrama de flujo If-else" src="https://github.com/user-attachments/assets/0c30372a-5e1c-46cb-968e-7b748eec78da" />

</div>

---

### 3️⃣ Estructura condicional múltiple (`Switch`)

**Definición**
Alternativa limpia y legible para comparar una sola variable contra muchos valores constantes. En lugar de usar múltiples `if-else if`, el `switch` evalúa una expresión una sola vez y ejecuta el caso que coincida.

| Característica | Detalle |
|---|---|
| 🎯 Uso ideal | Más de 2 opciones específicas (menús, selección de opciones) |
| ⚡ Ventaja | Código más legible y organizado que `if-else if` encadenados |
| 🔁 Evaluación | Una expresión, múltiples `case` posibles |
| ⛔ `break` | Detiene la ejecución para no evaluar otros casos |
| 🔚 `default` | Caso por defecto si ninguna opción coincide |

<div align="center">

**Pseudocódigo**

<img width="727" height="455" alt="Pseudocódigo Switch" src="https://github.com/user-attachments/assets/9e9a0fe9-c6b0-4fc0-9193-689e98f59bc5" />

**Diagrama de flujo**

<img width="791" height="320" alt="Diagrama de flujo Switch" src="https://github.com/user-attachments/assets/6239431d-a1a7-4ae4-a550-a47fd2cf5095" />

</div>

---

### 4️⃣ Anidamiento de estructuras condicionales (`if - else if`)

**Definición**
Aunque no es un tipo de estructura en sí, el anidamiento permite evaluar múltiples condiciones en orden secuencial. El programa revisa cada condición una por una; en cuanto una resulta verdadera, ejecuta su bloque correspondiente y sale del anidamiento sin evaluar las demás.

| Característica | Detalle |
|---|---|
| 🎯 Uso ideal | Múltiples condiciones con rangos o criterios complejos |
| ⚡ Ventaja | Maneja más de dos casos sin perder claridad |
| 🔁 Evaluación | Cadena de condiciones; solo se ejecuta la primera verdadera |
| ⚡ Cortocircuito | Se detiene al encontrar la primera condición verdadera |

<div align="center">

**Pseudocódigo**

<img width="305" height="332" alt="Pseudocódigo anidamiento condicional" src="https://github.com/user-attachments/assets/d28538cf-26a9-4c7d-a790-8515d6b88076" />

**Diagrama de flujo**

<img width="638" height="487" alt="Diagrama de flujo anidamiento condicional" src="https://github.com/user-attachments/assets/45079874-7ff4-4dad-9e0a-87360e1f135f" />

</div>

<br>

## 🔁 Estructuras repetitivas

> Las estructuras repetitivas, también conocidas como **ciclos** o **bucles**, permiten ejecutar un bloque de código múltiples veces hasta que se cumpla una condición de salida. Son esenciales porque automatizan tareas repetitivas, procesan colecciones de datos y evitan duplicación de código.

### 📌 Conceptos previos fundamentales

<table>
<tr>
<td width="50%" valign="top">

**🔢 Contador**

Variable que incrementa su valor de forma sucesiva (generalmente de uno en uno) mediante una operación de incremento. Se usa para controlar cuántas veces se ejecuta un ciclo.

```c
contador = 0
Mientras (contador < 5) hacer
    contador = contador + 1    // Incrementa en 1
Fin Mientras
```

</td>
<td width="50%" valign="top">

**➕ Acumulador**

Variable que almacena y acumula resultados dependiendo de otra variable. A diferencia del contador (que siempre suma 1), el acumulador suma valores variables. Se usa para totales, promedios, sumas, etc.

```c
suma = 0
Mientras (numero != 0) hacer
    Leer numero
    suma = suma + numero    // Acumula el valor
Fin Mientras
Imprimir suma
```

</td>
</tr>
</table>

---

### 1️⃣ Ciclo Mientras (`While`)

**Definición**
Ejecuta un bloque de código mientras una condición sea verdadera. Útil cuando el número de repeticiones es variable o desconocido y depende de entradas del usuario o datos externos.

| Característica | Detalle |
|---|---|
| ⏱️ Evaluación | Antes de cada iteración (al inicio del ciclo) |
| 🎯 Uso ideal | Cuando se desconoce el número de repeticiones |
| ⚠️ Riesgo | Puede generar ciclos infinitos si la condición nunca es falsa |
| 🛠️ Preparación | Generalmente requiere inicializar variables antes del ciclo |

```c
Mientras (condición) hacer
    bloque de código
Fin Mientras
```

**Ejemplo práctico**

```c
contador = 1
Mientras (contador <= 5) hacer
    Imprimir contador
    contador = contador + 1
Fin Mientras
// Resultado: imprime 1, 2, 3, 4, 5
```

<div align="center">

<img width="488" height="532" alt="Diagrama de flujo While" src="https://github.com/user-attachments/assets/c2f6a213-8f1b-4e9f-b857-ba175e6a3f0b" />

</div>

---

### 2️⃣ Ciclo Hacer...Mientras (`Do...While`)

**Definición**
Similar a `while`, pero con una diferencia fundamental: **garantiza que el bloque de código se ejecute al menos una vez**, ya que evalúa la condición al final del ciclo y no al principio.

| Característica | Detalle |
|---|---|
| ⏱️ Evaluación | Después de cada iteración (al final del ciclo) |
| ✅ Garantía | Se ejecuta mínimo una vez, aunque la condición sea falsa desde el inicio |
| 🔄 Flujo | Primero ejecuta → luego pregunta si continúa |
| 🎯 Uso ideal | Ciclos que deben ejecutarse al menos una vez |

```c
Hacer
    bloque de código
Mientras (condición)
```

**Ejemplo práctico**

```c
Hacer
    Imprimir "Ingresa un número (0 para salir):"
    Leer numero
    Imprimir "Número ingresado: " numero
Mientras (numero != 0)
// Se ejecuta al menos una vez, incluso si el usuario ingresa 0
```

<div align="center">

<img width="423" height="377" alt="Diagrama de flujo Do-While" src="https://github.com/user-attachments/assets/db563dd1-25b8-4bbc-8d3f-e2bbdeef29a9" />

</div>

---

### 3️⃣ Ciclo Para (`For`)

**Definición**
Es el ciclo más compacto y ordenado. Ideal cuando se conoce exactamente cuántas repeticiones se necesitan antes de ejecutar el programa. Agrupa inicialización, condición e incremento en una sola línea.

| Característica | Detalle |
|---|---|
| ⏱️ Evaluación | Antes de cada iteración (como `while`) |
| ⚙️ Ventaja | Maneja el incremento automáticamente |
| 📖 Legibilidad | Código más legible y menos propenso a errores |
| 🧩 Flexibilidad | Permite declarar variables en el `for` o usar un contador existente |

```c
Para (inicialización; condición; incremento) hacer
    bloque de código
Fin Para
```

**Ejemplo práctico**

```c
Para (i = 1; i <= 5; i = i + 1) hacer
    Imprimir i
Fin Para
// Resultado: imprime 1, 2, 3, 4, 5

Para (j = 10; j >= 1; j = j - 1) hacer
    Imprimir j
Fin Para
// Resultado: imprime 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

<div align="center">

<img width="522" height="461" alt="Diagrama de flujo For" src="https://github.com/user-attachments/assets/f1d9a58e-692d-4955-abf9-793936aa29a8" />

</div>

---

### 4️⃣ Anidamiento de estructuras repetitivas

**Definición**
Consiste en colocar un ciclo (bucle interno) dentro de otro ciclo (bucle externo). El ciclo interno se ejecuta completamente por cada iteración del ciclo externo. Muy útil para matrices, tablas de multiplicar o procesamiento de datos multidimensionales.

| Característica | Detalle |
|---|---|
| 🔄 Reinicio | El bucle interno se reinicia en cada iteración del externo |
| 📈 Impacto | Aumenta el número total de iteraciones (efecto multiplicativo) |
| 🧭 Flujo | Ciclo externo → ciclo interno completo → siguiente iteración externa |
| 📏 Recomendación | Se permiten 3+ niveles, pero se recomienda un máximo de 3 |

<div align="center">

**Pseudocódigo**

<img width="1077" height="281" alt="Pseudocódigo anidamiento de ciclos - parte 1" src="https://github.com/user-attachments/assets/00ab085b-8b02-4d24-9c2c-6690206ef6fd" />

<img width="1090" height="456" alt="Pseudocódigo anidamiento de ciclos - parte 2" src="https://github.com/user-attachments/assets/c7aa8491-16ce-43ce-afab-581e628c0dcc" />

</div>

**Ejemplo práctico**

```c
Para (i = 1; i <= 5; i = i + 1) hacer
    Para (j = 1; j <= i; j = j + 1) hacer
        Imprimir "*"
    Fin Para
    Saltar a siguiente línea
Fin Para
```

<div align="center">

**Diagrama de flujo**

<img width="257" height="212" alt="Diagrama de flujo anidamiento - parte 1" src="https://github.com/user-attachments/assets/1248929b-a33c-43bd-9717-6d6a34f9cc1d" />

<img width="370" height="540" alt="Diagrama de flujo anidamiento - parte 2" src="https://github.com/user-attachments/assets/e2af1d87-8ced-4ec6-9eb4-3688008ad6b7" />

</div>

<br>

## 🩸 Ejercicio con estructura condicional y repetitiva

### 🧾 1. Planteamiento del problema

<div align="center">

### Sistema de Control de Triage para Donación de Sangre (Tipo O-)

</div>

**Descripción**
El banco de sangre de un hospital requiere recolectar urgentemente **3 bolsas** de sangre Tipo O- para una cirugía de emergencia. Por seguridad médica, el requisito estricto para donar es tener un **peso igual o mayor a 50 kg**.

El sistema debe solicitar el peso de cada donante voluntario, en orden de llegada, y evaluar:

- ✅ Si el donante pesa **50 kg o más** → se aprueba la donación, se extrae una bolsa de sangre y se suma al inventario de emergencia.
- ❌ Si el donante pesa **menos de 50 kg** → se rechaza por su propia seguridad y no se extrae sangre.

El programa debe detenerse inmediatamente cuando:

1. Se alcance la meta de las **3 bolsas** de sangre recolectadas.
2. El personal médico introduzca un peso de **-1**, lo que indica que se cerró el laboratorio o se canceló la jornada.

Al final, el sistema mostrará cuántas donaciones fueron exitosas y cuántos voluntarios fueron rechazados por bajo peso.

---

### 🔍 2. Análisis del problema

**A. Datos de entrada**

| Variable | Tipo | Descripción |
|---|---|---|
| `peso` | Flotante / entero | Peso del donante (o `-1` para finalizar) |

**B. Datos de salida**

| Variable / mensaje | Descripción |
|---|---|
| `"Donación autorizada"` / `"Donante no apto por bajo peso"` | Mensajes en pantalla |
| `bolsasRecolectadas` | Contador de donaciones exitosas |
| `donantesRechazados` | Contador de personas que no cumplieron el peso mínimo |

**C. Proceso y lógica**

1. Inicializar: `bolsasRecolectadas = 0`, `donantesRechazados = 0`, `metaBolsas = 3`.
2. Leer el primer peso.
3. **Estructura repetitiva (`While`)**: mientras `bolsasRecolectadas < metaBolsas` **Y** `peso != -1`.
4. **Estructura condicional (`If`)** dentro del ciclo:
   - Si `peso >= 50` → sumar 1 a `bolsasRecolectadas`.
   - Si no (menor a 50, pero diferente de -1) → sumar 1 a `donantesRechazados`.
5. Si no se ha alcanzado la meta, solicitar el peso del siguiente voluntario.
6. Al salir del bucle, mostrar el reporte médico final.

---

### 🗺️ 3. Diseño del algoritmo (diagrama de flujo)

<div align="center">

<img width="4272" height="736" alt="Diagrama de flujo del sistema de triage para donación de sangre" src="https://github.com/user-attachments/assets/2454da66-91fe-4817-814c-25e363e2f822" />

</div>

---

### 💻 4. Codificación (código fuente)

```c
#include <stdio.h>

int main() {
    // Declarar variables
    int bolsasRec = 0, donantRech = 0, metaBolsas = 3;
    float peso;

    // Inicio del bucle
    do {
        // Dato de entrada
        do {
            printf("Donante, por favor ingrese su peso\n");
            scanf("%f", &peso);
            if (peso < -1 || peso > 635) {
                printf("El peso no es valido. Intente de nuevo.\n");
            }
        } while (peso > 635 || peso < -1);

        // Condiciones
        if (peso >= 50) {
            bolsasRec++;
            printf("El donante cumple con el peso para la extraccion.\n");
        } else if (peso < 50 && peso > -1) {
            donantRech++;
            printf("El donante no cumple con el peso para la extraccion.\n");
        } else {
            printf("Finalizado\n");
        }
    } while (bolsasRec < metaBolsas && peso != -1);

    // Dato de salida
    printf("Se recolectaron %i bolsas y %i donantes fueron rechazados\n", bolsasRec, donantRech);

    return 0;
}
```

---

### ✅ 5. Validación (prueba de escritorio)

<details open>
<summary><strong>Prueba 1 — Se alcanza la meta de bolsas</strong></summary>

<br>

| Peso | Bolsas recolectadas | Rechazados | Meta | Pantalla / Estado |
|:---:|:---:|:---:|:---:|:---|
| 72,5 | 1 | 0 | 3 | El donante cumple con el peso para la extracción. |
| 48 | 1 | 1 | 3 | El donante no cumple con el peso para la extracción. |
| 60 | 2 | 1 | 3 | El donante cumple con el peso para la extracción. |
| 55 | 3 | 1 | 3 | El donante cumple con el peso para la extracción. → 3 recolectadas y 1 rechazada |

<div align="center">

<img width="466" height="224" alt="Resultado en consola - Prueba 1" src="https://github.com/user-attachments/assets/fb7a6a11-861c-4651-b221-49b86bd79243" />

</div>

</details>

<details>
<summary><strong>Prueba 2 — Se cierra la jornada con peso -1</strong></summary>

<br>

| Peso | Bolsas recolectadas | Rechazados | Meta | Pantalla / Estado |
|:---:|:---:|:---:|:---:|:---|
| 80 | 1 | 0 | 3 | El donante cumple con el peso para la extracción. |
| 36 | 1 | 1 | 3 | El donante no cumple con el peso para la extracción. |
| -4 | 1 | 1 | 3 | El peso no es válido. Intente de nuevo. |
| -1 | 1 | 1 | 3 | Finalizado → Se recolectaron 1 bolsa y 1 donante fue rechazado |

</details>

<br>

## 🧠 Aplicación de contenido

### ⚠️ Principales dificultades

- **`While` vs. `Do-While`:** al comenzar la implementación, ambos ciclos se percibían como equivalentes o redundantes dentro del flujo lógico. La dificultad radicó en desglosar sus mecánicas internas hasta comprender que su divergencia es estructural: `while` condiciona la entrada al bucle (permitiendo cero ejecuciones), mientras que `do-while` asegura un ciclo inicial obligatorio antes de evaluar la continuidad.

- **Bucles infinitos:** se presentaron fallas operativas críticas por la ejecución de bucles infinitos. El problema principal es que no se origina por un error de sintaxis, lo que impide al compilador detectar la anomalía de forma previa. Al tratarse de un error de lógica pura en la actualización de las variables de control, el sistema no muestra advertencias ni detiene el proceso, manifestándose el fallo de forma imprevista durante el tiempo de ejecución.

### 💡 Reflexión crítica

La selección entre las distintas estructuras de control iterativas no debe responder a la familiaridad del programador, sino a un análisis riguroso de los requerimientos del flujo de datos. El diseño de la lógica algorítmica exige una evaluación previa y sistemática para determinar si la ejecución del bloque de código depende estrictamente de una precondición o si requiere una acción obligatoria inicial. Omitir este paso compromete la optimización y la claridad del código.

Asimismo, la experiencia con los bucles infinitos demuestra de forma contundente que la ausencia de errores de compilación no es sinónimo de un programa correcto. Dado que los errores de lógica eluden las herramientas de diagnóstico estándar de los entornos de desarrollo, se vuelve imperativo adoptar prácticas de depuración preventiva. La implementación sistemática de **pruebas de escritorio** antes de la ejecución en máquina es una metodología indispensable para rastrear el comportamiento de las variables de control, garantizando la validez de las condiciones de parada y blindando el software contra fallos lógicos imperceptibles para el compilador.

---

<div align="center">

[⬅️ **Regresar a la Unidad 2**](unidad2.md) &nbsp;·&nbsp; [🏠 **Regresar al inicio**](index.md)

</div>
