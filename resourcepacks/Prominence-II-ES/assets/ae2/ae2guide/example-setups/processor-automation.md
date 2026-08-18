---
navigation:
  parent: example-setups/example-setups-index.md
  title: Automatización de Procesadores
  icon: inscriber
---

# Automatización de la Producción de Procesadores

Hay muchas formas de automatizar [procesadores](../items-blocks-machines/processors.md), y esta es una de ellas.

Este diseño general se puede hacer con cualquier tipo de tubería o conducto de logística de objetos o lo que el mod llame, siempre que puedas filtrarlo.

![El Diagrama de Flujo del Proceso](../assets/diagrams/processor_flow_diagram.png)

Aquí se detalla cómo hacerlo solo con AE2, usando [subredes de "tubería"](pipe-subnet.md).

Nota: como esto usa un <ItemLink id="pattern_provider" />, está pensado para integrarse en tu configuración de [autocrafteo](../ae2-mechanics/autocrafting.md). Si solo quieres automatizar un procesador de forma independiente, reemplaza el proveedor de patrones con otro barril y pon los ingredientes directamente en el barril superior.

Esto resulta ser compatible con versiones anteriores de AE2, porque incluso si los <ItemLink id="inscriber" />s están orientados, las subredes de tubería aún insertan y extraen de las caras correctas.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/processor_automation.snbt" />

  <BoxAnnotation color="#dddddd" min="5 1 0" max="6 2 1" thickness=".05">
        (1) Proveedor de Patrones: En su configuración predeterminada, con los patrones de procesamiento relevantes.

        <Row>
            ![Patrón de Lógica](../assets/diagrams/logic_pattern_small.png)
            ![Patrón de Cálculo](../assets/diagrams/calculation_pattern_small.png)
            ![Patrón de Ingeniería](../assets/diagrams/engineering_pattern_small.png)
        </Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4.7 2 0" max="5 3 1" thickness=".05">
        (2) Bus de Almacenamiento #1: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 0" max="4.3 2 1" thickness=".05">
        (3) Bus de Exportación #1: Filtrado a Silicio, tiene 2 Tarjetas de Aceleración
        <Row><ItemImage id="silicon" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 4 0" max="4.3 3 1" thickness=".05">
        (4) Bus de Exportación #2: Filtrado a Lingote de Oro, tiene 2 Tarjetas de Aceleración
        <Row><ItemImage id="minecraft:gold_ingot" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 5 0" max="4.3 4 1" thickness=".05">
        (5) Bus de Exportación #3: Filtrado a Cristal de Cuarzo Certus, tiene 2 Tarjetas de Aceleración
        <Row><ItemImage id="certus_quartz_crystal" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 6 0" max="4.3 5 1" thickness=".05">
        (6) Bus de Exportación #4: Filtrado a Diamante, tiene 2 Tarjetas de Aceleración
        <Row><ItemImage id="minecraft:diamond" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 3 0" max="2 2 1" thickness=".05">
        (7) Bus de Exportación #5: Filtrado a Polvo de Redstone, tiene 2 Tarjetas de Aceleración
        <Row><ItemImage id="minecraft:redstone" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 0" max="3 2 1" thickness=".05">
        (8) Prensa #1: En su configuración predeterminada. Tiene un Molde de Silicio y 4 Tarjetas de Aceleración
        <Row><ItemImage id="silicon_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 3 0" max="3 4 1" thickness=".05">
        (9) Prensa #2: En su configuración predeterminada. Tiene un Molde de Lógica y 4 Tarjetas de Aceleración
        <Row><ItemImage id="logic_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 4 0" max="3 5 1" thickness=".05">
        (10) Prensa #3: En su configuración predeterminada. Tiene un Molde de Cálculo y 4 Tarjetas de Aceleración
        <Row><ItemImage id="calculation_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 5 0" max="3 6 1" thickness=".05">
        (11) Prensa #4: En su configuración predeterminada. Tiene un Molde de Ingeniería y 4 Tarjetas de Aceleración
        <Row><ItemImage id="engineering_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 2 0" max="1 3 1" thickness=".05">
        (12) Prensa #5: En su configuración predeterminada. Tiene 4 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 2 0" max="3 1 1" thickness=".05">
        (13) Bus de Importación #1: En su configuración predeterminada, tiene 2 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 4 0" max="3 3 1" thickness=".05">
        (14) Bus de Importación #2: En su configuración predeterminada, tiene 2 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 5 0" max="3 4 1" thickness=".05">
        (15) Bus de Importación #3: En su configuración predeterminada, tiene 2 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 6 0" max="3 5 1" thickness=".05">
        (16) Bus de Importación #4: En su configuración predeterminada, tiene 2 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 3 0" max="1 3.3 1" thickness=".05">
        (17) Bus de Almacenamiento #2: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1.7 0" max="1 2 1" thickness=".05">
        (18) Bus de Almacenamiento #3: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 0" max="0.7 3 1" thickness=".05">
        (19) Bus de Importación #5: En su configuración predeterminada, tiene 2 Tarjetas de Aceleración
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="5 0.7 0" max="6 1 1" thickness=".05">
        (20) Bus de Almacenamiento #4: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.3 2.7 0.3" max="3.7 3 0.7" thickness=".05">
        La Fibra de Cuarzo alimenta las 3 prensas porque las prensas actúan como cables y transmiten energía
  </BoxAnnotation>

<DiamondAnnotation pos="7 1.5 0.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="185" pitch="5" />
</GameScene>

## Configuraciones

* El <ItemLink id="pattern_provider" /> (1) está en su configuración predeterminada, con los <ItemLink id="processing_pattern" />s relevantes.

  ![Patrón de Lógica](../assets/diagrams/logic_pattern.png)
  ![Patrón de Cálculo](../assets/diagrams/calculation_pattern.png)
  ![Patrón de Ingeniería](../assets/diagrams/engineering_pattern.png)

* Los <ItemLink id="storage_bus" />ses (2, 17, 18, 20) están en su configuración predeterminada.
* Los <ItemLink id="export_bus" />ses (3-7) están filtrados al ingrediente relevante. Tienen 2 <ItemLink id="speed_card" />s.
    <Row>
      <ItemImage id="silicon" scale="2" />
      <ItemImage id="minecraft:gold_ingot" scale="2" />
      <ItemImage id="certus_quartz_crystal" scale="2" />
      <ItemImage id="minecraft:diamond" scale="2" />
      <ItemImage id="minecraft:redstone" scale="2" />
    </Row>
* Los <ItemLink id="import_bus" />ses (13-16, 19) están en su configuración predeterminada. Tienen 2 <ItemLink id="speed_card" />s.
* Las <ItemLink id="inscriber" />s están en su configuración predeterminada. Tienen el [molde](../items-blocks-machines/presses.md) relevante,
   y 4 <ItemLink id="speed_card" />s.
   <Row>
     <ItemImage id="silicon_press" scale="2" />
     <ItemImage id="logic_processor_press" scale="2" />
     <ItemImage id="calculation_processor_press" scale="2" />
     <ItemImage id="engineering_processor_press" scale="2" />
   </Row>

## Cómo Funciona

1. El <ItemLink id="pattern_provider" /> empuja los ingredientes al barril.
2. La primera [subred de tubería](pipe-subnet.md) (naranja) extrae el silicio, el polvo de redstone y el ingrediente del procesador relevante (Lingote de Oro, Cristal de Cuarzo Certus o Diamante) del barril y los coloca en la <ItemLink id="inscriber" /> relevante.
3. Las primeras cuatro <ItemLink id="inscriber" />s hacen el <ItemLink id="printed_silicon" />, y el <ItemLink id="printed_logic_processor" />, <ItemLink id="printed_calculation_processor" /> o <ItemLink id="printed_engineering_processor" />.
4. La segunda y tercera [subred de tubería](pipe-subnet.md) (verdes) sacan los circuitos impresos de las primeras cuatro <ItemLink id="inscriber" />s y los colocan en la quinta, la <ItemLink id="inscriber" /> de ensamblaje final.
5. La quinta <ItemLink id="inscriber" /> ensambla el [procesador](../items-blocks-machines/processors.md).
6. La cuarta [subred de tubería](pipe-subnet.md) (púrpura) coloca el procesador en el proveedor de patrones, devolviéndolo a la red principal.