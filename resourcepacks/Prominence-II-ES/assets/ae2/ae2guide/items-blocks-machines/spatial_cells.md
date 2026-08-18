---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Celdas de Almacenamiento Espacial
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# Celdas de Almacenamiento Espacial

  <Row>
    <ItemImage id="spatial_storage_cell_2" scale="4" />

    <ItemImage id="spatial_storage_cell_16" scale="4" />

    <ItemImage id="spatial_storage_cell_128" scale="4" />
  </Row>

Las Celdas de Almacenamiento Espacial se usan para [almacenar volúmenes físicos de espacio](../ae2-mechanics/spatial-io.md).
Se usan en un <ItemLink id="spatial_io_port" />.

A diferencia de las [Celdas de Almacenamiento](../items-blocks-machines/storage_cells.md), las celdas espaciales no se pueden reformatear.

De nuevo, **NO PUEDES REINICIAR, REFORMATEAR NI REDIMENSIONAR UNA CELDA ESPACIAL DESPUÉS DE HABERLA USADO.** Haz una celda nueva si quieres usar dimensiones diferentes.


## Recetas

  <Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
  </Row>

# Carcasas

Las celdas se pueden hacer con un componente espacial y una carcasa, o con la receta de carcasa alrededor de un componente espacial:

<Row>
  <Recipe id="network/cells/spatial_storage_cell_2_cubed" />

  <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
</Row>

Las carcasas por sí solas se craftean así:

  <RecipeFor id="item_cell_housing" />

# Componentes Espaciales

Los Componentes Espaciales son el núcleo de las celdas de almacenamiento espacial. Cada nivel aumenta las dimensiones del volumen que se puede
almacenar por un factor de 8.

  <Row>
    <RecipeFor id="spatial_cell_component_2" />

    <RecipeFor id="spatial_cell_component_16" />

    <RecipeFor id="spatial_cell_component_128" />
  </Row>