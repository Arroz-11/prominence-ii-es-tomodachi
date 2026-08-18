---
navigation:
  parent: example-setups/example-setups-index.md
  title: Fortunador Automático de Mineral
  icon: minecraft:raw_iron
---

# Automatización del Fortunado de Mineral

El <ItemLink id="annihilation_plane" /> puede ser encantado con cualquier encantamiento de pico, incluida Fortuna, así que un uso obvio es aplicar Fortuna a unos pocos, y tener <ItemLink id="formation_plane" />s y <ItemLink id="annihilation_plane" />s colocando y rompiendo minerales rápidamente.

Nota: como el <ItemLink id="import_bus" /> "acelera gradualmente", la configuración comenzará lenta y luego alcanzará velocidad máxima en unos segundos.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 0 2" max="3 1 3">
        (1) Bus de Importación: Tiene algunas Tarjetas de Aceleración.
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 2" max="2 1 2.3">
        (2) Planos de Formación: En su configuración predeterminada.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 0.7" max="2 1 1">
        (3) Planos de Aniquilación: Sin GUI para configurar, pero encantados con Fortuna.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 0" max="3 1 1">
        (4) Bus de Almacenamiento: En su configuración predeterminada.
  </BoxAnnotation>

<DiamondAnnotation pos="3.5 0.5 2.5" color="#00ff00">
        Entrada
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 0.5 0.5" color="#00ff00">
        Salida
    </DiamondAnnotation>

<DiamondAnnotation pos="4 0.5 1.5" color="#00ff00">
        A la Red Principal
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Configuraciones

*   El <ItemLink id="import_bus" /> (1) tiene algunas <ItemLink id="speed_card" />s. Se requieren más cuantos más planos de formación haya en el arreglo, ya que hacen que el bus de importación extraiga más objetos a la vez.
*   Los <ItemLink id="formation_plane" />s (2) están en su configuración predeterminada.
*   Los <ItemLink id="annihilation_plane" />s (3) no tienen GUI y no se pueden configurar, pero están encantados con Fortuna.
*   El <ItemLink id="storage_bus" /> (4) está en su configuración predeterminada.

## Cómo Funciona

1.  El <ItemLink id="import_bus" /> en la subred verde importa bloques del primer barril al [almacenamiento de red](../ae2-mechanics/import-export-storage.md)
2.  El único almacenamiento en la subred verde es el <ItemLink id="formation_plane" />, que coloca los bloques.
3.  El <ItemLink id="annihilation_plane" /> en la subred naranja rompe los bloques, aplicándoles Fortuna.
4.  El <ItemLink id="storage_bus" /> en la subred naranja almacena los resultados de la rotura en el segundo barril.
