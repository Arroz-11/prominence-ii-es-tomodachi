---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Plano de formación
  icon: formation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:formation_plane
---

# El Plano de formación

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/formation_plane.snbt" />
</GameScene>

El Plano de formación coloca bloques y suelta objetos. Funciona de manera similar a un <ItemLink id="storage_bus" /> de solo inserción,
colocando/soltando cuando los [dispositivos](../ae2-mechanics/devices.md) "almacenan" cosas en él al insertar en el [almacenamiento de red](../ae2-mechanics/import-export-storage.md),
como <ItemLink id="import_bus" />ses y <ItemLink id="interface" />s.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/formation_plane_demonstration.snbt" />
  <IsometricCamera yaw="255" pitch="30" />
</GameScene>

Este [dispositivo](../ae2-mechanics/devices.md) utiliza la mecánica de los buses de almacenamiento en cosas como [subredes de tuberías](../example-setups/pipe-subnet.md),
y puede reemplazar a los buses de almacenamiento en esas configuraciones si quieres soltar objetos/colocar bloques en lugar de transportar objetos.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

**RECUERDA HABILITAR LOS JUGADORES FALSOS EN TU RECLAMACIÓN DE TERRENO**

## Filtrado

Por defecto, el plano colocará/soltará cualquier cosa. Los objetos insertados en sus ranuras de filtro actuarán como una lista blanca, solo
permitiendo que se coloquen esos objetos específicos.

Los objetos y fluidos se pueden arrastrar a las ranuras desde JEI/REI incluso si no tienes ese objeto.

Haz clic derecho con un contenedor de fluidos (como un balde o tanque de fluidos) para establecer ese fluido como filtro en lugar del objeto del balde o tanque.

## Prioridad

Las prioridades se pueden establecer haciendo clic en la llave inglesa en la esquina superior derecha de la GUI.
Los objetos que ingresan a la red comenzarán en el almacenamiento de mayor prioridad.

## Ajustes

*   El plano se puede configurar para colocar bloques en el mundo o soltar objetos

## Mejoras

El plano de formación admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="capacity_card" /> aumenta la cantidad de ranuras de filtro
*   <ItemLink id="fuzzy_card" /> permite que el plano filtre por nivel de daño y/o ignore el NBT del objeto
*   <ItemLink id="inverter_card" /> cambia el filtro de lista blanca a lista negra

## Receta

<RecipeFor id="formation_plane" />
