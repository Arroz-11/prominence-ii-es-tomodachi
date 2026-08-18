---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Ensambladora Molecular
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# La Ensambladora Molecular

<BlockImage id="molecular_assembler" scale="8" />

La ensambladora molecular toma los objetos que se le introducen y lleva a cabo la operación definida por un <ItemLink id="pattern_provider" /> adyacente, o el <ItemLink id="crafting_pattern" />, <ItemLink id="smithing_table_pattern" /> o <ItemLink id="stonecutting_pattern" /> insertado, y luego empuja el resultado a los inventarios adyacentes.

Esta ensambladora tiene un patrón de crafteo que especifica la receta de 1 tronco de roble = 4 tablones de roble. Cuando se introducen troncos de roble en la tolva superior, la ensambladora craftea y escupe tablones de roble en la tolva inferior.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/standalone_assembler.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## El Uso Principal de la Ensambladora Molecular

Sin embargo, su uso principal es junto a un <ItemLink id="pattern_provider" />. Los proveedores de patrones tienen un comportamiento especial en este caso, y enviarán información sobre el patrón relevante junto con los ingredientes a las ensambladoras adyacentes. Dado que las ensambladoras expulsan automáticamente los resultados de los crafteos a los inventarios adyacentes (y por lo tanto a las ranuras de retorno del proveedor de patrones), una ensambladora en un proveedor de patrones es todo lo que se necesita para automatizar los patrones de crafteo.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Mejoras

La Ensambladora Molecular admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="speed_card" />

## Receta

<RecipeFor id="molecular_assembler" />

## Nota

Optifine rompe la función de "empujar a inventarios adyacentes", por lo que la mayoría de las configuraciones de crafteo con ensambladoras no funcionarán.