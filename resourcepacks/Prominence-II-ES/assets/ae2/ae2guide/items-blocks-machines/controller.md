---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Controlador
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# El ME Controlador

<BlockImage id="controller" p:state="online" scale="8" />

El controlador es el centro de enrutamiento de una [ME Network](../ae2-mechanics/me-network-connections.md).
Sin él, una red es "ad-hoc" y solo puede tener un máximo de 8 [dispositivos](../ae2-mechanics/devices.md) que usen canales en total.

No es posible tener 2 controladores en una [ME Network](../ae2-mechanics/me-network-connections.md).

El controlador proporciona 32 [Canales](../ae2-mechanics/channels.md) por cara.

El controlador requiere 6 AE/t por bloque de controlador para
funcionar. Cada bloque de controlador puede almacenar 8000 AE, por lo que las redes más grandes podrían requerir almacenamiento de energía adicional.
Consulta [energía](../ae2-mechanics/energy.md) para más detalles.

Los controladores multibloque pueden construirse de forma bastante libre.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Sin embargo, hay algunas reglas que deben seguirse:

1.  Todos los bloques de controlador en una [ME Network](../ae2-mechanics/me-network-connections.md) deben estar conectados; de lo contrario, los bloques se pondrán rojos.
2.  El tamaño del controlador debe estar dentro de 7x7x7; de lo contrario, se pondrá rojo.
3.  Un controlador puede tener 2 bloques adyacentes en como máximo 1 eje; si un bloque viola esta regla, se desactivará y se pondrá rojo.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Mientras se sigan todas las reglas y esté alimentado, el controlador debería brillar y
cambiar de colores.

Puedes hacer clic derecho en un controlador para obtener la misma GUI que una <ItemLink id="network_tool" />

## Receta

<RecipeFor id="controller" />
