---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Conexiones de Red
  icon: fluix_glass_cable
---

# Conexiones de Red

## ¿Qué Significa "Red"?

Una "Red" es un grupo de [dispositivos](../ae2-mechanics/devices.md) enlazados por bloques que pueden pasar [canales](../ae2-mechanics/channels.md), como [cables](../items-blocks-machines/cables.md) o máquinas de bloque completo y [dispositivos](../ae2-mechanics/devices.md). (<ItemLink id="charger" />, <ItemLink id="interface" />, <ItemLink id="drive" />, etc.) Técnicamente, un solo cable es una red, en realidad.

## Un Comentario Sobre la Posición de los Dispositivos

Para los [dispositivos](../ae2-mechanics/devices.md) que tienen alguna función específica de red (como una <ItemLink id="interface" /> que empuja y extrae del [almacenamiento de red](../ae2-mechanics/import-export-storage.md), un <ItemLink id="level_emitter" /> que lee el contenido del almacenamiento de red, una <ItemLink id="drive" /> que es almacenamiento de red, etc.) la posición física del dispositivo no importa.

De nuevo, **la posición física del dispositivo no importa**. Todo lo que importa es que el dispositivo esté conectado a la red (y por supuesto a qué red está conectado).

## Conexiones de Red

Una forma fácil de determinar qué está conectado en una red es usando una <ItemLink id="network_tool" />. Mostrará cada componente en la red, así que si ves cosas que no deberían estar o no ves cosas que deberían estar, tienes un problema.

Por ejemplo, estas son 2 redes separadas.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Red 1
  </BoxAnnotation>

<BoxAnnotation color="#915dcd" min="2 0 0" max="3 2 2">
        Red 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Estas también son 2 redes separadas, porque la <ItemLink id="quartz_fiber" /> comparte [energía](../ae2-mechanics/energy.md) sin proporcionar una conexión de red.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Red 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1.3 0 0" max="3 2 2">
        Red 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Sin embargo, esto es solo 1 red, no 2 separadas. El [puente cuántico](../items-blocks-machines/quantum_bridge.md) actúa como un [cable denso](../items-blocks-machines/cables.md#dense-cable) inalámbrico, así que ambos extremos están en la misma red.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        Todo es 1 red
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Esto también es solo 1 red, ya que el color del [cable](../items-blocks-machines/cables.md) no tiene nada que ver con las conexiones de red aparte de que los cables de diferentes colores no se conectan entre sí. Todos los colores se conectan a los cables de fluix (o "sin color").

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Todo es 1 red
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Conexiones Menos Intuitivas

En este caso, esto es solo 1 red, porque el <ItemLink id="pattern_provider" />, al ser un dispositivo de bloque completo, actúa como un cable, y el <ItemLink id="inscriber" /> hace algo similar. Así, la conexión de red pasa a través del proveedor y el inscriptor.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Todo es 1 red
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Para prevenir esto (útil para muchas configuraciones de autocrafteo que involucran [subredes](../ae2-mechanics/subnetworks.md)), puedes hacer clic derecho en el proveedor con una <ItemLink id="certus_quartz_wrench" /> para hacerlo direccional, en cuyo caso no pasará canales a través de un lado.

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="2 2 2">
        Red 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="4 2 2">
        Red 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        Observa cómo el cable no se conecta
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

Otras partes que no proporcionan conexiones de red direccionales son la mayoría de los [dispositivos](../ae2-mechanics/cable-subparts.md) [subparte](../ae2-mechanics/devices.md) como los <ItemLink id="import_bus" />ses, los <ItemLink id="storage_bus" />ses, y las <ItemLink id="cable_interface" />s.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>