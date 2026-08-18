---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Acelerador de Crecimiento
  icon: growth_accelerator
  position: 310
categories:
- machines
item_ids:
- ae2:growth_accelerator
---

# El Acelerador de Crecimiento

<BlockImage id="growth_accelerator" p:powered="true" scale="8"/>

El Acelerador de Crecimiento acelera masivamente [el crecimiento de](../ae2-mechanics/certus-growth.md) certus o amatista cuando se coloca adyacente al bloque en ciernes.

Curiosamente, *también* puede acelerar el crecimiento de varias plantas.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/growth_accelerator.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Para alimentarlo manualmente, coloca un <ItemLink id="crank" /> en la parte superior o inferior y haz clic derecho en él.

Solo se conecta a cables en sus extremos donde están los greebles de fluix rosa.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/accelerator_connections.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Receta

<RecipeFor id="growth_accelerator" />
