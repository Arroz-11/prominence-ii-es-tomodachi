---
navigation:
  parent: example-setups/example-setups-index.md
  title: Granja Avanzada de Certus
  icon: certus_quartz_crystal
  position: 120
---

# Granja Avanzada de Certus

Esto es básicamente lo mismo que la [Granja de Certus Semi-Automática](semiauto-certus-farm.md), excepto que ha sido completamente integrada en tu
sistema ME.

En lugar de tener un gran almacenamiento de bloques en ciernes y refrescarlos manualmente de vez en cuando,
esta configuración usa [Automatización de Cargador](charger-automation.md) y [Automatización de Lanzar al Agua](throw-in-water-automation.md)
para hacerlo automáticamente.

**ESTA ES UNA CONSTRUCCIÓN COMPLEJA CON COSAS OCULTAS DETRÁS DE OTRAS COSAS, GIRA LA CÁMARA PARA VERLA DESDE TODOS LOS ÁNGULOS**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) Plano de aniquilación #1: Sin GUI para configurar, pero puede encantarse con Fortuna.
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) Bus de almacenamiento #1: Filtrado a Cristal de Cuarzo Certus.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    Subred de rompedor de racimos
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) Plano de aniquilación #2: Sin GUI para configurar, pero encantado con Toque de Seda.
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) Bus de almacenamiento #2: Filtrado a Bloque de Cuarzo Certus.
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    Subred de rompedor de bloques de Certus
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) Plano de formación: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) Bus de importación: Filtrado a Cuarzo Certus en ciernes defectuoso.
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    Subred de colocador de bloques en ciernes
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) Bus de almacenamiento #3: Filtrado a Cristal de Cuarzo Certus. Tiene prioridad establecida más alta que tu almacenamiento principal.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) Interfaz: Configurada para mantener 1 Cuarzo Certus en ciernes defectuoso en sí misma, tiene una Tarjeta de Trabajo.
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        A la red principal, Automatización de Cargador y Automatización de Lanzar al Agua
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## Configuraciones

### Rompedor de Racimos:

* El primer <ItemLink id="annihilation_plane" /> (1) no tiene GUI y no puede configurarse, pero puede encantarse con Fortuna.
* El primer <ItemLink id="storage_bus" /> (2) está filtrado a <ItemLink id="certus_quartz_crystal" />.

### Rompedor de Bloques de Certus:

* El segundo <ItemLink id="annihilation_plane" /> (3) no tiene GUI y no puede configurarse, pero debe encantarse con Toque de Seda.
* El segundo <ItemLink id="storage_bus" /> (4) está filtrado a <ItemLink id="quartz_block" />.

### Colocador de Bloques en Ciernes:

* El <ItemLink id="formation_plane" /> (5) está en su configuración predeterminada.
* El <ItemLink id="import_bus" /> (6) está filtrado a <ItemLink id="flawed_budding_quartz" />.

### En la Red Principal:

* El tercer <ItemLink id="storage_bus" /> (7) está filtrado a <ItemLink id="certus_quartz_crystal" />, y tiene su
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) establecida más alta que tu almacenamiento principal.
* La <ItemLink id="interface" /> (8) está configurada para mantener 1 Cuarzo Certus en ciernes defectuoso en sí misma, y tiene una <ItemLink id="crafting_card" />.

## Cómo Funciona

### Rompedor de Racimos:

La subred de rompedor de racimos funciona de manera muy similar a la subred en la [granja de certus simple](simple-certus-farm.md).

1. El <ItemLink id="annihilation_plane" /> intenta romper lo que está frente a él, pero solo puede romper <ItemLink id="quartz_cluster" />
   porque el único almacenamiento en la subred es el <ItemLink id="storage_bus" />, filtrado a <ItemLink id="certus_quartz_crystal" />.
2. El <ItemLink id="storage_bus" /> almacena los cristales de cuarzo Certus en el barril.

### Rompedor de Bloques de Certus

La subred de rompedor de bloques de Certus sirve para romper el bloque en ciernes agotado una vez que se convierte en un <ItemLink id="quartz_block" /> simple.
Funciona de manera similar al rompedor de racimos.

1. El <ItemLink id="annihilation_plane" /> intenta romper lo que está frente a él, pero solo puede romper <ItemLink id="quartz_block" />
   porque el único almacenamiento en la subred es el <ItemLink id="storage_bus" />, filtrado a <ItemLink id="quartz_block" />.
   El plano necesita tener Toque de Seda, para que el bloque en ciernes no se degrade al romperse, y así el plano no lo rompa prematuramente.
2. El <ItemLink id="storage_bus" /> almacena el bloque de cuarzo Certus en la <ItemLink id="interface" />, permitiendo que la
   [Automatización de Lanzar al Agua](throw-in-water-automation.md) lo use para hacer un nuevo <ItemLink id="flawed_budding_quartz" />.

### Colocador de Bloques en Ciernes

La subred de colocador de bloques en ciernes sirve para colocar un nuevo <ItemLink id="flawed_budding_quartz" /> cuando la subred de rompedor rompe el antiguo agotado.

1. El <ItemLink id="import_bus" /> importa un bloque en ciernes de la <ItemLink id="interface" /> al [almacenamiento de la red](../ae2-mechanics/import-export-storage.md)
2. El único almacenamiento en la subred es el <ItemLink id="formation_plane" />, que coloca el bloque en ciernes.

### En la Red Principal

* El <ItemLink id="storage_bus" /> le da a la red principal (y también a la [Automatización de Cargador](charger-automation.md)) acceso a todos los cristales de cuarzo Certus en el barril. Está configurado con
  [prioridad](../ae2-mechanics/import-export-storage.md#storage-priority) alta para que los cristales de cuarzo Certus se coloquen preferentemente
  de vuelta en el barril en lugar de en tu almacenamiento principal.
* La <ItemLink id="interface" /> le da a la subred de colocador de bloques en ciernes acceso a un <ItemLink id="flawed_budding_quartz" />, y
    le da a la subred de rompedor de bloques de Certus una forma de devolver los bloques agotados a la red principal. La
    <ItemLink id="crafting_card" /> permite que la interfaz solicite nuevos bloques en ciernes del [autocrafteo](../ae2-mechanics/autocrafting.md) de la red principal.