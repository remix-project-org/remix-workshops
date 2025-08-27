Make we write one easy circom circuit.

## How you go take create new circuit file

1. For the file explorer wey dey the left sidebar, tap on the create new file icon.
2. Give your file this name `multiplier.circom`con press enter.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-3/images/create_new_file.png" alt="create-new-file" width=300 height=200>

## How you go take write the circuit

Open `multiplier.circom` con add these code:

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

## Meaning:

- template `Multiplier()`: dey define new circuit template wey dem dey call Multiplier.
- `signal input a;` and `signal input b;`: dey declare input signals a and b.
- `signal output c;`: dey declare output signal c.
- `c <== a * b;`: dey constrain c make e be the product of a and b.
- `component main = Multiplier();`: dey Instantiates the Multiplier circuit as main, which dey meant for the compiler.

### NB:

Signals na values for cryptographic circuit wey strictly dey based on the circuit equations and constraints. Reason the signal like say na value wey gats follow specific mathematical rules wey dey defined by the circuit- once you set am, e no fit just change. For normal programming, variables dey flexible and e fir dey updated or reassigned as you want am, but no forget say signals no fit change easily.
