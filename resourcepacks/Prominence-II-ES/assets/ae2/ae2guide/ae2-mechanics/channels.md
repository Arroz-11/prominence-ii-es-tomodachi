---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Canales
  icon: controller
---

# Canales

Las [Redes ME](me-network-connections.md) de Applied Energistics 2 requieren Canales para soportar [dispositivos](../ae2-mechanics/devices.md) que usan almacenamiento en red, u otros servicios de red. Piensa en los canales como cables USB para todos tus dispositivos. Una computadora solo tiene tantos puertos USB y solo puede soportar tantos dispositivos conectados a ella. La mayoría de las máquinas, dispositivos de bloque completo y cables estándar solo pueden pasar hasta 8 canales. Puedes pensar en los dispositivos de bloque completo y los cables estándar como un paquete de 8 "cables de canal". Sin embargo, los [cables densos](../items-blocks-machines/cables.md#dense-cable) pueden soportar hasta 32 canales. Los únicos otros dispositivos capaces de transmitir 32 son <ItemLink id="me_p2p_tunnel" /> y el [Puente de Red Cuántico](../items-blocks-machines/quantum_bridge.md). Cada vez que un dispositivo usa un canal, imagina sacar un "cable" USB del paquete, lo que obviamente significa que ese "cable" no está disponible más adelante en la línea.

<GameScene zoom="7" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_demonstration_1.snbt" />

  <LineAnnotation color="#33ff33" from="1 .4 .7" to="2.4 .4 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .7" to="2.4 .6 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .6" to="2.6 .4 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.4 .6 .7" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .4 .7" to="2.4 .4 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .6 .6" to="2.6 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 .6" to="2.6 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.1 .6 1.5" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 1.5" to="2.9 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.6 .6 1.5" to="2.6 .9 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .1 1.5" to="2.4 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .4" to="3.5 .6 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="3.5 .6 .4" to="3.5 .9 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="3.5 .1 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .3" to="1.5 .6 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1.5 .6 .3" to="1.5 .9 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1.5 .1 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#ff3333" from="3.5 .5 .5" to="5.5 .5 .5" alwaysOnTop={true}>
  Todos los 8 canales en el cable se han usado, así que la Unidad no recibe uno.
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        Todos los 8 canales en el cable se han usado, así que la Unidad no recibe uno.
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

Una forma fácil de ver cómo se usan y enrutan los canales a través de tu red es usar [cables inteligentes](../items-blocks-machines/cables.md), que mostrarán en ellos las rutas y el uso de los canales.

Los canales consumirán 1⁄128 ae/t por nodo que atraviesan, esto significa que al agregar un <ItemLink id="controller" /> para una red con 8 dispositivos y más de 96 nodos, tu consumo de energía podría en realidad disminuir porque cambia cómo se asignan los canales.

Nota: **LOS CANALES NO TIENEN NADA QUE VER CON EL COLOR DEL CABLE**, todo lo que hace el color del cable es evitar que los cables se conecten.

## Enrutamiento de Canales

Cuando usas un <ItemLink id="controller" />, los canales se enrutan en 3 pasos. Primero toman el camino más corto a través de máquinas adyacentes hasta el [cable normal](../items-blocks-machines/cables.md) más cercano (de vidrio, cubierto o inteligente). Luego toman el camino más corto a través de ese cable normal hasta el [cable denso](../items-blocks-machines/cables.md) más cercano (denso o denso inteligente). Luego toman el camino más corto a través de ese cable denso hasta el <ItemLink id="controller" />. Si el camino más corto ya está al máximo, algunos [dispositivos](devices.md) pueden no recibir sus canales requeridos. Usa cables de colores, anclas de cable y túneles a tu favor para asegurarte de que tus canales vayan por el camino que deseas.

Por ejemplo, en este caso algunas unidades no reciben canales porque aunque hay suficiente capacidad en los cables, los canales intentan tomar el camino más corto, sobrecargando algunos cables mientras dejan otros vacíos.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 3.6" to="1.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.4 0.5 3.6" to="1.4 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 1.6" to="0.6 .5 1.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 1.6" to="0.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 3.4" to="1.4 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 3.4" to="1.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <BoxAnnotation color="#dddddd" min="1.2 0.2 3.2" max="1.8 0.8 3.8" alwaysOnTop={true} thickness="0.05">
        Más de 8 canales intentan pasar por aquí, así que algunos se cortan.
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

Esto se puede solucionar restringiendo más cuidadosamente los caminos que los canales pueden tomar. Las redes deberían ser en forma de árbol (o arbusto). Los bucles y los caminos de canal ambiguos deberían minimizarse.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## Redes Ad-Hoc

Una red sin un <ItemLink id="controller" /> se considera Ad-Hoc, y puede soportar hasta 8 dispositivos que usan canales. Una vez que superas 8 dispositivos, los dispositivos que usan canales de la red se apagarán. Puedes eliminar dispositivos o agregar un <ItemLink id="controller" />.

A diferencia de las redes con controlador, los [cables inteligentes](../items-blocks-machines/cables.md) en redes ad-hoc mostrarán el número de canales en uso en toda la red en lugar del número de canales que fluyen a través de ese cable específico.

Mientras usas redes ad-hoc, cada dispositivo usará 1 canal en toda la red, esto es muy diferente de cómo un <ItemLink id="controller" /> asigna canales basados en la ruta más corta.

## Diseño

Como se mencionó antes en [enrutamiento de canales](channels.md#channel-routing), es mejor diseñar tu red en una estructura de árbol, con cables densos ramificándose desde el controlador, cables regulares ramificándose desde los densos, y [dispositivos](../ae2-mechanics/devices.md) en grupos de 8 o menos en los cables regulares.

Aquí hay un ejemplo de lo que no se debe hacer:

Siguiendo las rutas de canales,

1. Inmediatamente saliendo del controlador a la derecha, estamos limitados a 8 canales porque la unidad actúa como un cable normal. Sin embargo, como no estamos usando un cable inteligente aquí, no podemos ver cuántos canales están en uso. Quedan 8 canales.
2. La unidad toma un canal. Quedan 7 canales.
3. 2 canales suben a las terminales. Quedan 5 canales.
4. Continuando a la derecha, la interfaz toma otro canal. Quedan 4 canales.
5. 1 canal sube al proveedor de patrones. Quedan 3 canales.
6. Continuando a la derecha, 1 canal sube al bus de importación. Quedan 2 canales.
7. El grupo de proveedores de patrones que alimentan a las ensambladoras solo recibe 2 canales, así que 2 de los proveedores no reciben canales.

En última instancia, el error está en limitar los canales y no pensar en cómo se distribuirán.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/bad_network_structure.snbt" />

<LineAnnotation color="#33ff33" from="6.5 .5 1.5" to="6 .5 1.5" alwaysOnTop={true} thickness="0.4">
  32 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="6 .5 1.5" to="5.5 .5 1.5" alwaysOnTop={true} thickness="0.2">
  8 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 1.5 1.5" alwaysOnTop={true} thickness="0.1">
  2 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 1.5 1.5" to="5.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 2.5 1.5" to="5.5 2.5 1.1" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="4.5 .5 1.5" alwaysOnTop={true} thickness="0.158">
  5 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 1.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="3.5 .5 1.5" alwaysOnTop={true} thickness="0.122">
  3 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="3.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 2.5 1.5" to="3.7 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="1.5 .5 1.5" alwaysOnTop={true} thickness="0.1">
  2 canales
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="1.5 0.3 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="0.5 0.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#33ff33" from="0.5 0.5 1.5" to="0.5 0.5 0.5" alwaysOnTop={true} thickness="0.071">
  1 canal
</LineAnnotation>

<LineAnnotation color="#ff3333" from="0.5 1.5 1.5" to="0.5 1.3 1.5" alwaysOnTop={true} thickness="0.071">
  sin canales
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  sin canales
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

---

Aquí hay un ejemplo de una buena estructura:

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        Nota que los proveedores de patrones están en grupos separados de 8.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        Dos cables regulares llenos de canales que se unen significan que necesitas un cable denso.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        Se usan diferentes colores de cable para evitar que cables adyacentes se conecten.
    </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## Modos de Canal

AE2 10.0.0 para Minecraft 1.18 introduce nuevas opciones para cambiar cómo se comportan los canales de AE2 en tu mundo. Hay una nueva opción de configuración en la sección general (`channels`) que controla esta opción, y un nuevo comando en el juego para que los operadores cambien el modo y la configuración desde el juego. El comando es `/ae2 channelmode <mode>` para cambiarlo y `/ae2 channelmode` para mostrar el modo actual. Cuando el modo se cambia en el juego, todas las redes existentes se reiniciarán y usarán el nuevo modo inmediatamente.

Esto resucita y mejora la opción que estaba disponible en Minecraft 1.12 e introduce mejores opciones para los jugadores que solo quieren un juego un poco más relajado pero no quieren que la mecánica se elimine por completo.

La siguiente tabla enumera los modos disponibles tanto en el archivo de configuración como en el comando.

| Contexto   | Descripción                                                                                                                                                                                                                               |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `default`  | El modo estándar con las capacidades de canal de cable y redes ad-hoc como se describe en todo este sitio web                                                                                                                           |
| `x2`       | Todas las capacidades de canal se duplican (16 en cable normal, 64 en cable denso, las redes ad-hoc soportan 16 canales)                                                                                                                           |
| `x3`       | Todas las capacidades de canal se triplican (24 en cable normal, 92 en cable denso, las redes ad-hoc soportan 24 canales)                                                                                                                           |
| `x4`       | Todas las capacidades de canal se cuadruplican (32 en cable normal, 128 en cable denso, las redes ad-hoc soportan 32 canales)                                                                                                                       |
| `infinite` | Todas las restricciones de canal se eliminan. Los controladores aún reducen el consumo de energía de las redes *significativamente*. Los cables inteligentes solo alternarán entre completamente apagados (sin canales) y completamente encendidos (1 o más canales). |