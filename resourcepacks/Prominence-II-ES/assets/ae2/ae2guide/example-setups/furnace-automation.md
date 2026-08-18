---
navigation:
  parent: example-setups/example-setups-index.md
  title: Automatización de Horno
  icon: minecraft:furnace
---

# Automatización de Horno

Nota que, como esto usa un <ItemLink id="pattern_provider" />, está pensado para integrarse en tu configuración de [autocrafteo](../ae2-mechanics/autocrafting.md). Si solo quieres automatizar un horno de forma independiente, usa tolvas y cofres y esas cosas.

La automatización de un <ItemLink id="minecraft:furnace" /> es un poco más compleja que la de máquinas más simples como un [cargador](../example-setups/charger-automation.md). Un horno requiere entrada por dos lados separados y extracción por un tercero. El objeto a fundir debe empujarse por la cara superior, el combustible debe empujarse por una cara lateral, y el resultado debe extraerse por la parte inferior.

Esto podría hacerse con un <ItemLink id="pattern_provider" /> en la parte superior, un <ItemLink id="export_bus" /> en el lateral para empujar combustible constantemente, y un <ItemLink id="import_bus" /> en la parte inferior para importar los resultados a la red. Sin embargo, esto usa 3 [canales](../ae2-mechanics/channels.md).

Así es como puedes hacerlo con solo 1 canal:

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Proveedor de patrones: La variante direccional, usando una llave de cuarzo certificus, con los patrones de procesamiento relevantes.

        ![Patrón de hierro](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) Interfaz: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) Bus de almacenamiento #1: Filtrado a carbón.
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) Bus de almacenamiento #2: Filtrado para excluir carbón, usando una tarjeta inversora.
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        A la red principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El <ItemLink id="pattern_provider" /> (1) está en su configuración predeterminada, con los <ItemLink id="processing_pattern" /> relevantes.
    Se hace direccional usando una <ItemLink id="certus_quartz_wrench" /> sobre él.

  ![Patrón de hierro](../assets/diagrams/furnace_pattern.png)

* La <ItemLink id="interface" /> (2) está en su configuración predeterminada.
* El primer <ItemLink id="storage_bus" /> (3) está filtrado a carbón, o al combustible que quieras usar.
* El segundo <ItemLink id="storage_bus" /> (4) está filtrado para excluir el combustible que estás usando, usando una <ItemLink id="inverter_card" />.

## Cómo funciona

1. El <ItemLink id="pattern_provider" /> empuja los ingredientes a la <ItemLink id="interface" />.
   (En realidad, como optimización, empuja directamente a través de los buses de almacenamiento como si fueran extensiones de las caras del proveedor. Los objetos nunca entran realmente en la interfaz.)
2. La interfaz está configurada para no almacenar nada, así que intenta empujar los ingredientes al [almacenamiento de la red](../ae2-mechanics/import-export-storage.md).
3. El único almacenamiento en la subred verde son los <ItemLink id="storage_bus" />. El bus filtrado a carbón coloca el carbón en la ranura de combustible del horno a través de la cara lateral.
    El bus filtrado a NO carbón coloca los objetos a fundir en la ranura superior, a través de la cara superior.
4. El horno hace lo suyo.
5. La tolva extrae los resultados por la parte inferior del horno y los coloca en las ranuras de retorno del proveedor, devolviéndolos a la red principal.
