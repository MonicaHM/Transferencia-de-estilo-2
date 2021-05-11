# Transferencia de estilo
Este proyecto permite fusionar el contenido de una imagen con el estilo de otra.

![](https://drive.google.com/uc?export=view&id=1MtFF2GyrCyy4ipTP3jGCY4qUGFBtsASV)

Dentro de este proyecto podrás encontrar dos métodos para la transferencia de estilo: 
1. Construir una nueva red neuronal a partir de una ya pre-entrenada.
2. Utilizar una red neuronal entrenada del repositorio TensorFlow Hub.

# Tabla de contenido

- [Conozca la teoría detrás del proyecto](#Conozca-la-teoría-detrás-del-proyecto)
- [Obtenga el proyecto](#Obtenga-el-proyecto)
  * [Descargue el proyecto](#Descargue-el-proyecto)
  * [Copie el proyecto a Google Colab](#Copie-el-proyecto-a-Google-Colab)
- [Realice los pasos esenciales](#Realice-los-pasos-esenciales)
  * [Cargue las librerías](#Cargue-las-librerías)
  * [Cargue la imagen contenido y la imagen estilo](#Cargue-la-imagen-contenido-y-la-imagen-estilo)
- [Realice la transferencia de estilo con una red neuronal de resultados modificables](#Realice-la-transferencia-de-estilo-con-una-red-neuronal-de-resultados-modificables)
  * [Obtenga resultados por pasos](#Obtenga-resultados-por-pasos)
  * [Obtenga resultados por épocas](#Obtenga-resultados-por-épocas)
- [Realice la transferencia de estilo con una red predeterminada de TensorFlow Hub](#realice-la-transferencia-de-estilo-con-una-red-predeterminada-de-tensorflow-hub)

# Conozca la teoría detrás del proyecto
Las redes neuronales convolucionales utilizan el aprendizaje supervisado para el entrenamiento de sus capas. Estas capas se dividen en capa de entrada, capa oculta y capa de salida. Dentro de las capas ocultas existe la siguiente jerarquía:

![](https://drive.google.com/uc?export=view&id=1yfGqdGSRmyYIKh6vl40_i2XfYp16T5bI)

Tomando en cuenta la jerarquía anterior, se ha demostrado que, las capas ocultas que se encuentran a partir del nivel medio se encargan de detectar el estilo de la imagen. Por lo tanto, si se requiere realizar la transferencia de estilo será necesario seleccionar una capa oculta de nivel medio, para que así sea utilizada como un extractor de estilo.

# Obtenga el proyecto
GitHub permite la obtención del proyecto tanto para su ejecución local como en la nube. A continuación, se mostrarán los pasos a seguir para cada opción.

### Descargue el proyecto para ejecución local
Si desea ejecutar el proyecto con algún editor de Python tal como [Spyder](https://www.spyder-ide.org) o [Jupyter](https://jupyter.org) será necesario descargar el proyecto, ya sea como ZIP o clonándolo desde la consola.

#### Descargue como ZIP
Para obtener el archivo ZIP siga los siguientes pasos.

1. Visite la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Dé clic en el botón **Code**.
3. Dé clic en **Download ZIP**.

![](https://drive.google.com/uc?export=view&id=1USlcekIzozaNN5SWAZamfl0BtCSOSH4g)

#### Clone el repositorio desde línea de comando (vía HTTPS)
Para clonar el repositorio desde la consola de comandos de Windows siga los siguientes pasos.

1. Copie el [URL](https://github.com/MonicaHM/Transferencia-de-estilo.git) del repositorio.
2. Abra una consola de comando y vaya a la ubicación en donde quiera clonar el repositorio.
3. Escriba `git clone` y pegue la URL que copio anteriormente.

![](https://drive.google.com/uc?export=view&id=1JjlCfzNT--Av7xJQwTN6ZmSuHWivArSi)

4. Dé **Enter** y espere a que termine de clonarse el repositorio.

![](https://drive.google.com/uc?export=view&id=1paI-pzf8uO7rG5e6mCBUqcq1D4VgJvEq)




### Copie el proyecto a Google Colab para su ejecución en la nube
**Importante**. Para poder utilizar esta opción es necesario que posea una cuenta de Google.

1. Visite la página principal de [Google Colab](https://colab.research.google.com/).
2. Inicie sesión con su cuenta de Google.
3. Dé clic en la pestaña **GitHub**.
4. Pegue el [URL](https://github.com/MonicaHM/Transferencia-de-estilo) del repositorio.
5. Dé **Enter** o clic en <img align="float" width="15" height="15" src="https://cdn2.iconfinder.com/data/icons/ios-7-icons/50/search-512.png"> para buscar el repositorio.
6. Dé clic en el nombre del archivo de python **Vision_17_StyleTransfer.ipynb**.

![](https://drive.google.com/uc?export=view&id=1qYRuMZAU2hzN-q42NX-nKoM4JxOBu4U4)

**Nota**. Si desea modificar el código será necesario guardar una copia en su Drive, por ello:

1. Dé clic en **Archivo**
2. Dé clic en **Guardar una copia en Drive** 

También podrá descargar el código dando clic en **Descargar .ipynb** o **Descargar .py**.

![](https://drive.google.com/uc?export=view&id=18gvCLVFUC__iCyH0bU_v4-tJl6wUt8TQ)

# Realice los pasos esenciales

## Cargue las librerías

Las librerías se encuentran dentro de la sección **1.Librerías**, es indispensable ejecutar esta sección para evitar futuros errores.

![](https://drive.google.com/uc?export=view&id=1PP49lqkMvNFefadTXcLI-r27HL-nV67n)

## Cargue la imagen contenido y la imagen estilo
Para realizar la transferencia de estilo es necesario tener una imagen contenido y una imagen estilo. Por ello, se ofrece la opción de utilizar las imágenes ejemplo de la base de datos de Tensor Flow, sin embargo, también se tiene la opción de utilizar las imágenes de su preferencia. A continuación, se mostrarán los pasos a seguir para cada alternativa. 

**Importante**. Para evitar errores ejecute primero las secciones **1. Librerías** y **2.1 Funciones necesarias**.

### Cargue imágenes predeterminadas

Las imágenes predeterminadas se encuentran dentro de las sección **2.2 Cargar imágenes predeterminadas**. Al ejecutar esta sección se mostrarán las siguientes imágenes:

![](https://drive.google.com/uc?export=view&id=1EZBIiee1tXQY8HqTBP5Grdi2uB8Xda1W)

### Cargue imágenes propias
**Nota**. Si desea utilizar imágenes de su preferencia será necesario tenerlas guardadas con anterioridad dentro de su ordenador.

1. Dé clic en <img align="float" width="15" height="15" src="https://img.icons8.com/metro/452/folder-invoices.png"> de la barra lateral.
2. Arrastre desde su **Explorador de archivo** las imágenes que desea utilizar como imagen contenido e imagen estilo.

![](https://drive.google.com/uc?export=view&id=1XhUXpYI7R7wzMWS5kDK47LmMC6PaaO9-)

3. Sustituye dentro de la función `load_img`, de las variables `content_image` y `style_image`, el nombre y extensión de la imagen que desea utilizar. Estas líneas de código las puede encontrar dentro de la sección **2.3 Cargar imágenes propias**.

```python
content_image = load_img('ImgContenido.SuExtención')
style_image = load_img('ImgEstilo.SuExtención')
```

4. Ejecute la celda para cargar sus imágenes.

![](https://drive.google.com/uc?export=view&id=1WNuPwztC21Gl0_OlwlCJJPMfan3B1rLc)


# Realice la transferencia de estilo con una red neuronal de resultados modificables
**Importante**. Es necesario importar las librerías, cargar imagen contenido e imagen estilo y, ejecutar la sección **3. Primer método**.

## Obtenga resultados por pasos
La sección **4.1 Transferencia de estilos por pasos** nos da una imagen procesada con el número de pasos que nosotros programemos. Por ejemplo el código:
```python
train_step(image)
train_step(image)
train_step(image)
```
Significa que la imagen contenido fue procesada tres veces a través de la red neuronal.

![](https://drive.google.com/uc?export=view&id=1QFOslfcYqMbLl3YJqr2QughV5RxqmYvL)

## Obtenga resultados por épocas
La sección **4.2 Transferencia de estilos por épocas** nos da una imagen procesada con `steps_per_epoch` número de pasos y  `epochs` número de épocas que nosotros programemos. Por ejemplo:
```python
epochs = 10
steps_per_epoch = 100
```
Significa que la imagen contenido fue procesada durante 10 épocas y cada época constó de 100 pasos.
![](https://drive.google.com/uc?export=view&id=1BH1RQ3ctUKY0YthbC3AN4R5D5D4D6amy)


# Realice la transferencia de estilo con una red predeterminada de TensorFlow Hub
**Importante**. Es necesario mportar las librerías y, cargar la imagen contenido e imagen estilo.

Para este segundo método se carga una red neuronal del repositorio de TensorFlow Hub. Para obtener la imagen procesada solo es necesario ejecutar la sección **5. Segundo método: TensorFlow Hub**.

**Nota**. No es posible modificar ningún parámetro de la red neuronal, únicamente se puede obtener la imagen resultante.

![](https://drive.google.com/uc?export=view&id=1tJhTGE_kdDa0ssRY0J9BHrJF22F7UImy)










