# Transferencia de estilo
En este proyecto podrás encontrar el código en Python **Vision_17_StyleTransfer**, el cual tiene como objetivo fusionar el contenido de una imagen con el estilo de otra.

| ![](https://drive.google.com/uc?export=view&id=1MtFF2GyrCyy4ipTP3jGCY4qUGFBtsASV) | 
|:--:| 
| *Imagen 1: Transferencia de estilo* |

En el código se podrá encontrar dos métodos para la transferencia de estilo: 
1. Construir una nueva red neuronal a partir de una red neuronal pre-entrenada.
2. Utilizar una red neuronal entrenada del repositorio TensorFlow Hub.

**Importante.** Para los ejemplos visuales se utilizará el ambiente de **Google Colab**. 

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
Las redes neuronales convolucionales utilizan el aprendizaje supervisado para realizar su funcionamiento a través de capas. Estas capas se dividen en: 
1. Capa de entrada. Recibe los datos de entrada.
2. Capa oculta. Realiza el procesamiento de los datos.
3. Capa de salida. Proporciona la respuesta de la red neuronal.

Dentro de las capas ocultas existe una jerarquía:

| ![](https://drive.google.com/uc?export=view&id=1yfGqdGSRmyYIKh6vl40_i2XfYp16T5bI) | 
|:--:| 
| *Imagen 2: Jerarquía de capas ocultas* |

En general, las capas ocultas se van especializando conforme se van acercando a la capa de salida. Tomando en cuenta la jerarquía anterior, se ha demostrado que en las capas ocultas que se encuentran a partir del nivel medio se encargan de detectar del estilo de la imagen. Por lo tanto, la salida de la red neuronal para la transferencia de estilo, no será la capa de salida sino la capa oculta seleccionada como el extractor de estilo.

# Obtenga el proyecto

## Descargue el proyecto para ejecución local

### Descargue como ZIP
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**.
3. Da clic en **Download ZIP**.

![](https://drive.google.com/uc?export=view&id=1USlcekIzozaNN5SWAZamfl0BtCSOSH4g)

### Clone el repositorio desde línea de comando
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**.
3. Da clic en <img align="float" width="17" height="18" src="https://drive.google.com/uc?export=view&id=1P7XHP3GbYB7UqeBTONCZb_AppmsHbm9J"> de la sección **HTTPS** para copiar la URL del repositorio.

![](https://drive.google.com/uc?export=view&id=1u-uwSE7G1vvK8hWeXB8O7q-uAO9lrcYg)

4. Abra una consola de comando y vaya a la ubicación en donde quiera clonar el repositorio.
5. Escriba `git clone` y pega la URL que copio anteriormente.

![](https://drive.google.com/uc?export=view&id=1JjlCfzNT--Av7xJQwTN6ZmSuHWivArSi)

6. Da **Enter** y espera a que termine de clonarse el repositorio.

![](https://drive.google.com/uc?export=view&id=1paI-pzf8uO7rG5e6mCBUqcq1D4VgJvEq)

## Copie el proyecto directamente a Google Colab para ejecución en la nube
**Importante**. Es necesario que posea una cuenta de Google.

1. Visita la página principal de [Google Colab](https://colab.research.google.com/).
2. Inicia sesión con su cuenta de Google.
3. Da clic en la pestaña **GitHub**.
4. Pega el [URL](https://github.com/MonicaHM/Transferencia-de-estilo) del repositorio.
5. Da **Enter** o clic en <img align="float" width="15" height="15" src="https://cdn2.iconfinder.com/data/icons/ios-7-icons/50/search-512.png"> para buscar el repositorio.
6. Da clic en el nombre del archivo de python **Vision_17_StyleTransfer.ipynb**.

![](https://drive.google.com/uc?export=view&id=1qYRuMZAU2hzN-q42NX-nKoM4JxOBu4U4)

Si desea modificar el código será necesario guardar una copia en su Drive:

1. Da clic en **Archivo**
2. Da clic en **Guardar una copia en Drive** 

**Nota**. Podrá descargar el código para su ejecución local dando clic en **Descargar .ipynb** o **Descargar .py**.

![](https://drive.google.com/uc?export=view&id=18gvCLVFUC__iCyH0bU_v4-tJl6wUt8TQ)

# Realice los pasos escenciales del proyecto

## Cargue las librerías necesarias
Para que la ejecución del código no lance errores es importante ejecutar la sección: **1. Librerías**.

![](https://drive.google.com/uc?export=view&id=1PP49lqkMvNFefadTXcLI-r27HL-nV67n)

## Cargue la imagen contenido y la imagen estilo
**Importante**. Para cargar la imagen contenido y la imagen estilo es necesario ejecutar primero las secciones **1. Librerías** y **2.1 Funciones necesarias**.

### Cargue imágenes predeterminadas
Ejecute la sección **2.2 Cargar imágenes predeterminadas** y espere a que termine su ejecución. Al final se mostrarán las siguientes imágenes:
![](https://drive.google.com/uc?export=view&id=1EZBIiee1tXQY8HqTBP5Grdi2uB8Xda1W)

### Cargue imágenes propias

1. Da clic en <img align="float" width="15" height="15" src="https://img.icons8.com/metro/452/folder-invoices.png"> de la barra lateral.
2. Arrastra desde su **Explorador de archivo** las imánenes que desea utilizar.

![](https://drive.google.com/uc?export=view&id=1XhUXpYI7R7wzMWS5kDK47LmMC6PaaO9-)

3. Sustituya los nombres de las imágenes en las variables `content_image` y `style_image` dentro de la sección **2.3 Cargar imágenes propias**.

```python
content_image = load_img('SustituyaNombreImgContenido.SuExtención')
style_image = load_img('SustituyaNombreImgEstilo.SuExtención')
```

4. Ejecute la celda y espere a que finalice para que muestre sus imágenes.

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










