# **Portafolio Digital de Aprendizaje – Teoría de la Programación**
### **Universidad Nacional De Loja**
### **Facultad de la Energía, las Industrias y los Recursos Naturales no Renovables**
### **Carrera de Computacion**
### **Teoria de la Programacion**
### **Docente: Ing. Lissette Geoconda López Faicán**
### **Estudiante: Abraham Daniel Maza Lapo**
### **Primer Ciclo**
### **Período académico Marzo - Agosto 2026**
## **Unidad 1**

### **Resolucion de Problemas**

Resolver un problema real mediante la informática requiere seguir estos pasos: 
  1. Análisis (identificar entradas, salidas y restricciones),
  2. Diseño (pseudocódigo o diagramas),
  3. Codificación (traducción a código fuente), 
  4. Pruebas (eliminacion de errores) y 
  5. Documentación/Mantenimiento

### **1. Conceptos fundamentales**

#### **a. Algoritmo**
Es una secuencia de pasos establecidos, lógicamente ordenados que dan solución a un problema. Deben ser precisos (orden claro sin ambigüedades), definidos (mismo resultado ante mismas entradas) y finitos (deben concluir).

#### **b. Pseudocódigo** 
Es una herramienta que representa instrucciones del algoritmo sirviendo como un punto intermedio entre el lenguaje natural y el lenguaje de programacion.

**Ejemplo:**

    Algoritmo de Ahorro Anual
    // Definición de variables
    Definir sueldoMensual, ahorroSemanal, ahorroMensual, ahorroAnual Como Real;
    
    // Entrada de datos
    Escribir "Ingrese el sueldo mensual del trabajador:"
    Leer sueldoMensual;
    
    // Proceso lógico
    ahorroSemanal = sueldoMensual * 0.15
    ahorroMensual = ahorroSemanal * 4  // Considerando 4 semanas por mes
    ahorroAnual = ahorroMensual * 12
    
    // Salida de resultados
    Escribir "El ahorro mensual es: $", ahorroMensual
    Escribir "El ahorro anual proyectado es: $", ahorroAnual
    FinAlgoritmo

#### **c. Diagrama de Flujo**
Es una representacion grafica que emplea ciertos simbolos como el Terminal (Inicio/Fin), el         Proceso (rectángulo), Entrada/Salida (paralelogramo), Flujo del proceso (Flechas).
**Ejemplo:**<br>
    
![ahorroAnual](AhorroAnual.png)

#### **d. Prueba de Escritorio**
Es una tecnica que consiste en dar datos de entrada aleatorios para verificar el cambio de variables paso a paso y revisar que el resultado sea el esperado<br>
**Ejemplo:**<br>

| **Datos de Entrada**| **Proceso** | **Datos de Salida** |    
| --- | --- | --- |
| Sueldo Mensual | ahorro mensual<br> ahorro total | ahorro mensual <br>ahorro total |
| $482 | Ahorro mensual: 18.075\*4 = 72.30. <br>Ahorro total: 72.30\*12= 867.60 | Ahorro mensual: $72.30. <br>Ahorro Anual: $867.60 |
| $1200 | Ahorro mensual: 1200\*0.15 = 180. <br>Ahorro total: 180\*12= 2160 | Ahorro mensual: $180. <br>Ahorro anual: $2160 |

#### **e. Lenguajes de programacion**
<br>**- Lenguaje Máquina:**
Trabaja solo con binarios (1 y 0), que el procesador de una computadora entiende y ejecuta, es la base de todas las instrucciones de software.
<br>**- Lenguaje de bajo nivel:**
Funciona a través de comandos como add, div, str; requiere que el programador gestione manualmente la memoria y los recursos.
<br>**- Lenguaje de alto nivel:**
Mas cercano al lenguaje natural, existen 2 tipos, los compilados (que generan un archivo ejecutable, como c/c++ y java) e interpretados (que se ejecutan linea por linea a traves de un intérprete, Python es de este tipo de lenguaje). Internamente se convierten a lenguaje máquina.

#### **f. Programación por bloques**
Es un metodo visual para crear software mediante piezas grafias (bloques) que cumplen cierto comando o funcion, es principalmente utilizado para enseñar a principiantes y niños, porque permite aprender lógica sin escribir sintaxis compleja.










### **2. Ejercicio con estructura secuencial**
#### **Planteamiento de problema**<br>
Un lote de 10 equipos debe enviarse a diferentes sectores.
- 4 equipos se enviarán por Mensajería Express.
- 2 equipos por Transporte de Carga.
- Los 4 restantes se enviarán por Correo Convencional, el cual cuesta un 30% menos que la Mensajería Express.
- El programa debe solicitar el costo de la Mensajería Express y el Transporte de Carga para calcular el costo total del envío de los 10 equipos.

#### **Análisis del problema**<br>
Necesitamos calcular el costo total de envío de un lote de 10 equipos distribuidos en 3 modalidades de transporte, considerando que una tiene un costo con descuento respecto a otra.

**Tipos de datos:**<br>
la cantidad de equipos son **constantes.**
los costos, subtotales y el total son **variables de tipo Real.**

**Entradas:**<br>
- Costo unitario por Mensajería Express
- Costo unitario por Transporte de Carga

**Proceso:**<br>
Calcular los subtotales multiplicando el costo por la cantidad respectiva, como: costoEquipo1 x cantidad1 = Subtotal1
Calcular el total sumando los subtotales, tal que: total= Subtotal1 + Subtotal2 + Subtotal3

**Salidas:**<br>
- Subtotal por Mensajería Express.
- Subtotal por Transporte de Carga.
- Subtotal por Correo Convencional.
- Costo Total General.
#### **Diseño del algoritmo**
**Diagrama de flujo**<br>
![presupuestoEnvio](image-1.png) <br>

**Pseudocódigo**<!--Los saltos de linea (<br>) no estan incluidos en elpseudocodigo, son para mejorar la redaccion en el producto final-->

Algoritmo presupuestoEnvio<br>
//Def variables<br>
definir costoEquipoM, costoEquipoT Como Real;<br>
definir subtotalMensajeriaExpress, subtotalTransporteDeCarga, subtotalCorreoConvecional, total Como Real;<br>
	
//Datos de entrada<br>
Escribir "cual es el costo unitario del equipo enviado por Mensajeria Express";<br>
leer costoEquipoM;<br>
escribir "cual es el costo unitario del equipo enviado por Transporte de carga";<br>
leer costoEquipoT;<br>
	
//Proceso<br>
subtotalMensajeriaExpress = costoEquipoM*4; <br>
subtotalTransporteDeCarga = costoEquipoT*2;<br>
subtotalCorreoConvecional = (costoEquipoM\*0.7)\*4;<br>
total = subtotalCorreoConvecional + subtotalMensajeriaExpress + 
subtotalTransporteDeCarga;<br>
	
//Datos de salida<br>
escribir "El costo de los equipos enviados por mensajeria Express será $", subtotalMensajeriaExpress;

Escribir "El costo de los equipos enviados por Transporte de carga será $", subtotalTransporteDeCarga;

Escribir "El costo de los equipos enviados por Correo convencional sera $", subtotalCorreoConvecional;

Escribir "El costo total de los equipos enviados sera $", total;
	
FinAlgoritmo
#### **Codificación**
**Código en c :**<br><!--Los saltos de linea (<br>) no estan incluidos en elpseudocodigo, son para mejorar la redaccion en el producto final-->

  #include <stdio.h>
  int main(){<br>

  //def variables<br>
  float costoEquipoM, costoEquipoT;<br>
  float subtotalMensajeriaExpress, subtotalTransporteDeCarga, subtotalCorreoConvecional, total; <br>

  //Datos de entrada<br>
  printf ("Cual es el costo unitario del equipo enviado por Mensajeria Express\n");<br>
  scanf ("%f", &costoEquipoM);<br>
  printf ("Cual es el costo unitario del equipo enviado por Transporte de carga\n");<br>
  scanf ("%f", &costoEquipoT);<br>

  //Proceso<br>
  subtotalMensajeriaExpress = costoEquipoM*4;<br>
  subtotalTransporteDeCarga = costoEquipoT*2;<br>
  subtotalCorreoConvecional = (costoEquipoM*0.7)*4;<br>
  total= subtotalCorreoConvecional+subtotalMensajeriaExpress+subtotalTransporteDeCarga;<br>

  //Datos de salida<br>
  printf ("El costo de los equipos enviados por mensajeria Express sera $%.2f.\n", subtotalMensajeriaExpress);<br>
  printf ("El costo de los equipos enviados por Transporte de carga sera $%.2f.\n", subtotalTransporteDeCarga);<br>
  printf ("El costo de los equipos enviados por Correo convencional sera $%.2f.\n", subtotalCorreoConvecional);<br>
  printf ("El costo total de los equipos enviados sera $%.2f.", total);<br>
    
  return 0;<br>
}<br>
#### **Validación**
<!--PENDIENTE

-->
### **3. Principales dificultades**<br>

Una de las mayores dificultades que enfrenté al inicio fue comprender que el diseño de algoritmos no es un proceso lineal. Requiere reescribir el código tras realizar un análisis más profundo, lo que permite simplificar la lógica y entender mejor el ejercicio. Gracias a las practicas tanto personales como en clase, logré reconocer patrones en los problemas, encontrando soluciones más sencillas para desafíos que inicialmente parecían complejos.

### **4. Reflexion crítica**<br>
La buena costumbre de realizar pruebas de escritorio son el pilar de la formacion, porque permite detectar fallos antes de la implementacion final. Entender que un programa es la ejecucion de una serie de pasos nos asegura que cada instruccion cumpla su respectivo proposito.


















## Unidad 2  (no aplica).

## Unidad 3  (no aplica).

## Conclusiones generales (no aplica).

## Bibliografía (formato IEEE).

[1] G. L. López Faicán, "Guía Didáctica de Teoría de la Programación", Universidad Nacional de Loja, Loja, Ecuador, 2026.

[2] PSeInt, "Documentación oficial de PSeInt," 2021. [En línea]. Disponible en:
http://pseint.sourceforge.net/
