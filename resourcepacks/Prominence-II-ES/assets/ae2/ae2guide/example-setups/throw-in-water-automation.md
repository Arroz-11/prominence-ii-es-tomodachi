---
navigation:
  parent: example-setups/example-setups-index.md
  title: Automatización de Lanzar al Agua
  icon: fluix_crystal
---

# Automatización de recetas de Lanzar al Agua

Nota: como esto usa un <ItemLink id="pattern_provider" />, está pensado para integrarse en tu configuración de [autocrafteo](../ae2-mechanics/autocrafting.md).

Algunas recetas requieren que los ítems se lancen al agua (aunque se puede usar una configuración similar para lanzar ítems a otros lugares).
Esto se puede automatizar con un <ItemLink id="formation_plane" />, un <ItemLink id="annihilation_plane" />, y algo de infraestructura de soporte (esto es esencialmente 2 [subredes de tubería](pipe-subnet.md) modificadas).

Esta configuración está pensada para usarse en combinación con la [automatización del cargador](charger-automation.md) para proporcionar los <ItemLink id="charged_certus_quartz_crystal" />s.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (1) Proveedor de Patrones: En su configuración predeterminada, con los patrones de procesamiento relevantes.

        ![Patrón de Fluix](../assets/diagrams/fluix_pattern_small.png) ![Patrón de Brotante Defectuoso](../assets/diagrams/flawed_budding_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 1" max="2 1 2">
        (2) Interfaz: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 .7 1" max="2 1 2">
        (3) Plano de Formación: Configurado para soltar los ítems como ítems.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 2 1" max="2 2.3 2">
        (4) Plano de Aniquilación: Sin GUI para configurar.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (5) Bus de Almacenamiento: Filtrado a los resultados de los patrones
        <Row><ItemImage id="fluix_crystal" scale="2" /><BlockImage id="flawless_budding_quartz" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="3.9 0.5 1.5" color="#00ff00">
        A la Red Principal y a la Automatización del Cargador
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
    </DiamondAnnotation>

  <IsometricCamera yaw="180" pitch="0" />
</GameScene>

## Configuraciones y Patrones

* El <ItemLink id="pattern_provider" /> (1) está en su configuración predeterminada, con los <ItemLink id="processing_pattern" />s relevantes
  * Para <ItemLink id="fluix_crystal" /> la receta predeterminada de JEI/REI funciona bien:

    ![Patrón de Fluix](../assets/diagrams/fluix_pattern.png)

  * Para <ItemLink id="flawed_budding_quartz" /> probablemente sea mejor hacerlo directamente desde <ItemLink id="quartz_block" />,
    lo que evita problemas con que la entrada de una receta sea la salida de otra, causando que el bus de almacenamiento no pueda filtrar:

    ![Patrón de Brotante Defectuoso](../assets/diagrams/flawed_budding_pattern.png)

* La <ItemLink id="interface" /> (2) está en su configuración predeterminada.
* El <ItemLink id="formation_plane" /> (3) está configurado para soltar los ítems como ítems.
* El <ItemLink id="annihilation_plane" /> (4) no tiene GUI y no puede configurarse.
* El <ItemLink id="storage_bus" /> (5) está filtrado a los resultados de los patrones.

## Cómo Funciona

1.  El <ItemLink id="pattern_provider" /> empuja los ingredientes hacia la <ItemLink id="interface" /> en su lado, en la subred verde
2.  La interfaz (al estar configurada para no almacenar nada por defecto) intenta empujar su contenido hacia [almacenamiento de red](../ae2-mechanics/import-export-storage.md)
3.  El único almacenamiento en la subred verde es el <ItemLink id="formation_plane" />, que suelta los ítems que recibe en el agua
4.  El <ItemLink id="annihilation_plane" /> en la subred naranja intenta recoger los ítems que acaban de soltarse, pero no puede, porque
    el <ItemLink id="storage_bus" /> encima del proveedor de patrones (el único almacenamiento en la subred naranja) está filtrado para aceptar solo los resultados de posibles crafteos
5.  Los ítems realizan su transformación en el mundo.
6.  El plano de aniquilación ahora puede recoger los ítems frente a él, ya que el bus de almacenamiento puede almacenarlos.
7.  El bus de almacenamiento almacena los ítems resultantes en el proveedor de patrones, devolviéndolos a la red.