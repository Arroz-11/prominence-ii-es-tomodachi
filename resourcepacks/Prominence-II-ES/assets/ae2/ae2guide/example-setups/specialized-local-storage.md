---
navigation:
  parent: example-setups/example-setups-index.md
  title: Almacenamiento Local Especializado
  icon: drive
---

# Almacenamiento Local Especializado

Utilizando uno de los [comportamientos especiales de la Interfaz](../items-blocks-machines/interface.md#special-interactions), una
[subred](../ae2-mechanics/subnetworks.md) puede presentar el contenido de su almacenamiento a la red principal, sin poder
ver el almacenamiento de la red principal, y ocupando solo 1 [canal](../ae2-mechanics/channels.md).

Esto es útil para almacenamiento local en alguna granja, para que los ítems no se desborden hacia tu almacenamiento principal.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/local_storage.snbt" />

<BoxAnnotation color="#dddddd" min="4 0 0" max="5 2 1">
        (1) Algún método de importar ítems (en este caso una interfaz)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 0 0" max="4 1 1">
        (2) Unidad: Tiene algunas celdas. Las celdas deben estar filtradas a lo que sea que produzca la granja.
        Las celdas pueden tener Tarjetas de Distribución Equitativa y Tarjetas de Destrucción por Desbordamiento.
        <Row><ItemImage id="item_storage_cell_4k" scale="2" /> <ItemImage id="equal_distribution_card" scale="2" /> <ItemImage id="void_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1 0" max="4 2 0.3">
        (3) Terminal de Trabajo: Puede ver el contenido de la Unidad en la subred, pero no el contenido del almacenamiento de tu red principal.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (4) Interfaz #2: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 0" max="2 1 1">
        (5) Bus de Almacenamiento: Tiene prioridad más alta que el almacenamiento principal, puede filtrarse a lo que sea que produzca la granja.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 0.3">
        Terminal de Trabajo: Puede ver tanto el contenido del almacenamiento de la red principal *como* el de la subred.
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* La primera <ItemLink id="interface" /> (1) simplemente acepta ítems de cualquier granja que tengas y los empuja hacia la subred.
* La <ItemLink id="drive" /> (2) tiene algunas [celdas](../items-blocks-machines/storage_cells.md). Las celdas deben estar
  [particionadas](../items-blocks-machines/cell_workbench.md) a lo que sea que produzca la granja.
  Las celdas pueden tener <ItemLink id="equal_distribution_card" />s y <ItemLink id="void_card" />s.
* La segunda <ItemLink id="interface" /> (4) está en su configuración predeterminada.
* El <ItemLink id="storage_bus" /> tiene su [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) establecida
  más alta que el almacenamiento principal. Puede filtrarse a lo que sea que produzca la granja.

## Cómo Funciona

* La <ItemLink id="interface" /> en la subred le muestra al <ItemLink id="storage_bus" /> en la red principal el contenido de
la <ItemLink id="drive" />. Esto significa que el bus de almacenamiento puede extraer y empujar ítems directamente hacia las celdas en la unidad.
* El bus de almacenamiento está configurado con [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) alta para que los ítems se coloquen preferentemente
  de vuelta en la subred en lugar de en tu almacenamiento principal.
* Importante: si las celdas en la subred se llenan, los ítems no se desbordarán hacia la red principal. Si la granja es de un tipo
que se rompe si se acumula, se pueden usar <ItemLink id="void_card" />s para eliminar el exceso de ítems en su lugar.
* Si la granja produce múltiples ítems, las <ItemLink id="equal_distribution_card" />s pueden evitar que un ítem llene todas las celdas
y no permita que los otros ítems se almacenen.