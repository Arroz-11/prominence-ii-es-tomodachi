---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Autocrafteo
  icon: pattern_provider
---

# Autocrafteo

### El Gran Tema

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/autocraft_setup_greebles.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

El autocrafteo es una de las funciones principales de AE2. En lugar de tener que craftear manualmente la cantidad correcta de cada sub-ingrediente
y trabajar como un *plebeyo*, puedes pedirle a tu sistema ME que lo haga por ti. O craftear automáticamente objetos y exportarlos a algún lugar.
O mantener automáticamente ciertas cantidades de objetos en stock mediante un comportamiento emergente inteligente. También funciona con fluidos y, si tienes
ciertos addons para tipos de material extra de mods, como los gases de Mekanism, también con esos materiales. Es bastante genial.

Es un tema bastante complejo, así que abróchate el cinturón y vamos.

Una configuración de autocrafteo consta de 3 cosas:
- La cosa que envía la solicitud de crafteo
- La CPU de crafteo
- El <ItemLink id="pattern_provider" />.

Esto es lo que sucede:

1.  Algo crea una solicitud de crafteo. Puedes ser tú en la terminal haciendo clic en algo autocrafteable,
    o un bus de exportación o interfaz con una tarjeta de crafteo solicitando uno de los objetos que están configurados para exportar/mantener en stock.

*   (**IMPORTANTE:** usa lo que tengas vinculado a "seleccionar bloque" (generalmente el botón central del ratón) para solicitar crafteos de algo que ya tengas en stock, esto puede entrar en conflicto con los mods de ordenación de inventario),

2.  El sistema ME calcula los ingredientes requeridos y los pasos de crafteo previos para cumplir la solicitud, y los almacena en la CPU de crafteo seleccionada.

3.  El <ItemLink id="pattern_provider" /> con el [patrón](../items-blocks-machines/patterns.md) relevante empuja los ingredientes especificados en el patrón a cualquier inventario adyacente.
    En el caso de una receta de mesa de crafteo (un "patrón de crafteo"), esto será una <ItemLink id="molecular_assembler" />.
    En el caso de una receta que no es de crafteo (un "patrón de procesamiento"), esto será algún otro bloque, máquina o configuración elaborada controlada por redstone.

4.  El resultado del crafteo se devuelve al sistema de alguna manera, ya sea mediante un bus de importación, interfaz, o empujando el resultado de vuelta a un proveedor de patrones.
    **Ten en cuenta que debe ocurrir un evento de "objeto entrando al sistema", no puedes simplemente canalizar el resultado a un cofre con un <ItemLink id="storage_bus" /> puesto.**

5.  Si ese crafteo es un requisito previo para otro crafteo en la solicitud, los objetos se almacenan en esa CPU de crafteo y luego se usan en ese crafteo.

# Patrones

<ItemImage id="crafting_pattern" scale="4" />

Los patrones se crean en una <ItemLink id="pattern_encoding_terminal" /> a partir de patrones en blanco.

Hay varios tipos diferentes de patrones para diferentes cosas:

*   Los <ItemLink id="crafting_pattern" /> codifican recetas hechas por una mesa de crafteo. Se pueden poner directamente en una <ItemLink id="molecular_assembler" /> para que
    craftee el resultado cuando se le den los ingredientes, pero su uso principal es en un <ItemLink id="pattern_provider" /> junto a una ensambladora molecular.
    Los proveedores de patrones tienen un comportamiento especial en este caso, y enviarán el patrón relevante junto con los ingredientes a las ensambladoras adyacentes.
    Dado que las ensambladoras expulsan automáticamente los resultados de los crafteos a los inventarios adyacentes, una ensambladora en un proveedor de patrones es todo lo que se necesita para automatizar los patrones de crafteo.

***

*   Los <ItemLink id="smithing_table_pattern" /> son muy similares a los patrones de crafteo, pero codifican recetas de mesa de herrería. También se automatizan con un proveedor
    de patrones y una ensambladora molecular, y funcionan exactamente de la misma manera. De hecho, los patrones de crafteo, herrería y corte de piedra se pueden
    usar en la misma configuración.

***

*   Los <ItemLink id="stonecutting_pattern" /> son muy similares a los patrones de crafteo, pero codifican recetas de cortapiedras. También se automatizan con un proveedor
    de patrones y una ensambladora molecular, y funcionan exactamente de la misma manera. De hecho, los patrones de crafteo, herrería y corte de piedra se pueden
    usar en la misma configuración.

***

*   Los <ItemLink id="processing_pattern" /> son donde surge gran parte de la flexibilidad en el autocrafteo. Son el tipo más generalizado, simplemente
    dicen "si un proveedor de patrones empuja estos ingredientes a inventarios adyacentes, el sistema ME recibirá estos objetos en algún momento en el
    futuro cercano o lejano". Así es como autocraftearás con casi cualquier máquina de mods, o hornos y similares. Debido a que son tan
    generales en uso y no les importa qué sucede entre empujar ingredientes y recibir el resultado, puedes hacer cosas realmente extrañas, como ingresar
    los ingredientes en una cadena de producción de fábrica compleja que clasificará las cosas, tomar otros ingredientes de granjas de producción infinita,
    imprimir el guion completo de Bee Movie, al sistema ME no le importa siempre que reciba el resultado que especifica el patrón. De hecho,
    ni siquiera le importa si los ingredientes están relacionados de alguna manera con el resultado. Podrías decirle "1 tabla de madera de cerezo = 1 estrella del Nether" y tener
    tu granja de withers matando a un wither al recibir una tabla de madera de cerezo y funcionaría.

Se admiten múltiples <ItemLink id="pattern_provider" /> con patrones idénticos y funcionan en paralelo. Además, puedes hacer que un patrón diga,
por ejemplo, 8 piedra rocosa = 8 piedra en lugar de 1 piedra rocosa = 1 piedra, y el proveedor de patrones insertará 8 piedra rocosa en
 tu configuración de fundición en cada operación en lugar de una a la vez.

## La Forma Más General de "Patrón"

En realidad, existe una forma aún más "general" de "patrón" que un patrón de procesamiento. Un <ItemLink id="level_emitter" /> con una tarjeta de crafteo se puede configurar
para emitir una señal de redstone con el fin de craftear algo. Este "patrón" no define, ni siquiera le importan, los ingredientes.
Todo lo que dice es "Si emites redstone desde este emisor de nivel, el sistema ME recibirá este objeto en algún momento en el
futuro cercano o lejano". Esto se usa generalmente para activar y desactivar granjas infinitas que no requieren ingredientes de entrada,
o para activar un sistema que maneja recetas recursivas (que el autocrafteo estándar no puede entender) como, por ejemplo, "1 piedra rocosa = 2 piedra rocosa"
si tienes una máquina que duplica piedra rocosa.

# La CPU de Crafteo

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Las CPUs de crafteo gestionan solicitudes/trabajos de crafteo. Almacenan los ingredientes intermedios mientras se llevan a cabo trabajos de crafteo con múltiples pasos,
y afectan el tamaño de los trabajos que se pueden realizar y, hasta cierto punto, la velocidad a la que se completan. Son multibloques y
deben ser prismas rectangulares con al menos 1 almacenamiento de crafteo.

Las CPUs de crafteo están hechas de:

*   (Requerido) [Almacenamientos de crafteo](../items-blocks-machines/crafting_cpu_multiblock.md), disponibles en todos los tamaños de celda estándar (1k, 4k, 16k, 64k, 256k). Almacenan los ingredientes y
    los ingredientes intermedios involucrados en un crafteo, por lo que se requieren almacenamientos más grandes o más para que la CPU maneje trabajos de crafteo
    con más ingredientes.
*   (Opcional) <ItemLink id="crafting_accelerator" />, hacen que el sistema envíe más lotes de ingredientes desde los proveedores de patrones.
    Esto permite, por ejemplo, que un proveedor de patrones rodeado por 6 ensambladoras moleculares envíe ingredientes a (y por lo tanto use) las 6 a la vez en lugar de solo una.
*   (Opcional) <ItemLink id="crafting_monitor" />, muestran el trabajo que la CPU está manejando en el momento. Se pueden colorear con un <ItemLink id="color_applicator" />
*   (Opcional) <ItemLink id="crafting_unit" />, simplemente llenan espacio para hacer que la CPU sea un prisma rectangular.

Cada CPU de crafteo maneja 1 solicitud o trabajo, así que si quieres solicitar tanto un procesador de cálculo como 256 piedra lisa a la vez, necesitas 2 multibloques de CPU.

Se pueden configurar para manejar solicitudes de jugadores, automatización (buses de exportación e interfaces), o ambos.

# Proveedores de Patrones

<Row>
<BlockImage id="pattern_provider" scale="4" />

<BlockImage id="pattern_provider" p:push_direction="up" scale="4" />

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

Los <ItemLink id="pattern_provider" /> son la forma principal en que tu sistema de autocrafteo interactúa con el mundo. Empujan los ingredientes de
sus [patrones](../items-blocks-machines/patterns.md) a inventarios adyacentes, y se pueden insertar objetos en ellos para insertarlos en la red. A menudo
se puede ahorrar un canal canalizando la salida de una máquina de vuelta a un proveedor de patrones cercano (a menudo el que empujó los ingredientes)
en lugar de usar un <ItemLink id="import_bus" /> para extraer la salida de la máquina hacia la red.

Cabe destacar que, dado que empujan los ingredientes directamente desde el [almacenamiento de crafteo](../items-blocks-machines/crafting_cpu_multiblock.md#crafting-storage) en una CPU de crafteo,
nunca contienen realmente los ingredientes en su inventario, por lo que no puedes extraer de ellos. Tienes que hacer que el proveedor empuje
a otro inventario (como un barril) y luego extraer de ese.

También cabe destacar que el proveedor tiene que empujar TODOS los ingredientes a la vez, no puede empujar lotes parciales. Esto es útil
para explotar.

Los proveedores de patrones tienen una interacción especial con las interfaces en [subredes](../ae2-mechanics/subnetworks.md): si la interfaz no está modificada (nada en las ranuras de solicitud)
el proveedor omitirá la interfaz por completo y empujará directamente al [almacenamiento](../ae2-mechanics/import-export-storage.md) de esa subred,
omitiendo la interfaz y no llenándola con lotes de recetas, y lo que es más importante, no insertando el siguiente lote hasta que haya espacio en el almacenamiento.

Se admiten múltiples proveedores de patrones con patrones idénticos y funcionan en paralelo.

Los proveedores de patrones intentarán distribuir sus lotes en round-robin a todas sus caras, utilizando así todas las máquinas adjuntas en paralelo.

## Variantes

Los proveedores de patrones vienen en 3 variantes diferentes: normal, direccional y plana. Esto afecta a qué lados específicos empujan
los ingredientes, de qué lados reciben objetos y a qué lados proporcionan una conexión de red.

*   Los proveedores de patrones normales empujan ingredientes a todos los lados, reciben entradas de todos los lados y, como la mayoría de las máquinas de AE2, actúan
    como un cable que proporciona conexión de red a todos los lados.

*   Los proveedores de patrones direccionales se crean usando una <ItemLink id="certus_quartz_wrench" /> en un proveedor de patrones normal para cambiar su
    dirección. Solo empujan ingredientes al lado seleccionado, reciben entradas de todos los lados y, específicamente, no proporcionan una conexión de red
    en el lado seleccionado. Esto les permite empujar a máquinas de AE2 sin conectar redes, si quieres hacer una subred.

*   Los proveedores de patrones planos son una [subparte de cable](../ae2-mechanics/cable-subparts.md), por lo que se pueden colocar varios en el mismo cable, lo que permite configuraciones compactas.
    Actúan de manera similar al lado seleccionado en un proveedor de patrones direccional, proporcionando patrones, recibiendo entradas y no
    proporcionando una conexión de red en su cara.

Los proveedores de patrones se pueden intercambiar entre normal y plano en una mesa de crafteo.

## Configuraciones

Los proveedores de patrones tienen una variedad de modos:

*   **Modo Bloquear** evita que el proveedor empuje un nuevo lote de ingredientes si ya hay
    ingredientes en la máquina.
*   **Bloquear Crafteo** puede bloquear el proveedor bajo varias condiciones de redstone, o hasta que el resultado del
    crafteo anterior se inserte en ese proveedor de patrones específico.
*   El proveedor se puede mostrar u ocultar en los <ItemLink id="pattern_access_terminal" />.

## Prioridad

Las prioridades se pueden configurar haciendo clic en la llave inglesa en la esquina superior derecha de la GUI. En el caso de varios [patrones](../items-blocks-machines/patterns.md)
para el mismo objeto, los patrones en proveedores con mayor prioridad se usarán sobre los patrones en proveedores con menor prioridad,
a menos que la red no tenga los ingredientes para el patrón de mayor prioridad.

# Ensambladoras Moleculares

<BlockImage id="molecular_assembler" scale="4" />

La <ItemLink id="molecular_assembler" /> toma los objetos que se le ingresan y lleva a cabo la operación definida por un <ItemLink id="pattern_provider" /> adyacente,
o el <ItemLink id="crafting_pattern" />, <ItemLink id="smithing_table_pattern" /> o <ItemLink id="stonecutting_pattern" /> insertado,
luego empuja el resultado a los inventarios adyacentes.

Su uso principal es junto a un <ItemLink id="pattern_provider" />. Los proveedores de patrones tienen un comportamiento especial en este caso,
y enviarán información sobre el patrón relevante junto con los ingredientes a las ensambladoras adyacentes. Dado que las ensambladoras expulsan automáticamente los resultados de los
crafteos a los inventarios adyacentes (y por lo tanto a las ranuras de retorno del proveedor de patrones), una ensambladora en un proveedor de patrones
es todo lo que se necesita para automatizar los patrones de crafteo.

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>