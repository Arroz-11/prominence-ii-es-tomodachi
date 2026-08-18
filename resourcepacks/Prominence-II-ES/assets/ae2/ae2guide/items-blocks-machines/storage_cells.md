---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Celdas de Almacenamiento
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# Celdas de Almacenamiento

<Column>
  <Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

  <Row>
    <ItemImage id="fluid_storage_cell_1k" scale="4" />

    <ItemImage id="fluid_storage_cell_4k" scale="4" />

    <ItemImage id="fluid_storage_cell_16k" scale="4" />

    <ItemImage id="fluid_storage_cell_64k" scale="4" />

    <ItemImage id="fluid_storage_cell_256k" scale="4" />
  </Row>
</Column>

Las Celdas de Almacenamiento son uno de los métodos principales de almacenamiento en Applied Energistics. Se colocan en <ItemLink id="drive" />s
o en <ItemLink id="chest" />s.

Consulta [Bytes y Tipos](../ae2-mechanics/bytes-and-types.md) para una explicación de sus capacidades en bytes y tipos.

Los componentes de almacenamiento se pueden quitar de la carcasa si la celda está vacía, manteniendo presionada la tecla Shift y haciendo clic derecho con la celda en la mano.

## Capacidad de Almacenamiento con Diferente Cantidad de Tipos

El [costo inicial de tipos](../ae2-mechanics/bytes-and-types.md) es tal que una celda que contiene 1 tipo puede almacenar el doble que una celda con los 63 tipos en uso.

| Celda                                     | Capacidad total de la celda con 1 tipo en uso | Capacidad total de la celda con 63 tipos en uso |
| ---------------------------------------- | ----------------------------------------: | ------------------------------------------: |
| <ItemLink id="item_storage_cell_1k" />   |                                     8,128 |                                       4,160 |
| <ItemLink id="item_storage_cell_4k" />   |                                    32,512 |                                      16,640 |
| <ItemLink id="item_storage_cell_16k" />  |                                   130,048 |                                      66,560 |
| <ItemLink id="item_storage_cell_64k" />  |                                   520,192 |                                     266,240 |
| <ItemLink id="item_storage_cell_256k" /> |                                 2,080,768 |                                   1,064,960 |


## Particionado

Las celdas se pueden filtrar para que solo acepten ciertos objetos, similar a cómo se pueden filtrar los <ItemLink id="storage_bus" />ses. Esto se
hace en un <ItemLink id="cell_workbench" />.

Los objetos se pueden arrastrar a las ranuras desde JEI/REI incluso si no tienes ninguno de esos objetos.

## Mejoras

Las celdas de almacenamiento admiten las siguientes [mejoras](upgrade_cards.md), insertadas a través de un <ItemLink id="cell_workbench" />:

*   <ItemLink id="fuzzy_card" /> (no disponible en celdas de fluidos) permite que la celda se divida por nivel de daño y/o ignore el NBT del objeto
*   <ItemLink id="inverter_card" /> cambia el filtro de una lista blanca a una lista negra
*   <ItemLink id="equal_distribution_card" /> asigna la misma cantidad de espacio de bytes de la celda a cada tipo, para que un tipo no pueda llenar toda la celda
*   <ItemLink id="void_card" /> anula los objetos insertados si la celda está llena (o el espacio asignado de ese tipo específico en el
    caso de una tarjeta de distribución equitativa), útil para evitar que las granjas se bloqueen. ¡Ten cuidado al particionar esto!
*   Las celdas portátiles pueden aceptar <ItemLink id="energy_card" /> para aumentar su capacidad de batería

## Coloración

Las celdas portátiles de objetos y fluidos se pueden colorear de manera similar a la armadura de cuero, crafteándolas con tintes.

# Carcasas

Las celdas se pueden hacer con un componente de almacenamiento y una carcasa, o con la receta de la carcasa alrededor de un componente de almacenamiento:

<Row>
  <Recipe id="network/cells/item_storage_cell_1k" />

  <Recipe id="network/cells/item_storage_cell_1k_storage" />
</Row>

Las carcasas por sí solas se craftean así:

<Row>
  <RecipeFor id="item_cell_housing" />

  <RecipeFor id="fluid_cell_housing" />
</Row>

# Componentes de Almacenamiento

Los Componentes de Almacenamiento son el núcleo de todas las celdas de AE2, determinando la capacidad de las celdas. Cada nivel aumenta la capacidad
en 4x y cuesta 3 del nivel anterior.

<Column>
  <Row>
    <RecipeFor id="cell_component_1k" />

    <RecipeFor id="cell_component_4k" />

    <RecipeFor id="cell_component_16k" />
  </Row>

  <Row>
    <RecipeFor id="cell_component_64k" />

    <RecipeFor id="cell_component_256k" />
  </Row>
</Column>

# Celdas de Almacenamiento de Objetos

Las celdas de almacenamiento de objetos pueden contener hasta 63 tipos distintos de objetos y están disponibles en todas las capacidades estándar.

<Column>
  <Row>
    <Recipe id="network/cells/item_storage_cell_1k_storage" />

    <Recipe id="network/cells/item_storage_cell_4k_storage" />

    <Recipe id="network/cells/item_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/item_storage_cell_64k_storage" />

    <Recipe id="network/cells/item_storage_cell_256k_storage" />
  </Row>
</Column>

## Almacenamiento de Objetos Portátil

Estas actúan como un pequeño <ItemLink id="chest" /> en tu bolsillo, o como una especie de mochila. Se pueden cargar en un <ItemLink id="charger" />

A diferencia de las celdas de almacenamiento estándar, estas en realidad *reducen* la capacidad de tipos a medida que aumenta su capacidad de bytes, y tienen la mitad de la
capacidad total de bytes.

Además de las tarjetas de mejora que todas las celdas pueden recibir, estas también aceptan <ItemLink id="energy_card" />s para mejorar sus baterías internas.

<Column>
  <Row>
    <RecipeFor id="portable_item_cell_1k" />

    <RecipeFor id="portable_item_cell_4k" />

    <RecipeFor id="portable_item_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_item_cell_64k" />

    <RecipeFor id="portable_item_cell_256k" />
  </Row>
</Column>

# Celdas de Almacenamiento de Fluidos

Las celdas de almacenamiento de fluidos pueden contener hasta 5 tipos distintos de fluidos y están disponibles en todas las capacidades estándar.

<Column>
  <Row>
    <Recipe id="network/cells/fluid_storage_cell_1k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_4k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/fluid_storage_cell_64k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_256k_storage" />
  </Row>
</Column>

## Almacenamiento de Fluidos Portátil

Estas actúan como un pequeño <ItemLink id="chest" /> en tu bolsillo, o como una especie de mochila. Se pueden cargar en un <ItemLink id="charger" />

A diferencia de las celdas de almacenamiento estándar, estas en realidad *reducen* la capacidad de tipos a medida que aumenta su capacidad de bytes, y tienen la mitad de la
capacidad total de bytes.

Además de las tarjetas de mejora que todas las celdas pueden recibir, estas también aceptan <ItemLink id="energy_card" />s para mejorar sus baterías internas.

<Column>
  <Row>
    <RecipeFor id="portable_fluid_cell_1k" />

    <RecipeFor id="portable_fluid_cell_4k" />

    <RecipeFor id="portable_fluid_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_fluid_cell_64k" />

    <RecipeFor id="portable_fluid_cell_256k" />
  </Row>
</Column>

# Celdas Creativas de Objetos y Fluidos

<Row>
  <ItemImage id="creative_item_cell" scale="2" />

  <ItemImage id="creative_fluid_cell" scale="2" />
</Row>

Las celdas creativas de objetos y fluidos **no proporcionan almacenamiento infinito**. En cambio, actúan como fuentes y sumideros infinitos de cualquier
objeto o fluido para el que las [particiones](cell_workbench.md).
