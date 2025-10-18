Let's write a simple Circom circuit.

## Creating a New Circuit File

1. In the **File Explorer** on the left sidebar, click on the **Create New File** icon.
2. Name your file `multiplier.circom` and press **Enter**.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-3/images/create_new_file.png" alt="create-new-file" width=300 height=200>

## Writing the Circuit

Ouvrez `multiplier.circom` et ajoutez le code suivant :

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

## Explanation:

- template `Multiplier()`: Defines a new circuit template called Multiplier.
- `signal input a;` and `signal input b;`: Declare input signals a and b.
- `signal output c;`: Declare an output signal c.
- `c <== a * b;`: Constrain c to be the product of a and b.
- `component main = Multiplier();`: Instantiates the Multiplier circuit as main, which is required for the compiler.

### NB:

Les signaux sont des valeurs dans un circuit cryptographique qui sont strictement déterminées par les équations et les contraintes du circuit. Think of a signal as a value that must follow specific mathematical rules defined by the circuit—once set, it can't be changed arbitrarily. Dans la programmation régulière, les variables sont flexibles et peuvent être mises à jour ou réaffectées selon les besoins, alors que les signaux ne peuvent pas être modifiés librement.
