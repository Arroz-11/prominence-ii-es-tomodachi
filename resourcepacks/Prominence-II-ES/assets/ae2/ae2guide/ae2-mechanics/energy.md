---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Energía
  icon: energy_cell
---

# Energía

Tu red necesitará energía para funcionar. Las redes tienen un grupo de energía del que los [dispositivos](../ae2-mechanics/devices.md) extraen directamente, y las <ItemLink id="vibration_chamber" />s, los <ItemLink id="energy_acceptor" />s (y los <ItemLink id="controller" />s) agregan. Puedes ver las estadísticas de energía de una red haciendo clic derecho en cualquier parte de ella con una <ItemLink id="network_tool" /> o haciendo clic derecho en el controlador de la red, si tiene uno. Este almacenamiento y distribución a nivel de red significa que no hay límites de velocidad de transferencia de energía, por lo que los dispositivos pueden extraer cantidades arbitrariamente altas de energía y los aceptadores de energía pueden recibir a una velocidad funcionalmente ilimitada, solo limitada por tu almacenamiento de energía.

## Aceptación de Energía

<Row>
  <BlockImage id="energy_acceptor" scale="4" />

  <GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
  </GameScene>

  <BlockImage id="controller" p:state="online" scale="4" />

  <BlockImage id="vibration_chamber" p:active="true" scale="4" />
  
  <BlockImage id="crystal_resonance_generator" scale="4" />
</Row>

AE2 no usa Energía Forge (en Forge) o Energía TechReborn (en Fabric) internamente. En su lugar, las convierte a su propia unidad, AE. Esta conversión es unidireccional. La energía puede ser convertida por <ItemLink id="energy_acceptor" />s y <ItemLink id="controller" />s, aunque las caras del controlador se usan mejor para más [canales](../ae2-mechanics/channels.md). También puede ser generada por <ItemLink id="vibration_chamber" />s o pasivamente usando un <ItemLink id="crystal_resonance_generator" />, pero AE2 está diseñado para usarse con otros mods técnicos que tienen mejor generación de energía.

Todo esto significa que es mejor considerar una red de AE2 como una sola máquina multibloque grande al diseñar la infraestructura de distribución de energía de tu base.

Las proporciones para la conversión de Energía Forge y Energía Techreborn son

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

## Almacenamiento de energía

<Row>
  <BlockImage id="energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="4" />
</Row>

Por razones bastante obvias, una red no puede recibir o consumir más energía en un gametick de la que puede almacenar. Si una red solo puede almacenar 800 AE, cuando sus [dispositivos](../ae2-mechanics/devices.md) soliciten energía, solo podrán usar hasta 800 AE (asumiendo que el almacenamiento esté lleno) y un aceptador de energía solo podrá insertar hasta 800 AE en la red (asumiendo que el almacenamiento esté vacío).

Esta es una causa común de comportamiento extraño, donde uno hace una red pequeña con solo un aceptador de energía, una unidad, una terminal y algunos dispositivos, y trata de vaciar un inventario lleno de piedra de su inventario a la red. Insertar toda esa piedra a la vez en un solo gametick requiere más energía de la que la red tiene en almacenamiento, por lo que no toda la piedra se inserta, la red se queda sin energía y se reinicia.

**Esto se puede solucionar agregando celdas de energía.**

Las redes tienen un búfer de energía incorporado de 25 AE por cable, máquina o parte.

Los <ItemLink id="controller" />s tienen una pequeña cantidad de almacenamiento de energía interno, 8,000 AE

La <ItemLink id="energy_cell" /> puede almacenar 200k AE, y solo una debería ser suficiente para la mayoría de los casos de uso, manejando las sobretensiones de energía del uso normal de la red con facilidad.

La <ItemLink id="dense_energy_cell" /> puede almacenar 1.6M AE y es para cuando quieres ejecutar una red con energía almacenada, o manejar el enorme consumo instantáneo de energía de las configuraciones grandes de [almacenamiento espacial](spatial-io.md).

La <ItemLink id="creative_energy_cell" /> es un objeto creativo para pruebas, que proporciona PODER INFINITO o lo que sea.
