## Compilación del circuito

### Selección de la versión del compilador

1. Ve al complemento **Circuit Compiler** en la barra lateral.
2. Seleccione la **versión del compilador** deseada en el menú desplegable. Para este tutorial, selecciona la última versión estable.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/select_compiler_version.png" alt="select-compiler-version" width=250 height=100>

### Configuración de las opciones de compilación

- **Compilación automática:** Puede habilitar esta opción para compilar automáticamente su circuito cada vez que guarde los cambios.
- **Ocultar advertencias:** Active esta opción para suprimir las advertencias del compilador, si las hay.
- **Configuración avanzada:**
  - Haga clic para ampliar.
  - Seleccione el **campo principal**. En la mayoría de los casos, `BN128` es suficiente.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/advanced_configuration.png" alt="advanced-configuration" width=300 height=100>

### Compilación del circuito

1. Haga clic en el botón **Compilar**.
2. Espere a que finalice la compilación. Si la compilación se realiza correctamente, aparecerá una insignia de éxito.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/compilation_success.png" alt="compilation-success" width=300 height=675>

### Comprender el resultado de la compilación

- Tras una compilación satisfactoria, la sección **Configuración y exportaciones** se vuelve visible.
- Puede continuar con el siguiente paso para realizar una configuración de confianza.

En el siguiente paso, realizaremos una configuración de confianza utilizando el circuito compilado.