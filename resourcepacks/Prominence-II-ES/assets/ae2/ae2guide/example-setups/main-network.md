---
navigation:
  parent: example-setups/example-setups-index.md
  title: Un Ejemplo de "Red Principal"
  icon: controller
---

# Un Ejemplo de "Red Principal"

Muchas otras configuraciones hacen referencia a una "Red Principal". También podrías preguntarte cómo todos estos [dispositivos](../ae2-mechanics/devices.md) se
unen en un sistema funcional. Aquí tienes un ejemplo:

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="3.9 0 1.9" max="9.1 5 7.1" thickness="0.05">
        Un gran grupo de proveedores de patrones y ensambladoras da mucho espacio para patrones de crafteo, corte de piedra y herrería.
        El patrón de tablero de ajedrez permite que los proveedores utilicen múltiples ensambladoras en paralelo mientras se mantiene compacto.
        Los grupos de 8 hacen imposible que los canales se enruten incorrectamente.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="3.9 0 9.9" max="5.1 3 12.1" thickness="0.05">
        Algunas máquinas, con una subred de tuberías para empujar sus salidas hacia los proveedores.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="-0.1 0 8.9" max="1.1 3 13.1" thickness="0.05">
      Algunas terminales y varios artilugios de utilidad. (probablemente quieras solo una terminal de trabajo, no una terminal normal _y_ una terminal de trabajo)
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="-0.1 0 -0.1" max="2.1 3 8.1" thickness="0.05">
      Una variedad de CPUs de crafteo. Algunas con mayores cantidades de almacenamiento y un poco más con menores cantidades de almacenamiento.
      Probablemente quieras tener más coprocesadores en una configuración real, pero eso sería un poco grande para esta escena.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5.9 0 13.9" max="7.1 1 15.1" thickness="0.05">
      Tu controlador debería estar en el centro de tu base, y probablemente un poco más grande que esto. Una forma de palo es bastante buena.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="11.9 0 7.9" max="13.1 4 13.1" thickness="0.05">
        Varios métodos de almacenamiento, con unidades o buses de almacenamiento. Observa que todos están en grupos de 8.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="10.9 0 0.9" max="13.1 2 7.1" thickness="0.05">
        Varios métodos de almacenamiento, con unidades o buses de almacenamiento. Observa que todos están en grupos de 8.
    </BoxAnnotation>

  <IsometricCamera yaw="315" pitch="30" />
</GameScene>
