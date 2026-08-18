---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Tarjetas de Mejora
  icon: speed_card
  position: 410
categories:
- tools
item_ids:
- ae2:basic_card
- ae2:advanced_card
- ae2:redstone_card
- ae2:capacity_card
- ae2:void_card
- ae2:fuzzy_card
- ae2:speed_card
- ae2:inverter_card
- ae2:crafting_card
- ae2:equal_distribution_card
- ae2:energy_card
---

# Tarjetas de Mejora

<Row>
  <ItemImage id="redstone_card" scale="2" />

  <ItemImage id="capacity_card" scale="2" />

  <ItemImage id="void_card" scale="2" />

  <ItemImage id="fuzzy_card" scale="2" />

  <ItemImage id="speed_card" scale="2" />

  <ItemImage id="inverter_card" scale="2" />

  <ItemImage id="crafting_card" scale="2" />

  <ItemImage id="equal_distribution_card" scale="2" />

  <ItemImage id="energy_card" scale="2" />
</Row>

Las tarjetas de mejora cambian el comportamiento de los [dispositivos](../ae2-mechanics/devices.md) y máquinas de AE2, aumentando su velocidad, mejorando su capacidad de filtro, habilitando el control de redstone, etc.

## Componentes de las tarjetas

<Row>
  <ItemImage id="basic_card" scale="2" />

  <ItemImage id="advanced_card" scale="2" />
</Row>

Las tarjetas se fabrican con bases de tarjeta básicas o avanzadas

<Row>
  <RecipeFor id="basic_card" />

  <RecipeFor id="advanced_card" />
</Row>

## Tarjeta de Redstone

<ItemImage id="redstone_card" scale="2" />

Las tarjetas de redstone añaden control de redstone, agregando un botón de alternancia en la interfaz del dispositivo para cambiar entre varias condiciones de redstone.

<RecipeFor id="redstone_card" />

## Tarjeta de Capacidad

<ItemImage id="capacity_card" scale="2" />

Las tarjetas de capacidad aumentan la cantidad de ranuras de filtro en los buses de importación, exportación y almacenamiento, y en los planos de formación.

<RecipeFor id="capacity_card" />

## Tarjeta de Destrucción de Desbordamiento

<ItemImage id="void_card" scale="2" />

Las tarjetas de destrucción de desbordamiento se pueden aplicar a [celdas de almacenamiento](storage_cells.md) en un <ItemLink id="cell_workbench" /> y eliminarán los elementos entrantes si la celda está llena. (¡asegúrate de [particionar](cell_workbench.md) tus celdas!) Combinadas con una tarjeta de distribución equitativa, los elementos se anularán si la sección de esa celda específica está llena, incluso si las secciones de otros elementos están vacías.

<RecipeFor id="void_card" />

## Tarjeta Difusa

<ItemImage id="fuzzy_card" scale="2" />

Las tarjetas difusas permiten que los dispositivos y herramientas con filtros filtren por nivel de daño y/o ignoren el NBT del elemento, lo que te permite exportar todas las hachas de hierro sin importar el nivel de daño y los encantamientos, o solo exportar espadas de diamante dañadas, no las completamente reparadas.

A continuación se muestra un ejemplo de cómo funcionan los modos de comparación de daño difuso, el lado izquierdo es la configuración del bus, la parte superior es el elemento comparado.

| 25%                    | Pico dañado al 10% | Pico dañado al 30% | Pico dañado al 80% | Pico completamente reparado |
| ---------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
| Pico casi roto         | ✅                   | \*\*\*\*            | \*\*\*\*            | \*\*\*\*            |
| Pico completamente reparado | \*\*\*\*            | ✅                   | ✅                   | ✅                   |

| 50%                    | Pico dañado al 10% | Pico dañado al 30% | Pico dañado al 80% | Pico completamente reparado |
| ---------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
| Pico casi roto         | ✅                   | ✅                   | \*\*\*\*            | \*\*\*\*            |
| Pico completamente reparado | \*\*\*\*            | \*\*\*\*            | ✅                   | ✅                   |

| 75%                    | Pico dañado al 10% | Pico dañado al 30% | Pico dañado al 80% | Pico completamente reparado |
| ---------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
| Pico casi roto         | ✅                   | ✅                   | \*\*\*\*            | \*\*\*\*            |
| Pico completamente reparado | \*\*\*\*            |                     | ✅                   | ✅                   |

| 99%                    | Pico dañado al 10% | Pico dañado al 30% | Pico dañado al 80% | Pico completamente reparado |
| ---------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
| Pico casi roto         | ✅                   | ✅                   | ✅                   | \*\*\*\*            |
| Pico completamente reparado | \*\*\*\*            | \*\*\*\*            | \*\*\*\*            | ✅                   |

| Ignorar                | Pico dañado al 10% | Pico dañado al 30% | Pico dañado al 80% | Pico completamente reparado |
| ---------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
| Pico casi roto         | ✅                   | ✅                   | ✅                   | **✅**               |
| Pico completamente reparado | **✅**               | **✅**               | **✅**               | ✅                   |

<RecipeFor id="fuzzy_card" />

## Tarjeta de Aceleración

<ItemImage id="speed_card" scale="2" />

Las tarjetas de aceleración hacen que las cosas vayan más rápido, haciendo que los buses de importación y exportación muevan más elementos por operación, y haciendo que los inscriptores y ensambladores trabajen más rápido.

<RecipeFor id="speed_card" />

## Tarjeta Inversora

<ItemImage id="inverter_card" scale="2" />

Las tarjetas inversoras cambian los filtros en dispositivos y herramientas de lista blanca a lista negra.

<RecipeFor id="inverter_card" />

## Tarjeta de Trabajo

<ItemImage id="crafting_card" scale="2" />

Las tarjetas de trabajo permiten que el dispositivo envíe solicitudes de crafteo a tu sistema de [autocrafteo](../ae2-mechanics/autocrafting.md) para obtener los elementos que desea.

<RecipeFor id="crafting_card" />

## Tarjeta de Distribución Equitativa

<ItemImage id="equal_distribution_card" scale="2" />

Las tarjetas de distribución equitativa se pueden aplicar a [celdas de almacenamiento](storage_cells.md) en un <ItemLink id="cell_workbench" /> y dividen la celda en secciones del mismo tamaño según lo que la tarjeta está [particionada](cell_workbench.md). Esto evita que un tipo de elemento llene completamente la celda.

<RecipeFor id="equal_distribution_card" />

## Tarjeta de Energía

<ItemImage id="energy_card" scale="2" />

Las tarjetas de energía añaden más almacenamiento de energía a ciertas herramientas como terminales portátiles, y hacen que las <ItemLink id="vibration_chamber" />s sean más eficientes.

<RecipeFor id="energy_card" />
