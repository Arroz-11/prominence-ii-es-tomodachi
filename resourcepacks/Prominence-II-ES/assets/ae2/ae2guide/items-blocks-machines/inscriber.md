---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Prensa
  icon: inscriber
  position: 310
categories:
- machines
item_ids:
- ae2:inscriber
---

# La Prensa

<BlockImage id="inscriber" scale="8" />

La prensa se usa para inscribir circuitos y [procesadores](processors.md) usando [troqueles](presses.md), y para triturar varios objetos en polvo.
Puede aceptar tanto la energía de AE2 (AE) como Energía Forge (E/FE). Puede ser lateral, de modo que insertar objetos desde diferentes lados
los inserta en diferentes ranuras de su inventario. Para facilitar esto, se puede rotar con una <ItemLink id="certus_quartz_wrench" />.
También se puede configurar para empujar los resultados de los crafteos a inventarios adyacentes.

El tamaño del búfer de entrada se puede ajustar. Por ejemplo, si quieres alimentar desde un inventario a una gran variedad de prensas,
quieres un búfer pequeño para que los materiales se distribuyan entre las prensas de manera más óptima (en lugar de que la primera
prensa se llene hasta 64 y el resto esté vacío).

Los 4 troqueles de circuito se usan para craftear [procesadores](processors.md)

<Row>
  <ItemImage id="silicon_press" scale="4" />

  <ItemImage id="logic_processor_press" scale="4" />

  <ItemImage id="calculation_processor_press" scale="4" />

  <ItemImage id="engineering_processor_press" scale="4" />
</Row>

Mientras que el troquel de nombre se puede usar para nombrar bloques similar a un yunque, útil para etiquetar cosas en un <ItemLink id="pattern_access_terminal" />.

<ItemImage id="name_press" scale="4" />

## Ajustes

* La prensa se puede configurar para ser lateral (como se explica abajo) o permitir entradas a cualquier ranura desde cualquier lado, con un filtro interno que decide
    qué va dónde. En modo no lateral, los objetos no se pueden extraer de las ranuras superior e inferior.
* La prensa se puede configurar para empujar objetos a inventarios adyacentes.
* El tamaño del búfer de entrada se puede ajustar; la opción grande es para una prensa independiente que alimentas manualmente, la
opción pequeña es para hacer configuraciones paralelas grandes más viables.

## La GUI y la Lateralidad

Cuando está en modo lateral, la prensa filtra qué va dónde según el lado del que insertes o extraigas.

![GUI de la Prensa](../assets/diagrams/inscriber_gui.png) ![Lados de la Prensa](../assets/diagrams/inscriber_sides.png)

A. **Entrada Superior** accesible a través del lado superior de la prensa (los objetos se pueden empujar y extraer de esta ranura)

B. **Entrada Central** insertada a través de los lados izquierdo, derecho, frontal y trasero de la prensa (los objetos solo se pueden empujar a esta ranura, no extraer)

C. **Entrada Inferior** accesible a través del lado inferior de la prensa (los objetos se pueden empujar y extraer de esta ranura)

D. **Salida** extraída a través de los lados izquierdo, derecho, frontal y trasero de la prensa (los objetos solo se pueden extraer de esta ranura, no empujar)

## Automatización Simple

Como ejemplo, la lateralidad y la rotabilidad significan que puedes semi-automatizar prensas así:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/inscriber_hopper_automation.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

O simplemente canaliza hacia y desde la prensa cuando esté en modo no lateral.

## Mejoras

La prensa admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="speed_card" />

## Receta

<RecipeFor id="inscriber" />
