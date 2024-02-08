# Journal

Aquí voy registrando el avance de la pieza

## 2024-01-18
Se realizo la propuesta de un accesorio facial para la presentación en Faro Cosmos. Monky decide entre joyería facial impresa en 3D o una mascara de pantallas.

## 2024-01-19
Presenté un [boceto](https://github.com/hugoescalpelo/Exp4nd1ng-P3rs0n4l/blob/main/Imagenes/Boceto.png) que usa como base unos lentes para montar pantallas varias. 

## 2024-01-23
Decidimos realizar la máscara con [5 pantallas](https://github.com/hugoescalpelo/Exp4nd1ng-P3rs0n4l/blob/main/Imagenes/5pantallas.jpg)

---
He creado este repositorio.

---
He generado un presupuesto, fue aprobado por Monky.

---
He recogido el material, estoy en proceso de investigar el manejo de las pantallas

## 2023-01-24

Logré cargar una imagen a las pantallas. Hice una prueba y se puede ver en este [TikTok](https://www.tiktok.com/@hugoescalpelo/video/7327761072075607302?lang=es).

Generaré la documentación de eso.

No llegaron las pantallas.

## 2021-01-25

Ya pasó el pago de las pantallas.

---
Ya tengo en mi escritorio las 5 pantallas que necesito. Vía Monky, ella fué a recoger una de ellas. Dijo que pronto me manda las imágenes para hacer pruebas.

Mientras tanto, yo me pongo a desarrollar los imprimibles. Usare un modelo de [grabcad.com/library](grabcad.com/library) para el modelado.

---
He generado las pieazas imprimibles de la máscara.

## 2024-01-26

Imprmí ya la base de las pantallas. Se queda imprimiendo toda la noche el resto de las piezas.

---
Ya quedaron las piezas, se ven bien.

---



## 2024-01-27
### Post Mortem
Fué un día muy apurado! Este fue el día del Live Act. 

Cerca del medio día fui a casa de Monky a probar que el aro de la cabeza tuviera las dimensiones correctas. Aún tenía oportunidad de terminar de imprimir otro.

Estuve haciendo las pruebas de las imagenes. Descubrí que solo caben 24 imágenes de 320x240 en cada pantalla. Aúnque las redimensione con el [Resizer](https://github.com/hugoescalpelo/python-utilities/tree/main/Resizer) que hice o las comprima con [MassImageCompressor](https://sourceforge.net/projects/icompress/), Nextion Editor las importa en el formato de la pantalla y cada imagen pesa alrededor de 150 KB.

Se tuvieron que truncar las imágenes para que cada pantalla tenga 24 de ellas. Para esta etapa dieron las 14h.

Luego estuve realizando el programa para seguir las instrucciones de secuencias y los tiempos entre imagenes. El resultado se puede ver en la documentación del directorio [Nextion](https://github.com/hugoescalpelo/Exp4nd1ng-P3rs0n4l/tree/main/Nextion#secuencia-personalizada).

Es importante que luego de configurar todo como se explica en ese documento, se importe el archivo TFT a la tarjeta de memoria como lo indican las instrucciones de la [secuencia simple](https://github.com/hugoescalpelo/Exp4nd1ng-P3rs0n4l/tree/main/Nextion#configuraci%C3%B3n-de-imagenes-en-secuencia).

Los archivos TFT no están en este repositorio ya que incluyen actualizaciones de firmware de cada pantalla y el formato del programa en curso, por lo que es conveniente sacarlos del programa. Ya habían dado las 15h.

Armé la estructura y soldé las terminales de energía. Terminé cerca de las 17h.

Llevé la máscara a Faro Cosmos y expliqué su uso a Monky. Terminamos cerca de las 17:30h.

El Live Act sucedió a las 18h.

## 2024-02-07

Actualicé el repositorio y el Journal.

Quedo en espera de material de registro para vincular en este repositorio. En el futuro haré una nota en [hugoescalpelo.com](hugoescalpelo.com)