---
title: 'Encargo Bonus: Mecanizado Molde 3D'
date: 2020-06-17T19:30:08+10:00
draft: false
weight: 9
summary: Documentación del Encargo Bonus sobre el mecanizado CNC del **Modelo 3D** de Grasshoper en Fusion 360°.
---

Para llevar a cabo el mecanizado del molde 3D, realizaremos pasos muy similares a los utilizados en los fresados de los post anteriores. Tales como _"2D Contour"_, _"Adaptative Clearing"_, y _"Parallel"_. 

## Paso a Paso Mecanizado CNC

### Molde 3D

En primer lugar debemos abrir en Fusion 360° el archivo correspondiente.

{{< iframe-fusion-molde3d >}}

###### Este es el molde con los respectivos mecanizados que le haremos:

![Imagen Simple](/img/bonus1/plan.png)

#### 1. Establecer área de trabajo 

###### 1.1. Hacer el bloque de madera:
Para esto vamos a hacer un _"Sketch"_, seleccionamos el plano XY y dibujamos el cuadrado que sea un poco mas grande que la pieza de madera. Extruimos el plano de modo que el respaldo quede completamente contenido en el bloque. Para finalizar este paso, hacemos click derecho en _"Operation"_, luego en _"New Body"_ y para poder ver la figura que quedo en su interior le bajamos la opacidad al stock a un 20%.

![Imagen Simple](/img/bonus1/1.png)


###### 1.2. Definir el límite de trabajo de la máquina:
Aplicamos nuevamente el comando _"Sketch"_, seleccionamos el plano superior del bloque de madera. Después para delimitar el área exacta de trabajo vamos a la barra superior en _"Create"_ y seleccionamos _"Project / Include"_, luego _"Project"_ y le hacemos click al respaldo para que se proyecte en el stock. 

![Imagen Simple](/img/bonus1/2.png)

#### 2. Para comenzar la manufactura

En la parte superior izquierda debemos estar en el espacio de trabajo MANUFACTURE

###### 2.1. Definir máquina, orientación para fabricar y stock:
Primero debemos ir a _"Setup"_, y en la ventana que se abre a mano derecha; elegimos la máquina "Autodesk Generic 3-axis".

En segundo lugar, en _"Operation Type"_ seleccionamos la unidad en la que vamos a operar que se denomina _"Milling"_.

Luego, nos vamos a la pestaña siguiente para definir el _"Stock"_. En donde dice _"Mode"_ elegimos la opción _"From Solid"_ y seleccionamos el bloque de madera.

Después volvemos a la pestaña de _"Setup"_, donde definimos la orientación en la que se moverá la máquina. Para esto en _"Orientation"_ seleccionamos _"Z axis/plane & X axis"_. Después en _"Z axis"_ hacemos click en la cara superior de la plancha para que el eje Z se oriente en dirección vertical. A continuación en _"X axis"_ seleccionamos la arista superior frontal. Posteriormente en _"Stock Point"_ ponemos _"Box Point"_ para definir el punto de origen y elegimos el superior derecho (quedará en la misma arista que la orientación de los planos del programa). Para finalizar, seleccionamos el molde en _"Model"_.

###### 2.2. Adaptative Clearing:
En primer lugar debemos presionar el comando en la barra superior, para retirar la mayor cantidad de madera. Posteriormente en _"Tool"_ seleccionamos la fresa  _"Flat end mill. 6mm de diámetro"_, la cual modificaremos en _"Lenght Below"_ a 40mm para que el holder no choque con el bloque de madera igual que en el post anterior. 

Continuando con el proceso de desvaste, iremos a la pestaña _"Geometry"_ en la ventana que está a mano derecha en donde seleccionaremos el sketch hecho en el paso _1.2._ en _"Machine Boundary"_ y el molde en _"Model"_.


![Imagen Simple](/img/bonus1/3.png)

Luego simularemos las trayectorías por dónde pasará la fresa y removerá toda esa madera de manera bruta, sin una terminación prolija. 

![Imagen Simple](/img/bonus1/4.png)

{{< video-local src="/bonus1/desbaste.mov" >}}

![Imagen Simple](/img/bonus1/mold1.jpg)


###### 2.3. Parallel:
Esta función sirve para darle una terminación más exacta al calado. En la pestaña que se despliega a mano derecha, en la pestaña _"Tool"_ haremos un cambio respecto al paso anterior y seleccionaremos la fresa de punta redonda llamada _"Ball end mill. 6mm de diámetro"_. Posteriormente en _"Geometry"_ haremos lo mismo que en el paso _2.2._. 

![Imagen Simple](/img/bonus1/5.png)

Para finalizar debemos hacer click derecho sobre el comando _"Parallel"_ que acabamos de realizar, lo duplicamos y lo editamos en la pestaña _"Passes"_, específicamente en _"Pass Direction"_ escribimos 90° y 2mm en _"Step Over"_.

![Imagen Simple](/img/bonus1/6.png)

Es importante considerar que tenemos que simular el calado de los _"Passes"_ del eje X e Y al mismo tiempo.

{{< video-local src="/bonus1/parallel.mov" >}}

{{< video-local src="/bonus1/molding.mp4" >}}

![Imagen Simple](/img/bonus1/mold2.jpg)


###### 2.4. 2D Contour:
En último lugar, para poder desprender la figura exacta del bloque de madera aplicaremos el comando _"2D Contour"_ que hicimos en el _Encargo 2_. 

Es importante generar pedacitos de madera que no se mecanicen para que la pieza no se mueva al momento de calarla. Para esto debemos ir a la pestaña _"Geometry"_ en la ventana desplegada a la derecha y luego en _"Tabs"_ poner 6mm de _"Width"_, 3mm de _"Height"_ y 50mm de _"Distance"_. 

![Imagen Simple](/img/bonus1/7.png)

{{< video-local src="/bonus1/contour.mov" >}}

![Imagen Simple](/img/bonus1/mold5.jpg)

![Imagen Simple](/img/bonus1/mold6.jpg)


![Imagen Simple](/img/bonus1/mold8.jpg)

[[Volver Arriba]](#top)



