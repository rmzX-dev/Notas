1. Calcular los puntos  de casos de uso no ajustados (UUCP).
 
2. Calcular los puntos de casos de uso (UCP).
 
3. Estimar horas-hombre.

### **Calcular los puntos de casos de uso no ajustados(UUCP)**

**a) Pesar actores (AUW)**

| Tipo de interacción                         | Peso asignado |
| ------------------------------------------- | ------------- |
| Simple(a través de API)                     | 1             |
| Media(a través de protocolo )               | 2             |
| Compleja (a través de una interfaz grafica) | 3             |

**b) Pesar casos de uso (UUCW)**

| N de transacciones del caso de uso | Tipo     | Peso |
| ---------------------------------- | -------- | ---- |
| menor o igual que 3                | Simple   | 5    |
| mayor o igual que 4 y menor que 7  | Medio    | 10   |
| mayor o igual que 7                | Complejo | 15   |

**c) UUCP = AUW + UUCW**

UUCP = 3 + 25
UUCP = 28

| Factor | Descripcion                          | Peso | Influencia | Total |
| ------ | ------------------------------------ | ---- | ---------- | ----- |
| R1     | Sistema Distribuido                  | 2    | 5          | 10    |
| R2     | Objetivos de rendimiento             | 1    | 5          | 5     |
| R3     | Eficiencia respecto al usuario final | 1    | 5          | 5     |
| R4     | Procesamiento complejo               | 1    | 5          | 5     |
| R5     | Codigo reutilizable                  | 1    | 3          | 3     |
| R6     | Instalacion sencilla                 | 0.5  | 3          | 1.5   |
| R7     | Fácil utilización                    | 0.5  | 3          | 1.5   |
| R8     | Portabilidad                         | 2    | 1          | 2     |
| R9     | Fácil de cambiar                     | 1    | 3          | 3     |
| R10    | Uso concurrente                      | 1    | 4          | 4     |
| R11    | Características de seguridad         | 1    | 5          | 5     |
| R12    | Accesible por terceros               | 1    | 4          | 4     |
| R13    | Se requiere formación                | 1    | 5          | 5     |

TCP = 0.6 + (0.01* FACTOR TOTAL TECNICO )
TCP = 1.14

| Factor | Descripcion                           | Peso | Influencia | total |
| ------ | ------------------------------------- | ---- | ---------- | ----- |
| R1     | Familiar con RUP                      | 1,5  | 5          | 7.5   |
| R2     | Experiencia en la aplicación          | 0,5  | 4          | 2     |
| R3     | Experiencia con orientación a objetos | 1,0  | 4          | 4     |
| R4     | Capacidades de analisis               | 0,5  | 5          | 2.5   |
| R5     | Motivacion                            | 1,0  | 5          | 5     |
| R6     | Requisitos estables                   | 2,0  | 5          | 10    |
| R7     | Trabajadores a tiempo parcial         | -1,0 | 5          | -5    |
| R8     | Lenguaje complejo                     | -1,0 | 5          | -5    |

EF = 1.4 + (-0,03* FACTOR AMBIENTAL TOTAL)
EF = 1.4 + (-0.03 * 21) -0.63
EF = 0.77


UCP = UUCP * TCP * EF

UCP = 24.5784
UCP * 20 = 491.568

163.856

