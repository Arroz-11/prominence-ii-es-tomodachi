---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Interfaz
  icon: interface
  position: 210
categories:
- devices
item_ids:
- ae2:interface
- ae2:cable_interface
---

# La Interfaz

<Row gap="20">
<BlockImage id="interface" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_interface.snbt" />
</GameScene>
</Row>

Las interfaces actúan como un pequeño cofre y tanque de fluidos que se llena desde y se vacía hacia [el almacenamiento de la red](../ae2-mechanics/import-export-storage.md)
dependiendo de lo que configures para mantener en stock en sus ranuras. Intenta completar esto en un solo gametick, por lo que puede llenarse o
vaciarse hasta 9 stacks por gametick, lo que lo convierte en un método rápido de importación o exportación si tienes tuberías de objetos rápidas.

Otra característica útil es que mientras la mayoría de los tanques de fluidos solo pueden almacenar 1 tipo de fluido, las interfaces pueden almacenar hasta 9, además de objetos.
Son esencialmente cofres/tanques multifluido con funcionalidad extra, y puedes prevenir esa funcionalidad extra manteniéndolas
desconectadas de cualquier red.
Por lo tanto, son útiles en algunos casos específicos donde quieres almacenar una pequeña cantidad de varias cosas diferentes.

## Cómo Funciona una Interfaz Internamente

Como se dijo antes, una interfaz es esencialmente un cofre/tanque con un montón de <ItemLink id="import_bus" />s y
<ItemLink id="export_bus" />s adjuntos, con un montón de <ItemLink id="level_emitter" />s.

<GameScene zoom="3" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_internals.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 0.3 1.3" max="9.7 1 1.7">
        Un montón de emisores de nivel para controlar la cantidad de stock solicitada
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 4 1.3" max="9.7 4.7 1.7">
        Un montón de emisores de nivel para controlar la cantidad de stock solicitada
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 1.3 1.3" max="9.7 2 1.7">
        Un montón de buses de importación súper eficientes que pueden transferir 1 stack por gametick
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/import_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 3 1.3" max="9.7 3.7 1.7">
        Un montón de buses de exportación súper eficientes que pueden transferir 1 stack por gametick
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/export_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="10 3 2">
        9 ranuras internas separadas
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="15" />
</GameScene>

## Interacciones Especiales

Las interfaces también tienen algunas funcionalidades especiales con otros [dispositivos](../ae2-mechanics/devices.md) de AE2:

Un <ItemLink id="storage_bus" /> en una interfaz no configurada presentará la totalidad del [almacenamiento de la red](../ae2-mechanics/import-export-storage.md)
de su red al bus de almacenamiento de la red, como si la red de la interfaz fuera un gran cofre sobre el que se colocó el bus de almacenamiento.
Configurar un objeto para que esté en stock en las ranuras de filtro de la interfaz desactiva esto.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_storage.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Los proveedores de patrones tienen una interacción especial con las interfaces en [subredes](../ae2-mechanics/subnetworks.md): si la interfaz no está configurada,
el proveedor omitirá la interfaz por completo y empujará directamente al [almacenamiento](../ae2-mechanics/import-export-storage.md) de esa subred,
omitiendo la interfaz y no llenándola con lotes de recetas, y más importante, no insertando el siguiente lote hasta que haya espacio en el almacenamiento.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        Interfaz (debe ser plana, no bloque completo)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        Buses de almacenamiento
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        Lugares donde quieres proveer patrones (múltiples máquinas, o múltiples caras de 1 máquina)
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## Variantes

Las interfaces vienen en 2 variantes diferentes: normal y plana/[subparte](../ae2-mechanics/cable-subparts.md). Esto afecta desde qué lados específicos se puede acceder a sus inventarios
y que proporcionan una conexión de red.

*   Las interfaces normales permiten que las cosas empujen, extraigan y accedan a su inventario desde todos los lados y, como la mayoría de las máquinas de AE2, actúan
    como un cable que proporciona conexión de red a todos los lados.

*   Las interfaces planas son [subpartes de cable](../ae2-mechanics/cable-subparts.md), por lo que se pueden colocar varias en el mismo cable, permitiendo configuraciones compactas.
    Permiten que las cosas empujen, extraigan y accedan a su inventario desde su cara, pero no proporcionan conexión de red en su cara.

Las interfaces se pueden intercambiar entre normal y plana en una mesa de crafteo.

## Ajustes

Las ranuras superiores en la interfaz determinan lo que la interfaz está configurada para mantener en stock dentro de sí misma. Cuando se coloca algo en
ellas o se arrastra desde JEI/REI, aparece una llave inglesa que te permite configurar la cantidad.

Haz clic derecho con un contenedor de fluidos (como un cubo o tanque de fluidos) para configurar ese fluido como filtro en lugar del cubo o tanque.

## Mejoras

La interfaz admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="fuzzy_card" /> permite que el bus filtre por nivel de daño y/o ignore el NBT del objeto
*   <ItemLink id="crafting_card" /> permite que la interfaz envíe solicitudes de crafteo a tu sistema de [autocrafteo](../ae2-mechanics/autocrafting.md)
    para obtener los objetos que desea. Extraerá los objetos del almacenamiento si es posible, antes de hacer una solicitud
    para que se craftee un nuevo objeto.

## Prioridad

Las prioridades se pueden configurar haciendo clic en la llave inglesa en la esquina superior derecha de la GUI. Las interfaces con mayor prioridad obtendrán sus objetos
antes que aquellas con menor prioridad.

## Recetas

<Recipe id="network/blocks/interfaces_interface" />

<RecipeFor id="cable_interface" />
