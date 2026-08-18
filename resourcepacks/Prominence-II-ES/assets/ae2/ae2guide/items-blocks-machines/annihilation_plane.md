---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Plano de Aniquilación
  icon: annihilation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:annihilation_plane
---

# El Plano de Aniquilación

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/annihilation_plane.snbt" />
</GameScene>

El Plano de Aniquilación rompe bloques y recoge objetos. Funciona de manera similar a un <ItemLink id="import_bus" />, empujando cosas
hacia el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md). Para que los objetos sean recogidos, deben chocar con la
cara del plano, no recoge en un área.

Los planos de aniquilación pueden ser encantados con cualquier encantamiento de pico, así que sí, puedes poner niveles locos de fortuna en unos pocos y
automatizar el procesamiento de minerales](../example-setups/ore-fortuner.md) si tu modpack lo permite. Además, toque de seda hace lo que
esperarías, eficiencia reduce el costo de energía de romper un bloque, y irrompibilidad da una probabilidad de no usar energía.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

**RECUERDA HABILITAR JUGADORES FALSOS EN TU RECLAMACIÓN DE CHUNK**

## Filtrado

El plano de aniquilación solo romperá un bloque o recogerá un objeto si puede almacenar los objetos resultantes en su red. Esto significa que para filtrarlo, *debes restringir lo que se puede almacenar en su red*, muy probablemente poniéndolo en una [subred](../ae2-mechanics/subnetworks.md). Un <ItemLink id="storage_bus" /> o [celda](../items-blocks-machines/storage_cells.md) puede ser [particionado](cell_workbench.md) para lograr esto.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/annihilation_filtering.snbt" />

  <DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        Filtrado a lo que suelte lo que quieras romper.
  </DiamondAnnotation>

  <DiamondAnnotation pos=".5 0.5 2.5" color="#00ff00">
        Particionado a lo que suelte lo que quieras romper.
  </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

De nuevo, filtra *por los objetos que suelta* así que, por ejemplo, si quieres filtrar la rotura de <ItemLink id="minecraft:amethyst_cluster" />s,
necesitas un plano encantado con toque de seda, de lo contrario cada etapa de crecimiento anterior no suelta nada y así el plano los romperá sin importar
lo que sea, ya que la red siempre puede almacenar "nada".

## Receta

<RecipeFor id="annihilation_plane" />
