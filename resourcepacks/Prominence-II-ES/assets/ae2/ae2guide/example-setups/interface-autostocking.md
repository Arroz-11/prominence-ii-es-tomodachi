---
navigation:
  parent: example-setups/example-setups-index.md
  title: Autoabastecimiento con Interfaz
  icon: interface
---

# Autoabastecimiento con Interfaz

Uno podría preguntarse "¿Cómo mantengo una cierta cantidad de varios objetos en stock, crafteando más según sea necesario?"

Una solución es usar una <ItemLink id="interface" /> y una <ItemLink id="crafting_card" /> para solicitar automáticamente nuevos objetos
desde el [autocrafteo](../ae2-mechanics/autocrafting.md) de tu red. Esta configuración es más adecuada para mantener una pequeña cantidad de una amplia
variedad de objetos.

Esta configuración de demostración está recortada para que no sea demasiado ancha; probablemente sea más óptimo usar 4 <ItemLink id="interface" />s y 4 <ItemLink id="storage_bus" />ses,
para usar los 8 [canales](../ae2-mechanics/channels.md) en un [cable](../items-blocks-machines/cables.md) normal.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_autostocking.snbt" />

<BoxAnnotation color="#dddddd" min="0 0 0" max="2 1 1">
        (1) Interfaces: Configuradas para mantener los objetos deseados en sí mismas. Tienen Tarjetas de Trabajo.
        <ItemImage id="crafting_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="2 1.3 1">
        (2) Buses de almacenamiento: "Modo de Entrada/Salida" configurado en "Solo Extraer".
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        A la red principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* Las <ItemLink id="interface" />s (1) están configuradas para mantener los objetos deseados en sí mismas, haciendo clic en el objeto deseado en sus
   ranuras superiores o arrastrándolo desde JEI a las ranuras superiores, y luego haciendo clic en el ícono de llave inglesa sobre las ranuras para establecer la cantidad. Tienen <ItemLink id="crafting_card" />s.
* Los <ItemLink id="storage_bus" />ses (2) están configurados con "Modo de Entrada/Salida" en "Solo Extraer".

## Cómo funciona

1. Si una <ItemLink id="interface" /> no puede obtener suficiente de un objeto configurado del [almacenamiento de la red](../ae2-mechanics/import-export-storage.md),
   (y tiene una <ItemLink id="crafting_card" />), solicitará que el [autocrafteo](../ae2-mechanics/autocrafting.md) de la red craftee más de ese objeto.
2. Los <ItemLink id="storage_bus" />ses permiten que la red acceda al contenido de las interfaces.