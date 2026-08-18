---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: CPU de crafteo Multibloque (Almacenamiento, Coprocesador, Monitor, Unidad)
  icon: 1k_crafting_storage
  position: 210
categories:
- devices
item_ids:
- ae2:1k_crafting_storage
- ae2:4k_crafting_storage
- ae2:16k_crafting_storage
- ae2:64k_crafting_storage
- ae2:256k_crafting_storage
- ae2:crafting_accelerator
- ae2:crafting_monitor
- ae2:crafting_unit
---

# La CPU de crafteo

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="crafting_accelerator" scale="4" />

  <BlockImage id="crafting_monitor" scale="4" />

  <BlockImage id="crafting_unit" scale="4" />
</Row>

Las CPUs de crafteo gestionan solicitudes/trabajos de crafteo. Almacenan los ingredientes intermedios mientras se llevan a cabo trabajos de crafteo con múltiples pasos, y afectan qué tan grandes pueden ser los trabajos y, hasta cierto punto, qué tan rápido se completan. Consulta [autocrafteo](../ae2-mechanics/autocrafting.md) para más detalles.

Cada CPU de crafteo maneja 1 solicitud o trabajo, así que si quieres solicitar a la vez un procesador de cálculo y 256 piedra lisa, necesitas 2 multibloques de CPU.

Se pueden configurar para manejar solicitudes de jugadores, de automatización (bus de exportación e interfaces), o de ambos.

Al hacer clic derecho en una, se abre una interfaz de estado de crafteo donde puedes ver el progreso del trabajo de crafteo que la CPU está manejando.

## Ajustes

*   La CPU se puede configurar para aceptar solicitudes solo de jugadores, solo de automatización (como <ItemLink id="export_bus" />ses con <ItemLink id="crafting_card" />s), o de ambos.

## Construcción

Las CPUs de crafteo son multibloques y deben ser prismas rectangulares sólidos sin huecos. Están hechas de varios componentes.

Cada CPU debe contener al menos 1 bloque de almacenamiento de crafteo (y la CPU mínima viable es, de hecho, solo un almacenamiento de crafteo de 1k).

# Unidad de Creación

<BlockImage id="crafting_unit" scale="4" />

(Opcional) Las unidades de creación simplemente llenan espacio en una CPU para hacerla un prisma rectangular sólido, si no tienes suficientes de los otros componentes. También son un ingrediente base en los otros componentes.

<RecipeFor id="crafting_unit" />

# Almacenamiento de crafteo

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="4k_crafting_storage" scale="4" />

  <BlockImage id="16k_crafting_storage" scale="4" />

  <BlockImage id="64k_crafting_storage" scale="4" />

  <BlockImage id="256k_crafting_storage" scale="4" />
</Row>

(Obligatorio) Los almacenamientos de crafteo están disponibles en todos los tamaños de celda estándar (1k, 4k, 16k, 64k, 256k). Almacenan los ingredientes e ingredientes intermedios involucrados en un crafteo, por lo que se requieren almacenamientos más grandes o más numerosos para que la CPU maneje trabajos de crafteo con más ingredientes.

<Column>
  <Row>
    <RecipeFor id="1k_crafting_storage" />

    <RecipeFor id="4k_crafting_storage" />

    <RecipeFor id="16k_crafting_storage" />
  </Row>

  <Row>
    <RecipeFor id="64k_crafting_storage" />

    <RecipeFor id="256k_crafting_storage" />
  </Row>
</Column>

# Unidad de Coprocesamiento de Crafteo

<BlockImage id="crafting_accelerator" scale="4" />

(Opcional) Los coprocesadores de crafteo hacen que el sistema envíe lotes de ingredientes desde <ItemLink id="pattern_provider" />s con más frecuencia. Esto les permite mantenerse al día con máquinas que procesan rápidamente. Un ejemplo de esto es un proveedor de patrones rodeado de <ItemLink id="molecular_assembler" />s que puede empujar ingredientes más rápido de lo que un solo ensamblador puede procesar, y así distribuir los lotes de ingredientes entre los ensambladores circundantes.

<RecipeFor id="crafting_accelerator" />

# Monitor de Trabajo

<BlockImage id="crafting_monitor" scale="4" />

(Opcional) El monitor de trabajo muestra el trabajo que la CPU está manejando en ese momento. La pantalla se puede colorear con un <ItemLink id="color_applicator" />.

<RecipeFor id="crafting_monitor" />
