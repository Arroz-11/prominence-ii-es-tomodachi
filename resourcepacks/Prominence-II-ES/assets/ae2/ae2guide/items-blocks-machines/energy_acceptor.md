---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Conector de Energía
  icon: energy_acceptor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_acceptor
---

# El Conector de Energía

<Row gap="20">
<BlockImage id="energy_acceptor" scale="8" /> 

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
</GameScene>
</Row>

El conector de energía convierte las formas comunes de energía de otros mods técnicos en la forma interna de energía de AE2, AE. Mientras que el <ItemLink id="controller" /> también puede hacer esto, las caras del controlador son valiosas, así que a menudo es mejor usar un conector de energía en su lugar.

Las proporciones para la conversión de Energía Forge y Energía Techreborn son

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

La velocidad de conversión depende completamente de cuánta AE pueda almacenar tu red, por razones que se explican en [esta página](../ae2-mechanics/energy.md).

## Variantes

Los conectores de energía vienen en 2 variantes diferentes: normal y plana/[subparte](../ae2-mechanics/cable-subparts.md). Esto te permite hacer algunas configuraciones más compactas.

Los conectores de energía se pueden intercambiar entre normal y plana en una mesa de crafteo.

## Receta

<RecipeFor id="energy_acceptor" />

<RecipeFor id="cable_energy_acceptor" />