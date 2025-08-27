En este paso, configuraremos Remix para el desarrollo con Circom activando la extensión `Circom ZKP compiler`.

## Activando el Circom ZKP compiler

1. En el botón que se encuentra al final del panel a la izquierda de la pantalla, dale click en **Administrador de Complementos** (el botón con forma de enchufe).
   2. En la barra de búsqueda, escriba **Circom**.
2. Encuentra el complemento de **Compilador de Circuito** en la lista y dale click en el botón **Activar**.
3. La extensión aparecerá en su barra lateral.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-2/images/install_plugin.png" alt="install-plugin" width=200 height=475>

## La Interfaz del Compilador Circom

- **Menú de Versiones Desplegable:** Selecciona la versión del compilador de Circom que deseas usar.
- **Casilla de Compilación Automática:** Activa esta opción para compilar de forma automática tu circuido cada vez que realices un cambio en este.
- **Casilla para Ocultar Advertencias:** Activa esta opción para suprimir las advertencias del compilador.
- **Configuración Avanzada:** Dale click para expandir las opciones y seleccionar el campo prime (Ej: BN128, BLS12381).

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-2/images/compiler_interface.png" alt="compiler-interface" width=300 height=300>

Con el complemento instalado, ahora está listo para empezar a escribir código Circom en Remix-IDE.

**Nota:** asegúrese de que su conexión a Internet es estable, ya que Remix-IDE es una herramienta basada en la web.

En el siguiente paso, escribiremos nuestro primer circuito de Circom.
