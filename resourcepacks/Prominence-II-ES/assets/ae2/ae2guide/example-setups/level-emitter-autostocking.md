---
navigation:
  parent: example-setups/example-setups-index.md
  title: Autoabastecimiento con Emisor de Nivel
  icon: level_emitter
---

# Autoabastecimiento con Emisor de Nivel

Uno podría preguntarse "¿Cómo mantengo una cierta cantidad de un objeto en stock, crafteando más según sea necesario?"

Una solución es usar un <ItemLink id="export_bus" />, un <ItemLink id="level_emitter" /> y una <ItemLink id="crafting_card" /> para solicitar automáticamente nuevos objetos
desde el [autocrafteo](../ae2-mechanics/autocrafting.md) de tu red. Esta configuración es para mantener una gran cantidad de un solo objeto.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/level_emitter_autostocking.snbt" />

  <BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (1) Bus de exportación: Filtrado al objeto deseado. Tiene una Tarjeta de Redstone y una Tarjeta de Trabajo. Modo de Redstone configurado en
        "Activo con señal", Comportamiento de Creación configurado en "No usar objetos en stock".
        <Row><ItemImage id="redstone_card" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0.7 1 0" max="1 2 1">
        (2) Emisor de Nivel: Configurado con el objeto y la cantidad deseados, configurado en "Emitir cuando los niveles estén por debajo del límite".
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (3) Interfaz: En su configuración predeterminada.
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        A la red principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El <ItemLink id="export_bus" /> (1) está filtrado al objeto deseado. Tiene una <ItemLink id="redstone_card" /> y una <ItemLink id="crafting_card" />.
  El "Modo de Redstone" está configurado en "Activo con señal", el "Comportamiento de Creación" está configurado en "No usar objetos en stock".
* El <ItemLink id="level_emitter" /> (2) está configurado con el objeto y la cantidad deseados, y configurado en "Emitir cuando los niveles estén por debajo del límite".
* La <ItemLink id="interface" /> (3) está en su configuración predeterminada.

## Cómo funciona

1. Si la cantidad del objeto deseado en el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md) está por debajo de la cantidad especificada en el
   <ItemLink id="level_emitter" />, emitirá una señal de redstone.
2. Al recibir una señal de redstone (y debido a la <ItemLink id="crafting_card" /> y a estar configurado para no usar objetos en stock),
   el <ItemLink id="export_bus" /> solicitará que el [autocrafteo](../ae2-mechanics/autocrafting.md) de la red craftee
   más del objeto deseado, y luego lo exportará.
3. Al recibir un objeto empujado hacia ella (y al no estar configurada para tener nada en su inventario interno), la <ItemLink id="interface" /> empujará ese objeto al almacenamiento de la red.