---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Túneles P2P
  icon: me_p2p_tunnel
  position: 210
categories:
- devices
item_ids:
- ae2:me_p2p_tunnel
- ae2:redstone_p2p_tunnel
- ae2:item_p2p_tunnel
- ae2:fluid_p2p_tunnel
- ae2:fe_p2p_tunnel
- ae2:light_p2p_tunnel
---

# Túneles Punto a Punto

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Los túneles P2P son una forma de mover cosas como objetos, fluidos, señales de redstone, energía, luz y [canales](../ae2-mechanics/channels.md)
alrededor de una red sin que interactúen directamente con la red. Hay muchas variantes de túnel P2P, pero cada una
solo transporta su tipo específico de cosa. Esencialmente actúan como portales que conectan directamente
dos caras de bloques a distancia. No son bidireccionales, hay entradas y salidas definidas.

![Portal](../assets/assemblies/p2p_portal.png)

Por ejemplo, la tolva que mira al P2P de objetos actuará como si estuviera directamente conectada al barril, y los objetos fluirán.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_hopper_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Sin embargo, dos barriles uno al lado del otro no transferirán objetos entre sí.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_barrel_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

También hay otras variantes como el P2P de redstone.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_redstone.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Tipos de Túnel P2P y Sintonización

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="180" pitch="90" />
</GameScene>

Hay muchos tipos de túnel P2P. Solo el túnel P2P de ME es directamente crafteable, los demás se hacen haciendo clic derecho en otros
túneles P2P con ciertos objetos:
- Los túneles P2P de ME se seleccionan haciendo clic derecho con cualquier [cable](../items-blocks-machines/cables.md).
- Los túneles P2P de redstone se seleccionan haciendo clic derecho con una variedad de componentes de redstone.
- Los túneles P2P de objetos se seleccionan haciendo clic derecho con un cofre o tolva.
- Los túneles P2P de fluidos se seleccionan haciendo clic derecho con un cubo o botella.
- Los túneles P2P de energía se seleccionan haciendo clic derecho con casi cualquier objeto que contenga energía.
- Los túneles P2P de luz se seleccionan haciendo clic derecho con una antorcha o piedra luminosa

Algunos tipos de túnel tienen peculiaridades. Por ejemplo, los canales de los túneles P2P de ME no pueden pasar a través de otros túneles P2P de ME, y
los túneles P2P de energía extraen indirectamente un impuesto del 5% sobre FE o E que fluye a través de ellos al aumentar su
consumo de [energía](../ae2-mechanics/energy.md).

## La Forma Más Usada de P2P

El caso de uso más común de los túneles P2P es usar un túnel P2P de ME para compactar la densidad del transporte de [canales](../ae2-mechanics/channels.md).
En lugar de un montón de cable denso, un solo cable denso puede usarse para llevar muchos canales.

En este ejemplo, 8 entradas P2P de ME toman 256 canales (8*32) del <ItemLink id="controller" /> de la red principal y 8 salidas P2P de ME
los emiten en otro lugar. Observa cómo cada entrada o salida de túnel P2P ocupa 1 canal. Así podemos llevar muchos canales
a través de un cable delgado. Y como nuestros túneles P2P están en una [subred](../ae2-mechanics/subnetworks.md) dedicada, ni siquiera
estamos usando canales de la red principal para hacer esto. También observa cómo mientras los túneles P2P pueden colocarse directamente
contra un controlador, un [cable inteligente denso](../items-blocks-machines/cables.md#smart-cable) puede colocarse en medio para visualizar más fácilmente los canales.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/p2p_compact_channels.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 1.3 6.3" max="2 2.7 6.7">
        La Fibra de Cuarzo comparte energía entre la red principal y la subred P2P.
  </BoxAnnotation>

  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

Para otro ejemplo (incluyendo su uso con [Puentes Cuánticos](quantum_bridge.md)) mira este diagrama de MS Paint que no me molesté
en retocar:

![P2P y puentes cuánticos](../assets/diagrams/p2p_quantum_network.png)

## Anidamiento

Sin embargo, no puedes usar esto para enviar canales infinitos a través de un solo cable. El canal de un túnel P2P de ME no
pasará a través de otro túnel P2P de ME, así que no puedes anidarlos recursivamente. Observa cómo la capa exterior de túneles P2P de ME
en los cables rojos están fuera de línea. Nota que esto solo aplica a los túneles P2P de ME, otros tipos de túnel P2P pueden pasar a través de un túnel P2P de ME,
como se ve con los túneles P2P de redstone funcionando bien.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_nesting.snbt" />
  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

## Vinculación

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_linking_frequency.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Los extremos de una conexión de túnel P2P pueden vincularse usando una <ItemLink id="memory_card" />. La frecuencia se mostrará
como una matriz de colores 2x2 en la parte trasera del túnel.
- Mayús izdo. + clic derecho para generar una nueva frecuencia de vinculación P2P.
- Clic derecho para pegar la configuración, tarjetas de mejora o frecuencia de vinculación.

El túnel en el que hagas Mayús izdo. + clic derecho será la entrada y el túnel en el que hagas clic derecho será la salida. Puedes tener múltiples salidas,
pero con los túneles P2P de ME, los canales que fluyen en la entrada se dividirán entre las salidas, así que no puedes duplicar canales.

## Receta

<RecipeFor id="me_p2p_tunnel" />