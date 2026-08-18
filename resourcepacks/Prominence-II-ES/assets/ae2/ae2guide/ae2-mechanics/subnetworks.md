---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Subredes
---

# Subredes

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/subnet_demonstration.snbt" />

<DiamondAnnotation pos="6.5 2.5 0.5" color="#00ff00">
        Subred de tubería de ítems
    </DiamondAnnotation>

<DiamondAnnotation pos="5.5 2.5 0.5" color="#00ff00">
        Subred de tubería de fluidos
    </DiamondAnnotation>

<DiamondAnnotation pos="4.5 2.5 0.5" color="#00ff00">
        Plano de aniquilación filtrado
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 2.5 0.5" color="#00ff00">
        Subred de plano de formación
    </DiamondAnnotation>

<DiamondAnnotation pos="2.5 2.5 0.5" color="#00ff00">
        Subred que usa la interacción Interfaz-Bus de almacenamiento para actuar como un sub-almacenamiento local que la red principal puede acceder
    </DiamondAnnotation>

<DiamondAnnotation pos="1.5 1.5 0.5" color="#00ff00">
        Otra subred de tubería de ítems, para devolver los ítems cargados al Proveedor de patrones
    </DiamondAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

"Subred" es un término bastante flexible, pero se podría decir que una subred es cualquier red que apoya a tu
red principal o hace alguna tarea pequeña. Por lo general, son lo suficientemente pequeñas como para no requerir controladores. Sus 2 usos principales tienden a ser:

*   Restringir qué [dispositivos](../ae2-mechanics/devices.md) tienen acceso a qué almacenamiento (no quieres que el bus de importación en una subred de "tubería" tenga acceso a tu almacenamiento de la red principal,
    o pondrá los ítems en tus celdas de almacenamiento en lugar de en el inventario de destino).
*   Ahorrar canales en tu red principal, como tener un proveedor de patrones que salga a una interfaz conectada a varios buses de almacenamiento
    en varias máquinas, usando 1 canal, en lugar de poner un proveedor de patrones en cada máquina, usando varios canales.

Los cables de diferentes colores no tienen nada que ver con hacer una subred, aparte de que no se conectarán entre sí.

Pueden ser

*   un bus de importación y un bus de almacenamiento configurados para transferir ítems o fluidos de un contenedor a otro como una tubería de ítems o fluidos
*   un plano de aniquilación y un bus de almacenamiento, para que el único lugar donde el plano de aniquilación pueda poner lo que rompe sea el bus de almacenamiento, permitiéndote filtrar el plano
*   una interfaz y un plano de formación, para que lo que se inserte en la interfaz se empuje al plano de formación y se coloque/suelte en el mundo
*   una configuración para hacer cuarzo Certus automáticamente, regulada y controlada por un <ItemLink id="level_emitter" /> en la red principal
*   un sistema de almacenamiento especializado accesible desde la red principal mediante la interacción especial de bus de almacenamiento en interfaz, para almacenar la producción de una granja sin desbordar infinitamente tu almacenamiento principal
*   y así sucesivamente

Muy útil para hacer subredes es el <ItemLink id="quartz_fiber" />. Transfiere energía entre redes sin
conectarlas, permitiéndote alimentar subredes sin necesidad de poner aceptadores de energía y cables de energía por todas partes.