---
title: 'Encargo 2: Mecanizado CNC'
date: 2020-06-17T19:30:08+10:00
draft: false
weight: 8
summary: Documentación del Encargo 2 sobre el mecanizado CNC de la **"Silla Fresia"** en Fusion 360°.
---

El mecanizado CNC (Control Numérico Computacional), es una técnica de corte en dónde una máquina fresadora trabaja en las tres coordenadas cartesianas, en el eje x e y para realizar dibujos y en el eje z para dar profundidad a las incisiones que se quieren realizar, siendo controlada por un computador mediante números. 

Hay muchos tipos de máquinas que pueden trabajar diversos materiales para poder fabricar, tales como metales, maderas, ya sean MDF, melamina, terciado como también las que se denominan nobles. 

A continuación veremos el mecanizado sobre una plancha de terciado de madera. Es importante distinguir que va fijada en el router con tornillos para evitar un posible desprendimiento provocado por la vibración que se produce al momento de cortar. La máquina actúa sobre ella gracias a su cabezal parecido a un taladro, el cual va recortando (no perforando).

![Imagen Simple](/img/imagenesclase4/fresadora2.png)


_Máquina Fresadora CNC_


A continuación mostraré el paso a paso de como se puede mecanizar un producto en Fusion 360°, específicamente el proceso de la Silla Fresia, que iniciamos el día Martes 14 de Julio en clases. 

## Paso a Paso Mecanizado CNC

### Silla Fresia

En primer lugar debemos abrir en Fusion 360° el archivo correspondiente.

{{< iframe-fusion-fresia >}}

###### Estas son las piezas que fabricaremos, con sus respectivas técnicas de mecanizado:

![Imagen Simple](/img/imagenesclase4/planimetría.png)

#### 1. Disponer las piezas en la plancha de terciado

En la parte superior izquierda debemos estar en el espacio de trabajo DESIGN.

###### 1.1. Definir área de trabajo:

Seleccionando el comando _"Create Sketch"_ vamos a delimitar media plancha de terciado. Desde el punto de origen hacemos un cuadrado y le damos las medidas de 1220mm x 1220mm. Luego extruimos esta plancha en 15mm, como un bloque de madera estándar.

![Imagen Simple](/img/imagenesclase4/paso-1.png)

###### 1.2. Copiar las piezas en la plancha:

En esta etapa utilizamos el comando _"Move Copy"_. Tomamos la pieza que queremos llevar al área de trabajo y luego, en la ventana que se abre a mano derecha, ponemos un check en _"Create Copy"_ y la desplazamos.

{{< video-local src="/imagenesclase4/video-paso1-2.mp4" >}}

###### 1.3. Alinear las piezas con la plancha:

Debemos ingresar al comando _"Modify"_ y luego a la opción _"Align"_. Con ella podremos seleccionar la cara del objeto que queremos ubicar sobre la plancha y después hacemos click en el plano correspondiente a la planta. Finalmente acomodamos la pieza utilizando el comando _"Move"_.

![Imagen Simple](/img/imagenesclase4/paso-4.png)

#### 2. Para comenzar la manufactura
En la parte superior izquierda debemos estar en el espacio de trabajo MANUFACTURE.

###### 2.1. Definir máquina, orientación para fabricar y stock:

Ponemos el comando _"Setup"_ y en la ventana que se abre a mano derecha; elegimos la máquina "Autodesk Generic 3-axis".

![Imagen Simple](/img/imagenesclase4/paso-5.png)

En segundo lugar, en _"Operation Type"_ seleccionamos la unidad en la que vamos a operar que se denomina _"Milling"_.

Luego, nos vamos a la pestaña siguiente para definir el _"Stock"_. En donde dice _"Mode"_ elegimos la opción _"From Solid"_ y seleccionamos la plancha de terciado.

Después volvemos a la pestaña de _"Setup"_, donde definimos la orientación en la que se moverá la máquina. Para esto en _"Orientation"_ seleccionamos _"Z axis/plane & X axis"_. Después en _"Z axis"_ hacemos click en la cara superior de la plancha para que el eje Z se oriente en dirección vertical. A continuación en _"X axis"_ seleccionamos la arista superior frontal. Posteriormente en _"Stock Point"_ ponemos _"Box Point"_ para definir el punto de origen y elegimos el superior izquierdo.

Para finalizar, seleccionamos las piezas que queremos cortar en _"Model"_. Es recomendable apagar la plancha para tener una mejor visualización y les haremos click a cada una de ellas. 

###### 2.2. 2D Contour interior:

Esta es la primera operación del mecanizado. Para esto hacemos click en el comando _"2D Contour"_, nos acercamos a la pieza y elegimos la parte inferior del calado. Después de esto Fusion 360° nos pedirá escoger la fresa que usaremos (en este caso utilizaremos una sola para todos los cortes), la cual será  la _"Flat end mill. 6mm de diámetro"_. Veremos que en el calado aparecerán unas lineas azules que serán la trayectoria que hará la fresa.

El calado que mecanizamos en este paso, sirve para enzamblar las piezas de la silla en el momento del armado. Este no es cuadrado y tiene dos semicículos en cada lado, debido a que la fresa al tener una forma cilíndrica no puede hacer ángulos covexos de 90°.

![Imagen Simple](/img/imagenesclase4/paso-6.png)

{{< video-local src="/imagenesclase4/calado1.mov" >}}

Pero acá hay un problema, una fresa de 6mm no puede calar una placa de 15mm, ya que no quedaría bien el corte y la fresa se gastaría mucho. Para esto debemos hacer click derecho sobre el _"2D Contour"_ que acabamos de crear, luego en _"Editar"_, posteriormente en  _"Passes"_, seleccionamos _"Multiple Depths"_ y en _"Maximum Roughing"_ ponemos 3mm. De esta forma generamos varias líneas azules por donde pasará la fresa haciendo el calado, que sean 5 pasadas como vemos en la imagen a continuación lo que es muy recomendale para todos los materiales (ley que se usa: paso en el eje z sea el 50% de la fresa).

![Imagen Simple](/img/imagenesclase4/paso-8.png)


Para simular el calado ponemos click derecho sobre el _"2D Contour"_ que hicimos. Luego seleccionamos _"Simular"_ y en la ventana que se abrirá a mano derecha le damos check en _"Stock"_ y en _"Transparente"_ (para poder visualizar como se va haciendo el corte).

{{< video-local src="/imagenesclase4/contornointerior.mov" >}}

###### 2.3. 2D Pocket:

Seleccionamos el comando _"2D Pocket"_ y elegimos las caras superiores. 

![Imagen Simple](/img/imagenesclase4/paso-9.png)

Luego, dentro de la ventana que se desplega a mano derecha, nos posicionamos en la pestaña _"Passes"_. Allí seleccionamos _"Multiple Depths"_ y ponemos 3mm en _"Maximum Roughing"_. Todo esto para que generemos multiples trayectorias en donde pueda pasar la fresa y hacer el calado. 

![Imagen Simple](/img/imagenesclase4/paso-9.2.png)

{{< video-local src="/imagenesclase4/pocket.mov" >}}

![Imagen Simple](/img/imagenesclase4/contourinterno.jpg)
###### 2.4. 2D Countour exterior:

Ponemos nuevamente el comando _"2D Contour"_, pero ahora seleccionamos el área exterior de la pieza a cortar y volvemos a editar las trayectorias en la pestaña _"Passes"_, donde seleccionamos _"Multiple Depths"_ y ponemos 3mm en _"Maximum Roughing"_. 

![Imagen Simple](/img/imagenesclase4/paso-10.png)

{{< video-local src="/imagenesclase4/contornoexterior.mov" >}}


###### 2.5. Tabs para fijar la pieza:

Este paso es muy importante ya que si no lo realizamos la pieza que se este mecanizando puede soltarse con la vibración. Para esto iremos al _"2D Contour exterior"_ donde, utilizando el click derecho, seleccionaremos _"Editar"_, _"Geometría"_ y luego en _"Tabs"_ ponemos 6mm de _"Width"_, 3mm de _"Height"_ y 350mm de _"Distance"_. Estos son pedacitos de madera que no se mecanizarán para lograr la fijación de la pieza, los cuales se retirarán posteriormente. 

![Imagen Simple](/img/imagenesclase4/paso-11.png)

{{< video-local src="/imagenesclase4/caladobetas.mov" >}}

![Imagen Simple](/img/imagenesclase4/paso-11.2.png)


###### 2.6. Simular el Setup completo:

Para simular al mismo tiempo todos los cortes que debe realizar la fresadora, ponemos click derecho sobre _"Setups"_, después _"Simular"_ y luego en la ventana que se abre a mano derecha le damos check a _"Toolpath"_. Seleccionamos el modo _"Tail"_, que será el patrón de como la herramienta de corte seguirá su trayectoria.

{{< video-local src="/imagenesclase4/caladosetup.mov" >}}

### Los pasos anteriores se deben aplicar a todas las piezas que queramos cortar. 

Acá les dejo cómo lo apliqué a todas las piezas de la _Silla Fresia_, que se pueden mecanizar en dos dimensiones. 

- En primer lugar, copié y organicé todas las piezas de la silla en la plancha de terciado, estando en el espacio de trabajo de DESIGN.

{{< video-local src="/imagenesclase4/piezasenplancha.MOV" >}}

- Luego, fuí al espacio de trabajo MANUFACTURE, donde en _"Setup"_ definí la máquina, la orientación para fabricar y el stock, tal como se indica anteriormente en el paso _2.1._

![Imagen Simple](/img/imagenesclase4/seleccionpiezas.png)


![Imagen Simple](/img/imagenesclase4/orientacionlista.png)

- Después, llevé a cabo el comando _"2D Contour"_ interno de todas las piezas, al igual que en el paso _2.2._

{{< video-local src="/imagenesclase4/contourinternotodas.mov" >}}

- Posteriormente, proseguí con el comando _"2D Pocket"_, de la misma forma que en el paso _2.3._

{{< video-local src="/imagenesclase4/pocket2.mov" >}}

- Para finalizar, realicé el comando _"2D Contour"_, pero esta vez para los contornos exteriores de las piezas y las corté con los _"Tabs"_, tal como en los pasos _2.4._ y _2.5._.

{{< video-local src="/imagenesclase4/todo.mov" >}}


- Luego simulé todos los cortes como está descrito en el paso _2.6._

{{< video-local src="/imagenesclase4/exterior.MOV" >}}

![Imagen Simple](/img/imagenesclase4/patasenteras.jpg)

### Asiento Fresia

En primer lugar debemos abrir en Fusion 360° el archivo correspondiente.

{{< iframe-fusion-fresia-asiento >}}

#### 1. Disponer las piezas en la plancha de terciado

En la parte superior izquierda debemos estar en el espacio de trabajo DESIGN.

- Hacemos lo mismo que en el paso _1.1._ anteriormente explicado para la **Silla Fresia**. Con la diferencia que esta plancha la extruiremos 9mm.

![Imagen Simple](/img/imagenesclase4/1planchaasiento.png)

#### 2. Para comenzar la manufactura

En la parte superior izquierda debemos estar en el espacio de trabajo MANUFACTURE.

- A continuación, definimos la máquina, la orientación para fabricar y el stock. Tal como lo indica el punto _2.1._ de la **Silla Fresia**.

-  Luego, aplicamos el comando _"2D Contour"_ para hacer el corte del asiento. En este paso también debemos llevar a cabo los cambios corresponientes  en la ventana que se despliega a mano derecha. En la pestaña _"Passes"_ seleccionamos _"Multiple Depths"_ y ponemos 3mm en _"Maximum Roughing"_. 

{{< video-local src="/imagenesclase4/asientoexterior.mov" >}}

- Para finalizar, seleccionamos un nuevo comando llamado _"Trace"_, el cual nos permitirá seleccionar todas las líneas que tiene la pieza del asiento en su superficie. Para luego en la pestaña _"Passes"_ indicar 4,5mm en _"Stock Toleave"_. Esta indicación es para que la fresa pase por los vectores indicados y obtengamos una madera flexible.  

{{< video-local src="/imagenesclase4/trace.mov" >}}

![Imagen Simple](/img/imagenesclase4/asiento1.jpg)

[[Volver Arriba]](#top)


















