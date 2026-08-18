---
navigation:
  parent: example-setups/example-setups-index.md
  title: Volcador o Llenador de Celdas
  icon: io_port
---

# Volcador o Llenador de Celdas

Uno podría preguntarse "¿Cómo vacío rápidamente una celda en un cofre, un conjunto de cajones o una mochila, o, inversamente, lleno una celda desde lo mismo?"

La respuesta es usar un <ItemLink id="io_port" /> y algo de subredes para restringir dónde puede poner los objetos, o de dónde puede extraerlos.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/cell_dumper_filler.snbt" />

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 1">
        (1) Puerto de E/S: Se puede configurar en "Transferir datos a la red" o "Transferir datos a la celda de almacenamiento" usando el botón de flecha
        en el centro de la GUI. Tiene 3 tarjetas de aceleración.
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0.7 0" max="1 1 1">
        (2) Bus de almacenamiento: En su configuración predeterminada.
  </BoxAnnotation>

<BoxAnnotation color="#33dd33" min="0 1 0" max="1 2 1">
        Coloca aquí lo que quieras llenar o vaciar.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0.35 0.35" max="2.3 0.65 0.65">
        Fibra de Cuarzo: Solo se necesita si la fuente de energía es otra red.
  </BoxAnnotation>

<DiamondAnnotation pos="3 0.5 0.5" color="#00ff00">
        A alguna fuente de energía, como otra red, o un aceptador de energía.
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El <ItemLink id="io_port" /> (1) se puede configurar en "Transferir datos a la red" o "Transferir datos a la celda de almacenamiento" usando el botón de flecha
  en el centro de la GUI. Tiene 3 tarjetas de aceleración para máxima velocidad.
* El <ItemLink id="storage_bus" /> (2) está en su configuración predeterminada.

## Cómo Funciona

### En Modo "Transferir a la Red"

1. El <ItemLink id="io_port" /> intenta vaciar el contenido de la [celda de almacenamiento](../items-blocks-machines/storage_cells.md) insertada
    en el [almacenamiento de la red](../ae2-mechanics/import-export-storage.md).
2. El único almacenamiento en la subred es el <ItemLink id="storage_bus" />, que almacena los objetos, fluidos, etc. en lo que
    coloques delante de él.
* La <ItemLink id="energy_cell" /> proporciona un búfer de [energía](../ae2-mechanics/energy.md) lo suficientemente grande como para que la red no
    se quede sin energía por el consumo de transferir tantos objetos por tick de juego.

### En Modo "Transferir a la Celda de Almacenamiento"

1. El <ItemLink id="io_port" /> intenta vaciar el contenido del [almacenamiento de la red](../ae2-mechanics/import-export-storage.md)
   en la [celda de almacenamiento](../items-blocks-machines/storage_cells.md) insertada.
2. El único almacenamiento en la subred es el <ItemLink id="storage_bus" />, que extrae los objetos, fluidos, etc. de lo que
   coloques delante de él.
* La <ItemLink id="energy_cell" /> proporciona un búfer de [energía](../ae2-mechanics/energy.md) lo suficientemente grande como para que la red no
  se quede sin energía por el consumo de transferir tantos objetos por tick de juego.