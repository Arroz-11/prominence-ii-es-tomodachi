---
navigation:
  parent: example-setups/example-setups-index.md
  title: Granja de Cuarzo Certus Semiautomática
  icon: certus_quartz_crystal
  position: 110
---

# Granja de Cuarzo Certus Semiautomática

Desafortunadamente, la [granja de cuarzo Certus simple](simple-certus-farm.md) requiere un <ItemLink id="flawless_budding_quartz" /> para funcionar completamente
automática. Esto requiere ya sea [IO Espacial](../ae2-mechanics/spatial-io.md) o construir la granja en el [meteorito](../ae2-mechanics/meteorites.md).

Sin embargo, AE2 puede colocar y romper bloques, así que podría ser posible hacer que tu granja *reemplace el cuarzo Certus brotante por ti*. (Tendrás que insertar periódicamente algo de <ItemLink id="flawed_budding_quartz" /> en el barril de entrada y extraer <ItemLink id="quartz_block" /> del barril de cuarzo brotante agotado).

Para hacer esto completamente automático, consulta [Granja de Cuarzo Certus Avanzada](advanced-certus-farm.md).

Esta granja es un poco más compleja que la [granja de cuarzo Certus simple](simple-certus-farm.md), porque en realidad son 3 configuraciones separadas combinadas.

**ESTA ES UNA CONSTRUCCIÓN COMPLEJA CON COSAS OCULTAS DETRÁS DE OTRAS COSAS, GIRA LA CÁMARA PARA VERLA DESDE TODOS LOS ÁNGULOS**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/semiauto_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) Plano de Aniquilación #1: Sin GUI para configurar, pero puede encantarse con Fortuna.
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1" max="2.3 3 2">
        (2) Bus de Almacenamiento #1: Filtrado a Cristal de Cuarzo Certus.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    Subred Rompedora de Racimos
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) Plano de Aniquilación #2: Sin GUI para configurar, pero encantado con Toque de Seda.
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1" max="2.3 2 2">
        (4) Bus de Almacenamiento #2: Filtrado a Bloque de Cuarzo Certus.
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    Subred Rompedora de Bloques Certus
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) Plano de Formación: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0 1" max="2.3 1 2">
        (6) Bus de Importación: En su configuración predeterminada.
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    Subred Colocadora de Bloques Brotantes
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="0.7 2 1" max="1 3 2">
        (7) Bus de Almacenamiento #3: Filtrado a Cristal de Cuarzo Certus. Tiene prioridad más alta que tu almacenamiento principal.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

    <DiamondAnnotation pos="1.5 0.5 1.5" color="#00ff00">
        Inserta manualmente Cuarzo Certus Brotante Defectuoso.
        <BlockImage id="flawed_budding_quartz" scale="2" />
    </DiamondAnnotation>

    <DiamondAnnotation pos="1.5 1.5 1.5" color="#00ff00">
        Extrae manualmente Bloque de Cuarzo Certus.
        <BlockImage id="quartz_block" scale="2" />
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## Configuraciones

### Rompedor de Racimos:

* El primer <ItemLink id="annihilation_plane" /> (1) no tiene GUI y no puede configurarse, pero puede encantarse con Fortuna.
* El primer <ItemLink id="storage_bus" /> (2) está filtrado a <ItemLink id="certus_quartz_crystal" />.

### Rompedor de Bloques Certus:

* El segundo <ItemLink id="annihilation_plane" /> (3) no tiene GUI y no puede configurarse, pero debe encantarse con Toque de Seda.
* El segundo <ItemLink id="storage_bus" /> (4) está filtrado a <ItemLink id="quartz_block" />.

### Colocador de Bloques Brotantes:

* El <ItemLink id="formation_plane" /> (5) está en su configuración predeterminada.
* El <ItemLink id="import_bus" /> (6) está en su configuración predeterminada.

### En la Red Principal:

* El tercer <ItemLink id="storage_bus" /> (7) está filtrado a <ItemLink id="certus_quartz_crystal" />, y tiene su
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) establecida más alta que tu almacenamiento principal.

## Cómo Funciona

### Rompedor de Racimos:

La subred rompedora de racimos funciona de manera muy similar a la subred en la [granja de cuarzo Certus simple](simple-certus-farm.md).

1. El <ItemLink id="annihilation_plane" /> intenta romper lo que está frente a él, pero solo puede romper <ItemLink id="quartz_cluster" />
   porque el único almacenamiento en la subred es el <ItemLink id="storage_bus" />, filtrado a <ItemLink id="certus_quartz_crystal" />.
2. El <ItemLink id="storage_bus" /> almacena los cristales de cuarzo Certus en el barril.

### Rompedor de Bloques Certus

La subred rompedora de bloques Certus sirve para romper el bloque brotante agotado una vez que se convierte en un <ItemLink id="quartz_block" /> simple.
Funciona de manera similar al rompedor de racimos.

1. El <ItemLink id="annihilation_plane" /> intenta romper lo que está frente a él, pero solo puede romper <ItemLink id="quartz_block" />
   porque el único almacenamiento en la subred es el <ItemLink id="storage_bus" />, filtrado a <ItemLink id="quartz_block" />.
   El plano necesita tener Toque de Seda, para que el bloque brotante no se degrade al romperse, y así el plano no lo rompa prematuramente.
2. El <ItemLink id="storage_bus" /> almacena el bloque de cuarzo Certus en el barril de cuarzo brotante agotado; tendrás que tirarlo manualmente al agua con <ItemLink id="charged_certus_quartz_crystal" /> para regenerarlo.

### Colocador de Bloques Brotantes

La subred colocadora de bloques brotantes sirve para colocar un nuevo <ItemLink id="flawed_budding_quartz" /> cuando la subred rompedora rompe el bloque agotado anterior.

1. El <ItemLink id="import_bus" /> importa un bloque brotante del barril de entrada.
2. El único almacenamiento en la subred es el <ItemLink id="formation_plane" />, que coloca el bloque brotante.

### En la Red Principal

* El <ItemLink id="storage_bus" /> le da a la red principal (y también a la [Automatización del Cargador](charger-automation.md)) acceso a todos los cristales de cuarzo Certus en el barril. Está configurado con
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) alta para que los cristales de cuarzo Certus se coloquen preferentemente
  de vuelta en el barril en lugar de en tu almacenamiento principal.