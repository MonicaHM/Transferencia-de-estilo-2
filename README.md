# Transferencia de estilo
En este proyecto podrás encontrar el código en python **Vision_17_StyleTransfer**, el cual tiene como objetivo fusionar el contenido de una imagen con el estilo de otra (Imagen 1)

| ![](https://drive.google.com/uc?export=view&id=1MtFF2GyrCyy4ipTP3jGCY4qUGFBtsASV) | 
|:--:| 
| *Imagen 1: Transferencia de estilo* |

En el código de este proyecto se podrá encontrar dos formas de obtener la transferencia de estilo: 
1. El primer método es construir una nueva red neuronal a partir de una red neuronal pre-entrenada.
2. El segundo método es utilizar una red neuronal entrenada del repositorio TensorFlow Hub.

**Importante.** En esta guia de ususario se utilizará el ambiente de **Google Colab** para los ejemplos visuales. 

# Tabla de contenido

- [Conozca la teoría detrás del proyecto](#Conozca-la-teoría-detrás-del-proyecto)
- [Obtenga el proyecto](#Obtenga-el-proyecto)
  * [Descargue el proyecto para ejecución local](#Descargue-el-proyecto-para-ejecución-local)
    + [Descargue como ZIP](#Descargue-como-ZIP)
    + [Clone el repositorio desde línea de comando](#Clone-el-repositorio-desde-línea-de-comando)
  * [Copie el proyecto directamente a Google Colab para ejecución en la nube](#Copie-el-proyecto-directamente-a-Google-Colab-para-ejecución-en-la-nube)
- [Realice los pasos escenciales del proyecto](#Realice-los-pasos-escenciales-del-proyecto)
  * [Cargue las librerías necesarias](#Cargue-las-librerías-necesarias)
  * [Cargue la imagen contenido y la imagen estilo](#Cargue-la-imagen-contenido-y-la-imagen-estilo)
    + [Cargue imágenes predeterminadas](#Cargue-imágenes-predeterminadas)
    + [Cargue imágenes propias](#Cargue-imágenes-propias)
- [Realice la transferencia de estilo con el primer método](#Realice-la-transferencia-de-estilo-con-el-primer-método)
  * [Obtenga resultados por pasos](#Obtenga-resultados-por-pasos)
  * [Obtenga resultados por épocas](#Obtenga-resultados-por-épocas)
- [Realice la transferencia de estilo con el segundo método](#Realice-la-transferencia-de-estilo-con-el-segundo-método)

# Conozca la teoría detrás del proyecto
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

# Obtenga el proyecto

## Descargue el proyecto para ejecución local
GitHub nos permite descargar el proyecto completo como un ZIP o clonarlo dentro de nuestra computadora.

### Descargue como ZIP
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**
3. Da clic en **Download ZIP**

![](https://drive.google.com/uc?export=view&id=1USlcekIzozaNN5SWAZamfl0BtCSOSH4g)

### Clone el repositorio desde línea de comando
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

## Copie el proyecto directamente a Google Colab para ejecución en la nube
Para poder completar los siguientes pasos será necesario que posea una cuenta de Google.

1. Visita la página principal de [Google Colab](https://colab.research.google.com/)
2. Inicia sesión con su cuenta de Google, si ya tiene abierta alguna no será necesario este paso.
3. Da clic en la pestaña **GitHub**.
4. Escriba el URL del repositorio. Para conseguir el URL realice los pasos 1, 2 y 3 de la sección [Clona el repositorio desde línea de comando](#Clona-el-repositorio-desde-línea-de-comando)
5. Da **Enter** o clic en <img align="float" width="15" height="15" src="https://cdn2.iconfinder.com/data/icons/ios-7-icons/50/search-512.png"> para buscar el repositorio.
6. Da clic en el nombre del archivo de python **Vision_17_StyleTransfer.ipynb**.

![](https://drive.google.com/uc?export=view&id=1qYRuMZAU2hzN-q42NX-nKoM4JxOBu4U4)

Hasta este punto podrá ejecutar el código sin complicaciones, sin embargo, no podrá realizar ningún cambio. Para poder modificar el código será necesario guardar una copia en su *Drive* si desea ejecutarlo desde Colab o descargarlo a su computadora, para ejecutarlo de forma local. Por ello, realice los siguientes pasos.
1. Da clic en **Archivo**
2. Da clic en **Guardar una copia en Drive** o **Descargar .ipynb** o **Descarga .py** según sea el caso que dessee.

![](https://drive.google.com/uc?export=view&id=18gvCLVFUC__iCyH0bU_v4-tJl6wUt8TQ)

# Realice los pasos escenciales del proyecto

## Cargue las librerías necesarias
Para que la ejecución del código en general no lance errores es importate ejecutar la primera celda de código: **1. Librerías**
![](https://drive.google.com/uc?export=view&id=1PP49lqkMvNFefadTXcLI-r27HL-nV67n)

## Cargue la imagen contenido y la imagen estilo
**Importante**. Para cargar la imagen contenido y la imagen estilo es necesario ejecutar primero las celdas de código **2.1 Funciones necesarias** dentro de la sección **2. Imagen contenido e imagen estilo**.

### Cargue imágenes predeterminadas
Ejecute las celdas dentro de **2.2 Cargar imágenes predeterminadas** y espere a que termine cada una su ejecución. Al final se mostrarán las siguintes imágenes:
![](https://drive.google.com/uc?export=view&id=1EZBIiee1tXQY8HqTBP5Grdi2uB8Xda1W)

### Cargue imágenes propias

1. Da clic en <img align="float" width="15" height="15" src="https://img.icons8.com/metro/452/folder-invoices.png"> de la barra lateral.
2. Arrastra desde su **Explorador de archivo** las imánenes que desea utilizar.

![](https://drive.google.com/uc?export=view&id=1XhUXpYI7R7wzMWS5kDK47LmMC6PaaO9-)

4. Sustituya los nombres de las imágenes en las variables `content_image` y `style_image` dentro de la celda **2.3 Cargar imágenes propias**.

```python
content_image = load_img('SustituyaNombreImgContenido.SuExtención')
style_image = load_img('SustituyaNombreImgEstilo.SuExtención')
```

6. Ejecute la celda y espere a que finalice para que muestre sus imágenes.

![](https://drive.google.com/uc?export=view&id=1WNuPwztC21Gl0_OlwlCJJPMfan3B1rLc)


# Realice la transferencia de estilo con el primer método.
**Importante**. Para poder obtener resultados es necesario:
+ Haber importado las librerias.
+ Haber cargado la imagen contenido e imagen estilo.
+ Haber ejecutado las celdas de código dentro de las seccion **3. Primer método**.

La función `train_step(image)` pasa la imágen de entrada una vez a través de la red neuronal.
La función `tensor_to_image(image)` nos ayuda a imprimir el tensor que contiene la imágen resultante.

## Obtenga resultados por pasos
La celda de código **4.1 Transferencia de estilos por pasos** nos ayuda a obtener una imagen resultante con el número de pasos que nosotros programemos. Por ejemplo:
```python
train_step(image)
train_step(image)
train_step(image)
```
Significa que la imagen de contenido fue procesada tres veces a través de la red neuronal.
![](https://drive.google.com/uc?export=view&id=1QFOslfcYqMbLl3YJqr2QughV5RxqmYvL)

## Obtenga resultados por épocas
La celda de código **4.2 Transferencia de estilos por épocas** nos ayuda a obtener una imagen resultante con el número de pasos `steps_per_epoch` por epocas `epochs` que nosotros programemos. Por ejemplo:
```python
epochs = 10
steps_per_epoch = 100
```
Significa que la imagen de contenido fue procesada por 10 épocas y cada época consta de 100 pasos, danto un total de 1,000 pasos de entrenamiento.
![](https://drive.google.com/uc?export=view&id=1BH1RQ3ctUKY0YthbC3AN4R5D5D4D6amy)


# Realice la transferencia de estilo con el segundo método
**Importante**. Para poder obtener resultados es necesario:
+ Haber importado las librerias.
+ Haber cargado la imagen contenido e imagen estilo.

Para este segundo método se carga un red neuronal del repositorio de TensorFlow Hub, por ello no se puede modificar la red neuronal. Para obtener la imagen resultante solo es necesario ejecutar la celda de la sección **5. Segundo método: TensorFlow Hub** y esperar a que finalice.

![](https://drive.google.com/uc?export=view&id=1tJhTGE_kdDa0ssRY0J9BHrJF22F7UImy)










