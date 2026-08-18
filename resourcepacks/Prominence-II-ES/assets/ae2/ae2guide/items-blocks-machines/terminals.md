---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Terminales
  icon: crafting_terminal
  position: 210
categories:
- devices
item_ids:
- ae2:terminal
- ae2:crafting_terminal
- ae2:pattern_encoding_terminal
- ae2:pattern_access_terminal
---

# Terminales

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminals.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Mientras que los <ItemLink id="pattern_provider" />s, los <ItemLink id="import_bus" />ses, los <ItemLink id="storage_bus" />ses y demás
son el método principal por el cual una red de AE2 interactúa con el mundo, los Terminales son el método principal por el cual una red de AE2
interactúa con *tú*. Hay varias variantes con diferentes funciones.

Los terminales heredarán el color del [cable](cables.md) en el que estén montados.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

## Colocación del Terminal

Como un terminal suele ser la primera [subparte](../ae2-mechanics/cable-subparts.md) que alguien coloca,
es común equivocarse y colocar el terminal al revés. Aquí hay un ejemplo de qué hacer y qué no hacer:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminal_placement.snbt" />
  <IsometricCamera yaw="195" pitch="30" />

  <LineAnnotation color="#ff3333" from="2.5 .5 .5" to="4.5 2.5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="2.5 2.5 .5" to="4.5 .5 .5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="-.5 2.5 .5" to="1 .5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1 .5 .5" to="1.5 1 .5" alwaysOnTop={true} thickness="0.05"/>
</GameScene>

Aún tienes un terminal y un aceptador de energía, excepto que ahora el terminal está en la dirección correcta y realmente
conectado a la red, y todo cabe en un espacio más pequeño.

<a name="terminal-ui"></a>

# Terminal

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

Tu terminal básico, que te permite ver y acceder al contenido del [almacenamiento de tu red](../ae2-mechanics/import-export-storage.md)
y solicitar cosas desde tu configuración de [autocrafteo](../ae2-mechanics/autocrafting.md).

## La interfaz

Hay varias secciones en la interfaz de un terminal básico

La sección central te da acceso al almacenamiento de tu red. Puedes poner y sacar cosas. Hay varios
almacenes de acceso rápido de mouse/teclado:

*   Clic izquierdo agarra un stack, clic derecho agarra medio stack.
*   Si un objeto, fluido, etc. se puede [autocraftear](../ae2-mechanics/autocrafting.md),
    lo que tengas vinculado a "seleccionar bloque" (generalmente clic central) abre una interfaz para especificar la cantidad a craftear. También puedes ingresar fórmulas como `3*64/2`,
    o escribir `=32` para craftear solo la cantidad necesaria para llegar a 32 en tu almacenamiento.
*   Mantener presionada la tecla Mayús congelará los objetos mostrados en su lugar, evitando que se reorganicen cuando cambian las cantidades o entran nuevos objetos al sistema.
*   Clic derecho con un balde u otro contenedor de fluidos depositará el fluido, clic izquierdo en un fluido en el terminal con
    un contenedor de fluidos vacío extraerá el fluido.

La sección izquierda tiene botones de configuración para:

*   Ordenar por diferentes atributos como nombre, mod y cantidad
*   Ver almacenado, crafteable o ambos
*   Ver objetos, fluidos o ambos
*   Cambiar el orden de clasificación
*   Abrir la ventana de configuración detallada del terminal
*   Cambiar la altura de la interfaz del terminal

A la derecha hay ranuras para <ItemLink id="view_cell" />s

La parte superior derecha de la sección central (botón de martillo) abre el estado de [autocrafteo](../ae2-mechanics/autocrafting.md)
interfaz, lo que te permite ver el progreso de tus autocrafteos y qué está haciendo cada [CPU de crafteo](crafting_cpu_multiblock.md).

## Receta

<RecipeFor id="terminal" />

<a name="crafting-terminal-ui"></a>

# Terminal de Trabajo

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/crafting_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

El Terminal de Trabajo es similar a un terminal normal, con todas las mismas configuraciones y secciones, pero con una cuadrícula de crafteo adicional que se rellenará automáticamente
desde el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md). ¡Ten cuidado al hacer clic con Mayús en el resultado!

Deberías mejorar tu terminal a un terminal de trabajo lo antes posible.

## La interfaz

El terminal de trabajo tiene la misma interfaz que el terminal normal, pero con una cuadrícula de crafteo adicional en el medio.

Hay 2 botones adicionales, para vaciar la cuadrícula de crafteo en el almacenamiento de la red o en tu inventario.

## Receta

<RecipeFor id="crafting_terminal" />

<a name="pattern-encoding-terminal-ui"></a>

# Terminal de Codificación de Patrones

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_encoding_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

El Terminal de Codificación de Patrones es similar a un terminal normal, con todas las mismas configuraciones y secciones, pero con una interfaz adicional de
codificación de [patrones](patterns.md). Se parece a la interfaz de un terminal de trabajo, pero esta cuadrícula de crafteo no realiza
crafteos reales.

Deberías tener uno de estos además de un terminal de trabajo.

## La interfaz

El terminal de trabajo tiene la misma interfaz que el terminal normal, con la interfaz de codificación de [patrones](patterns.md) añadida.

La interfaz de codificación de patrones tiene varias secciones:

Una ranura para insertar <ItemLink id="blank_pattern" />s.

Una flecha grande para codificar el patrón.

Una ranura para patrones codificados. Coloca un patrón que ya haya sido codificado en esta ranura para editarlo, luego haz clic en la flecha "codificar".

4 pestañas a la derecha para cambiar el tipo de patrón a codificar entre

*   Crafteo
*   Procesamiento
*   Herrería
*   Cortapiedras

La interfaz central cambia según el tipo de patrón a codificar:

*   En modo de crafteo:
    *   Clic izquierdo o arrastra desde JEI/REI los ingredientes para formar la receta. Clic derecho para eliminar el ingrediente.
    *   Habilitar sustituciones permite cosas como craftear palos de cualquier tipo de tabla. Esto solo debe usarse
        cuando sea absolutamente necesario.
    *   Las sustituciones de fluidos permiten usar fluidos almacenados en lugar de baldes de fluidos.
    *   También puedes codificar directamente un patrón desde la pantalla de recetas de JEI/REI.

*   En modo de procesamiento:
    * Clic izquierdo o derecho en o arrastra desde JEI/REI los ingredientes para especificar las entradas y salidas de la receta.
    * Clic derecho con un contenedor de fluidos (como un balde o tanque de fluidos) para establecer ese fluido como ingrediente en lugar del balde o el tanque.
    * Al sostener un stack, clic izquierdo coloca todo el stack, clic derecho coloca un objeto. Clic izquierdo en un stack de ingredientes existente para
        eliminar todo el stack y clic derecho para disminuir el stack en 1. Lo que tengas vinculado a "seleccionar bloque" (generalmente clic central)
        te permite especificar una cantidad precisa del objeto o fluido.
    * Las ranuras de salida tienen una salida principal y espacio para cualquier salida secundaria que quieras que el algoritmo de autocrafteo conozca.
    * Tanto las ranuras de entrada como las de salida se desplazan, por lo que puedes tener 81 ingredientes diferentes y 26 salidas secundarias
    * También puedes codificar directamente un patrón desde la pantalla de recetas de JEI/REI.

*   Las interfaces de modo de herrería y cortapiedras funcionan de manera similar a una mesa de herrería y un cortapiedras, respectivamente.

## Receta

<RecipeFor id="pattern_encoding_terminal" />

<a name="pattern-access-terminal-ui"></a>

# Terminal de Acceso a Patrones

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_access_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

El Terminal de Acceso a Patrones sirve para resolver un problema específico: en una torre densa de <ItemLink id="pattern_provider" />s
y <ItemLink id="molecular_assembler" />s, no puedes acceder físicamente a los proveedores para insertar nuevos patrones. Además,
tal vez eres perezoso y no quieres caminar por tu base para insertar un [patrón](patterns.md). El terminal de acceso a patrones
permite el acceso a todos los proveedores de patrones en la red.

## La interfaz

Este terminal tiene una interfaz diferente a todos los demás terminales.

Tiene configuraciones para la altura del terminal y qué proveedores de patrones mostrar.

Cada fila en el terminal corresponde a un proveedor de patrones específico.

Los proveedores de patrones en el terminal se ordenan por los bloques a los que están conectados, o por el nombre que les hayas dado (en un yunque o
con un <ItemLink id="name_press" />).

## Receta

<RecipeFor id="pattern_access_terminal" />
