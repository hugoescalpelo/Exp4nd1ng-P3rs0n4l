# Carga de imagenes

Las imágenes deben cargarse por separado a cada pantalla. Las instrucciones se presentan a continuación.

## Preparar las imágenes

Dado que la pantalla seleccionada es el modelo NX3224T024_011, todas las imágenes deben ser de la resolución de la pantalla, la cual es 320x240 pixeles.

Puedes realizar este proceso con cualquier software de tu preferencia. A continuación se presentan las instrucciones para GIMP.

1. Abrir el archivo de imágen.
2. En el menú *Imágen* selecciona la opción *Escalar Imágen*.
3. En el cuadro de dialogo que aparece, escribe una altura de 320 pixeles o una anchura de 240 pixeles. Configura solo una dimensión, de forma tal que no haya ninguna de ellas menor a los valores señalados. Si la imágen tiene una relación de asécto de 4:3 no será necesario recortar la imagen. 
4. Haz clic en *Escalar*.
5. En caso de que la imágen no tenga una proporción 4:3, es necesario recortarla. Para ello, haz clic en el menú *Imágen* y selecciona la opción *Tamaño de lienzo...*
6. Ajusta ambos valores, anchura a 240 y altura a 320 pixeles. Esto mostrará una vista previa de la imagen final.
7. Ajusta la imagen para que se vea como se desea en el area de vista previa del mismo cuadro de dialogo.
8. Haz clic en *Redimensionar*.
9. Exporta la imagen en un directorio conocido haciendo clic en el menú *Archivo* y luego seleccionando la opción *Exportar como*.
10. Selecciona el directorio de exportación, haz clic en *Exportar*.
11. Ahora puedes seleccionar la calidad. Se recomienda dejar esto sin cambios. Haz clic en *Exportar*.

## Configuración de imagenes en secuencia
Este proceso requiere [Nextion Editor](https://nextion.tech/nextion-editor/).

1. Crea un nuevo proyecto. Selecciona el modelo de pantalla NX3224T024_011 y luego una orientación vertical.
2. En el area de trabajo inferior izquierda, selecciona la pestaña *Picture* y agrega las imagenes que necesites haciendo clic en el boton *+*. Nota que cada imágen se le asocia un *ID*, este se usará mas adelante
3. En el area *Toolbox*, en la esquina superior izquierda, haz clic en la herramienta *Picture*. Esto agregará un objeto de imágen "p0" a la pantalla.
4. Selecciona la imagen inicial en el area *Attribute* en la esquina inferior derecha haciendo clic en la opción *pic*. Se desplegará un boton *browse...* con el cual puedes seleccionar una de las imágenes previamente agregadas.
5. Ahora, en el area de *Toolbox* en la esquina superior izquierda, haz clic una vez en la herramienta *Timer* y *Variable*. Podrás ver dichas herramientas agregadas debajo del area de trabajo.
6. Haz clic en el timer agregado en el icono de timer que aparede debajo del area de trabajo y sobre el area Output.
7. En la sección *Event* escribe el siguiente programa.
    ```
    p0.pic=va0.val
    va0.val=va0.val+1
    if(va0.val>1)
    {
    va0.val=0
    }
    ```
    Este programa solo realiza el cambio en secuencia de 2 imagenes. Si quieres agregar mas imágenes, por ejemplo para poner un GIF, cambia el valor de comparación del *if* para que coincida con el *ID* del último frame agregado.
8. En el area *Attribute* en la esquina inferior derecha, configura el valor *tim* para seleccionar el tiempo entre imagenes en milisegundos. El valor minimo compatible con la pantalla NX3224T024_011 es de 50. Para que las imágenes cambien cada segundo escribe 1000.
9. Comprueba que todo está correcto haciendo clic en el botón *Compile* en la barra de herramientas. Deberás ver un mensaje que diga `Compile Successful!` en el area *Output*.
10. Puedes ver una simulación del comportamiento de las imágenes haciendo clic en el boton *debug* de la barra de herramientas.
11. Para enviar el proyecto a una pantalla, necesitas generar un archivo `.tft`. Para ello, haz clic en el menú *File* y selecciona la opción *TFT file output*.
12. Guarda el archivo en la tarjeta microSD. La tarjeta debe ser máximo de 32GB y debe estar en formato FAT32.

## Secuencia personalizada

A continuación puedes ver el código que va en el *timer* para la secuencia personalizada indicada en el [README.md](https://github.com/hugoescalpelo/Exp4nd1ng-P3rs0n4l/tree/main/Imagenes/Resized) de la portada de este repositorio.

```
if(va0.val==0&&va1.val<28)
{
  randset 0,6
  tm0.tim=5000
  p0.pic=rand
  va1.val=va1.val+1
}
if(va1.val==28)
{
  va0.val=1
}
if(va0.val==1&&va1.val<66)
{
  randset 0,23
  tm0.tim=4000
  p0.pic=rand
  va1.val=va1.val+1
}
if(va1.val==66)
{
  va0.val=2
}
if(va0.val==2)
{
  randset 0,23
  tm0.tim=3000
  p0.pic=rand
}
```

Antes de hacer clic en el boton *Compile*, configura la propiedad *tim* en 5000 para que el primer valor de tiempo sea 5 segundos.

**Nota**: Las pantallas Nextion NX3224T024_011 tienen la limitación de que sólo pueden almacenar un programa de 4MB, por lo que se hizo un truncamiento de las 38 imagenes correspondientes por cada pantalla a 24 imágenes. Esto se debe a que aunqué el tamaño en disco de las 38 imágenes originales o comprimidas con [MassImageCompressor](https://sourceforge.net/projects/icompress/) sea mucho menor, *Nextion Editor* las convierte al formato compatible con las pantallas y el tamaño sube a aproximadamente 150.04 KB. En otras palabras, este programa sólo reproducirá 24 imagenes.

## Carga de imágenes a la pantalla
1. Asegurate que la pantalla se encuentra desconectada.
2. Inserta la tarjeta en la pantalla.
3. Enciende la pantalla. Verás un mensaje indicando que se ha comenzado la transferencia de archivos. Espera a que termine. Es muy importante que no interrumpas esta operación ya que podría dañarse el sistema de archivos de la pantalla.
4. Cuando la transferencia haya terminado, desenergiza la pantalla y extrae la memoria.
5. Vuelve a energizar la pantalla. El proeycto creado en Nextion Editor debería desplegarse.