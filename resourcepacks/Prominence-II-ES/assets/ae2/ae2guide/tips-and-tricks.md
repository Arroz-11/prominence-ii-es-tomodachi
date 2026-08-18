---
navigation:
  title: Consejos y Trucos
  position: 20
---

# Consejos y Trucos

Un montón de pequeñas recomendaciones aleatorias

* Quita Optifine
* Puedes rotar y hacer zoom en las escenas de la guía que tengan los botones de zoom y de mostrar/ocultar anotaciones
* Mantén tu red en forma de árbol y evita bucles
* [Dispositivos](ae2-mechanics/devices.md) de bloque completo en grupos de 8 o menos a menos que entiendas profundamente cómo los [canales](ae2-mechanics/channels.md)
  se enrutan a través de una red
* Elige una madera y quédate con ella para todos tus [patrones](items-blocks-machines/patterns.md). Sí, habilitar sustituciones
  en los patrones a veces funciona, pero usar el mismo tipo de madera en todas partes reduce mucho las molestias.
* Organiza tus [patrones](items-blocks-machines/patterns.md) verticalmente en la <ItemLink id="pattern_access_terminal" />/
  distribuye tus patrones entre tus [proveedores](items-blocks-machines/pattern_provider.md) para que las recetas se puedan realizar en paralelo.
* Añade una [celda de energía](items-blocks-machines/energy_cells.md) para que tu red pueda manejar picos de energía.
* Puedes usar agua en el <ItemLink id="condenser" />
* La mejor manera de mantener tu red limpia es no poner botín aleatorio de mobs como espadas y armaduras. Cada combinación única de
  encantamiento y durabilidad es otro [tipo](ae2-mechanics/bytes-and-types.md).
* Debe ocurrir un evento de "entrada de objeto al sistema" al devolver el resultado de un [patrón de procesamiento](items-blocks-machines/patterns.md),
  como a través de un <ItemLink id="import_bus" />, <ItemLink id="interface" /> o la ranura de retorno de un <ItemLink id="pattern_provider" />,
  no puedes simplemente canalizar el resultado a un cofre con un <ItemLink id="storage_bus" />.
* No olvides que puedes rotar y hacer zoom en las escenas de la guía que tengan los botones de zoom y de mostrar/ocultar anotaciones
* El <ItemLink id="pattern_provider" /> solo enviará lotes completos de recetas y solo a través de un solo lado. Esto es útil
  para asegurarse de que las máquinas no reciban lotes parciales, pero a veces quieres que los ingredientes vayan a varios lugares.
  Puedes lograr esto usando un <ItemLink id="interface" />, ya sea como una subred de ["tubería"](example-setups/pipe-subnet.md) o usando
  su capacidad para contener múltiples pilas de objetos diferentes, fluidos, químicos, etc., todo a la vez, para usarlo como una especie de cofre/tanque intermedio.
* Puedes hacer zoom y rotar las escenas de la guía que tengan los botones de zoom y de mostrar/ocultar anotaciones