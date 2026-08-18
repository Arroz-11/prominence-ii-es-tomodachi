---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Celdas de Energía
  icon: energy_cell
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_cell
- ae2:dense_energy_cell
- ae2:creative_energy_cell
---

# Celdas de Energía

<Row gap="20">
  <BlockImage id="energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="8" />
</Row>

Las celdas de energía le dan a una red más almacenamiento de [energía](../ae2-mechanics/energy.md). Un poco de buffer de energía ayuda a suavizar los picos en el consumo de energía cuando se insertan o extraen grandes cantidades de ítems, y mayores cantidades de almacenamiento de energía permiten que la red funcione mientras no se está generando energía (como de noche con paneles solares) o manejar el enorme consumo instantáneo de energía del [almacenamiento espacial](../ae2-mechanics/spatial-io.md).

## Barras de llenado

<Row>
<BlockImage id="energy_cell" scale="4" p:fullness="0" />
<BlockImage id="energy_cell" scale="4" p:fullness="1" />
<BlockImage id="energy_cell" scale="4" p:fullness="2" />
<BlockImage id="energy_cell" scale="4" p:fullness="3" />
<BlockImage id="energy_cell" scale="4" p:fullness="4" />
</Row>

Las barras en el costado de una celda corresponden a cuánta energía tiene.

*   0 cuando está por debajo del 25% de carga
*   1 cuando está entre 25% y 50% de carga
*   2 cuando está entre 50% y 75% de carga
*   3 cuando está entre 75% y 99% de carga
*   4 cuando está por encima del 99% de carga

## Tipos de celda

*   La <ItemLink id="energy_cell" /> puede almacenar 200k AE, y solo una debería ser suficiente para la mayoría de los casos de uso, manejando las subidas de energía del uso normal de la red con facilidad.
*   La <ItemLink id="dense_energy_cell" /> puede almacenar 1.6M AE y es para cuando quieres hacer funcionar una red con energía almacenada, o manejar el enorme consumo instantáneo de energía de configuraciones grandes de [almacenamiento espacial](../ae2-mechanics/spatial-io.md).
*   La <ItemLink id="creative_energy_cell" /> es un ítem creativo para pruebas, proporcionando PODER INFINITO o lo que sea.

## Recetas

<Row>
  <RecipeFor id="energy_cell" />

  <RecipeFor id="dense_energy_cell" />
</Row>
