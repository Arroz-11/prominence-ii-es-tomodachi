---
navigation:
  title: Cómo Empezar (1.20+)
  position: 10
---

<div class="notification is-info">
  La siguiente información solo aplica a Applied Energistics 2 en Minecraft 1.20 y versiones más nuevas.
</div>

# Cómo Empezar

## Obteniendo los Materiales Iniciales

<GameScene zoom="4" background="transparent">
  <ImportStructure src="assets/assemblies/meteor_interior.snbt" />
</GameScene>

Para empezar con Applied Energistics 2, primero debes encontrar un [meteorito](ae2-mechanics/meteorites.md). Estos son bastante comunes y tienden a dejar enormes agujeros en el terreno, así que probablemente ya te hayas topado con uno en tus viajes.
Si no lo has hecho, puedes craftear una <ItemLink id="meteorite_compass" />, que apuntará hacia el <ItemLink id="mysterious_cube" /> más cercano.

Una vez que hayas encontrado un meteorito, excava hasta su centro. Encontrarás racimos de cuarzo certus, brotes de cuarzo certus, [bloques de certus en ciernes](items-blocks-machines/budding_certus.md) de varios tipos, y un Cubo Misterioso en el centro.

Extrae los racimos de cuarzo certus y cualquier bloque de cuarzo certus que encuentres. También puedes recoger los bloques de certus en ciernes, pero sin toque de seda se degradarán en 1 nivel.

No rompas ningún certus en ciernes impecable, ya que incluso con toque de seda se degradarán a certus en ciernes defectuoso, y es imposible repararlos de vuelta a impecable.

También extrae el Cubo Misterioso en el centro del meteorito para obtener las 4 prensas de inscripción.

## Cultivando Cuarzo Certus

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_1.snbt" />
</GameScene>

Los brotes de cuarzo certus brotarán de [bloques de certus en ciernes](items-blocks-machines/budding_certus.md), similar al amatista. Si rompes un brote que no ha terminado de crecer, soltará un <ItemLink id="certus_quartz_dust" />, sin cambios por fortuna. Si rompes un racimo completamente crecido, soltará cuatro <ItemLink id="certus_quartz_crystal" />s, y la fortuna aumentará este número.

Hay 4 niveles de bloques de certus en ciernes: Impecable, Defectuoso, Astillado y Dañado.

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_blocks.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Cada vez que un brote crece una etapa más, el bloque en ciernes tiene una probabilidad de degradarse un nivel, eventualmente convirtiéndose en un bloque de cuarzo certus normal. Pueden ser reparados (y se pueden crear nuevos bloques en ciernes) lanzando el bloque en ciernes (o un bloque de cuarzo certus) en agua con uno o más <ItemLink id="charged_certus_quartz_crystal" />.

<RecipeFor id="damaged_budding_quartz" />

Los bloques de certus en ciernes impecables no se degradarán y generarán certus infinitamente. Sin embargo, no pueden ser crafteados ni movidos con un pico, incluso con toque de seda. (sí pueden ser movidos con [almacenamiento espacial](ae2-mechanics/spatial-io.md) aunque)

Por sí solos, los brotes de cuarzo certus crecen muy lentamente. Afortunadamente, el <ItemLink id="growth_accelerator" /> acelera masivamente este proceso cuando se coloca adyacente al bloque en ciernes. Deberías construir algunos de estos como tu primera prioridad.

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Si no tienes suficiente cuarzo para hacer también un <ItemLink id="energy_acceptor" /> o una <ItemLink id="vibration_chamber" />,
puedes hacer una <ItemLink id="crank" /> y ponerla en el extremo de tu acelerador.

Cosechar el certus automáticamente está [descrito aquí](example-setups/simple-certus-farm.md).

## Un Breve Paréntesis sobre el Fluix

Otro material que necesitarás es el Fluix, que ya has encontrado al hacer aceleradores de crecimiento. Se hace lanzando certus cargado, redstone y cuarzo del Nether en agua. Hacer esto automáticamente se "deja como ejercicio para el lector".

El <ItemLink id="charger" /> es necesario para producir <ItemLink id="charged_certus_quartz_crystal" />., si no has hecho uno ya.

## Inscribiendo Algunos Procesadores

En tu saqueo de un meteorito, habrás encontrado cuatro "prensas" al romper el Cubo Misterioso. Estas se usan en el <ItemLink id="inscriber" /> para hacer los tres tipos de procesadores.

<ItemGrid>
  <ItemIcon id="silicon_press" />

  <ItemIcon id="logic_processor_press" />

  <ItemIcon id="calculation_processor_press" />

  <ItemIcon id="engineering_processor_press" />
</ItemGrid>

El inscriptor es una máquina con lados, muy parecido al horno de vainilla. Insertar desde arriba o abajo coloca objetos en las ranuras superior o inferior, e insertar desde el lateral o la parte trasera inserta en la ranura central. Los resultados se pueden extraer desde el lateral o la parte trasera.

Para facilitar la automatización con tolvas (y posiblemente reducir el espagueti de tuberías), los inscriptores se pueden rotar con una <ItemLink id="certus_quartz_wrench" />.

Produce algunos de cada tipo de procesador en preparación para el siguiente paso, haciendo un sistema ME muy básico. Automatizar la producción de procesadores se "deja como ejercicio para el lector".

## Tecnología de Materia Energía: Redes ME y Almacenamiento

### ¿Qué es el Almacenamiento ME?

Se pronuncia Emm-Eee, y significa Materia Energía.

Materia Energía es el componente principal de Applied Energistics 2, es como una versión de científico loco de un cofre multibloque,
y puede revolucionar tu situación de almacenamiento. ME es extremadamente diferente a otros sistemas de almacenamiento en Minecraft, y
puede que necesites un poco de pensamiento fuera de la caja para acostumbrarte; pero una vez que empiezas, vastas cantidades de almacenamiento en poco
espacio, y múltiples terminales de acceso son solo la punta del iceberg de lo que se vuelve posible.

### ¿Qué necesito saber para empezar?

Primero, ME guarda objetos dentro de otros objetos, llamados [Celdas de almacenamiento](items-blocks-machines/storage_cells.md); hay 5 niveles con cantidades cada vez mayores de
almacenamiento. Para usar una Celda de almacenamiento debe colocarse dentro de un <ItemLink id="chest" />,
o un <ItemLink id="drive" />.

El <ItemLink id="chest" /> te muestra el contenido de la Celda tan pronto como se coloca dentro, y puedes agregar y quitar objetos como si fuera un <ItemLink id="minecraft:chest" />, con la excepción de que los objetos están realmente guardados en las Celdas de almacenamiento, y no en el <ItemLink id="chest" /> en sí.

Mientras que el <ItemLink id="chest" /> es una gran manera de introducirte al concepto de ME, para realmente aprovecharlo necesitas configurar una [Red ME](ae2-mechanics/me-network-connections.md).

## Tu Primer Sistema ME

Ahora que tienes todos los materiales y máquinas básicos para Applied Energistics 2, puedes hacer tu primer sistema ME (Materia Energía). Este será muy básico, sin autocrafteo, sin logística, solo almacenamiento agradable, simple y buscable.

<GameScene zoom="6" interactive={true}>
<ImportStructure src="assets/assemblies/tiny_me_system.snbt" />

</GameScene>

*   Tu lista de ingredientes:
    * 1x <ItemLink id="drive" />
    * 1x <ItemLink id="terminal" /> o <ItemLink id="crafting_terminal" />
    * 1x <ItemLink id="energy_acceptor" />
    * Unos pocos [cables](items-blocks-machines/cables.md), ya sean de vidrio, cubiertos o inteligentes, pero no densos
    * Unas pocas [celdas de almacenamiento](items-blocks-machines/storage_cells.md), recomendadas las de variedad 4k para una buena mezcla de capacidad y tipos (sería más eficiente [particionar](items-blocks-machines/cell_workbench.md) una mezcla de 4k y 1k pero eso es una complejidad en la que no entraremos ahora)
---
1.  Coloca el drive.
2.  El aceptador de energía (y varios otros [dispositivos](ae2-mechanics/devices.md) de AE2) viene en 2 modos, cubo y plano. Se pueden cambiar entre ellos en una mesa de crafteo. Si tu aceptador de energía es un cubo, colócalo junto al drive. Si es un cuadrado plano, coloca un cable en el drive y coloca el aceptador sobre ese cable.
3.  Conduce energía al aceptador de energía con un cable/tubería/conducto de tu mod de generación de energía favorito.
4.  Coloca un cable encima del drive (o de otra manera a la altura de los ojos) y coloca tu terminal o terminal de trabajo sobre él.
5.  Pon tus celdas de almacenamiento en el drive
6.  Benefíciate
7.  Juega con la configuración del terminal
8.  Disfruta de tu poder y habilidad supremos
9.  Date cuenta de que esta red es, en el gran esquema de las cosas, bastante pequeña

### Expandiendo tu Red

Así que tienes algo de almacenamiento básico, y acceso a ese almacenamiento, es un buen comienzo, pero probablemente querrás quizás
automatizar algo de procesamiento.

Un gran ejemplo de esto es colocar un <ItemLink id="export_bus" /> en la parte superior de un horno para
verter minerales, y un <ItemLink id="import_bus" />
en la parte inferior del horno para extraer minerales fundidos.

El <ItemLink id="export_bus" /> te permite exportar objetos de la red, al inventario adjunto,
mientras que el <ItemLink id="import_bus" /> importa objetos del inventario adjunto a la red.

### Superando Límites

En este punto probablemente estás cerca de 8 o más [dispositivos](ae2-mechanics/devices.md), una vez que llegues a 9 dispositivos tendrás que empezar a gestionar [canales](ae2-mechanics/channels.md). Muchos dispositivos, pero no todos, requieren un canal para funcionar.

Por defecto una red puede soportar 8 canales, una vez que superes este límite, tendrás que añadir un <ItemLink id="controller" /> a tu red. Esto te permite expandir tu red enormemente.
[Los cables inteligentes](items-blocks-machines/cables.md) te permitirán ver cómo se enrutan los canales a través de tu red. Úsalos extensivamente al empezar para aprender cómo actúan los canales, o si tienes mucho redstone y piedra luminosa.
