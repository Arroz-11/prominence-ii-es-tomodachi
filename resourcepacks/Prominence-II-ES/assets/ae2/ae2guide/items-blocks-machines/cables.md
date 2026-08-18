---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Cables
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# Cables

<GameScene zoom="3" background="transparent">
  <ImportStructure src="../assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

Aunque las redes ME también se crean con máquinas adyacentes compatibles con ME, los cables son la forma principal de extender una red ME sobre áreas más grandes.

Los cables de diferentes colores se pueden usar para asegurar que los cables adyacentes no se conecten entre sí, permitiendo que los [canales](../ae2-mechanics/channels.md) se distribuyan de manera más eficiente. También afectan el color de los terminales conectados a ellos, así no tienes que tener todos tus terminales de color púrpura. Los cables de fluix se conectan con todos los demás colores.

Ten en cuenta que **LOS CANALES NO TIENEN NADA QUE VER CON EL COLOR DEL CABLE**

## Una Nota Importante

**Si eres nuevo en AE2 y no estás familiarizado con los canales, usa cable inteligente y cable inteligente denso siempre que puedas. Mostrará cómo se enrutan los canales a través de tu red, haciendo su comportamiento más comprensible.**

## Otra Nota

**Estos no son tuberías de objetos, fluidos, energía, etc.** No tienen inventario interno, los proveedores de patrones y las máquinas no "empujan" hacia ellos, todo lo que hacen es conectar [dispositivos](../ae2-mechanics/devices.md) de AE2 en una red.

## Cable de Cristal

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/fluix_glass_cable.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" /> es el cable más simple de craftear, transfiere energía y hasta 8 [canales](../ae2-mechanics/channels.md). Viene en 17 colores diferentes, siendo el predeterminado el fluix, y se puede teñir de cualquier color usando cualquiera de los 16 tintes.

Para craftear cables de colores, rodea un tinte de cualquier tipo con 8 cables del mismo tipo (el color de los cables no importa, pero deben ser del mismo tipo: cristal, inteligente, etc.). También puedes pintar cables con cualquier pincel compatible con Forge en el mundo.

Puedes craftear cualquier cable de color con un cubo de agua para quitar el tinte.

Puedes cubrir el cable con lana para crear <ItemLink id="fluix_covered_cable" />, y craftear <ItemLink id="fluix_smart_cable" /> para tener una mejor idea de lo que está pasando con tus [canales](../ae2-mechanics/channels.md).

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

## Cable Revestido

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

La variante de cable revestido no ofrece ventajas de juego sobre su contraparte <ItemLink id="fluix_glass_cable" />. Sin embargo, se puede usar como una opción estética alternativa si prefieres el aspecto revestido.

Se puede colorear de la misma manera que <ItemLink id="fluix_glass_cable" />. Cuatro <ItemLink id="fluix_covered_cable" /> se pueden craftear con redstone y piedra luminosa para hacer <ItemLink id="fluix_covered_dense_cable" />.

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

## Cable Densos

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Cable de mayor capacidad, puede transportar 32 canales a diferencia del cable estándar que solo puede transportar 8, sin embargo no admite buses, por lo que primero debes bajar de denso a un cable más pequeño (como <ItemLink id="fluix_glass_cable" /> o <ItemLink id="fluix_smart_cable" />) antes de usar buses o paneles.

Los cables densos anulan ligeramente el comportamiento de "camino más corto" de los canales; los canales tomarán el camino más corto hacia un cable denso, y luego el camino más corto a través de ese cable denso hacia un controlador.

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

## Cable Inteligente

<Row>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

Aunque tienen cierta similitud en apariencia con <ItemLink id="fluix_covered_cable" />, proporcionan una función de diagnóstico al visualizar el uso de canales en los cables; los canales aparecen como líneas de colores iluminadas que recorren la franja negra en los cables, dándote una comprensión de cómo se están usando tus canales en tu red. Para cables inteligentes regulares, los primeros cuatro canales se muestran como líneas del color del cable, los siguientes cuatro se muestran como líneas blancas. Para cable inteligente denso, cada franja representa 4 canales.

En redes con un <ItemLink id="controller" />, las líneas en los cables muestran la ruta exacta que toman los canales.

Los cables inteligentes en redes ad-hoc mostrarán en cambio el número de canales en uso en toda la red en lugar del número de canales que fluyen a través de ese cable específico.

Estos también se pueden colorear de la misma manera que <ItemLink id="fluix_glass_cable" />.

<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />
