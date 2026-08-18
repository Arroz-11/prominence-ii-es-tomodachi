---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Cargador
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# El Cargador

<BlockImage id="charger" scale="8" />

El Cargador proporciona una forma de cargar
herramientas compatibles y <ItemLink id="certus_quartz_crystal" />.

La energía se puede suministrar por la parte superior o inferior, ya sea a través de los [cables](cables.md) de AE2 u otros cables de energía de otros mods. Puede
aceptar tanto energía de AE2 (AE) como Energía Forge (FE). Los objetos se pueden insertar o extraer de cualquier lado. Solo se pueden extraer los resultados,
así que no necesitas filtros para evitar extraer cristales de certus en lugar de certus cargado. Se puede rotar con una
<ItemLink id="certus_quartz_wrench" /> para facilitar la automatización.

Se puede usar para crear <ItemLink id="charged_certus_quartz_crystal" />
a partir de <ItemLink id="certus_quartz_crystal" />, y <ItemLink id="meteorite_compass" /> a partir de <ItemLink id="minecraft:compass" />.

Para alimentarlo manualmente, coloca un <ItemLink id="crank" /> en la parte superior o inferior y haz clic derecho hasta que el objeto esté cargado.

También actúa como la estación de trabajo para el aldeano de AE2.

## Automatización simple

Como ejemplo, la capacidad de rotación te permite semi-automatizar cargadores así:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/charger_hopper.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Receta

<RecipeFor id="charger" />
