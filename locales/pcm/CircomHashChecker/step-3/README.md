## As we de check wetin de `calculate_hash.circom`

Fain your way go the `circuits` directory con open `calculate_hash.circom`. Circom code for the Hash Checker circuit dey inside this file.

### Breakdown of di code

#### Pragma and Includes:

- `pragma circom 2.0.0;` de specify the Circom version.
- "Put "circomlib/circuits/poseidon.circom";\` fetch con add the Poseidon hash function from [CircomLib](https://github.com/iden3/circomlib).

#### 'CalculateHash\` Template:

- Defines inputs `value1`, `value2`, `value3`, `value4`.
- E de use the `Poseidon` hash function to compute hash of all dis values.\
- Outputs `out`, na the hash be this.

#### `HashChecker` Template:

- Input na the same numbers plus hash.
- Instantiates `CalculateHash` as `calculateSecret`.
- Computes `calculatedHash`.
- E de use `assert(hash == calculatedHash);` de make sure say the hash wey dem provide match the hash wey dem don calculate.

#### Main Component:

- `component main {public [hash]} = HashChecker();`
- E de specify say `hash` na `public` input, while the values con be `private`.

### Purpose

The circuit de allow persin to prove say they know `value1`, `value2`, `value3`, and `value4` wey de hash to `hash` wey dey specific and dem no go reveal the value by themselves.