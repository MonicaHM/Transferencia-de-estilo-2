# Transferencia de estilo
En este proyecto podrás encontrar el código en python **Vision_17_StyleTransfer**, el cual tiene como objetivo aplicar el estilo de una imagen a otra. Es decir, se busca fusionar el contenido de una imagen con el estilo de otra (Imagen 1)

| ![](https://drive.google.com/uc?export=view&id=1MtFF2GyrCyy4ipTP3jGCY4qUGFBtsASV) | 
|:--:| 
| *Imagen 1: Transferencia de estilo* |

Un ejemplo de lo que se quiere lograr lo podemos encontrar en aplicación para Android [Lucid](https://play.google.com/store/apps/details?id=com.doodle.doodle)

En este código se podrá encontrar dos formas de obtener la transferencia de estilo: 
 + El primer método es entrenar una red neuronal pre-entrenada
 + El segundo método es utilizar una red neuronal entrenada del repositorio TensorFlow Hub.

# Tabla de contenido

- [Teoría detrás de la transferencia de estilo](#teoría-detrás-de-la-transferencia-de-estilo)
- [Obten el proyecto](#Obten-el-proyecto)
  * [Descarga el proyecto para ejecución local](#Descarga-el-proyecto-para-ejecución-local)
    + [Descarga como ZIP](#Descarga-como-ZIP)
    + [Clona el repositorio desde línea de comando](#Clona-el-repositorio-desde-línea-de-comando)
  * [Copia el proyecto directamente a Google Colab](#Copia-el-proyecto-directamente-a-Google-Colab)


- [Abre el código en un IDE](#Abre-el-código-en-un-IDE)
- [Realiza las precionaciones iniciales](#Preparaciones-iniciales)
  * [Carga las librerías necesarias]()
  * [Carga imagen contenido e imagen estilo]()
- [Primer método de transferencia de estilo: terminar de entrenar una red neuronal](#requerimientos-del-sistema)
- [Segundo método de transferencia de estilo: red neuronal de TensorFlow Hub](#requerimientos-del-sistema)

# Teoría detrás de la transferencia de estilo
Las redes neuronales convolucionales (CNN) son redes neuronales de aprendizaje supervisado que realiza su funcionamiento a través de diversas capas. Estas capas están divididas en: 
1. Capa de entrada. Recibe los datos de entrada.
2. Capa oculta. Donde se realiza el procesamiento de los datos.
3. Capa de salida. Proporciona la respuesta de la red neuronal. Por ejemplo, regresa un vector de probabilidades para saber a que clase pertenece la imagen de entrada. 

Dentro de las capas intermedias existe una jerarquía (Imagen 2):
- Las capas ocultas de nivel bajo detectan bordes
- Las capas ocultas de nivel medio detectan esquinas y contornos.
- Las capas ocultas de nivel alto detectan partes de objetos o formas complejas. 

En general, se dice que las capas ocultas se van especializando conforme se van acercando a la capa de salida, pues pasan de detectar simples líneas a detectar siluetas de rostros, objetos o animales. 

| ![](https://drive.google.com/uc?export=view&id=1yfGqdGSRmyYIKh6vl40_i2XfYp16T5bI) | 
|:--:| 
| *Imagen 2: Jerarquía de capas ocultas (filtros)* |

Tomando en cuenta la jerarquía anterior, se ha demostrado que los filtros formados en las capas ocultas que se encuentran a partir del nivel medio contienen el estilo de la imagen. Por lo tanto, la salida de la red neuronal para la transferencia de estilo, no será la capa de salida sino la capa oculta seleccionada como extractor de estilo.

# Obten el proyecto

## Descarga el proyecto para ejecución local
GitHub nos permite descargar el proyecto completo como un ZIP o clonarlo dentro de nuestra computadora.

### Descarga como ZIP
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**
3. Da clic en **Download ZIP**

![](https://drive.google.com/uc?export=view&id=1USlcekIzozaNN5SWAZamfl0BtCSOSH4g)

### Clona el repositorio desde línea de comando
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**
3. Da clic en <img align="float" width="17" height="18" src="https://drive.google.com/uc?export=view&id=1P7XHP3GbYB7UqeBTONCZb_AppmsHbm9J"> de la sección **HTTPS** para copiar la URL del repositorio.

![](https://drive.google.com/uc?export=view&id=1u-uwSE7G1vvK8hWeXB8O7q-uAO9lrcYg)

5. Abre una consola de comando de tu computadora.
6. Cambia el directorio de trabajo actual a la ubicación en donde quieres clonar el repositorio.
7. Escribe 'git clone' y pega la URL que copio anteriormente.

![](https://drive.google.com/uc?export=view&id=1JjlCfzNT--Av7xJQwTN6ZmSuHWivArSi)

9. Da **Enter** para comenzar a crear el clon del repositorio.

![](https://drive.google.com/uc?export=view&id=1paI-pzf8uO7rG5e6mCBUqcq1D4VgJvEq)

## Copia el proyecto directamente a Google Colab










