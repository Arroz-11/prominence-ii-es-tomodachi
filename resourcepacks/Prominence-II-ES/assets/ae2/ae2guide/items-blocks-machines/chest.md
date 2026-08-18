---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Chest
  icon: chest
  position: 210
categories:
- devices
item_ids:
- ae2:chest
---

# El ME Chest

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/chest.snbt" />
</GameScene>

El ME Chest actúa como una mini red con una <ItemLink id="terminal" />, una <ItemLink id="drive" /> y un <ItemLink id="energy_acceptor" />.
Aunque puede usarse como una pequeña red de almacenamiento, su capacidad para una sola [celda de almacenamiento](../items-blocks-machines/storage_cells.md)
significa que tiene utilidad limitada como tal.

En cambio, es útil para interactuar específicamente con la celda de almacenamiento montada en su interior. Su terminal integrada solo puede ver y acceder
a los objetos en la unidad montada, mientras que los [dispositivos](../ae2-mechanics/devices.md) en la red general pueden acceder a objetos en cualquier [almacenamiento de red](../ae2-mechanics/import-export-storage.md),
incluidos los ME Chests.

Tiene 2 GUIs diferentes y está orientado para el transporte de objetos. Interactuar con la terminal superior abre la terminal integrada. Los objetos pueden insertarse en
la celda de almacenamiento montada a través de esta cara, pero no extraerse. Interactuar con cualquier otra cara abre la GUI con la ranura para la celda de almacenamiento
y los ajustes de prioridad. La celda puede insertarse y extraerse solo mediante logística de objetos a través de la cara con la ranura de celda.

Puede rotarse con una <ItemLink id="certus_quartz_wrench" />.

Tiene un pequeño búfer de energía AE, por lo que si no está en una red con una [celda de energía](../items-blocks-machines/energy_cells.md),
insertar o extraer demasiados objetos a la vez puede causar que se apague.

La terminal puede colorearse con un <ItemLink id="color_applicator" />.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/chest_color.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Ajustes

El ME Chest tiene todos los mismos ajustes que una <ItemLink id="terminal" /> o un <ItemLink id="crafting_terminal" />.
Sin embargo, no soporta <ItemLink id="view_cell" />s.

## LEDs de estado de la celda

Las celdas en el chest tienen un LED que muestra su estado:

| Color  | Estado                                                                           |
| :----- | :------------------------------------------------------------------------------- |
| Verde  | Vacío                                                                            |
| Azul   | Tiene algunos contenidos                                                                |
| Naranja | [Tipos](../ae2-mechanics/bytes-and-types.md) llenos, no se pueden añadir nuevos tipos     |
| Rojo    | [Bytes](../ae2-mechanics/bytes-and-types.md) llenos, no se pueden insertar más objetos |
| Negro  | Sin energía o la unidad no tiene [canal](../ae2-mechanics/channels.md)                 |

## Prioridad

Las prioridades pueden establecerse haciendo clic en la llave inglesa en la esquina superior derecha de la GUI de la ranura de celda.
Los objetos que entran a la red comenzarán en el almacenamiento de mayor prioridad como
su primer destino. En el caso de que dos almacenamientos o celdas tengan la misma prioridad,
si uno ya contiene el objeto, preferirán ese almacenamiento sobre cualquier
otro. Cualquier celda [particionada](cell_workbench.md) se tratará como si ya contuviera el objeto
cuando esté en el mismo grupo de prioridad que otros almacenamientos. Los objetos que se eliminan del almacenamiento se
eliminarán del almacenamiento con la prioridad más baja. Este sistema de prioridad significa que a medida que los objetos se insertan y eliminan
del almacenamiento de red, los almacenamientos de mayor prioridad se llenarán y los de menor prioridad se vaciarán.

## Receta

<RecipeFor id="chest" />
