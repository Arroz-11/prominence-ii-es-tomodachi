---
navigation:
  parent: example-setups/example-setups-index.md
  title: Granja de Amatista
  icon: minecraft:amethyst_shard
---

# Cultivo de Amatista

Aunque el <ItemLink id="growth_accelerator" /> funciona con la amatista, los métodos habituales de filtrar [brotes de certus](../items-blocks-machines/budding_certus.md)
con un <ItemLink id="annihilation_plane" /> no funcionan con los brotes de amatista. A diferencia de los brotes de certus no maduros, que sueltan
<ItemLink id="certus_quartz_dust" />, los brotes de amatista no maduros no sueltan nada, por lo que un plano de aniquilación siempre los romperá
porque una red siempre puede almacenar "nada".

La forma de solucionarlo es encantar el plano de aniquilación con toque de seda. Entonces los brotes de amatista no maduros *sí* sueltan algo
(los distintos estados de los bloques de brotes físicos), y por tanto se pueden filtrar.

El <ItemLink id="minecraft:amethyst_cluster" /> debe colocarse de nuevo con un <ItemLink id="formation_plane" />, para luego ser
roto de nuevo por un <ItemLink id="annihilation_plane" /> sin toque de seda, con el fin de obtener <ItemLink id="minecraft:amethyst_shard" />s.

Ten en cuenta que debido a la direccionalidad del racimo, debe haber una cara de bloque sólida directamente opuesta al plano de formación.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/amethyst_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 1 1" max="3 2 2">
        (1) Plano de aniquilación #1: Sin GUI que configurar, pero encantado con toque de seda.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1 1" max="2.3 2 2">
        (2) Plano de formación: Filtrado a Racimo de Amatista.
        <ItemImage id="minecraft:amethyst_cluster" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 0.7 1" max="2 1 2">
        (3) Plano de aniquilación #2: Sin GUI que configurar, pero se puede encantar con Fortuna.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="1.3 1 2">
        (4) Bus de almacenamiento #1: Filtrado a Fragmento de Amatista.
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 .7" max="1 1 1">
        (5) Bus de almacenamiento #2: Filtrado a Fragmento de Amatista. Tiene prioridad más alta que tu almacenamiento principal.
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        A la red principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El primer <ItemLink id="annihilation_plane" /> (1) no tiene GUI y no se puede configurar, pero debe estar encantado con toque de seda.
* El <ItemLink id="formation_plane" /> (2) está filtrado a <ItemLink id="minecraft:amethyst_cluster" />.
* El segundo <ItemLink id="annihilation_plane" /> (3) no tiene GUI y no se puede configurar, pero se puede encantar con Fortuna.
* El primer <ItemLink id="storage_bus" /> (4) está filtrado a <ItemLink id="minecraft:amethyst_shard" />.
* El segundo <ItemLink id="storage_bus" /> (5) está filtrado a <ItemLink id="minecraft:amethyst_shard" />, y tiene su
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) establecida más alta que tu almacenamiento principal.

## Cómo Funciona

1. El primer <ItemLink id="annihilation_plane" /> intenta romper lo que tiene delante, pero solo puede romper <ItemLink id="minecraft:amethyst_cluster" />
    porque el único almacenamiento en la subred es el <ItemLink id="formation_plane" />, filtrado a racimo de amatista. Esto solo funciona porque
el plano está encantado con toque de seda, de lo contrario podría romper los brotes no maduros porque no sueltan nada.
2. El <ItemLink id="formation_plane" /> coloca el racimo en el bloque opuesto.
3. El segundo <ItemLink id="annihilation_plane" /> rompe el racimo, produciendo <ItemLink id="minecraft:amethyst_shard" />.
4. El primer <ItemLink id="storage_bus" /> almacena los fragmentos en el barril. Técnicamente no necesita filtro porque lo único
que el segundo plano de aniquilación debería encontrar son racimos completamente crecidos.
5. El segundo <ItemLink id="storage_bus" /> da acceso a la red principal a todos los fragmentos de amatista del barril. Está configurado con
[prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) alta para que los fragmentos de amatista se coloquen preferentemente
en el barril en lugar de en tu almacenamiento principal.
