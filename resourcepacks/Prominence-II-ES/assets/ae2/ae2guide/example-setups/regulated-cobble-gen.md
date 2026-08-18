---
navigation:
  parent: example-setups/example-setups-index.md
  title: Generador de Adoquín Autorregulado
  icon: minecraft:cobblestone
---

# Generador de Adoquín Autorregulado

La automatización de un generador de adoquín es simple, solo enfrenta un <ItemLink id="annihilation_plane" /> a un generador de adoquín manual estándar de vanilla. Sin embargo, hacer esto eventualmente llenará tu red de adoquín, así que se desea algo de regulación.

Debido a cómo funcionan los planos de aniquilación (actúan como <ItemLink id="import_bus" />ses), no podemos simplemente poner un <ItemLink id="level_emitter" /> frente a un <ItemLink id="export_bus" /> con una <ItemLink id="redstone_card" /> (ya que no puedes ir directamente de importación a exportación sin almacenamiento en el medio). Tenemos que ser un poco más indirectos.

Los <ItemLink id="toggle_bus" />ses te permiten conectar y desconectar partes de tu red con señales de redstone, pero causan que la red se reinicie cada vez que lo hacen. Hay un truco simple: pon el bus de alternancia en una [subred](../ae2-mechanics/subnetworks.md) para que solo reinicie la subred.

Podemos tener una [subred](../ae2-mechanics/subnetworks.md) autocontenida de <ItemLink id="annihilation_plane" /> y <ItemLink id="storage_bus" /> que empuje hacia una <ItemLink id="interface" /> en la red principal. El bus de alternancia conectará y desconectará la subred de una <ItemLink id="quartz_fiber" />, cortando la energía a los planos.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/regulated_cobble_gen.snbt" />

<BoxAnnotation color="#dddddd" min="3 2 2" max="7 2.3 3">
        (1) Planos de Aniquilación: Sin GUI para configurar, pero pueden encantarse con Eficiencia y Irrompibilidad para reducir el consumo de energía.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 2 2" max="2.3 3 3">
        (2) Bus de Almacenamiento: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 2.3 2" max="2.7 2.7 2.3">
        (3) Bus de Alternancia: Muy importante que el bus de alternancia esté en la
        subred, y no en la red principal.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 3 2.3" max="2.7 3.3 2.7">
        (4) Emisor de Nivel: Configurado con adoquín y la cantidad deseada, puesto en "Emitir cuando los niveles estén por debajo del límite".
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 3" max="2 3 2">
        (5) Interfaz: En su configuración predeterminada.
  </BoxAnnotation>

<DiamondAnnotation pos="0 2.5 1.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

<DiamondAnnotation pos="5 1.5 3.5" color="#00ff00">
        Las escaleras con agua evitan que el agua fluya y convierta la lava en obsidiana.
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

* Los <ItemLink id="annihilation_plane" />s (1) No tienen GUI para configurar, pero pueden encantarse con Eficiencia y Irrompibilidad para reducir el consumo de energía.
* El <ItemLink id="storage_bus" /> (2) está en su configuración predeterminada.
* El <ItemLink id="toggle_bus" /> (3) debe estar en el lado de la subred de la fibra de cuarzo, no en la red principal, o la red principal se reiniciará cada vez que se alterne.
* El <ItemLink id="level_emitter" /> (4) está configurado con el objeto y la cantidad deseados, y puesto en "Emitir cuando los niveles estén por debajo del límite".
* La <ItemLink id="interface" /> (5) está en su configuración predeterminada.

## Cómo Funciona

1. El generador de adoquín hace algo de adoquín.
2. Los <ItemLink id="annihilation_plane" />s rompen el adoquín. 
3. El <ItemLink id="storage_bus" /> almacena el adoquín en la <ItemLink id="interface" />, enviándolo a la red principal.
4. Cuando la cantidad de adoquín en la red principal excede la cantidad establecida, el <ItemLink id="level_emitter" /> deja de enviar una señal, apagando el <ItemLink id="toggle_bus" />.
5. Esto corta la energía a la subred, deteniendo el trabajo de los planos de aniquilación.
