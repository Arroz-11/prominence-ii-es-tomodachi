---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Fachadas
  icon: facade
  icon_nbt: '{item: "minecraft:stone"}'
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:facade
---

# Fachadas

Las fachadas se pueden usar para hacer que tu base se vea más limpia. Pueden cubrir ambos tamaños de cable y se pueden hacer con muchos
tipos de bloques.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/facades_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Pueden cubrir todos los lados de un cable, pero dejarán que las [subpartes](../ae2-mechanics/cable-subparts.md) y las conexiones de cable
sobresalgan.

<GameScene zoom="6"  interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Sé ingenioso con ellas para mejorar la estética de tu base o crear bloques con diferentes texturas en cada lado.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_3.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Ocultar fachadas

Las fachadas se ocultarán mientras sostengas una <a href="network_tool.md">herramienta de red</a> en cualquiera de tus manos.

Puedes interactuar con los bloques detrás de las fachadas ocultas sin tener que quitarlas primero.

## Receta

Coloca el bloque del que quieras la textura en el medio de 4 <ItemLink id="cable_anchor" />.

![Receta de fachada](../assets/diagrams/facade_recipe.png)
