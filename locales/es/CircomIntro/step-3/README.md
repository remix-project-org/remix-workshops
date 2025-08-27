Escribamos un circuito de Circom simple.

## Creación de un nuevo archivo de circuito

1. En el **Explorador de archivos** en la barra lateral izquierda, haga clic en el icono **Crear nuevo archivo**.
2. Nombre su archivo `multiplier.circom` y presione **Enter**.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-3/images/create_new_file.png" alt="create-new-file" width=300 height=200>

## Escribiendo el circuito

Abra `multiplier.circom` y agregue el siguiente código:

```circom
pragma circom 2.0.0;

template Multiplier() {
    signal input a;
    signal input b;
    signal output c;

    c <== a * b;
}

component main = Multiplier();
```

## Explicación:

 - plantilla `Multiplier()`: Define una nueva plantilla de circuito llamada Multiplier.
 - `entrada de señal a;` y `entrada de señal b;`: Declarar señales de entrada a y b.
 - `salida de señal c;`: Declara una señal de salida c.
 - `c <== a * b;`: Restringa c a ser el producto de a y b.
 - `component main = Multiplier();`: Instancia el circuito multiplicador como principal, que es necesario para el compilador.

### NB:

Las señales son valores en un circuito criptográfico que están estrictamente determinados por las ecuaciones y restricciones del circuito. Piense en una señal como un valor que debe seguir reglas matemáticas específicas definidas por el circuito; una vez establecido, no se puede cambiar arbitrariamente. En la programación regular, las variables son flexibles y se pueden actualizar o reasignar según sea necesario, mientras que las señales no se pueden alterar libremente.
