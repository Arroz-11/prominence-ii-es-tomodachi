---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Export Bus
  icon: export_bus
  position: 220
categories:
- devices
item_ids:
- ae2:export_bus
---

# El Export Bus

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/export_bus.snbt" />
</GameScene>

El export bus extrae objetos y fluidos (y cualquier otra cosa, según los addons) del [almacenamiento de red](../ae2-mechanics/import-export-storage.md)
y los empuja hacia el inventario que está tocando.

Para reducir la lag, si el export bus no ha exportado algo recientemente, entra en una especie de
"modo de suspensión" donde opera lentamente, y se despierta y acelera a toda velocidad (4 operaciones por segundo) cuando exporta algo con éxito.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

## Filtrado

Por defecto, el bus no exporta nada. Los objetos insertados en sus ranuras de filtro actuarán como una lista blanca,
permitiendo que esos objetos específicos sean exportados.

Los objetos y fluidos se pueden arrastrar a las ranuras desde JEI/REI incluso si no tienes ninguno de esos objetos.

Haz clic derecho con un contenedor de fluidos (como un balde o tanque de fluido) para configurar ese fluido como filtro en lugar del balde o el tanque.

## Mejoras

El import bus admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="capacity_card" /> aumenta la cantidad de ranuras de filtro y agrega una opción para configurar el orden de exportación de lo filtrado.
*   <ItemLink id="speed_card" /> aumenta la cantidad de objetos movidos por operación.
*   <ItemLink id="fuzzy_card" /> permite que el bus filtre por nivel de daño y/o ignore el NBT del objeto.
*   <ItemLink id="crafting_card" /> permite que el bus envíe solicitudes de crafteo a tu sistema de [autocrafteo](../ae2-mechanics/autocrafting.md)
    para obtener los objetos que desea. Se puede configurar para extraer los objetos del almacenamiento si es posible, o para siempre solicitar
    que se craftee un objeto nuevo.
*   <ItemLink id="redstone_card" /> agrega control de redstone, permitiendo activación con señal alta, señal baja, o una vez por pulso.

## Velocidades

| Tarjetas de aceleración | Objetos movidos por operación |
|:------------------------|:------------------------------|
| 0                       | 1                             |
| 1                       | 8                             |
| 2                       | 32                            |
| 3                       | 64                            |
| 4                       | 96                            |

## Receta

<RecipeFor id="import_bus" />
