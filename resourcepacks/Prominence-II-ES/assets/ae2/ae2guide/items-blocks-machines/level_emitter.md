---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Emisor de Nivel
  icon: level_emitter
  position: 220
categories:
- devices
item_ids:
- ae2:level_emitter
- ae2:energy_level_emitter
---

# El Emisor de Nivel

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/level_emitter.snbt" />
</GameScene>

El Emisor de Nivel emite una señal de redstone dependiendo de la cantidad de un objeto en el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md).

También hay una versión que emite una señal de redstone dependiendo de la [energía](../ae2-mechanics/energy.md) almacenada en tu red.

Los objetos y fluidos se pueden arrastrar a la ranura desde JEI/REI incluso si no tienes ninguno de ese objeto.

Haz clic derecho con un contenedor de fluidos (como un cubo o tanque) para configurar ese fluido como filtro en lugar del cubo o tanque.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

A diferencia de otros [dispositivos](../ae2-mechanics/devices.md), los emisores de nivel *no* requieren un [canal](../ae2-mechanics/channels.md).

## Ajustes

*   El Emisor de Nivel se puede configurar en modo "mayor que/igual a" o "menor que".
*   Cuando se inserta una <ItemLink id="crafting_card" />, se puede configurar para "emitir redstone mientras se craftea el objeto" o "emitir redstone para craftear el objeto".

## Mejoras

El emisor de nivel admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="fuzzy_card" /> permite al emisor filtrar por nivel de daño y/o ignorar el NBT del objeto.
*   <ItemLink id="crafting_card" /> habilita la funcionalidad de crafteo.

## Funcionalidad de Crafteo

Si se inserta una <ItemLink id="crafting_card" />, el emisor cambiará al modo de crafteo.

Esto habilita dos opciones:

La primera opción, "emitir redstone mientras se craftea el objeto", hace que el emisor emita una señal de redstone mientras tu [autocrafteo](../ae2-mechanics/autocrafting.md) esté crafteando algún objeto específico a través de <ItemLink id="pattern_provider" />s. Esto es útil para activar solo configuraciones de automatización que consumen mucha energía mientras realmente se están usando.

La segunda opción, "emitir redstone para craftear el objeto", es extremadamente útil para casos de uso específicos como granjas infinitas y configuraciones de automatización que solo tienen una probabilidad de producir una salida, en lugar de una salida garantizada.
Este ajuste crea un [patrón](patterns.md) virtual para que el [autocrafteo](../ae2-mechanics/autocrafting.md) lo use, para cualquier objeto que esté en la ranura de filtro del emisor.
(Para un funcionamiento correcto, un patrón real para el mismo objeto **no debe existir** en tus <ItemLink id="pattern_provider" />s)

Este "patrón" no define, ni siquiera le importan los ingredientes.
Todo lo que dice es: "Si emites redstone desde este emisor de nivel, el sistema ME recibirá este objeto en algún momento en el futuro cercano o lejano". Esto se usa generalmente para activar y desactivar granjas infinitas que no requieren ingredientes de entrada, o para activar un sistema que maneja recetas recursivas (que el autocrafteo estándar no puede entender) como, por ejemplo, "1 piedra = 2 piedras" si tienes una máquina que duplica piedra.

## Receta

<RecipeFor id="level_emitter" />

<RecipeFor id="energy_level_emitter" />
