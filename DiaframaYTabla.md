# Tarea Semana 2: Algoritmo de Control de Temperatura
## Tabla de Trazado (Prueba de Escritorio)
A continuación se presenta la ejecución manual del algoritmo utilizando un conjunto de datos plausibles para N = 5 servidores.

| i | N | temperatura_actual | Condición Validación (<0 o >100) | temperaturas[i] | suma_temperaturas | ¿temperaturas[i] > max? | maxima_temperatura | promedio | Salida (Pantalla) |
|---|---|---|---|---|---|---|---|---|---|
| - | 5 | - | - | - | - | - | - | - | "Ingrese cantidad..." / LEER N |
| 1 | 5 | 24.5 | Falsa (Válido) | [1] = 24.5 | - | - | - | - | "Ingrese temp servidor 1" |
| 2 | 5 | 28.0 | Falsa (Válido) | [2] = 28.0 | - | - | - | - | "Ingrese temp servidor 2" |
| 3 | 5 | 115.5 | **Verdadera (Error)** | - | - | - | - | - | "Error: Temperatura fuera..." |
| 3 | 5 | 19.0 | Falsa (Válido) | [3] = 19.0 | - | - | - | - | "Ingrese temp servidor 3" |
| 4 | 5 | 31.5 | Falsa (Válido) | [4] = 31.5 | - | - | - | - | "Ingrese temp servidor 4" |
| 5 | 5 | 22.0 | Falsa (Válido) | [5] = 22.0 | - | - | - | - | "Ingrese temp servidor 5" |
| - | 5 | - | - | - | 0 | - | 24.5 (temp[1]) | - | (Fin de captura. Inicialización) |
| 1 | 5 | - | - | 24.5 | 24.5 | Falsa (24.5 > 24.5) | 24.5 | - | (Ciclo de procesamiento) |
| 2 | 5 | - | - | 28.0 | 52.5 | **Verdadera (28.0 > 24.5)** | **28.0** | - | (Ciclo de procesamiento) |
| 3 | 5 | - | - | 19.0 | 71.5 | Falsa (19.0 > 28.0) | 28.0 | - | (Ciclo de procesamiento) |
| 4 | 5 | - | - | 31.5 | 103.0 | **Verdadera (31.5 > 28.0)** | **31.5** | - | (Ciclo de procesamiento) |
| 5 | 5 | - | - | 22.0 | 125.0 | Falsa (22.0 > 31.5) | 31.5 | - | (Ciclo de procesamiento) |
| - | 5 | - | - | - | 125.0 | - | 31.5 | **25.0** | "Promedio: 25.0 \| Máxima: 31.5" |
