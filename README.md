# Transferencia de estilo
Este proyecto tiene como objetivo presentar una red neural que realiza la transferencia de estilo. La transferencia de estilo se logra a partir de dos imágenes: una para el contenido o forma y otra para el estilo o color, creando así, una nueva imagen, tal y como se muestra a continuación:

![](https://drive.google.com/uc?export=view&id=1MtFF2GyrCyy4ipTP3jGCY4qUGFBtsASV)

Dentro de este proyecto podrás encontrar dos métodos para la transferencia de estilo: 
1. Construir una nueva red neuronal a partir de una ya pre-entrenada.
2. Utilizar una red neuronal entrenada del repositorio TensorFlow Hub.

# Tabla de contenido

- [Conozca la teoría detrás del proyecto](#Conozca-la-teoría-detrás-del-proyecto)
- [Obtenga el proyecto](#Obtenga-el-proyecto)
  * [Descargue el proyecto](#Descargue-el-proyecto)
    + [Descargue como ZIP](#Descargue-como-ZIP)
    + [Clone el repositorio desde línea de comando](##clone-el-repositorio-desde-línea-de-comando-vía-https)
  * [Copie el proyecto a Google Colab](#Copie-el-proyecto-a-Google-Colab)
- [Realice los pasos esenciales](#Realice-los-pasos-esenciales)
  * [Cargue las librerías](#Cargue-las-librerías)
  * [Cargue la imagen contenido y la imagen estilo](#Cargue-la-imagen-contenido-y-la-imagen-estilo)
    + [Cargue imágenes predeterminadas](#Cargue-imágenes-predeterminadas)
    + [Cargue imágenes propias](#Cargue-imágenes-propias)
- [Realice la transferencia de estilo con una red neuronal de resultados modificables](#Realice-la-transferencia-de-estilo-con-una-red-neuronal-de-resultados-modificables)
  * [Obtenga resultados por pasos](#Obtenga-resultados-por-pasos)
  * [Obtenga resultados por épocas](#Obtenga-resultados-por-épocas)
- [Realice la transferencia de estilo con una red predeterminada de TensorFlow Hub](#realice-la-transferencia-de-estilo-con-una-red-predeterminada-de-tensorflow-hub)

# Conozca la teoría detrás del proyecto
Las redes neuronales convolucionales utilizan el aprendizaje supervisado para el entrenamiento de sus capas. Estas capas se dividen en: capa de entrada, capa oculta y capa de salida. Dentro de las capas ocultas existe la siguiente jerarquía:

![](https://drive.google.com/uc?export=view&id=1yfGqdGSRmyYIKh6vl40_i2XfYp16T5bI)

Tomando en cuenta la jerarquía presentada en la imagen, se ha demostrado que, las capas ocultas que se encuentran a partir del nivel medio se encargan de detectar el estilo de la imagen. Por lo tanto, si se requiere realizar la transferencia de estilo será necesario seleccionar una capa oculta de nivel medio, para que así, sea posible utilizarla como un extractor de estilo.

# Obtenga el proyecto

## Descargue el proyecto

### Descargue como ZIP
1. Visita la página del [repositorio](https://github.com/MonicaHM/Transferencia-de-estilo).
2. Da clic en el botón **Code**.
3. Da clic en **Download ZIP**.

![](https://drive.google.com/uc?export=view&id=1USlcekIzozaNN5SWAZamfl0BtCSOSH4g)

### Clone el repositorio desde línea de comando (vía HTTPS)
1. Copia el [URL](https://github.com/MonicaHM/Transferencia-de-estilo.git) del repositorio.
2. Abra una consola de comando y vaya a la ubicación en donde quiera clonar el repositorio.
3. Escriba `git clone` y pega la URL que copio anteriormente.

![](https://drive.google.com/uc?export=view&id=1JjlCfzNT--Av7xJQwTN6ZmSuHWivArSi)

4. Da **Enter** y espera a que termine de clonarse el repositorio.

![](https://drive.google.com/uc?export=view&id=1paI-pzf8uO7rG5e6mCBUqcq1D4VgJvEq)

## Copie el proyecto a Google Colab
**Importante**. Es necesario que posea una cuenta de Google.

1. Visita la página principal de [Google Colab](https://colab.research.google.com/).
2. Inicia sesión con su cuenta de Google.
3. Da clic en la pestaña **GitHub**.
4. Pega el [URL](https://github.com/MonicaHM/Transferencia-de-estilo) del repositorio.
5. Da **Enter** o clic en <img align="float" width="15" height="15" src="https://cdn2.iconfinder.com/data/icons/ios-7-icons/50/search-512.png"> para buscar el repositorio.
6. Da clic en el nombre del archivo de python **Vision_17_StyleTransfer.ipynb**.

![](https://drive.google.com/uc?export=view&id=1qYRuMZAU2hzN-q42NX-nKoM4JxOBu4U4)

Si desea modificar el código será necesario guardar una copia en su Drive, por ello:

1. Da clic en **Archivo**
2. Da clic en **Guardar una copia en Drive** 

**Nota**. Podrá descargar el código dando clic en **Descargar .ipynb** o **Descargar .py**.

![](https://drive.google.com/uc?export=view&id=18gvCLVFUC__iCyH0bU_v4-tJl6wUt8TQ)

# Realice los pasos esenciales

## Cargue las librerías

Las librerías se encuentran dentro de la sección **1.Librerías**, es indispensable ejecutar esta sección para evitar futuros errores.

![](https://drive.google.com/uc?export=view&id=1PP49lqkMvNFefadTXcLI-r27HL-nV67n)

## Cargue la imagen contenido y la imagen estilo
**Importante**. Ejecute primero las secciones **1. Librerías** y **2.1 Funciones necesarias**.

### Cargue imágenes predeterminadas

Las imágenes predeterminadas se encuentran dentro de las sección **2.2 Cargar imágenes predeterminadas**. Al ejecutar esta sección se mostrarán las siguientes imágenes:

![](https://drive.google.com/uc?export=view&id=1EZBIiee1tXQY8HqTBP5Grdi2uB8Xda1W)

### Cargue imágenes propias

1. Da clic en <img align="float" width="15" height="15" src="https://img.icons8.com/metro/452/folder-invoices.png"> de la barra lateral.
2. Arrastra desde su **Explorador de archivo** las imágenes que desea utilizar como imagen contenido e imagen estilo.

![](https://drive.google.com/uc?export=view&id=1XhUXpYI7R7wzMWS5kDK47LmMC6PaaO9-)

3. Sustituya dentro de la función `load_img`, de las variables `content_image` y `style_image`, el nombre y extensión de la imagen que desea utilizar. Estas líneas de código las puede encontrar dentro de la sección **2.3 Cargar imágenes propias**.

```python
content_image = load_img('ImgContenido.SuExtención')
style_image = load_img('ImgEstilo.SuExtención')
```

4. Ejecute la celda para cargar sus imágenes.

![](https://drive.google.com/uc?export=view&id=1WNuPwztC21Gl0_OlwlCJJPMfan3B1rLc)


# Realice la transferencia de estilo con una red neuronal de resultados modificables
**Importante**. Es necesario:
+ Importar las librerías.
+ Cargar imagen contenido e imagen estilo.
+ Ejecutar la sección **3. Primer método**.

**Nota**. La función `train_step(image)` procesa la imagen de contenido solo una vez a través de la red neuronal.

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
**Importante**. Es necesario:
+ Importar las librerías.
+ Cargar imagen contenido e imagen estilo.

Para este segundo método se carga una red neuronal del repositorio de TensorFlow Hub. Para obtener la imagen procesada solo es necesario ejecutar la sección **5. Segundo método: TensorFlow Hub**.

**Nota**. No es posible modificar ningún parámetro de la red neuronal, únicamente se puede obtener la imagen resultante.

![](https://drive.google.com/uc?export=view&id=1tJhTGE_kdDa0ssRY0J9BHrJF22F7UImy)










