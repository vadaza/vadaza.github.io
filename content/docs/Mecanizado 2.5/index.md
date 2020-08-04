---
title: 'Encargo 3: Mecanizado 2,5 D'
date: 2020-06-17T19:30:08+10:00
draft: false
weight: 9
summary: Documentación del Encargo 3 sobre el Mecanizado CNC en 2,5 dimensiones de la **"Silla Fresia"** en Fusión 360°.
---

Para este encargo realizamos la técnica de Mecanizado en 2,5 ejes de desplazamiento de la máquina CNC para modelar el respaldo de la **"Silla Fresia"**. 

Tal como indicamos en el encargo anterior, el mecanizado CNC es: _" la técnica de corte en dónde una máquina fresadora trabaja en las tres coordenadas cartesianas, en el eje x e y para realizar dibujos y en el eje z para dar profundidad a las incisiones que se quieren realizar"_. Pero existen distintos tipos de mecanizados según los ejes en que la máquina se desplaza. 

Específicamente en el fresado de 2,5 ejes la máquina va tallando las piezas, esta se puede mover en las coordenadas X, Y y Z pero nunca en las tres al mismo tiempo mientras esté cortando. Vale decir que se desplaza en en Z sólo cuando comienza y termina el fresado y el resto del tiempo se mueve en X e Y (mecanizado en tres dimensiones hay un movimiento coordinado en X, Y y Z). Este tipo de corte se usa mayormente cuando se quiere desbastar una cantidad importante del stock que se interviene y también para hacer figuras sencillas.

A continuación mostraré el paso a paso de como se puede mecanizar un producto en Fusion 360°, específicamente el proceso de la Silla Fresia, que iniciamos el día Martes 14 de Julio en clases. 

## Paso a Paso Mecanizado CNC en 2,5 Dimensiones

### Respaldo Silla Fresia

#### 1. Para abrir la pieza del respaldo en un archivo independiente

###### 1.1. Debemos abrir en Fusion 360° el archivo correspondiente a la **"Silla Fresia"**:

###### iFrame Fusion 360 
{{< iframe-fusion-fresia >}}

###### 1.2. Exportar la pieza del asiento:
Seleccionamos el respaldo, vamos a mano izquierda para hacer click derecho sobre la pestaña _"Bodies"_, donde elegimos la opción _"Create Components from Bodies"_. Luego hacemos click derecho sobre el nuevo componente, pinchamos _"Export"_ y la guardamos en el computador.

![Imagen Simple](/img/imagenesclase5/paso1.png)

#### 2. Establecer área de trabajo 

###### iFrame Fusion 360 

{{< iframe-fusion-fresia-respaldo >}}

En la parte superior izquierda debemos estar en el espacio de trabajo DESIGN.

###### 2.1. Orientar la pieza:
Una vez dentro el archivo que contiene sólo el respaldo, nos debemos preocupar de que esta quede ortogonal y horizontal a los planos del programa a través del comando _"Move"_ y _"Align"_.

![Imagen Simple](/img/imagenesclase5/paso3.2.png)

###### 2.2. Hacer el bloque de madera:
Para esto vamos a hacer un _"Sketch"_ que sea un poco mas grande que la pieza de madera, extruimos el plano de modo que el respaldo quede completamente contenido en el bloque. Para finalizar este paso, hacemos click derecho en _"Operation"_, luego en _"New Body"_ y para poder ver la figura que quedo en su interior le bajamos la opacidad al stock a un 20%.

![Imagen Simple](/img/imagenesclase5/paso3.3.png)


###### 2.3. Definir el límite de trabajo de la máquina:
Aplicamos nuevamente el comando _"Sketch"_, seleccionamos el plano superior del bloque de madera. Después para delimitar el área exacta de trabajo vamos a la barra superior en _"Create"_ y seleccionamos _"Project / Include"_, luego _"Project"_ y le hacemos click al respaldo para que se proyecte en el stock. 

![Imagen Simple](/img/imagenesclase5/paso5.png)

#### 3. Para comenzar la manufactura

En la parte superior izquierda debemos estar en el espacio de trabajo MANUFACTURE

###### 3.1. Definir máquina, orientación para fabricar y stock:
Primero debemos ir a _"Setup"_, y en la ventana que se abre a mano derecha; elegimos la máquina "Autodesk Generic 3-axis".

En segundo lugar, en _"Operation Type"_ seleccionamos la unidad en la que vamos a operar que se denomina _"Milling"_.

Luego, nos vamos a la pestaña siguiente para definir el _"Stock"_. En donde dice _"Mode"_ elegimos la opción _"From Solid"_ y seleccionamos la plancha de terciado.

Después volvemos a la pestaña de _"Setup"_, donde definimos la orientación en la que se moverá la máquina. Para esto en _"Orientation"_ seleccionamos _"Z axis/plane & X axis"_. Después en _"Z axis"_ hacemos click en la cara superior de la plancha para que el eje Z se oriente en dirección vertical. A continuación en _"X axis"_ seleccionamos la arista superior frontal. Posteriormente en _"Stock Point"_ ponemos _"Box Point"_ para definir el punto de origen y elegimos el superior derecho.

Para finalizar, seleccionamos el respaldo en _"Model"_.

![Imagen Simple](/img/imagenesclase5/paso3.4.png)

###### 3.2. Adaptative Clearing:
Este paso también es conocido como "Desvaste" o "Limpieza Adaptativa", ya que remueve el material del bloque, acelerando y optimizando el proceso de la obtención de la superficie del respaldo. 
En primer lugar debemos presionar el comando en la barra superior.

Posteriormente en _"Tool"_ seleccionamos la fresa  _"Flat end mill. 6mm de diámetro"_, la cual modificaremos porque no es lo suficientemente larga para poder hacer el procedimiento, si no lo hacemos el holder chocará en varias ocasiones del mecanizado con el stock. 

Para esto en _"Tool Library"_ haremos click derecho sobre la fresa escogida recientemente y la duplicaremos (así nos quedan ambas al principio de la lista), luego haremos nuevamente click derecho sobre ella e iremos a _"Edit Tool"_ y cambiaremos el nombre en "General Description" a 6MM EDITADA. Después en la siguiente pestaña _"Cutter"_ cambiaremos el número que aparece en la categoría _"Lenght Below Holder"_ a 40mm y le damos OK. Para finalizar debemos ir a la pestaña _"Passes"_ y ponemos 3mm en _"Optimal Load"_.

Continuando con el proceso de desvaste, iremos a la pestaña _"Geometry"_ en la ventana que está a mano derecha en donde seleccionaremos el sketch hecho en el paso _2.3._ en _"Machine Boundary"_ y el respaldo en _"Model"_.

![Imagen Simple](/img/imagenesclase5/paso6.png)

![Imagen Simple](/img/imagenesclase5/paso6.2.png)

Las líneas azules que vemos son todas las trayectorías por dónde pasará la fresa y removerá toda esa madera de manera bruta, sin una terminación prolija. En la simulación a continuación veremos que la fresadora entra en el material desde el centro haciendo una elipse, esto sirve para disminuir el estrés de la máquina. Lo cual se usa mucho para metales y también funciona de manera adecuada en maderas.
{{< video-local src="/imagenesclase5/clearing1.mov" >}}

###### 3.3. Parallel:
Esta función sirve para darle una terminación paralela y continua al calado. En la pestaña que se despliega a mano derecha, en la pestaña _"Tool"_ haremos un cambio respecto al paso anterior y seleccionaremos la fresa de punta redonda llamada _"Ball end mill. 6mm de diámetro"_ la cual modificaremos de la misma forma que la otra fresa en _"Tool Library"_ para que tenga un largo de 40mm. 

![Imagen Simple](/img/imagenesclase5/paso16.png)

Para finalizar en _"Geometry"_ haremos lo mismo que en el paso _3.2.__. 

![Imagen Simple](/img/imagenesclase5/paso7.png)

![Imagen Simple](/img/imagenesclase5/paso7.2.png)

También debemos hacer las trayectorias azules que vemos a lo largo del respaldo en el eje Y para obtener una correcta terminación. Para esto hacemos click derecho sobre el comando _"Parallel"_ que acabamos de realizar, lo duplicamos y lo editamos en la pestaña _"Passes"_, específicamente en _"Pass Direction"_ escribimos 90° y 2mm en _"Step Over"_ (mientras menos milímetros mejor resolución).

![Imagen Simple](/img/imagenesclase5/paso8.png)

Es importante considerar que tenemos que simular el calado de los _"Passes"_ del eje X e Y al mismo tiempo.
![Imagen Simple](/img/imagenesclase5/paso8.2.png)
{{< video-local src="/imagenesclase5/simulacionentera1.mov" >}}
Después de que finalizamos el proceso de desbaste y las trayectorias de terminación del lado frontal del respaldo, debemos hacer el mismo procedimiento pero para la parte trasera y para los lados de esta pieza. Para esto debemos volver a **repetir pasos anteriores**, los cuales indicaré a continuación. 

![Imagen Simple](/img/imagenesclase5/respaldo3.jpg)

#### 2. Establecer área de trabajo 

Volvemos a trabajar al espacio de trabajo DESIGN y repetimos el paso _2.1_ para orientar la pieza.

![Imagen Simple](/img/imagenesclase5/paso10.png)

Luego hacemos el paso _2.3_ en el cual delimitamos el área de desplazamiento de la fresa a través de un sketch.

![Imagen Simple](/img/imagenesclase5/paso10.2.png)


#### 3. Para comenzar la manufactura

Nos movemos al espacio de trabajo MANUFACTURE. 

Posteriormente realizamos el paso _3.1._ que nos sirve para definir la máquina, la orientación para fabricar y el stock. Luego debemos aplicar el paso _3.2._ de _"Adaptative Clearing"_ en dónde nos debemos percatar de continuar usando la fresa editada. 

![Imagen Simple](/img/imagenesclase5/paso12.png)
{{< video-local src="/imagenesclase5/clearing2.mov" >}}
![Imagen Simple](/img/imagenesclase5/respaldo1.jpg)


Por último aplicamos la función _3.3._ _"Parallel"_ en el eje X e Y. 

_(en la simulación hay que realizar los tres pasos juntos)_

{{< video-local src="/imagenesclase5/simulacioncompleta2.mov" >}}

![Imagen Simple](/img/imagenesclase5/paso13.png)

![Imagen Simple](/img/imagenesclase5/respaldo2.jpg)

#### 4. Para finalizar

La terminación del respaldo se hace fuera de la máquina CNC, se deben lijar y pulir todos los lados de la pieza. 

![Imagen Simple](/img/imagenesclase5/pulido.jpg)

![Imagen Simple](/img/imagenesclase5/respaldo4.jpg)

Y luego se hay que unir con la técnica de ensamblaje todas las partes de la **Silla Fresia**.

![Imagen Simple](/img/imagenesclase5/ensamblaje1.jpg)

![Imagen Simple](/img/imagenesclase5/ensamblaje2.jpg)

Reforzando el anclaje y uniendo las piezas que mecanizamos en el post anterior, prensándolas con pegamento. 

![Imagen Simple](/img/imagenesclase5/prensado0.jpg)

![Imagen Simple](/img/imagenesclase5/prensado1.jpg)

![Imagen Simple](/img/imagenesclase5/prensado2.jpg)

Finalmente el modelo de la **Silla Fresia** queda así.

![Imagen Simple](/img/imagenesclase5/final.jpg)

![Imagen Simple](/img/imagenesclase5/final2.jpg)

[[Volver Arriba]](#top)