---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Cuarzo Certus en Ciernes
  icon: flawless_budding_quartz
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:flawless_budding_quartz
- ae2:flawed_budding_quartz
- ae2:chipped_budding_quartz
- ae2:damaged_budding_quartz
- ae2:small_quartz_bud
- ae2:medium_quartz_bud
- ae2:large_quartz_bud
- ae2:quartz_cluster
---

# Cuarzo Certus en Ciernes

(también ver [Crecimiento de Certus](../ae2-mechanics/certus-growth.md))

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Los brotes de cuarzo certus brotarán de bloques de certus en ciernes, similar a la amatista. Estos se encuentran en [meteoritos](../ae2-mechanics/meteorites.md).
Hay 4 niveles de bloques de certus en ciernes: Impecable, Defectuoso, Astillado y Dañado. Se pueden identificar más fácilmente
con un mod como HWYLA, Jade, The One Probe, etc. (o la pantalla f3)

Con certus en ciernes defectuoso, astillado y dañado, cada vez que un brote crece una etapa más, el bloque en ciernes tiene una probabilidad
de degradarse un nivel, eventualmente convirtiéndose en un <ItemLink id="quartz_block" /> normal.

El certus en ciernes impecable no se degradará por el crecimiento de brotes, y actúa como una fuente infinita.

Si se rompe con un pico normal, los bloques de certus en ciernes se degradarán 1 nivel. Si se rompe con un pico
encantado con toque de seda, no se degradarán, a menos que fueran impecables. **Esto significa que los bloques de certus en ciernes impecables no pueden
ser recogidos y movidos con un pico**. En su lugar, [Almacenamiento Espacial](../ae2-mechanics/spatial-io.md) puede ser usado para
cortar y pegar los bloques impecables en ciernes.

## Recetas

El certus en ciernes defectuoso, astillado y dañado puede ser crafteado lanzando el nivel anterior de bloque en ciernes (o un <ItemLink id="quartz_block" />)
en agua con uno o más <ItemLink id="charged_certus_quartz_crystal" />.

El certus en ciernes impecable no puede ser crafteado, solo encontrado en el mundo.

<Row>
  <RecipeFor id="damaged_budding_quartz" />

  <RecipeFor id="chipped_budding_quartz" />

  <RecipeFor id="flawed_budding_quartz" />
</Row>
