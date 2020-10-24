# Generar melodías con LSTM a partir de archivos MIDI
Articulo IEEE: https://github.com/ryu-ed/Music-and-Genetic-Algorithm/blob/main/Melodias%20MIDI%20IA.pdf
## Redes LSTM
Las redes LSTM o por sus siglas en inglés, Long short term memory; son un tipo de redes neuronales recurrentes que consiste en múltiples puertas y son capaces de aprender a largo plazo debido a su estructura tienen la capacidad de recordar información por periodos largos de tiempo, olvidad información innecesaria y exponer la información dada. 

Este tipo de redes depende mucho de su resultado actual para tomar en cuenta el resultado posterior. Si el resultado actual es menos que el posterior, entonces el posterior no es tomado en cuenta y el programa sigue buscando un resultado actual óptimo. Si no encuentra ninguno, simplemente se queda con el mejor. 

En una neurona LSTM hay tres puertas: puerta de entrada, puerta del olvido y puerta de salida. Estas puertas determinan si se permite o no una nueva entrada. Ya que elimina la información que no es importante o se deja que afecta a la salida en el paso de tiempo actual.  

## Planteamiento del Problema
Los estudiantes de música necesitan un programa que les ayude a inspirarse, para la confección de nuevas melodías. Actualmente solo cuentan con una base de datos, con los sonidos de las teclas de un piano y quieren usar eso como la base del sistema. Por lo que necesitamos una solución apropiada que se pueda aprovechar las notas adquiridas para que pueda complementar el estudio de la música generando automáticamente melodías.

## Experimentación
El experimento fue basado en un blog de towards data science.
Para la experimentación del laboratorio se utilizo la herramienta de Google, Colab. La cual fue aumentada a Colab Pro para la disminución del entrenamiento. 

### Recursos del laboratorio 
El repositorio en classroom donde nos proporcionaban los recursos del proyecto, no fueron utilizados en su totalidad. Ya que muchos de los archivos que nos proporcionaban están en el formato WAV.
Nuestro grupo opto por utilizar archivos con extensión MIDI, ya que estos archivos pueden medir fácilmente los tiempos, las notas, vibratos, etc. Mientras que los demás son solo audios.  
Para el entrenamiento de la data utilizamos canciones de chopin en formato MIDI. Se pueden utilizar cualquier tipo de música siempre y cuando este en formato MIDI. 

**Colab del proyecto: https://github.com/ryu-ed/Music-and-Genetic-Algorithm/blob/main/IA_Music.ipynb** 

**Archivo MIDI para el proyecto: https://github.com/ryu-ed/Music-and-Genetic-Algorithm/blob/main/midi_files.zip**
### Primer Entrenamiento

Dentro de lo explicado en el video del laboratorio 1, el primer entrenamiento fue de 75 clases y cada una de ella tenían una duración de 1h 30 min cada una aproximadamente (a veces menos, a veces más). Al parecer el Colab no puede estar mas de 12h seguidas ejecutándose sin ningún movimiento en el documento. Por consiguiente, el primer entrenamiento fue bajado a 20 clases, las cuales solo 16 lograron salvarse. Por lo que este entrenamiento fue descartado. Ya que no cumplió con las 20 clases. 

Data del Primer Entrenamiento: https://drive.google.com/drive/folders/1ikbxhYkAeLfoIW6OzJWRHzDMwF3f6QB9?usp=sharing

### Segundo Entrenamiento
Durante este entrenamiento se tomó la decisión de pagar por el Google Colab, ya que nos garantiza una mejor GPU, RAM, y espacio en disco. Los resultados fueron notables, cada clase terminaba en 71 segundos. Por consiguiente, se realizó un entrenamiento de 200 para que la data fuera entrenada correctamente. 
Al llegar a la clase 94, notamos que no siguió guardando data. Ya que llego a un estado optimo y todas las clases siguientes eran mayores que la clase 94 y no las tomaba en cuenta. 

Data del Segundo Entrenamiento: https://drive.google.com/drive/folders/1R6_qznNWb18qLg--gA8jYV8U890GeKdq?usp=sharing
PDF con el entrenamiento: https://github.com/ryu-ed/Music-and-Genetic-Algorithm/blob/main/Entrenamiento.pdf
## Conclusión
El segundo entrenamiento funciono, inclusive podemos notar una amplia diferencia en la variedad de notas que se encuentran en las partituras. Este método es lento, pero sin lugar a duda es el más optimo siempre y cuando se tenga con los recursos para realizarlo. 
Esta implementación del LSTM puede entrenar cualquier tipo de melodía. Por ejemplo: las melodías propuestas en el planteamiento del problema pueden pasar a archivos MIDI con algún software de sonido e importar la data para su posterior entrenamiento. 

Audio MIDI de los entrenamientos: https://drive.google.com/drive/folders/1sLaXcKe6wFTqEBck4YKPcRPLuZs0EmoA?usp=sharing
Video de explicación: https://www.youtube.com/watch?v=JrvRdA4jwyM
