---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME Caner
    icon: extendedae:caner
categories:
- extended devices
item_ids:
- extendedae:caner
---

# ME Caner

<BlockImage id="extendedae:caner" scale="8"></BlockImage>

ME Caner es una máquina que "enlata" cosas, incluyendo fluidos, gas de Mecanismo, maná de Botania e incluso ¡energía!

La primera ranura es para lo que se va a rellenar, y la segunda ranura es para lo que se va a llenar.

Necesita energía para funcionar y cada operación cuesta 80 AE.

![GUI](../pic/caner_gui.png)

Solo rellena fluidos por defecto, necesitas instalar el addon correspondiente para que rellene otras cosas.

### Addons compatibles:
- Applied Flux
- Applied Mekanistics
- Applied Botanics Addon

## Autocrafteo con ME Caner

Solo los lados superior e inferior pueden aceptar energía y conectarse a la red.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/caner_example.snbt"></ImportStructure>
</GameScene>

Una configuración simple para ME Caner. ME Caner expulsará automáticamente el objeto lleno cuando acepte los ingredientes del <ItemLink id="ae2:pattern_provider" />.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/caner_auto.snbt"></ImportStructure>
</GameScene>

El patrón solo debe contener lo que se va a rellenar y el contenedor que se va a llenar. Aquí hay algunos ejemplos:

Rellenar cubo de agua:

![P1](../pic/fill_water.png)

Cargar Energy Tablet (Necesita Applied Flux instalado):

![P1](../pic/fill_energy.png)


## Desenlatado

ME Caner también puede drenar cosas de contenedores en modo Vacío. Necesitas intercambiar las entradas y salidas en el patrón.
