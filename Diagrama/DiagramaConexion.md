## Diagrama de Conexiones

Este diagrama de conexiónes está hecho en lenguaje Mermaid para MarkDown. 

```mermaid
graph TD;
    P1[Pantalla 1] --> |I2C| MC1[Micro Controlador 1]
    MC1 --> |USB| B1[Batería 1];
    
    P2[Pantalla 2] --> |I2C| MC2[Micro Controlador 2]
    MC2 --> |USB| B1[Batería 1];

    P3[Pantalla 3] --> |I2C| MC3[Micro Controlador 3]
    MC3 --> |USB| B2[Batería 2];

    P4[Pantalla 4] --> |I2C| MC4[Micro Controlador 4]
    MC4 --> |USB| B2[Batería 2];

    P5[Pantalla 5] --> |I2C| MC5[Micro Controlador 5]
    MC5 --> |USB| B3[Batería 3];
```