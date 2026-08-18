---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Pattern Provider
  icon: pattern_provider
  position: 210
categories:
- devices
item_ids:
- ae2:pattern_provider
- ae2:cable_pattern_provider
---

# El Proveedor de Patrones

<Row gap="20">
<BlockImage id="pattern_provider" scale="8" />
<BlockImage id="pattern_provider" p:push_direction="up" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

Los proveedores de patrones son la forma principal en que tu sistema de [autocrafteo](../ae2-mechanics/autocrafting.md) interactúa con el mundo. Empujan los ingredientes de sus [patrones](patterns.md) a inventarios adyacentes, y se pueden insertar ítems en ellos para insertarlos en la red. A menudo se puede ahorrar un canal canalizando la salida de una máquina de vuelta a un proveedor de patrones cercano (a menudo el que empujó los ingredientes) en lugar de usar un <ItemLink id="import_bus" /> para extraer la salida de la máquina hacia la red.

Cabe destacar que, como empujan los ingredientes directamente desde el [almacenamiento de crafteo](crafting_cpu_multiblock.md#crafting-storage) en una CPU de crafteo, nunca contienen realmente los ingredientes en su inventario, por lo que no puedes extraer de ellos. Tienes que hacer que el proveedor empuje a otro inventario (como un barril) y luego extraer de ahí.

También cabe destacar que el proveedor tiene que empujar TODOS los ingredientes a la vez, no puede empujar lotes parciales. Esto es útil para explotar.

Los proveedores de patrones tienen una interacción especial con las interfaces en [subredes](../ae2-mechanics/subnetworks.md): si la interfaz no está modificada (nada en los espacios de solicitud), el proveedor omitirá la interfaz por completo y empujará directamente al [almacenamiento](../ae2-mechanics/import-export-storage.md) de esa subred, omitiendo la interfaz y no llenándola con lotes de recetas, y lo más importante, no insertando el siguiente lote hasta que haya espacio en la máquina. Esto funciona correctamente con el modo bloqueo, el proveedor monitoreará los espacios de la máquina para los ingredientes, en lugar de los espacios de la interfaz.

Por ejemplo, esta configuración empujará tanto lo que se va a fundir como el combustible directamente a los espacios correspondientes en el horno. Puedes usar esto para proporcionar patrones a múltiples lados de una máquina, o a múltiples máquinas.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Proveedor de Patrones: La variante direccional, usando una llave de cuarzo certificado, con los patrones de procesamiento relevantes.

        ![Patrón de hierro](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) Interfaz: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) Bus de Almacenamiento #1: Filtrado a carbón.
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) Bus de Almacenamiento #2: Filtrado a lista negra de carbón, usando una tarjeta inversora.
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Esta es una ilustración general de cómo proporcionar a múltiples máquinas

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        Interfaz (debe ser plana, no de bloque completo)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        Buses de Almacenamiento
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        Lugares a los que quieres proporcionar patrones
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

Se admiten múltiples proveedores de patrones con patrones idénticos y funcionan en paralelo.

Los proveedores de patrones intentarán distribuir sus lotes en todas sus caras, usando así todas las máquinas conectadas en paralelo.

## Variantes

Los proveedores de patrones vienen en 3 variantes diferentes: normal, direccional y plana/[subparte](../ae2-mechanics/cable-subparts.md). Esto afecta a qué lados específicos empujan los ingredientes, de qué lados reciben ítems y a qué lados proporcionan conexión de red.

*   Los proveedores de patrones normales empujan ingredientes a todos los lados, reciben entradas de todos los lados y, como la mayoría de las máquinas de AE2, actúan como un cable que proporciona conexión de red a todos los lados.

*   Los proveedores de patrones direccionales se crean usando una <ItemLink id="certus_quartz_wrench" /> en un proveedor de patrones normal para cambiar su dirección. Solo empujan ingredientes al lado seleccionado, reciben entradas de todos los lados y, específicamente, no proporcionan conexión de red en el lado seleccionado. Esto les permite empujar a máquinas de AE2 sin conectar redes, si quieres hacer una subred.

*   Los proveedores de patrones planos son [subpartes de cable](../ae2-mechanics/cable-subparts.md), por lo que se pueden colocar varios en el mismo cable, permitiendo configuraciones compactas. Actúan de manera similar al lado seleccionado en un proveedor direccional, proporcionando patrones, recibiendo entradas y **no** proporcionando conexión de red en su cara.

Los proveedores de patrones se pueden intercambiar entre normal y plano en una mesa de crafteo.

## Configuraciones

Los proveedores de patrones tienen varios modos:

*   **Modo Bloquear** evita que el proveedor empuje un nuevo lote de ingredientes si ya hay ingredientes en la máquina.
*   **Bloquear Crafteo** puede bloquear el proveedor bajo varias condiciones de redstone, o hasta que el resultado del crafteo anterior se inserte en ese proveedor de patrones específico.
*   El proveedor se puede mostrar u ocultar en los <ItemLink id="pattern_access_terminal" />.

## Prioridad

Las prioridades se pueden establecer haciendo clic en la llave en la esquina superior derecha de la GUI. En el caso de varios [patrones](patterns.md) para el mismo ítem, los patrones en proveedores con mayor prioridad se usarán sobre los de menor prioridad, a menos que la red no tenga los ingredientes para el patrón de mayor prioridad.

## Un Error Común

Por alguna razón la gente sigue haciendo esto, no entiendo por qué, pero lo pongo aquí para ayudar. (Quizás la gente se equivoca, pensando que un <ItemLink id="export_bus" /> es la única forma de que las cosas salgan de la red, sin saber que los proveedores de patrones también exportan cosas)

Esto no hará lo que quieres que haga. Como se menciona en [cables](cables.md), los cables no son tuberías de ítems, no tienen inventario interno, los proveedores no empujarán hacia ellos.

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_1.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        No es un Alto Horno
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

Como el proveedor no tiene nada a lo que empujar, no podrá funcionar. Todo lo que está haciendo aquí es actuar como un cable, conectando el <ItemLink id="export_bus" /> a la red.

El proveedor tampoco le dirá al <ItemLink id="export_bus" /> qué exportar, el bus de exportación simplemente exportará todo lo que pongas en su filtro.

Lo que esencialmente hemos hecho aquí es esto:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_2.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        No es un Alto Horno
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

Probablemente lo que realmente querrías hacer es esto, donde el proveedor de patrones puede exportar el contenido de sus patrones a la máquina adyacente:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_3.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        No es un Alto Horno
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

## Recetas

<RecipeFor id="pattern_provider" />

<RecipeFor id="cable_pattern_provider" />
