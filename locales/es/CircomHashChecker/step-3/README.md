## Explorando `calculate_hash.circom`

Navegue hasta el directorio «circuits» y abra «calculate_hash.circom». Este archivo contiene el código Circom para el circuito Hash Checker.

### Desglose del código

#### Pragma e incluye:

- `pragma circom 2.0.0;` especifica la versión de Circom.
- `incluir «circomlib/circuits/poseidon.circom»;` obtiene e incluye la función hash Poseidon de [CircomLib](https://github.com/iden3/circomlib).

#### Plantilla `CalculateHash`:

- Define las entradas «valor1», «valor2», «valor3» y «valor4».
- Utiliza la función hash `Poseidon` para calcular un hash de estos valores.
- Salida `out`, que es el hash.

#### Plantilla `HashChecker`:

- Las entradas son los mismos valores más un «hash».
- Instancia `CalculateHash` como `calculateSecret`.
- Calcula `calculatedHash`.
- Utiliza `assert(hash == calculatedHash);` para garantizar que el hash proporcionado coincide con el hash calculado.

#### Componente Principal:

- `componente principal {público [hash]} = HashChecker();`
- Especifica que «hash» es una entrada «pública», mientras que los valores son «privados».

### Objetivo

El circuito permite a alguien demostrar que conoce «valor1», «valor2», «valor3» y «valor4», que se resumen en un «hash» específico, sin revelar los valores en sí.