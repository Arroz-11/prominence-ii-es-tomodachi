---
navigation:
  parent: example-setups/example-setups-index.md
  title: Subred de "Tubería" de Objetos/ Fluidos
  icon: storage_bus
---

# Subred de "Tubería" de Objetos/Fluidos

Un método simple para emular una tubería de objetos y/o fluidos con [dispositivos](../ae2-mechanics/devices.md) de AE2, útil para, bueno, cualquier cosa para la que usarías una tubería de objetos o fluidos.
Esto incluye devolver el resultado de un crafteo a un <ItemLink id="pattern_provider" />.

Generalmente hay dos métodos diferentes para lograr esto:

## Bus de Importación -> Bus de Almacenamiento

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Bus de Importación: Puede filtrarse.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Bus de Almacenamiento: Puede filtrarse. Este (y otros buses de almacenamiento que quieras como destino)
        deben ser el único almacenamiento en la red.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Fuente
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Destino
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

El <ItemLink id="import_bus" /> (1) en el inventario de origen importa los objetos o fluidos, e intenta almacenarlos en el [almacenamiento de red](../ae2-mechanics/import-export-storage.md).
Como el único almacenamiento en la red es el <ItemLink id="storage_bus" /> (2) (por eso esto es una subred y no tu red principal), los objetos o fluidos se colocan en el inventario de destino, transfiriéndose así. La energía se proporciona a través de una <ItemLink id="quartz_fiber" />.
Tanto el bus de importación como el bus de almacenamiento pueden filtrarse, pero la configuración transferirá todo lo que pueda acceder si no se aplican filtros.
Esta configuración también funciona con múltiples buses de importación y múltiples buses de almacenamiento.

## Bus de Almacenamiento -> Bus de Exportación

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Bus de Almacenamiento: Puede filtrarse. Este (y otros buses de almacenamiento que quieras como fuente)
        deben ser el único almacenamiento en la red.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Bus de Exportación: Debe filtrarse.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Fuente
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Destino
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

El <ItemLink id="export_bus" /> en el inventario de destino intenta extraer objetos en su filtro del [almacenamiento de red](../ae2-mechanics/import-export-storage.md).
Como el único almacenamiento en la red es el <ItemLink id="storage_bus" /> (por eso esto es una subred y no tu red principal), los objetos o fluidos se extraen del inventario de origen, transfiriéndose así. La energía se proporciona a través de una <ItemLink id="quartz_fiber" />.
Debido a que los buses de exportación deben filtrarse para funcionar, esta configuración solo opera si filtras el bus de exportación.
Esta configuración también funciona con múltiples buses de almacenamiento y múltiples buses de exportación.

## Una Configuración Que No Funciona (Bus de Importación -> Bus de Exportación)

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        Bus de Importación: Como la red no tiene almacenamiento, no hay a dónde importar.
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        (2) Bus de Exportación: Como la red no tiene almacenamiento, no hay nada que exportar.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        Fuente
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        Destino
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Una configuración con solo un bus de importación y exportación no funcionará. El bus de importación intentará extraer del inventario de origen y almacenar los objetos o fluidos en el almacenamiento de red. El bus de exportación intentará extraer del almacenamiento de red y poner los objetos o fluidos en el inventario de destino. Sin embargo, como esta red **no tiene almacenamiento**, el bus de importación no puede importar y el bus de exportación no puede exportar, así que no pasa nada.

## Entrada y Salida a Través de 1 Cara

Digamos que tienes alguna máquina que puede recibir entrada y que su salida sea extraída a través de 1 cara. (Como un <ItemLink id="charger" />)
Puedes tanto empujar los ingredientes como extraer el resultado, combinando los 2 métodos de subred de tubería:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) Bus de Importación: Puede filtrarse.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) Bus de Almacenamiento: Puede filtrarse. Este (y otros buses de almacenamiento a los que quieras empujar y extraer objetos)
        deben ser el único almacenamiento en la red.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) Cosa a la que quieres empujar y de la que quieres extraer: En este caso un Cargador.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) Bus de Exportación: Debe filtrarse.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        Fuente
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        Destino
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Interfaces

Resulta que hay [dispositivos](../ae2-mechanics/devices.md) además de los buses de importación y exportación que empujan objetos hacia y extraen objetos del [almacenamiento de red](../ae2-mechanics/import-export-storage.md)!
De relevancia aquí está la <ItemLink id="interface" />. Si se inserta un objeto que la interfaz no está configurada para almacenar, la interfaz lo empujará al almacenamiento de red, lo cual podemos explotar de manera similar a la tubería de bus de importación -> bus de almacenamiento. Configurar una interfaz para almacenar algún objeto lo extraerá del almacenamiento de red, similar a la tubería de bus de almacenamiento -> bus de exportación. Las interfaces pueden configurarse para almacenar algunas cosas y no otras, permitiéndote empujar y extraer remotamente a través de buses de almacenamiento, si por alguna razón quieres hacer eso.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        Interfaz
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        Bus de Almacenamiento
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        Bus de Almacenamiento
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        Bus de Almacenamiento
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Uno-a-Muchos y Muchos-a-Uno (y muchos-a-muchos)

Por supuesto, no tienes que usar solo un <ItemLink id="import_bus" /> o <ItemLink id="export_bus" /> o <ItemLink id="storage_bus" />

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## Proporcionar a Múltiples Lugares

De todo esto, podemos derivar un método para enviar ingredientes desde una cara de <ItemLink id="pattern_provider" /> a muchos lugares diferentes, como un conjunto de máquinas, o varias caras diferentes de una máquina.

No queremos una tubería de importación -> almacenamiento o de almacenamiento -> exportación porque el <ItemLink id="pattern_provider" /> nunca contiene realmente los ingredientes. En cambio, los proveedores *empujan* los ingredientes a inventarios adyacentes, así que necesitamos algún inventario adyacente que también pueda importar objetos.

Esto suena como... ¡una <ItemLink id="interface" />!
Asegúrate de que el proveedor esté en modo direccional o de subparte plana y/o la interfaz esté en modo de subparte plana, para que los dos no formen una conexión de red.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        Interfaz (debe ser plana, no bloque completo)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        Buses de Almacenamiento
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        Lugares a los que quieres proporcionar patrones (múltiples máquinas, o múltiples caras de 1 máquina)
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>