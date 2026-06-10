# **Estructuras condicionales**
Las estructuras condicionales son utilizadas para seleccionar el bloque de codigo que el programa ejecutará, segun se cumpla o no una condicion.
Existen 3 tipos:
## **Estructura condicional simple (If)**
### **Definición:**
Es la forma más básica de estructura condicional. Ejecuta un bloque de código **solo si la condición es verdadera**. Si la condición es falsa, el programa continúa con la siguiente instrucción sin ejecutar el bloque interno.

### **Características:**
- Para requisitos únicos o cuando solo necesitas ejecutar código si se cumple una condición específica.
- Simplicidad y eficiencia cuando solo necesitas una rama de ejecución.
- Una sola condición evaluada una sola vez.

### **en pseudocodigo:** <br> 
<img width="263" height="143" alt="image" src="https://github.com/user-attachments/assets/2e90c2c8-516f-4f62-89c7-c59e0551077e" /> <br>

### **En diagrama de flujo:** <br>
<img width="510" height="731" alt="image" src="https://github.com/user-attachments/assets/a63f3cea-4eb5-4117-9048-492bcdbb9c03" /> <br>


## **Estructura condicional doble (If-else)**
### **Definición:**
Es una estructura que añade una alternativa para decisiones binarias. Si la condición es verdadera, se ejecuta el primer bloque de código. Si la condición es falsa, se ejecuta un bloque de código diferente (else).

### **Características:**
- Uso ideal cuando necesitas ejecutar un camino u otro según una condición.
- Permite manejar ambos casos posibles (verdadero y falso) de una manera clara y ordenada.
- Una condición con dos ramas de ejecución mutuamente excluyentes.

### **en pseudocodigo:** <br>
<img width="258" height="253" alt="image" src="https://github.com/user-attachments/assets/c0100f33-fb21-4966-beff-e5d803a4e35b" /> <br>
### **En diagrama de flujo:** <br>
<img width="530" height="380" alt="image" src="https://github.com/user-attachments/assets/0c30372a-5e1c-46cb-968e-7b748eec78da" />
 <br>

## **Estructura condicional Multiple (Switch)**
### Definición:**
Es una alternativa más limpia y legible cuando se compara una sola variable contra muchos valores específicos y constantes. En lugar de usar múltiples if-else if, el switch evalúa una expresión una sola vez y ejecuta el caso que coincida.

### **Características:**
- Cuando tienes más de 2 opciones específicas (menús, selección de opciones, evaluación de un rango de valores discretos).
- Código más legible, organizado y eficiente que múltiples if-else if encadenados.
- Expresión evaluada una sola vez con múltiples casos (case) posibles.
- Break: Detiene la ejecución para evitar que continúe evaluando otros casos.
- Default: Caso por defecto cuando ninguna opción coincide.

### **en pseudocodigo:** <br>
<img width="727" height="455" alt="image" src="https://github.com/user-attachments/assets/9e9a0fe9-c6b0-4fc0-9193-689e98f59bc5" /> <br>

### **En diagrama de flujo:** <br>
<img width="791" height="320" alt="image" src="https://github.com/user-attachments/assets/6239431d-a1a7-4ae4-a550-a47fd2cf5095" /> <br>


## **Anidamiento de estructuras condicionales (if-else if)**
### **Definición:**
Si bien el anidamiento no es un tipo de estructura en sí, permite evaluar múltiples condiciones en orden secuencial. El programa revisa cada condición una por una; en cuanto una de ellas resulta verdadera, ejecuta su bloque de código correspondiente y sale del anidamiento sin evaluar las demás condiciones.

### **Características:**
- Cuando tienes múltiples condiciones con rangos o criterios complejos que deben evaluarse en orden.
- Permite manejar más de dos casos sin perder claridad en el código.
- Cadena de condiciones donde solo se ejecuta la primera que sea verdadera.
- Corta circuito (cortocircuita al encontrar la primera condición verdadera).

### **en pseudocodigo:** <br>
<img width="305" height="332" alt="image" src="https://github.com/user-attachments/assets/d28538cf-26a9-4c7d-a790-8515d6b88076" /> <br>

### **En diagrama de flujo:** <br>
<img width="638" height="487" alt="image" src="https://github.com/user-attachments/assets/45079874-7ff4-4dad-9e0a-87360e1f135f" /> <br>

## [**Regresar al Unidad 2**](unidad2.md)
## [**Regresar al inicio**](index.md)
