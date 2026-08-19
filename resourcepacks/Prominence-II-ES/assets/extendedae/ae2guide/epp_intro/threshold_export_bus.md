---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: Bus de Exportación con Umbral ME
    icon: extendedae:threshold_export_bus
categories:
- extended devices
item_ids:
- extendedae:threshold_export_bus
---

# Bus de Exportación con Umbral ME

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_threshold_export_bus.snbt"></ImportStructure>
</GameScene>

El Bus de Exportación con Umbral ME funciona cuando la cantidad de un objeto almacenado en la red ME está por encima o por debajo del umbral.

## Ejemplo

![GUI](../pic/thr_bus_gui1.png)

El umbral del cobre está configurado en 128, por lo que exporta cobre cuando el cobre almacenado en la red supera los 128.

![GUI](../pic/thr_bus_gui2.png)

El umbral es el mismo que arriba, pero el modo está configurado en DEBAJO. Exporta cobre cuando el cobre almacenado está por debajo de 128.