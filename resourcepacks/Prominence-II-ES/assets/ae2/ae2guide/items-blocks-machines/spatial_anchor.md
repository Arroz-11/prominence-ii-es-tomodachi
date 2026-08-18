---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Ancla Espacial
  icon: spatial_anchor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:spatial_anchor
---

# El Ancla Espacial

<BlockImage id="spatial_anchor" p:powered="true" scale="8"/>

Una red de AE2 necesita estar cargada en chunks para que cualquiera de sus [dispositivos](../ae2-mechanics/devices.md) pueda funcionar, y si solo parte de ella está cargada,
puede que no funcione correctamente. El Ancla Espacial resuelve este problema. Fuerza la carga de los chunks que ocupa su red.
Un solo cable que se extienda a través del límite de un chunk es suficiente para cargar ese nuevo chunk.

Propagará su "carga" a través de [puentes cuánticos](quantum_bridge.md), pero no entre dimensiones, así que si
 tienes un puente cuántico al Nether, necesitas un ancla espacial en la red de tu base y en la red del Nether.

Por defecto también activará los ticks aleatorios en los chunks cargados, esto se puede desactivar en la configuración de ae2.

Se puede rotar con una <ItemLink id="certus_quartz_wrench" /> si por alguna razón quieres hacer eso.

## Ajustes

*   El ancla espacial proporciona acceso al ajuste global para ver la energía en AE o E/FE.
*   Se puede mostrar un holograma en el mundo que muestre los chunks que se están cargando.

## Energía

El ancla espacial usará [energía](../ae2-mechanics/energy.md) según esta ecuación:

e = 80 + (x\*(x+1))/2

donde x es el número de chunks que se están cargando

## Receta

<RecipeFor id="spatial_anchor" />
