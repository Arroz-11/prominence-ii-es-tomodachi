---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Bus de Almacenamiento ME
  icon: storage_bus
  position: 220
categories:
- devices
item_ids:
- ae2:storage_bus
---

# El Bus de Almacenamiento

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/storage_bus.snbt" />
</GameScene>

¿Alguna vez quisiste *conservar* tu monstruo de cofres en lugar de reemplazarlo con algo sensato? ¡Te presentamos el Bus de Almacenamiento!

El bus de almacenamiento convierte el inventario que está tocando en [almacenamiento de red](../ae2-mechanics/import-export-storage.md).
Lo hace permitiendo que la red vea el contenido de ese inventario, y empujando y tirando de ese
inventario para satisfacer a los [dispositivos](../ae2-mechanics/devices.md) que empujan y tiran del almacenamiento de red.

Debido a la filosofía de AE2 de mecánicas emergentes a través de la interacción de las funciones de los [dispositivos](../ae2-mechanics/devices.md), no
necesariamente *tienes* que usar un bus de almacenamiento para *almacenamiento*. Usando [subredes](../ae2-mechanics/subnetworks.md)
para hacer que un bus de almacenamiento (o un puñado de buses de almacenamiento) sea el *único* almacenamiento en una red, puedes usarlo como fuente o destino
para la transferencia de objetos. (ver ["subred de tubería"](../example-setups/pipe-subnet.md))

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

## Filtrado

Por defecto, el bus almacenará todo. Los objetos insertados en sus ranuras de filtro actuarán como lista blanca, solo
permitiendo que se almacenen esos objetos específicos.

Los objetos y fluidos se pueden arrastrar a las ranuras desde JEI/REI incluso si no tienes ninguno de ese objeto.

Haz clic derecho con un contenedor de fluido (como un cubo o tanque de fluido) para establecer ese fluido como filtro en lugar del cubo o tanque.

## Prioridad

Las prioridades se pueden establecer haciendo clic en la llave inglesa en la esquina superior derecha de la GUI.
Los objetos que entran a la red comenzarán en el almacenamiento de mayor prioridad como
su primer destino. En el caso de que dos almacenamientos tengan la misma prioridad,
si uno ya contiene el objeto, preferirán ese almacenamiento sobre cualquier
otro. Cualquier almacenamiento filtrado se tratará como si ya contuviera el objeto
cuando esté en el mismo grupo de prioridad que otros almacenamientos. Los objetos que se eliminan del almacenamiento se
eliminarán del almacenamiento con la prioridad más baja. Este sistema de prioridad significa que a medida que los objetos se insertan y eliminan
del almacenamiento de red, los almacenamientos de mayor prioridad se llenarán y los de menor prioridad se vaciarán.

## Ajustes

*   El bus se puede particionar (filtrar) a lo que está actualmente en el inventario adyacente
*   Se puede permitir o no que la red vea los objetos en el inventario adyacente que el bus no puede extraer
    (por ejemplo, un bus de almacenamiento no puede extraer objetos de la ranura de entrada central de un <ItemLink id="inscriber" />)
*   El bus puede filtrar tanto en inserción como en extracción, o solo en inserción
*   El bus puede ser bidireccional, solo inserción o solo extracción

## Mejoras

El bus de almacenamiento admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="capacity_card" /> aumenta la cantidad de ranuras de filtro
*   <ItemLink id="fuzzy_card" /> permite que el bus filtre por nivel de daño y/o ignore el NBT del objeto
*   <ItemLink id="inverter_card" /> cambia el filtro de lista blanca a lista negra
*   <ItemLink id="void_card" /> anula los objetos insertados si el inventario adjunto está lleno, útil para evitar que las granjas se atasquen. ¡Ten cuidado al particionar esto!

## Receta

<RecipeFor id="storage_bus" />
