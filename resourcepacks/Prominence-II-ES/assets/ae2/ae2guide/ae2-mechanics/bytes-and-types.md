---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Bytes y Tipos
  icon: creative_item_cell
---

# Bytes y Tipos

<Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

Las [Celdas de almacenamiento](../items-blocks-machines/storage_cells.md) se definen tanto por *bytes* como por *tipos*. Los bytes, como en tu
computadora real, son una medida de la cantidad total de "cosas" en una celda de almacenamiento. Los tipos son una medida de cuántos diferentes,
bueno, *tipos* de cosas se almacenan en una celda. Cada tipo representa un objeto único, por lo que 4,096 piedra rocosa es 1 tipo, pero 16 espadas
diferentes con diferentes encantamientos son 16 tipos.

Cada celda de almacenamiento puede almacenar una cantidad fija de datos. Cada tipo consume una cantidad de bytes por adelantado (que varía con el tamaño de la celda),
y cada objeto consume un bit de almacenamiento, por lo que ocho objetos consumen un byte, y una pila completa de 64 consume 8 bytes, independientemente de cómo
se apilaría el objeto fuera de una red ME. Por ejemplo, 64 sillas de montar idénticas no ocupan más espacio que 64 piedra.

De nuevo, cada objeto es 1 bit, por lo que 8 objetos equivalen a 1 byte. Para celdas de fluidos, esto es 8 cubos por byte.

Mucha gente se queja de la cantidad limitada de tipos que puede contener una celda, pero son una ***limitación necesaria***.
Las celdas almacenan sus datos en una etiqueta NBT en el propio objeto, lo que las hace bastante estables. Sin embargo, esto significa que poner demasiados
datos en una celda puede causar que se envíen demasiados datos a un jugador, causando un efecto similar al "Book Banning" en Minecraft vanilla.
Además, tener demasiados tipos diferentes en tu sistema aumenta la carga en la clasificación y el manejo de objetos. Sin embargo, esta
limitación no termina siendo muy restrictiva. Una bahía de <ItemLink id="drive" /> llena de celdas es 630 tipos, lo cual es bastante
alto siempre y cuando no almacenes montones de objetos únicos no apilables.

Por esta razón, los tipos existen para "desalentar firmemente" que vuelques los cientos de armaduras y herramientas dañadas aleatoriamente de una
granja de mobs directamente en tu sistema ME. Cada pieza de armadura con daño y encantamientos únicos tiene que almacenarse como una entrada separada,
lo que causa hinchazón. Se recomienda filtrarlos del flujo de objetos antes de que toquen tu sistema.

Ir directamente a las celdas de almacenamiento de gama alta generalmente no es la mejor idea,
ya que usas más recursos pero no obtienes almacenamiento de tipos adicional. Esto significa que todos los tamaños de celda siguen siendo útiles incluso
en el juego tardío, ya que tienen compensaciones.

A continuación se muestra una tabla que compara los diferentes niveles de celdas de almacenamiento, cuánto almacenan y
una estimación aproximada de su costo.

## Contenido de la Celda de Almacenamiento vs Costo

| Celda                                     |   Bytes | Tipos | Bytes por Tipo | Certus | Redstone | Dorado | Piedra Luminosa |
| ---------------------------------------- | ------: | ----: | -------------: | -----: | -------: | ---: | --------: |
| <ItemLink id="item_storage_cell_1k" />   |   1,024 |    63 |              8 |      4 |        5 |    1 |         0 |
| <ItemLink id="item_storage_cell_4k" />   |   4,096 |    63 |             32 |  14.25 |       20 |    3 |         0 |
| <ItemLink id="item_storage_cell_16k" />  |  16,384 |    63 |            128 |     45 |       61 |    9 |         4 |
| <ItemLink id="item_storage_cell_64k" />  |  65,536 |    63 |            512 | 137.25 |      184 |   27 |        16 |
| <ItemLink id="item_storage_cell_256k" /> | 262,144 |    63 |           2048 |    414 |      553 |   81 |        48 |

## Capacidad de Almacenamiento con Diferente Cantidad de Tipos

El costo inicial de los tipos es tal que una celda que contiene 1 tipo puede contener 2 veces más que una celda con los 63 tipos en uso.

| Celda                                     | Capacidad total de la celda con 1 tipo en uso | Capacidad total de la celda con 63 tipos en uso |
| ---------------------------------------- | ----------------------------------------: | ------------------------------------------: |
| <ItemLink id="item_storage_cell_1k" />   |                                     8,128 |                                       4,160 |
| <ItemLink id="item_storage_cell_4k" />   |                                    32,512 |                                      16,640 |
| <ItemLink id="item_storage_cell_16k" />  |                                   130,048 |                                      66,560 |
| <ItemLink id="item_storage_cell_64k" />  |                                   520,192 |                                     266,240 |
| <ItemLink id="item_storage_cell_256k" /> |                                 2,080,768 |                                   1,064,960 |

![Una celda con 1 tipo](../assets/diagrams/1_type_cell.png)

![Una celda con 63 tipos](../assets/diagrams/63_type_cell.png)