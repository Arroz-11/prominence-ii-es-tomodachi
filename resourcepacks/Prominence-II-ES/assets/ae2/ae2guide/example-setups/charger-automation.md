---
navigation:
  parent: example-setups/example-setups-index.md
  title: Automatización del Cargador
  icon: charger
---

# Automatización del Cargador

Ten en cuenta que, como esto usa un <ItemLink id="pattern_provider" />, está pensado para integrarse en tu configuración de [autocrafteo](../ae2-mechanics/autocrafting.md).
Si solo quieres automatizar un <ItemLink id="charger" /> de forma independiente, usa tolvas, cofres y demás.

Automatizar un <ItemLink id="charger" /> es bastante simple. Un <ItemLink id="pattern_provider" /> empuja el ingrediente al cargador, y luego una [subred de tuberías](pipe-subnet.md)
ou otra tubería de objetos empuja el resultado de vuelta al proveedor.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/charger_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Proveedor de patrones: En su configuración predeterminada, con los patrones de procesamiento relevantes. También proporciona energía al cargador.

        ![Patrón de Cargador](../assets/diagrams/charger_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="1 1.3 1">
        (2) Bus de importación: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (3) Bus de almacenamiento: En su configuración predeterminada.
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        A la red principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El <ItemLink id="pattern_provider" /> (1) está en su configuración predeterminada, con los <ItemLink id="processing_pattern" />s relevantes.
  También proporciona al <ItemLink id="charger" /> [energía](../ae2-mechanics/energy.md) porque actúa como un [cable](../items-blocks-machines/cables.md).
  
    ![Patrón de Cargador](../assets/diagrams/charger_pattern.png)

* El <ItemLink id="import_bus" /> (2) está en su configuración predeterminada.
* El <ItemLink id="storage_bus" /> (3) está en su configuración predeterminada.

## Cómo Funciona

1. El <ItemLink id="pattern_provider" /> empuja los ingredientes al <ItemLink id="charger" />.
2. El cargador hace su trabajo de carga.
3. El <ItemLink id="import_bus" /> en la subred verde extrae el resultado del cargador e intenta almacenarlo en
   el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md).
4. El único almacenamiento en la subred verde es el <ItemLink id="storage_bus" />, que almacena los objetos resultantes en el proveedor de patrones, devolviéndolos a la red principal.
