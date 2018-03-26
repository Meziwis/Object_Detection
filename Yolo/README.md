## Intro



Pequeña guía para intalar YOLO en windows.

Lee más acerca de Yolo (en darknet)y descarga weight files [Aquí](http://pjreddie.com/darknet/yolo/). En caso de que el archivo no pueda ser encontrado subí los mios [aquí](https://drive.google.com/drive/folders/0B1tW_VtY7onidEwyQ2FtQVplWEU), los que incluyen `yolo-full` y `yolo-tiny` de v1.0, `tiny-yolo-v1.1` de v1.1 y `yolo`, `tiny-yolo-voc` de v2.


Haz click en la imagen para ver el demo de yolov2:

[![img](preview.png)](http://i.imgur.com/EyZZKAA.gif)

## Requerimientos

[Anaconda](https://www.anaconda.com/download/#windows), tensorflow abre anaconda  prompt y escribe "pip install tensorflow", opencv 3 al igual que tensorflow en anaconda prompt escribir "pip install opencv-python", por ultimo necesitamos Cython de la misma forma anterior "pip install cython".

Ahora descargaremos el repostorio original  desde [aquí](https://github.com/thtrieu/darkflow), deben descargarlo en su pc y extraerlo en algun lugar comodo.

Luego desde el anaconda prompt naveguen hasta donde dejaron el archivo:
tips: cd "nombre de capeta" (esto ira a la carpeta que nombren)
      cd .. (ira al directorio superior)
      dir (muestra las capetas a las que pueden ir con cd)
      Si apretan Tab, rellena el nombre de las carpetas

Una vez lleguen a la carpeta pueden elegir uno  de los siguientes tres metodos para instalar:


1. Solo armar las extenciones de Cython en el lugar. NOTA: Si instalas de esta forma tendras que usar el comando`./flow` más adelante en vez de solo `flow`.
    ```
    python3 setup.py build_ext --inplace
    ```

2. Deja que pip instale darkflow globalmente en modo desarrollador (los cambios en el codigo toman efecto inmediato (propenso a bugs))
    ```
    pip install -e .
    ```

3. Instalar de forma global (recomendado)
    ```
    pip install .
    ```
    
    
Para finalizar dentro de la carpeta que descargaron creen una carpeta llamada "bin" y ahí pongan las weights que bajaron de la pagina, sientance libres de bajar cualquiera, pero para este turorial usaremos     

## Update

**Android demo on Tensorflow's** [here](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/examples/android/src/org/tensorflow/demo/TensorFlowYoloDetector.java)

**Buen tutorial youtube:**
 - https://www.youtube.com/watch?v=PyjBd7IDYZs&list=PLX-LrBk6h3wSGvuTnxB2Kj358XfctL4BM

**YOLO v3**

-https://www.youtube.com/watch?time_continue=28&v=MPU2HistivI
 

## Demo

Para ese demo utilizaremos un video, realmente no importa cual así que dejare eso a su libre elección. Dicho video debe ser guardado dentro de la carpeta que descargamos previamente.

Luego ejecutamos el siguiente comando:

    ```
    python flow --model cfg/yolo.cfg --load bin/yolo.weights --demo videofile.mp4 --gpu 1.0 --saveVideo
    ```
Donde videofile.mp4 es el video  yolo.cfg es el modelo que utilizaremos yolo.weights es el archivo que descargaron desde la pagina oficial. Por ultimo saveVideo guardara el video nuevo con las cajas.


## Creditos

Creditos a  [https://github.com/thtrieu](https://github.com/thtrieu). Por haber portado el algoritmo a tensorflow.
