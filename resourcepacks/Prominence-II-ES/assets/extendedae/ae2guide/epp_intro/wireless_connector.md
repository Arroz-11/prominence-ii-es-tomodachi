---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: Conector Inalámbrico ME
    icon: extendedae:wireless_connect
categories:
- extended devices
item_ids:
- extendedae:wireless_connect
- extendedae:wireless_tool
---

# Conector Inalámbrico ME

<Row gap="20">
<BlockImage id="extendedae:wireless_connect" scale="6"></BlockImage>
<ItemImage id="extendedae:wireless_tool" scale="6"></ItemImage>
</Row>

El Conector Inalámbrico ME puede vincular dos redes como <ItemLink id="ae2:quantum_link" /> pero con distancias limitadas y no puede
cruzar dimensiones.

## Vincular los Conectores Inalámbricos

Haz clic en los dos Conectores Inalámbricos que quieras vincular con el Kit de Configuración Inalámbrica ME, luego podrás vincularlos entre sí.

Agáchate y haz clic para limpiar la configuración actual del Kit de Configuración Inalámbrica ME.

El Conector Inalámbrico ME cambiará su textura cuando se establezca un enlace exitosamente.

Conectores Inalámbricos ME Sin Vincular

<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_off.snbt"></ImportStructure>
</GameScene>

Conectores Inalámbricos ME Vinculados

<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_on.snbt"></ImportStructure>
</GameScene>

## Color

Los Conectores Inalámbricos se pueden colorear como los cables y solo se conectan con cables/conectores del mismo color.

Necesitas un <ItemLink id="ae2:color_applicator" /> para colorear el conector.

Así que puedes configurar tus conectores inalámbricos de esta manera:

<GameScene zoom="3" background="transparent" interactive={true}>
  <ImportStructure src="../structure/wireless_connector_setup.snbt"></ImportStructure>
</GameScene>


## Uso de Energía

El Conector Inalámbrico ME cuesta más energía cuando están más separados. Su curva de costo-distancia no es lineal, por lo que el costo
de energía puede volverse muy alto si están demasiado separados.

Puedes usar <ItemLink id="ae2:energy_card" /> para ahorrar energía, cada tarjeta puede reducir el costo de energía en un 10%.

