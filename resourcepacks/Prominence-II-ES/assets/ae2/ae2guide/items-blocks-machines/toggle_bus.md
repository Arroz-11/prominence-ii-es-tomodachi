---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Bus de Alternancia
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# El Bus de Alternancia

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/toggle_bus.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Un bus que funciona de manera similar a <ItemLink id="fluix_glass_cable" /> u otros cables, pero que
permite alternar su estado de conexión mediante redstone. Esto te permite cortar
una sección de una [Red ME](../ae2-mechanics/me-network-connections.md).

Cuando se suministra una señal de redstone, la parte habilita la conexión, <ItemLink id="inverted_toggle_bus" /> proporciona el comportamiento
inverso al deshabilitar la conexión.

Ten en cuenta que alternar estos puede hacer que la red se reinicie y recalcule los dispositivos conectados.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

## Recetas

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />
