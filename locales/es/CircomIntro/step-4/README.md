Con tu circuito `multiplier.circom` listo, vamos a compilarlo usando el complemento Compilador de Circuito.

## Selección de la Versión del Compilador

Escoge la **Versión del Compilador** deseada desde el menú desplegable. Para este tutorial, selecciona la última versión estable.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/select_compiler_version.png" alt="select-compiler-version" width=250 height=100>

## Configuración de las Opciones de Compilación

- **Auto Compilación:** Puedes habilitar esta opción para que automáticamente se compile tu circuito cada vez que guardes algún cambio realizado en este.
- **Ocultar Advertencias:** Habilita esto para suprimir las advertencias del compilador.
- **Configuración Avanzada:**
  - Click en expandir.
  - Selecciona el **Campo Prime**. Para la mayoría de los casos, `BN128` es suficiente.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/advanced_configuration.png" alt="advanced-configuration" width=300 height=100>

## Compilación del circuito

1. Haga clic en el botón **Compilar**.
2. El compilador procesará su circuito.
3. Si tiene éxito, verá un mensaje de éxito de compilación.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/compilation_success.png" alt="compilation-success" width=200 height=400>

**Nota:** Si hay algún error, se mostrará en la consola. Revise su código en busca de errores tipográficos o de sintaxis.

## Entendiendo el resultado de la compilación

- Después de una compilación exitosa, la sección **Configuración y Exportaciones** se hace visible.
- Puede continuar con el siguiente paso para realizar una configuración de confianza.

En el siguiente paso, realizaremos una configuración de confianza utilizando el circuito compilado.
