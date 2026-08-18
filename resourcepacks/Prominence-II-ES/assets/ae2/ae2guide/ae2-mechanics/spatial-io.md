---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: IO Espacial
  icon: spatial_storage_cell_2
---

# IO Espacial

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/spatial_storage_1x1x1.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="2 2 2">
        El volumen a mover
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />

</GameScene>

El IO Espacial es una forma de cortar y pegar volúmenes físicos de espacio en tu mundo. Se puede usar para mover <ItemLink id="flawless_budding_quartz" />,
tener una habitación en tu base donde puedas intercambiar varios interiores para usarla con diferentes propósitos, o incluso mover
¡el portal del End!

Funciona *intercambiando* el volumen definido con un volumen de tamaño idéntico en la dimensión de almacenamiento espacial, enviando lo que sea
que esté en la matriz de pilones a la dimensión de almacenamiento espacial, y lo que sea que esté en la dimensión a la matriz de pilones.

Esto significa que si tienes una forma de viajar entre dimensiones (el IO Espacial *puede* usarse para hacer un teletransportador,
pero hacerlo es muy complejo, un poco inestable, y está más allá del alcance de esta guía), puedes usarlos como máquinas compactas de tamaño personalizado o dimensiones de bolsillo.

# La Configuración Multibloque

El IO Espacial requiere una disposición específica de sus componentes para funcionar y definir el volumen a cortar y pegar.

Todos los componentes deben estar en la misma [red](me-network-connections.md) para funcionar, y solo puedes tener una
configuración de IO Espacial por red. Por lo tanto, se recomienda una [subred](subnetworks.md).

## El Puerto de IO Espacial

<BlockImage id="spatial_io_port" p:powered="true" scale="4" />

El <ItemLink id="spatial_io_port" /> controla la operación de IO Espacial. Muestra estadísticas sobre la configuración multibloque y contiene
las [celdas espaciales](../items-blocks-machines/spatial_cells.md)

Muestra
- Energía [energía](energy.md) almacenada y máxima en la red
- Energía requerida para realizar la operación. Esta puede ser bastante grande y se usa instantáneamente, así que asegúrate de tener suficiente
  [celdas de energía](../items-blocks-machines/energy_cells.md) para contenerla toda.
- Eficiencia de la matriz de pilones
- Tamaño del volumen definido

Para realizar una operación de IO Espacial, coloca una celda de almacenamiento espacial en la ranura de entrada y dale al puerto de IO Espacial un pulso de redstone.
Luego *intercambiará* el volumen en los pilones con el volumen en la dimensión de almacenamiento espacial. Esto significa que si envías algún
conjunto de bloques a la dimensión de almacenamiento espacial, *luego colocas otro conjunto de bloques en los pilones*, pones la celda de nuevo en la ranura de entrada,
y activas el puerto de IO nuevamente, el segundo conjunto de bloques desaparecerá y el primer conjunto de bloques reaparecerá.

**TEN CUIDADO, cualquier entidad en el volumen definido, incluyéndote a ti, será transportada, y si no tienes forma de salir, quedarás atrapado
en la dimensión de almacenamiento espacial, en una caja oscura y sin rasgos distintivos.** ¡Usa esto para gastarles bromas a tus amigos!

## Pilones

<BlockImage id="spatial_pylon" p:powered_on="true" scale="4" />

Los <ItemLink id="spatial_pylon" /> son la parte principal de una configuración de IO Espacial y definen el volumen a afectar.

El volumen se define por el cuadro delimitador del exterior de los pilones, contraído en 1 bloque en todas las direcciones.

Las reglas son:
- Tamaño mínimo de 3x3x3 (que define un volumen de 1x1x1)
- Todos los pilones espaciales deben estar en el cuadro delimitador exterior
- Todos los pilones espaciales deben estar en la misma red
- Todos los pilones deben tener al menos 2 bloques de largo

Por ejemplo, digamos que quieres definir un volumen de 3x3x3. Siguiendo la regla 2, todos los pilones deben estar dentro de una capa de 5x5x5 alrededor
del volumen que quieres definir. Pueden estar en casi cualquier configuración, siempre que estén contenidos dentro de esa capa de 5x5x5 de 1 bloque de grosor.

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/spatial_storage_3x3x3_pylon_demonstration.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        El volumen a mover
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Una configuración más razonable es esta:

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/better_spatial_storage_3x3x3.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        El volumen a mover
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Eficiencia

La eficiencia de la matriz de pilones depende de la cantidad de la capa que llenes. Configuraciones mínimas alrededor de volúmenes grandes
serán muy ineficientes y posiblemente requieran *miles de millones* de AE.

## Dimensiones de la Celda

Una vez que una [celda espacial](../items-blocks-machines/spatial_cells.md) ha sido usada, gana un conjunto de dimensiones XYZ definidas permanentemente (ej., 3x4x2)
y está vinculada a un volumen de espacio en la dimensión de almacenamiento espacial. **NO PUEDES REINICIAR, REFORMATEAR O REDIMENSIONAR UNA CELDA ESPACIAL DESPUÉS DE
QUE HAYA SIDO USADA.** Haz una celda nueva si quieres usar dimensiones diferentes.

Estas no son las mismas dimensiones en el nombre de una celda, una celda de 16^3 puede tener cualquier dimensión *hasta* 16x16x16

Ten en cuenta que este volumen es direccional y no puede rotarse. Un volumen de 2x2x3 no es lo mismo que un volumen de 3x2x2, aunque sean del mismo tamaño.

Si las dimensiones XYZ de una celda no coinciden con el volumen definido (visto en el puerto de IO), el puerto de IO no operará.