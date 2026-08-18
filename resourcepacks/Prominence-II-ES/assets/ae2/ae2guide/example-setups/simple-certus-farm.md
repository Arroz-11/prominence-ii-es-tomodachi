---
navigation:
  parent: example-setups/example-setups-index.md
  title: Granja de Cuarzo Certus Simple
  icon: certus_quartz_crystal
  position: 110
---

# Granja de Cuarzo Certus Simple

Como se mencionó en [Crecimiento del Cuarzo Certus](../ae2-mechanics/certus-growth.md), la automatización de la cosecha de <ItemLink id="certus_quartz_crystal" />
implica <ItemLink id="annihilation_plane" />s y <ItemLink id="storage_bus" />ses.
Los <ItemLink id="growth_accelerator" />s se usan para acelerar masivamente el crecimiento de los brotes de cuarzo Certus, y luego los planos
rompen el <ItemLink id="quartz_cluster" /> completamente crecido. Se filtran aprovechando el rasgo sospechosamente afortunado de que los brotes de Certus no maduros
tiran <ItemLink id="certus_quartz_dust" /> en lugar de no tirar nada.

Esta granja funciona completamente automática con <ItemLink id="flawless_budding_quartz" />, pero con cuarzo Certus brotante defectuoso, astillado y dañado
tendrás que reemplazar el bloque brotante manualmente. O, como se describe en [Granja de Cuarzo Certus Semiautomática](semiauto-certus-farm.md)
y [Granja de Cuarzo Certus Avanzada](advanced-certus-farm.md), automáticamente.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/simple_certus_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="3.7 1 1" max="4 2 2">
        (1) Plano de Aniquilación: Sin GUI para configurar, pero puede encantarse con Fortuna.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="3.3 2 2">
        (2) Bus de Almacenamiento #1: Filtrado a Cristal de Cuarzo Certus.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 .7" max="2 2 1">
        (3) Bus de Almacenamiento #2: Filtrado a Cristal de Cuarzo Certus. Tiene prioridad más alta que el almacenamiento principal.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* El primer <ItemLink id="annihilation_plane" /> (1) no tiene GUI y no puede configurarse, pero puede encantarse con Fortuna.
* El primer <ItemLink id="storage_bus" /> (2) está filtrado a <ItemLink id="certus_quartz_crystal" />.
* El segundo <ItemLink id="storage_bus" /> (3) está filtrado a <ItemLink id="certus_quartz_crystal" />, y tiene su
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) establecida más alta que el almacenamiento principal.

## Cómo Funciona

1. El <ItemLink id="annihilation_plane" /> intenta romper lo que está frente a él, pero solo puede romper <ItemLink id="quartz_cluster" />
   porque el único almacenamiento en la subred es el <ItemLink id="storage_bus" />, filtrado a <ItemLink id="certus_quartz_crystal" />.
4. El primer <ItemLink id="storage_bus" /> almacena los cristales de cuarzo Certus en el barril.
5. El segundo <ItemLink id="storage_bus" /> le da a la red principal acceso a todos los cristales de cuarzo Certus en el barril. Está configurado con
   [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) alta para que los cristales de cuarzo Certus se coloquen preferentemente
   de vuelta en el barril en lugar de en tu almacenamiento principal.
