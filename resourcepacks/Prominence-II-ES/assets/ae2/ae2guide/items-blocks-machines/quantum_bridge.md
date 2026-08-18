---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Puente Cuántico
  icon: quantum_ring
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:quantum_link
- ae2:quantum_ring
---

# El Puente de Red Cuántico

![Un Puente de Red Cuántico formado](../assets/diagrams/quantum_bridge_demonstration.png)

Los Puentes de Red Cuánticos pueden extender una [red](../ae2-mechanics/me-network-connections.md) a distancias infinitas e incluso entre dimensiones.
Pueden transportar 32 canales en total (sin importar cómo se conecten los cables a cada cara), actuando
esencialmente como un [cable denso](cables.md#dense-cable) inalámbrico.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_2.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="6 2 3">
        Un cable imaginario entre los dos extremos
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Ten en cuenta que **ambos lados deben estar cargados en chunks**, por lo que se debe usar un <ItemLink id="spatial_anchor" /> u otro cargador de chunks
si los 2 lados están muy separados.

# Anillo Cuántico

<BlockImage id="quantum_ring" scale="8" />

Ocho de estos bloques colocados alrededor de un <ItemLink id="quantum_link" /> crearán un
Puente de Red Cuántico. Solo los 4 bloques de <ItemLink id="quantum_ring" /> adyacentes a
<ItemLink id="quantum_link" /> aceptarán conexiones de red,
los 4 bloques de las esquinas no pueden conectarse a cables.

## Receta

<RecipeFor id="quantum_ring" />

# Cámara de Enlace Cuántico

<BlockImage id="quantum_link" scale="8" />

Uno de estos bloques rodeado por un <ItemLink id="quantum_ring" />
creará un Puente de Red Cuántico. Este bloque no se conecta a ningún cable y solo se registra
como parte de la red cuando el puente completo está formado.

El inventario de este bloque solo puede contener una única <ItemLink id="quantum_entangled_singularity" /> y es
accesible para la automatización.

## Receta

<RecipeFor id="quantum_link" />
