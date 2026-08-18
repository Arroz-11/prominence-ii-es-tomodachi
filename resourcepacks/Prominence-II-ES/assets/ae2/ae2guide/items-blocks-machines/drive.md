---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Drive
  icon: drive
  position: 210
categories:
- devices
item_ids:
- ae2:drive
---

# El ME Drive

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/drive.snbt" />
</GameScene>

El Drive es el [dispositivo](../ae2-mechanics/devices.md) donde conectas tus [celdas de almacenamiento](storage_cells.md) para usarlas como [almacenamiento de red](../ae2-mechanics/import-export-storage.md). Tiene 10 ranuras, cada una acepta una celda.

Si por alguna razón quieres, puedes insertar y extraer las celdas de su inventario con cualquier logística de objetos como tolvas o buses de AE2.

Se puede rotar con una <ItemLink id="certus_quartz_wrench" />.

## LEDs de Estado de las Celdas

Las celdas en el Drive tienen un LED que muestra su estado:

| Color  | Estado                                                                           |
| :----- | :------------------------------------------------------------------------------- |
| Verde  | Vacío                                                                            |
| Azul   | Tiene algo de contenido                                                                |
| Naranja | [Tipos](../ae2-mechanics/bytes-and-types.md) llenos, no se pueden añadir tipos nuevos     |
| Rojo    | [Bytes](../ae2-mechanics/bytes-and-types.md) llenos, no se pueden insertar más objetos |
| Negro  | Sin energía o el drive no tiene [canal](../ae2-mechanics/channels.md)                 |

## Prioridad

Puedes establecer prioridades haciendo clic en la llave inglesa en la esquina superior derecha de la interfaz.
Los objetos que entran a la red comenzarán en el almacenamiento de mayor prioridad como su primer destino. En el caso de que dos almacenamientos o celdas tengan la misma prioridad, si uno ya contiene el objeto, preferirán ese almacenamiento sobre cualquier otro. Cualquier celda [particionada](cell_workbench.md) se tratará como si ya contuviera el objeto cuando esté en el mismo grupo de prioridad que otros almacenamientos. Los objetos que se eliminan del almacenamiento se eliminarán del almacenamiento con la prioridad más baja. Este sistema de prioridad significa que a medida que los objetos se insertan y eliminan del almacenamiento de red, los almacenamientos de mayor prioridad se llenarán y los de menor prioridad se vaciarán.

## Receta

<RecipeFor id="drive" />
