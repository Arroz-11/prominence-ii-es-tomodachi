---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Crecimiento de Certus
  icon: quartz_cluster
---

# Crecimiento de Certus

## Básicamente copiado de la página de inicio

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_1.snbt" />
</GameScene>

Los brotes de cuarzo Certus brotarán de los [bloques de Certus brotante](../items-blocks-machines/budding_certus.md), similar al amatista. Si rompes un brote que no ha terminado de crecer, soltará un <ItemLink id="certus_quartz_dust" />, sin cambios por fortuna. Si rompes un racimo completamente crecido, soltará cuatro <ItemLink id="certus_quartz_crystal" />s, y la fortuna aumentará este número.

Hay 4 niveles de bloques de Certus brotante: Impecable, Imperfecto, Agrietado y Dañado.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Cada vez que un brote crece otra etapa, el bloque brotante tiene una probabilidad de degradarse un nivel, eventualmente convirtiéndose en un bloque de cuarzo Certus normal. Pueden repararse (y crear nuevos bloques brotantes) lanzando el bloque brotante (o un bloque de cuarzo Certus) en agua con uno o más <ItemLink id="charged_certus_quartz_crystal" />.

<RecipeFor id="damaged_budding_quartz" />

Los bloques de Certus brotante impecables no se degradarán y generarán Certus infinitamente. Sin embargo, no pueden craftearse ni moverse con un pico, incluso con toque de seda. (aunque *pueden* moverse con [almacenamiento espacial](../ae2-mechanics/spatial-io.md))

Por sí solos, los brotes de cuarzo Certus crecen muy lentamente. Afortunadamente, el <ItemLink id="growth_accelerator" /> acelera masivamente este proceso cuando se coloca adyacente al bloque brotante. Deberías construir algunos de estos como tu primera prioridad.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_certus_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Si no tienes suficiente cuarzo para hacer también un <ItemLink id="energy_acceptor" /> o una <ItemLink id="vibration_chamber" />, puedes hacer una <ItemLink id="crank" /> y ponerla en el extremo de tu acelerador.

La cosecha automática del Certus se describe [aquí](../example-setups/simple-certus-farm.md).