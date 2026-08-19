---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: Emisor de Nivel de Umbral ME
    icon: extendedae:threshold_level_emitter
categories:
- extended devices
item_ids:
- extendedae:threshold_level_emitter
---

# Emisor de Nivel de Umbral ME

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_threshold_level_emitter.snbt"></ImportStructure>
</GameScene>

Funciona como un pestillo Reiniciar-Establecer. Apaga la señal de redstone cuando la cantidad de un objeto en la red es menor que
el umbral inferior y la enciende cuando la cantidad es mayor que el umbral superior.

Por ejemplo, supongamos que el umbral inferior está configurado en 100 y el umbral superior en 150.

Al principio la red está vacía, por lo que el emisor no estará activo.

A medida que la cantidad del objeto crece y supera 150, el emisor enviará una señal de redstone.

Cuando la cantidad disminuye y es menor que 150, el emisor sigue enviando señal.

Finalmente, cuando la cantidad es menor que 100, el emisor se apagará.
