En este paso, configuraremos Remix para el desarrollo con Circom activando la extensión `Circom ZKP compiler`.

## Activando el Circom ZKP compiler

1. At the bottom of the icon panel on the left of the screen, click on the **Plugin Manager** (the plug icon).
   2. En la barra de búsqueda, escriba **Circom**.
2. Find the **Circuit Compiler** plugin in the list and click on the **Activate** button.
3. La extensión aparecerá en su barra lateral.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-2/images/install_plugin.png" alt="install-plugin" width=200 height=475>

## The Circom Compiler Interface

- **Compiler Version Dropdown:** Select the Circom compiler version you wish to use.
- **Auto Compile Checkbox:** Enable this to automatically compile your circuit whenever you make changes.
- **Hide Warnings Checkbox:** Enable this to suppress compiler warnings.
- **Advanced Configuration:** Click to expand options for selecting the prime field (e.g., BN128, BLS12381).

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-2/images/compiler_interface.png" alt="compiler-interface" width=300 height=300>

Con el complemento instalado, ahora está listo para empezar a escribir código Circom en Remix-IDE.

**Nota:** asegúrese de que su conexión a Internet es estable, ya que Remix-IDE es una herramienta basada en la web.

En el siguiente paso, escribiremos nuestro primer circuito de Circom.
