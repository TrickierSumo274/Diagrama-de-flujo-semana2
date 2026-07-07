## Descripción del caso

El algoritmo diseñado resuelve el monitoreo y control automatizado de la temperatura en un centro de datos para prevenir fallas por sobrecalentamiento. El sistema solicita al usuario ingresar la cantidad total de servidores a evaluar y, de manera secuencial, recopila la temperatura en grados Celsius de cada uno. El programa realiza una validación inmediata mediante un ciclo condicional para asegurar que cada lectura se encuentre dentro de un rango plausible de 0°C a 100°C, rechazando cualquier valor erróneo. Los datos válidos se almacenan en un arreglo para su posterior procesamiento, donde se calcula el promedio general de temperatura del datacenter y se aplica un patrón de búsqueda para identificar el valor máximo registrado, mostrando ambos resultados analíticos al finalizar la ejecución.

## Pseudocódigo

```pascal
ALGORITMO MonitoreoServidores

VARIABLES
    N : ENTERO
    i : ENTERO
    temperatura_actual : REAL
    suma_temperaturas : REAL
    promedio : REAL
    maxima_temperatura : REAL
    temperaturas : ARREGLO [30] DE REAL

INICIO
    // 1. Preguntar cuántos servidores se van a evaluar
    ESCRIBIR "Ingrese la cantidad de servidores a monitorear (máximo 30): "
    LEER N
    
    // 2. Ciclo para registrar y validar las temperaturas de cada servidor
    PARA i DE 1 HASTA N CON PASO 1 HACER
        ESCRIBIR "Ingrese la temperatura del servidor ", i, " (°C): "
        LEER temperatura_actual
        
        // Validación: Debe estar entre 0 y 100°C según la consigna
        MIENTRAS temperatura_actual < 0 OR temperatura_actual > 100 HACER
            ESCRIBIR "Error: La temperatura debe estar entre 0°C y 100°C."
            ESCRIBIR "Ingrese nuevamente la temperatura del servidor ", i, ": "
            LEER temperatura_actual
        FIN_MIENTRAS
        
        // Guardamos el valor validado en nuestro arreglo
        temperaturas[i] <- temperatura_actual
    FIN_PARA

    // 3. Inicializar acumulador y valor máximo antes del ciclo de procesamiento
    suma_temperaturas <- 0
    maxima_temperatura <- temperaturas[1]

    // 4. Recorrer el arreglo para calcular la suma y encontrar la más alta
    PARA i DE 1 HASTA N CON PASO 1 HACER
        suma_temperaturas <- suma_temperaturas + temperaturas[i]
        
        SI temperaturas[i] > maxima_temperatura ENTONCES
            maxima_temperatura <- temperaturas[i]
        FIN_SI
    FIN_PARA
    
    // 5. Calcular el promedio y mostrar los resultados finales
    promedio <- suma_temperaturas / N
    
    ESCRIBIR "El promedio de temperatura del datacenter es: ", promedio, " °C"
    ESCRIBIR "La temperatura más alta registrada es: ", maxima_temperatura, " °C"
FIN
