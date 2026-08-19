---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: Bus de Exportación Preciso ME
    icon: extendedae:precise_export_bus
categories:
- extended devices
item_ids:
- extendedae:precise_export_bus
---

# Bus de Exportación Preciso ME

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_precise_export_bus.snbt"></ImportStructure>
</GameScene>

El Bus de Exportación Preciso ME exporta objetos/fluidos en cantidades específicas. Solo exporta si el contenedor puede aceptar completamente la salida total.

## Ejemplo

![GUI](../pic/pre_bus_gui1.png)

Esto significa exportar 3 piedras por operación. Se detiene cuando la cantidad de piedras en la red es menor a 3.

![GUI](../pic/pre_bus_gui2.png)

También se detiene cuando el contenedor de destino no puede contener todo lo que exporta. El cofre solo puede contener 2 piedras más ahora, así que el bus de exportación se detiene.
