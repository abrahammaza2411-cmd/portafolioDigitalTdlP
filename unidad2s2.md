# **Estructuras repetitivas**

Las estructuras repetitivas, también conocidas como ciclos o bucles, permiten ejecutar un bloque de código múltiples veces hasta que se cumpla una condición de salida (condición falsa). Son esenciales en programación porque permiten automatizar tareas repetitivas, procesar colecciones de datos y evitar duplicación de código.

---

## **Conceptos previos fundamentales**

Antes de estudiar las estructuras repetitivas, es necesario comprender dos conceptos clave:

### **1. Contador**
Un **contador** es una variable que incrementa su valor de forma sucesiva, generalmente de **uno en uno**, gracias a una operación de incremento (suma de una constante). Se utiliza para controlar cuántas veces se ejecuta un ciclo.

**Ejemplo:**
```
contador = 0
Mientras (contador < 5) hacer
    contador = contador + 1    // Incrementa en 1
Fin Mientras
```

### **2. Acumulador**
Un **acumulador** es una variable que almacena y acumula resultados dependiendo de otra variable. A diferencia del contador que siempre suma 1, el acumulador suma valores variables. Se usa para calcular totales, promedios, sumas, etc.

**Ejemplo:**
```
suma = 0
Mientras (numero != 0) hacer
    Leer numero
    suma = suma + numero    // Acumula el valor de número
Fin Mientras
Imprimir suma
```

---

## **1. Ciclo Mientras (While)**

### **Definición:**
Es el ciclo más flexible y fundamental. Permite ejecutar un bloque de código **mientras una condición sea verdadera**. Es especialmente útil cuando el número de repeticiones es **variable o desconocido** y depende de las entradas del usuario o de datos externos.

### **Características:**
- Evalúa la condición **ANTES** de cada iteración (al principio del ciclo)
- Cuando se desconoce cuántas repeticiones necesitas (ejemplo: leer datos hasta que el usuario ingrese 0)
- Flexibilidad total sobre cuándo terminar el ciclo
- Posibilidad de crear ciclos infinitos si la condición nunca se vuelve falsa
- Generalmente necesita inicializar variables antes del ciclo

### **Sintaxis en pseudocódigo:**
```
Mientras (condición) hacer
    bloque de código
Fin Mientras
```

### **Ejemplo práctico:**
```
contador = 1
Mientras (contador <= 5) hacer
    Imprimir contador
    contador = contador + 1
Fin Mientras
// Resultado: imprime 1, 2, 3, 4, 5
```

### **Diagrama de flujo:**
<img width="488" height="532" alt="image" src="https://github.com/user-attachments/assets/c2f6a213-8f1b-4e9f-b857-ba175e6a3f0b" /> <br>


## **2. Ciclo Hacer...Mientras (Do...While)**

### **Definición:**
Es muy similar a **while**, pero con una diferencia fundamental: **garantiza que el bloque de código se ejecutará al menos una vez**. Esto ocurre porque evalúa la condición **AL FINAL del ciclo** y no al principio.

### **Características:**
- Evalúa la condición **DESPUÉS** de cada iteración (al final del ciclo)
- Se ejecuta mínimo una vez, aunque la condición sea falsa desde el inicio
- Primero hace → luego pregunta si continúa
- Para ciclos que necesitan ejecutarse al menos una vez

### **Sintaxis en pseudocódigo:**
```
Hacer
    bloque de código
Mientras (condición)
```

### **Ejemplo práctico:**
```
Hacer
    Imprimir "Ingresa un número (0 para salir):"
    Leer numero
    Imprimir "Número ingresado: " numero
Mientras (numero != 0)
// Se ejecuta al menos una vez, incluso si el usuario ingresa 0
```


### **Diagrama de flujo:**
<img width="423" height="377" alt="image" src="https://github.com/user-attachments/assets/db563dd1-25b8-4bbc-8d3f-e2bbdeef29a9" /> <br>



## **3. Ciclo Para (For)**

### **Definición:**
Es el ciclo más compacto y ordenado. Es **ideal cuando conoces exactamente cuántas repeticiones necesitas** antes de ejecutar el programa. Agrupa la **inicialización**, la **condición** y la **actualización del contador** en una sola línea, lo que lo hace muy eficiente.

### **Características:**
- Similar a while, evalúa la condición antes de cada iteración
- Maneja el incremento automáticamente
- Código más legible y menos propenso a errores
- Puede declarar variables en el for o usar un contador pre-existente

### **Sintaxis en pseudocódigo:**
```
Para (inicialización; condición; incremento) hacer
    bloque de código
Fin Para
```

### **Ejemplo práctico:**
```
Para (i = 1; i <= 5; i = i + 1) hacer
    Imprimir i
Fin Para
// Resultado: imprime 1, 2, 3, 4, 5

Para (j = 10; j >= 1; j = j - 1) hacer
    Imprimir j
Fin Para
// Resultado: imprime 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```


### **Diagrama de flujo:**
<img width="522" height="461" alt="image" src="https://github.com/user-attachments/assets/f1d9a58e-692d-4955-abf9-793936aa29a8" /> <br>

## **4. Anidamiento de estructuras repetitivas**

### **Definición:**
El **anidamiento** consiste en colocar un ciclo (bucle interno) **dentro de otro ciclo** (bucle externo). El ciclo interno se ejecuta completamente por cada iteración del ciclo externo. Es muy útil para trabajar con matrices, tablas de multiplicar o procesamiento de datos multidimensionales.

### **Características:**
- El bucle interno se reinicia en cada iteración del bucle externo
- Aumenta el número total de iteraciones (multiplicativo)
- Ciclo externo → Ciclo interno completo → Siguiente iteración externa
- Puede haber múltiples niveles (3 o más ciclos anidados), aunque se recomienda máximo 3
- 
### **Pseudocódigo :**

<img width="1077" height="281" alt="image17" src="https://github.com/user-attachments/assets/00ab085b-8b02-4d24-9c2c-6690206ef6fd" /> <br>
<img width="1090" height="456" alt="image34" src="https://github.com/user-attachments/assets/c7aa8491-16ce-43ce-afab-581e628c0dcc" /> <br>

### **Ejemplo práctico:**

```
Para (i = 1; i <= 5; i = i + 1) hacer
    Para (j = 1; j <= i; j = j + 1) hacer
        Imprimir "*"
    Fin Para
    Saltar a siguiente línea
Fin Para
```


### **Visualización - Diagrama de flujo:**
<img width="257" height="212" alt="image" src="https://github.com/user-attachments/assets/1248929b-a33c-43bd-9717-6d6a34f9cc1d" /> <br>
<img width="370" height="540" alt="image" src="https://github.com/user-attachments/assets/e2af1d87-8ced-4ec6-9eb4-3688008ad6b7" /> <br>




## **Navegación:**
- [**Regresar a Unidad 2**](unidad2.md)
- [**Regresar al inicio**](index.md)
