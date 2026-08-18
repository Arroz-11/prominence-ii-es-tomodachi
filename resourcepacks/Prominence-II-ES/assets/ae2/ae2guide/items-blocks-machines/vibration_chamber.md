---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Cámara de Vibración
  icon: vibration_chamber
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:vibration_chamber
---

# La Cámara de Vibración

<BlockImage id="vibration_chamber" p:active="true" scale="8" />

Si bien el método principal previsto para proporcionar [energía](../ae2-mechanics/energy.md) a tu red es un <ItemLink id="energy_acceptor" />, la cámara de vibración puede generar directamente cantidades pequeñas a medianas de AE.

Por defecto (sin [mejoras](upgrade_cards.md) y configuraciones predeterminadas) produce 40 AE/t.

Cuando el almacenamiento de [energía](../ae2-mechanics/energy.md) de la red está lleno, la cámara de vibración reduce su velocidad para conservar combustible, pero no puede apagarse por completo.

## Ajustes

*   La cámara de vibración proporciona acceso a la configuración global para ver la energía en AE o E/FE.

## Mejoras

La cámara de vibración admite las siguientes [mejoras](upgrade_cards.md):

*   <ItemLink id="energy_card" /> aumenta la eficiencia de la cámara en +50%, hasta un máximo de +150%, o 250% de la eficiencia base.
*   <ItemLink id="speed_card" /> aumenta la velocidad de combustión de la cámara en +50%, hasta un máximo de +150%, o 250% de la producción de energía base.

## Configuración

Las propiedades de la cámara de vibración se pueden editar en common.json en la carpeta ae2 dentro de la carpeta de configuración de tu directorio .minecraft\

*   baseEnergyPerFuelTick establece la eficiencia base, sin mejoras, de la cámara de vibración.
*   minEnergyPerGameTick establece la generación de energía más baja posible (la cámara siempre usará algo de combustible incluso si la red no requiere energía).
*   maxEnergyPerGameTick establece la salida máxima (y velocidad) sin mejoras de la cámara de vibración.

## Receta

<RecipeFor id="vibration_chamber" />
