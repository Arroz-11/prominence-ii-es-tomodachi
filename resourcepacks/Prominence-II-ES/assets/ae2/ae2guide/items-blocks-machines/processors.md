---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Procesadores
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# Procesadores

<Row>
  <ItemImage id="logic_processor" scale="4" />

  <ItemImage id="calculation_processor" scale="4" />

  <ItemImage id="engineering_processor" scale="4" />
</Row>

Los procesadores son uno de los ingredientes principales en los [dispositivos](../ae2-mechanics/devices.md) y máquinas de AE2. También son uno de tus primeros
grandes desafíos de automatización. Hay tres tipos de procesadores, hechos con oro, <ItemLink id="certus_quartz_crystal" />,
y diamante respectivamente. Se fabrican usando [prensas](presses.md) en una <ItemLink id="inscriber" />, en un proceso de
varios pasos (generalmente logrado mediante una serie de inscriptoras y tuberías filtradas).

## Pasos de producción

<Column gap="5">
  1.  Reúne/fabrica los ingredientes necesarios: silicio, redstone, oro, <ItemLink id="certus_quartz_crystal" />, diamante.

  <RecipeFor id="silicon" />

  <br />

  2.  Presiona los componentes de circuito impreso necesarios

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3.  Ensamblaje final

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>
