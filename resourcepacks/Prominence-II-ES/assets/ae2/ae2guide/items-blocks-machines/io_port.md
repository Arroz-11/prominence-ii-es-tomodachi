---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Puerto de E/S
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# El Puerto de E/S ME

<BlockImage id="io_port" p:powered="true" scale="8" />

El Puerto de E/S te permite llenar o vaciar rápidamente [celdas de almacenamiento](../items-blocks-machines/storage_cells.md) desde o hacia el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md).

Se puede rotar con una <ItemLink id="certus_quartz_wrench" />.

## Ajustes

*   El Puerto de E/S se puede configurar para mover la celda a las ranuras de salida cuando la celda esté vacía, llena o cuando el trabajo esté terminado.
*   Si se inserta una <ItemLink id="redstone_card" />, habrá opciones para varias condiciones de redstone.
*   En el centro de la interfaz, hay una flecha para configurar la dirección de transferencia de objetos: de la celda al [almacenamiento de la red](../ae2-mechanics/import-export-storage.md), o del almacenamiento a la celda.

## Mejoras

El Puerto de E/S admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="speed_card" /> aumenta la cantidad de cosas movidas por operación.
*   <ItemLink id="redstone_card" /> añade control por redstone, permitiendo activación con señal alta, señal baja o una vez por pulso.

## Receta

<RecipeFor id="io_port" />
