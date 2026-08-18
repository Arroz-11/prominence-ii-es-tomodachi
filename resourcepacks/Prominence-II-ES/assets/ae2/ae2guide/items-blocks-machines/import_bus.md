---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Bus de Importación ME
  icon: import_bus
  position: 220
categories:
- devices
item_ids:
- ae2:import_bus
---

# El Bus de Importación

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/import_bus.snbt" />
</GameScene>

El bus de importación extrae objetos y fluidos (y cualquier otra cosa, según los addons) del inventario que está tocando y los empuja hacia
[el almacenamiento de la red](../ae2-mechanics/import-export-storage.md).

Para reducir el lag, si el bus de importación no ha importado algo recientemente, entra en una especie de
"modo de suspensión" donde opera lentamente, y se despierta y acelera a velocidad completa (4 operaciones por segundo) cuando importa algo con éxito.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

## Filtrado

Por defecto, el bus importará cualquier cosa a la que tenga acceso. Los objetos insertados en sus ranuras de filtro actuarán como una lista blanca, permitiendo
solo que esos objetos específicos sean importados.

Los objetos y fluidos pueden arrastrarse a las ranuras desde JEI/REI incluso si no tienes ninguno de esos objetos.

Haz clic derecho con un contenedor de fluidos (como un cubo o tanque de fluidos) para configurar ese fluido como filtro en lugar del cubo o tanque.

## Mejoras

El bus de importación admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="capacity_card" /> aumenta la cantidad de ranuras de filtro
*   <ItemLink id="speed_card" /> aumenta la cantidad de cosas movidas por operación
*   <ItemLink id="fuzzy_card" /> permite que el bus filtre por nivel de daño y/o ignore el NBT del objeto
*   <ItemLink id="inverter_card" /> cambia el filtro de lista blanca a lista negra
*   <ItemLink id="redstone_card" /> añade control de redstone, permitiendo activación con señal alta, señal baja, o una vez por pulso

## Velocidades

| Tarjetas de Aceleración | Objetos movidos por operación |
|:-------------------|:--------------------------|
| 0                  | 1                         |
| 1                  | 8                         |
| 2                  | 32                        |
| 3                  | 64                        |
| 4                  | 96                        |

## Receta

<RecipeFor id="import_bus" />
