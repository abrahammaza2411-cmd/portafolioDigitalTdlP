# Ejercicio con estructura condicional y repetitiva 

## **1. Planteamiento de problema**
### **Sistema de Control de Triage para Donación de Sangre (Tipo O-)**

### **Descripción:**
El banco de sangre de un hospital requiere recolectar urgentemente 3 bolsas de sangre Tipo O- para una cirugía de emergencia. Por seguridad médica, un requisito estricto para que una persona pueda donar es que tenga un peso igual o mayor a 50 kg.

### **El sistema debe solicitar el peso de cada donante voluntario en orden de llegada y evaluar:**

- Si el donante pesa 50 kg o más, se aprueba la donación, se extrae una bolsa de sangre y se suma al inventario de emergencia.

- Si el donante pesa menos de 50 kg, se rechaza por su propia seguridad y no se extrae sangre.

### **El programa debe detenerse inmediatamente cuando:**

- Se alcance la meta de las 3 bolsas de sangre recolectadas.

- El personal médico introduzca un peso de -1, lo que indica que se cerró el laboratorio o se canceló la jornada.

### **Al final, el sistema mostrará cuántas donaciones fueron exitosas y cuántos voluntarios fueron rechazados por bajo peso.**

## **2. Análisis del problema**
### **A. Datos de Entrada**
peso: Número flotante o entero que representa el peso del donante (o -1 para finalizar).

### **B. Datos de Salida**
Mensajes en pantalla ("Donación autorizada" / "Donante no apto por bajo peso").

bolsas recolectadas: Contador de donaciones exitosas.

donantes rechazados: Contador de personas que no cumplieron el peso mínimo.

### **C. Proceso y Lógica**
- Inicializar: bolsas Recolectadas = 0, donantes Rechazados = 0, meta de Bolsas = 3.

- Leer el primer peso.

- Estructura Repetitiva (While): Mientras bolsas recolectadas < Meta de bolsas Y peso != -1.

- Estructura Condicional (If): Dentro del ciclo:

    Si peso >= 50: Sumar 1 a bolsas recolectadas.

    Si no (menor a 50 pero diferente de -1): Sumar 1 a donantes rechazados.

- Si no se ha alcanzado la meta, solicitar el peso del siguiente voluntario.

- Al salir del bucle, mostrar el reporte médico final.

## **3. Diseño del algoritmo (diagrama de flujo)**

<img width="4252" height="760" alt="Diagrama en blanco" src="https://github.com/user-attachments/assets/34124601-d28c-4248-87d1-3b3deac29254" /> <br>

## **4. Codificación (código fuente)**
```
#include <stdio.h>
int main (){ 
    int peso, bolsasRec = 0, donantRech = 0, metaBolsas = 3;
    do{ 
        do {
            printf ("Donante, porfavor ingrese su peso\n");
            scanf ("%i", &peso);
            if (peso < -1 || peso > 635) {
                printf("El peso no es valido. Intente de nuevo.\n");
            }
        }while (peso>635||peso<-1);

        if (peso>=50){
            bolsasRec++;
            printf ("El donante cumple con el peso para la extraccion.\n");
        }else if (peso<50&&peso>-1){
            donantRech++;
            printf("El donante no cumple con el peso para la extraccion.\n");
        }else{
            printf("Finalizado \n");
        }
    }while (bolsasRec<metaBolsas&&peso!=-1); 
    printf ("se Recolectaron %i bolsas y %i donantes fueron rechazados\n", bolsasRec, donantRech);

    return 0;
}

```
## **5. Validación (prueba de escritorio)**

## [**Regresar al Unidad 2**](unidad2.md)
## [**Regresar al inicio**](index.md)
