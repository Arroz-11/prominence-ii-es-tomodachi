---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Condensador de Materia
  icon: condenser
  position: 310
categories:
- machines
item_ids:
- ae2:condenser
---

# El Condensador de Materia

<BlockImage id="condenser" scale="8" />

El condensador de materia puede usarse como un bote de basura o para crear <ItemLink id="matter_ball" />s y
[singularidades](singularities.md). Puede aceptar cualquier objeto, fluido, etc. que una celda de almacenamiento pueda almacenar.

## Ajustes/Recetas

*   En modo bote de basura, el condensador de materia simplemente anula todo lo que entra
*   En modo bola de materia, el condensador hace <ItemLink id="matter_ball" />s con lo que pongas en él.
    Este modo requiere que pongas un componente de almacenamiento en la ranura superior del condensador. Las bolas de materia requieren 256 objetos o cubos
    cada una, por lo que un <ItemLink id="cell_component_1k" /> (que proporciona 8192 bits de capacidad) es más que suficiente.
*   En modo singularidad de materia, el condensador hace [singularidades](singularities.md) con lo que pongas en él.
    Este modo requiere que pongas un componente de almacenamiento en la ranura superior del condensador. Las singularidades requieren 256,000 objetos o cubos
    cada una, por lo que un <ItemLink id="cell_component_64k" /> (que proporciona 524,288 bits de capacidad) es más que suficiente.

Nota que en los últimos dos modos donde se produce algún recurso, el Condensador de Materia *puede* atascarse y no
aceptará más entrada si tanto el búfer de energía como el de salida de objetos están completamente llenos.

## Receta

<RecipeFor id="condenser" />
