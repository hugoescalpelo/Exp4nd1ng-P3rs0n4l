## Diagrama de Conexiones

Este diagrama de conexiónes está hecho en lenguaje Mermaid para MarkDown. 

```mermaid
graph TD;
    P1[Pantalla 1] --> MC1[Micro Controlador 1]
    MC1 --> B1[Batería 1];
    
    P2[Pantalla 2] --> MC2[Micro Controlador 2]
    MC2 --> B1[Batería 1];

    P3[Pantalla 3] --> MC3[Micro Controlador 3]
    MC3 --> B2[Batería 2];

    P4[Pantalla 4] --> MC4[Micro Controlador 4]
    MC4 --> B2[Batería 2];

    P5[Pantalla 5] --> MC5[Micro Controlador 5]
    MC5 --> B5[Batería 5];
```