---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Importar, Exportar y Almacenar
---

# Importar, Exportar y Almacenar

**Tu sistema ME y el mundo**

Un concepto importante en AE2 es la idea de Almacenamiento de Red. Es el lugar donde se guardan los contenidos de una red, usualmente [celdas de almacenamiento](../items-blocks-machines/storage_cells.md) o cualquier inventario al que esté conectado un <ItemLink id="storage_bus" />. La mayoría de los [dispositivos](../ae2-mechanics/devices.md) de AE2 interactúan con él de una forma u otra.

Por ejemplo,

*   Los <ItemLink id="import_bus" />ses empujan cosas hacia el almacenamiento de red
*   Los <ItemLink id="export_bus" />ses extraen cosas del almacenamiento de red
*   Las <ItemLink id="interface" />s tanto extraen como empujan hacia el almacenamiento de red
*   Las [terminales](../items-blocks-machines/terminals.md) empujan y extraen del almacenamiento de red cuando insertas o tomas objetos, o para rellenar los espacios de crafteo
*   Los <ItemLink id="storage_bus" />ses no empujan ni extraen realmente del almacenamiento, empujan o extraen del inventario conectado para usarlo como almacenamiento de red (así que en realidad otros dispositivos empujan o extraen de *ellos*)

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_export_storage.snbt" />

  <BoxAnnotation color="#dddddd" min="8 1 1" max="9 1.3 2">
        Los buses de importación importan cosas de los inventarios a los que apuntan hacia el almacenamiento de red
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="8 2 1" max="9 3 1.3">
        Insertar algo en una terminal desde tu inventario cuenta como que la red lo importa
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="7 0 1" max="8 1 2">
        Las interfaces importarán desde sus inventarios internos si ese espacio no está configurado para almacenar nada, o si hay más objetos en ese espacio de los configurados para almacenar, así que se pueden empujar cosas hacia ellas para insertarlas en la red
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="6 0 1" max="7 1 2">
        Los proveedores de patrones importarán desde su inventario interno de retorno, así que se pueden empujar cosas hacia ellos para insertarlas en la red
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 1" max="5 2 2">
        Las bahías proporcionan las celdas insertadas como almacenamiento de red
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        Los buses de almacenamiento usan el inventario al que apuntan como almacenamiento de red
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 1 1" max="2 1.3 2">
        Los buses de exportación exportan cosas del almacenamiento de red hacia los inventarios a los que apuntan
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="2 3 1.3">
        Sacar algo de una terminal cuenta como que la red lo exporta
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 1 1" max="1 2 2">
        Las interfaces exportarán a sus inventarios internos si ese espacio está configurado para almacenar algo, así que se pueden extraer cosas de ellas para sacarlas de la red
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Las acciones/eventos de empujar y extraer del almacenamiento de red son importantes a tener en cuenta al diseñar automatizaciones y configuraciones logísticas.

## Prioridad de Almacenamiento

Se pueden establecer prioridades haciendo clic en la llave en la esquina superior derecha de algunas GUIs. Los objetos que entran a la red comenzarán en el almacenamiento de mayor prioridad, como su primer destino. En el caso de que dos almacenamientos tengan la misma prioridad, si uno ya contiene el objeto, preferirán ese almacenamiento sobre cualquier otro. Las celdas en lista blanca se tratarán como si ya contuvieran el objeto cuando estén en el mismo grupo de prioridad que otros almacenamientos. Los objetos que se eliminan del almacenamiento se eliminarán del almacenamiento con la prioridad más baja. Este sistema de prioridad significa que a medida que los objetos se insertan y eliminan del almacenamiento de red, los almacenamientos de mayor prioridad se llenarán y los de menor prioridad se vaciarán.
