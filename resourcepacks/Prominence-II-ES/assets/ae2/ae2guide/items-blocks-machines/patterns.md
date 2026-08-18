---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Patterns
  icon: crafting_pattern
  position: 410
categories:
- tools
item_ids:
- ae2:blank_pattern
- ae2:crafting_pattern
- ae2:processing_pattern
- ae2:smithing_table_pattern
- ae2:stonecutting_pattern
---

# Patrones

<ItemImage id="crafting_pattern" scale="4" />

Los patrones se crean en un <ItemLink id="pattern_encoding_terminal" /> a partir de patrones en blanco, y se insertan en <ItemLink id="pattern_provider" />s o <ItemLink id="molecular_assembler" />s.

Hay varios tipos diferentes de patrones para diferentes cosas:

*   Los <ItemLink id="crafting_pattern" /> codifican recetas hechas en una mesa de crafteo. Se pueden poner directamente en un <ItemLink id="molecular_assembler" /> para que craftee el resultado cuando se le den los ingredientes, pero su uso principal es en un <ItemLink id="pattern_provider" /> junto a un ensamblador molecular. Los proveedores de patrones tienen un comportamiento especial en este caso, y enviarán el patrón relevante junto con los ingredientes a los ensambladores adyacentes. Como los ensambladores expulsan automáticamente los resultados de los crafteos a inventarios adyacentes, un ensamblador en un proveedor de patrones es todo lo que se necesita para automatizar los patrones de crafteo.

***

*   Los <ItemLink id="smithing_table_pattern" /> son muy similares a los patrones de crafteo, pero codifican recetas de mesa de herrería. También se automatizan con un proveedor de patrones y un ensamblador molecular, y funcionan exactamente de la misma manera. De hecho, los patrones de crafteo, herrería y corte de piedra se pueden usar en la misma configuración.

***

*   Los <ItemLink id="stonecutting_pattern" /> son muy similares a los patrones de crafteo, pero codifican recetas de cortapiedras. También se automatizan con un proveedor de patrones y un ensamblador molecular, y funcionan exactamente de la misma manera. De hecho, los patrones de crafteo, herrería y corte de piedra se pueden usar en la misma configuración.

***

*   Los <ItemLink id="processing_pattern" /> son de donde proviene mucha flexibilidad en el autocrafteo. Son el tipo más generalizado, simplemente dicen "si un proveedor de patrones empuja estos ingredientes a inventarios adyacentes, el sistema ME recibirá estos ítems en algún momento en el futuro cercano o lejano". Así es como automatizarás con casi cualquier máquina moddeada, o hornos y similares. Debido a que son tan generales en uso y no les importa qué sucede entre empujar ingredientes y recibir el resultado, puedes hacer cosas realmente extrañas, como ingresar los ingredientes en una cadena de producción de fábrica compleja que se encargará de las cosas, tomar otros ingredientes de granjas de producción infinita, imprimir el guion completo de Bee Movie, al sistema ME no le importa siempre que obtenga el resultado que especifica el patrón. De hecho, ni siquiera le importa si los ingredientes están relacionados de alguna manera con el resultado. Podrías decirle "1 tablón de madera de cerezo = 1 estrella del Nether" y tener tu granja de withers matando a un wither al recibir un tablón de madera de cerezo y funcionaría.

Se admiten múltiples <ItemLink id="pattern_provider" /> con patrones idénticos y funcionan en paralelo. Además, puedes tener un patrón que diga, por ejemplo, 8 piedra = 8 piedra lisa en lugar de 1 piedra = 1 piedra lisa, y el proveedor de patrones insertará 8 piedra en tu configuración de fundición en cada operación en lugar de una a la vez.

## Receta

<RecipeFor id="blank_pattern" />
