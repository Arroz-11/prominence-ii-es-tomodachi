---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Monitores
  icon: storage_monitor
  position: 210
categories:
- devices
item_ids:
- ae2:storage_monitor
- ae2:conversion_monitor
---

# Monitores

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/monitors.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Los monitores permiten visualizar e interactuar con un solo tipo de objeto o fluido, sin abrir una interfaz gráfica.

Los monitores heredarán el color del [cable](cables.md) en el que estén montados.

Si el monitor está en el suelo o en el techo, puedes rotarlo con una <ItemLink id="certus_quartz_wrench" />.

Son [subpartes de cable](../ae2-mechanics/cable-subparts.md).

# Monitor de Almacenamiento

Mostrará un objeto o fluido y su cantidad. Colócalos junto a tus granjas o algo así...

*No* requiere un [canal](../ae2-mechanics/channels.md).

Teclas:

*   Clic derecho con un objeto o doble clic derecho con un contenedor de fluido para configurar el monitor a ese objeto/fluido.
*   Clic derecho con la mano vacía para limpiar el monitor.
*   Mayús izdo. + clic derecho con la mano vacía para bloquear el monitor.

## Receta

<RecipeFor id="storage_monitor" />

# Monitor de Conversión

El Monitor de Conversión es similar a un monitor de almacenamiento, pero te permite insertar o extraer su objeto configurado.

Si el objeto configurado es [autocrafteable](../ae2-mechanics/autocrafting.md) y no hay ninguno en el almacenamiento, al intentar tomar un
objeto se abrirá una interfaz para especificar la cantidad a craftear.

*Sí* requiere un [canal](../ae2-mechanics/channels.md).

Teclas adicionales:

*   Clic izquierdo para extraer un stack del objeto configurado, o solicitar el crafteo de ese objeto si no hay ninguno en el almacenamiento.
*   Clic derecho con cualquier objeto para insertar ese objeto.
*   Clic derecho con la mano vacía para insertar todo el objeto configurado desde tu inventario.

## Receta

<RecipeFor id="conversion_monitor" />
