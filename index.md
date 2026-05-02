<div align="center">
<img src= "https://redi.cedia.edu.ec/members/UNL.png" width= "230px"> <br>

# **Portafolio Digital de Aprendizaje – Teoría de la Programación**
### **Universidad Nacional De Loja**
### **Facultad de la Energía, las Industrias y los Recursos Naturales no Renovables**
### **Carrera de Computación**
### **Teoría de la Programación**
### **Docente: Ing. Lissette Geoconda López Faicán**
### **Estudiante: Abraham Daniel Maza Lapo**
### **Primer Ciclo**
### **Período académico Marzo - Agosto 2026**
</div> <br>

## **Unidad 1**

### **Resolución de Problemas**

Resolver un problema real mediante la informática requiere seguir estos pasos: 
  1. Análisis (identificar entradas, salidas y restricciones).
  2. Diseño (pseudocódigo o diagramas).
  3. Codificación (traducción a código fuente). 
  4. Pruebas (eliminación de errores).
  5. Documentación/Mantenimiento.




### **1. Conceptos fundamentales**

#### **a. Algoritmo**
Es una secuencia de pasos lógicamente ordenados que dan solución a un problema. Se caracteriza por ser preciso (orden claro sin ambigüedades), definido (mismo resultado ante las mismas entradas) y finito (debe tener un fin).<br>

#### **b. Pseudocódigo** 
Es una herramienta que representa las instrucciones del algoritmo, funcionando como un punto intermedio entre el lenguaje natural y el lenguaje de programación. Permite centrarse en la lógica antes de enfrentar la sintaxis..<br>

**Ejemplo:**
```
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

```
#### **c. Diagrama de Flujo**
Es una representación gráfica que emplea simbología estandarizada para visualizar la lógica de un algoritmo. Entre sus elementos principales se encuentran el Terminal (Inicio/Fin), el Proceso (rectángulo para operaciones), la Entrada/Salida de datos (paralelogramo) y las líneas de Flujo del proceso (flechas) que indican el orden de ejecución.<br>
**Ejemplo:**<br>
    
<img width="381" height="651" alt="Captura de pantalla 2026-05-01 102508" src="https://github.com/user-attachments/assets/5876060e-9b5b-4d6c-9326-10a61fcf83e6" />



#### **d. Prueba de Escritorio**
Es una técnica que consiste en ingresar datos de entrada (propios o aleatorios) para verificar el cambio de las variables paso a paso. Este proceso permite supervisar la evolución del estado del algoritmo y revisar que el resultado final sea el esperado antes de la codificación definitiva.<br>

**Ejemplo:**<br>

| **Datos de Entrada**| **Proceso** | **Datos de Salida** |    
| --- | --- | --- |
| Sueldo Mensual | ahorro mensual<br> ahorro total | ahorro mensual <br>ahorro total |
| $482 | Ahorro mensual: 18.075\*4 = 72.30. <br>Ahorro total: 72.30\*12= 867.60 | Ahorro mensual: $72.30. <br>Ahorro Anual: $867.60 |
| $1200 | Ahorro mensual: 1200\*0.15 = 180. <br>Ahorro total: 180\*12= 2160 | Ahorro mensual: $180. <br>Ahorro anual: $2160 |

#### **e. Lenguajes de programacion**
- **Lenguaje Máquina:**
Trabaja exclusivamente con código binario (0 y 1), que es el único lenguaje que el procesador de una computadora entiende y ejecuta directamente. Constituye la base fundamental de todas las instrucciones de software.



- **Lenguaje de bajo nivel (Ensamblador):**
Funciona a través de mnemónicos o comandos como ADD, DIV y STR; este nivel requiere que el programador gestione manualmente la memoria y los recursos del hardware, exigiendo un alto rigor técnico.



- **Lenguaje de alto nivel:**
Más cercano al lenguaje natural humano para facilitar la programación. Se divide principalmente en dos tipos: los compilados (generan un archivo ejecutable previo a la ejecución, como C, C++ y Java) e interpretados (se ejecutan línea por línea a través de un intérprete, como es el caso de Python). Internamente, todos se traducen finalmente a lenguaje máquina para ser procesados.

#### **f. Programación por bloques**
La programación visual es un método diseñado para crear software mediante piezas gráficas o bloques que ejecutan comandos y funciones específicas. Es utilizado principalmente para introducir a principiantes y niños en este ámbito, ya que permite asimilar la lógica fundamental sin la barrera que supone una sintaxis compleja. Al eliminar las preocupaciones sobre errores de escritura, el estudiante puede concentrar sus esfuerzos en la arquitectura del algoritmo y en el flujo de control, estableciendo una base sólida de entender la estructura antes de dar el salto a los lenguajes de programación basados en texto.

<img width="964" height="600" alt="image" src="https://github.com/user-attachments/assets/e90e1ed4-6fc8-4010-ab6b-27ca903f2fec" />


### **2. Ejercicio con estructura secuencial**
#### **Planteamiento de problema**<br>
Un lote de 10 equipos debe enviarse a diferentes sectores.
- 4 equipos se enviarán por Mensajería Express.
- 2 equipos por Transporte de Carga.
- Los 4 restantes se enviarán por Correo Convencional, el cual cuesta un 30% menos que la Mensajería Express.
- El programa debe solicitar el costo de la Mensajería Express y el Transporte de Carga para calcular el costo total del envío de los 10 equipos.

#### **Análisis del problema**<br>
Es necesario calcular el costo total de envío de un lote de 10 equipos distribuidos en tres modalidades de transporte, considerando que una de ellas tiene un costo con descuento respecto a una de las demás."

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
<img width="274" height="667" alt="Captura de pantalla 2026-05-01 204008" src="https://github.com/user-attachments/assets/c2683898-5aeb-4aad-b5aa-aeb06ea0e75c" />


**Pseudocódigo:**
```
Algoritmo presupuestoEnvio
//Def variables
definir costoEquipoM, costoEquipoT Como Real;
definir subtotalMensajeriaExpress, subtotalTransporteDeCarga, subtotalCorreoConvencional, total Como Real;
	
//Datos de entrada
Escribir "cual es el costo unitario del equipo enviado por Mensajeria Express";
leer costoEquipoM;
escribir "cual es el costo unitario del equipo enviado por Transporte de carga";
leer costoEquipoT;
	
//Proceso<br>
subtotalMensajeriaExpress = costoEquipoM*4;
subtotalTransporteDeCarga = costoEquipoT*2;
subtotalCorreoConvencional = (costoEquipoM\*0.7)\*4;
total = subtotalCorreoConvencional + subtotalMensajeriaExpress + 
subtotalTransporteDeCarga;
	
//Datos de salida
escribir "El costo de los equipos enviados por mensajeria Express será $", subtotalMensajeriaExpress;

Escribir "El costo de los equipos enviados por Transporte de carga será $", subtotalTransporteDeCarga;

Escribir "El costo de los equipos enviados por Correo convencional sera $", subtotalCorreoConvencional;

Escribir "El costo total de los equipos enviados sera $", total;
	
FinAlgoritmo

```

#### **Codificación**
**Código en c :**
```
#include <stdio.h>

int main(){

  //def variables
  float costoEquipoM, costoEquipoT;
  float subtotalMensajeriaExpress, subtotalTransporteDeCarga, subtotalCorreoConvencional, total;

  //Datos de entrada
  printf ("Cual es el costo unitario del equipo enviado por Mensajeria Express?\n");
  scanf ("%f", &costoEquipoM);
  printf ("Cual es el costo unitario del equipo enviado por Transporte de carga?\n");
  scanf ("%f", &costoEquipoT);

  //Proceso<br>
  subtotalMensajeriaExpress = costoEquipoM*4;
  subtotalTransporteDeCarga = costoEquipoT*2;
  subtotalCorreoConvencional = (costoEquipoM*0.7)*4;
  total= subtotalCorreoConvencional+subtotalMensajeriaExpress+subtotalTransporteDeCarga;

  //Datos de salida<br>
  printf ("El costo de los equipos enviados por mensajeria Express sera $%.2f.\n", subtotalMensajeriaExpress);
  printf ("El costo de los equipos enviados por Transporte de carga sera $%.2f.\n", subtotalTransporteDeCarga);
  printf ("El costo de los equipos enviados por Correo convencional sera $%.2f.\n", subtotalCorreoConvencional);
  printf ("El costo total de los equipos enviados sera $%.2f.", total);
    
  return 0;
}
```
#### **Validación**
| Entrada (Variables) | Proceso (Operaciones / Fórmulas) | Salida (Resultados Esperados) |
| :--- | :--- | :--- |
| **Costo Express:** `costoEquipoM` <br> **Costo Carga:** `costoEquipoT` | `subtotalExpress = costoEquipoM * 4` <br> `subtotalCarga = costoEquipoT * 2` <br> `subtotalConvencional = (costoEquipoM * 0.7) * 4` <br> `total = subtotalExpress + subtotalCarga + subtotalConvencional` | **El subtotal express es:** `subtotalExpress` <br> **El subtotal carga es:** `subtotalCarga` <br> **El subtotal convencional es:** `subtotalConvencional` <br> **El total es:** `total` |
| **Costo Express:** $24.00 <br> **Costo Carga:** $52.00 | $96.00 = 24 * 4$ <br> $104.00 = 52 * 2$ <br> $67.20 = (24 * 0.7) * 4$ <br> $Total = 96 + 104 + 67.20$ | **El subtotal express es:** $96.00 <br> **El subtotal carga es:** $104.00 <br> **El subtotal convencional es:** $67.20 <br> **El total es:** $267.20 |
| **Costo Express:** $12.80 <br> **Costo Carga:** $9.50 | $51.20 = 12.8 * 4$ <br> $19.00 = 9.5 * 2$ <br> $35.84 = (12.8 * 0.7) * 4$ <br> $Total = 51.20 + 19.00 + 35.84$ | **El subtotal express es:** $51.20 <br> **El subtotal carga es:** $19.00 <br> **El subtotal convencional es:** $35.84 <br> **El total es:** $106.04 |

### **3. Principales dificultades**<br>

Una de las mayores dificultades que enfrenté al inicio fue comprender que el diseño de algoritmos no es un proceso lineal. Requiere reescribir el código tras realizar un análisis más profundo, lo que permite simplificar la lógica y entender mejor el ejercicio. Gracias a las prácticas, tanto personales como en clase, logré reconocer patrones en los problemas, encontrando soluciones más sencillas para desafíos que inicialmente parecían complejos.

### **4. Reflexion crítica**<br>
La buena costumbre de realizar pruebas de escritorio es el pilar de la formación, porque permite detectar fallos antes de la implementación final. Entender que un programa es la ejecución de una serie de pasos nos asegura que cada instrucción cumpla su respectivo propósito








## Unidad 2  (no aplica).

## Unidad 3  (no aplica).

## Conclusiones generales (no aplica).

## Bibliografía.

[1] PSeInt, "Documentación oficial de PSeInt," 2021. [En línea]. Disponible en:
http://pseint.sourceforge.net/

[2] Microsoft, "Visual Studio Code," v. 1.118, 2026. [En línea]. Disponible en: https://code.visualstudio.com/.

 ## Declaración de uso de la IA generativa
 Para la elaboración de este portafolio, se utilizó la Inteligencia Artificial como una erramienta de tipo Tutor de acompañamiento.
 El uso de esta tecnología se basó en los siguiemtes aspectos:
 1. La IA funcionó como guía para entender la sintaxis en Markdown, permitiendo la correcta estructuracion de los bloques de codigo, la organizacion de tablas en las pruebas de escritorio y en el insertado de los diagramas de flujo
 2. Realizó una revisión del material, ayudando a identificar los errores ortográficos, de redaccion y de consistencia lógica en el desarrollo de los temas.

Aunque se contó con apoyo de la IA para el formato y la correccion, la autoría intelectual, el analisis de los problemas y la resolucion de los ejercicios prácticos son de mi total responsabilidad como estudiante.
