## Comprender «groth16_zkproof.ts»

Navega hasta `scripts/groth16/groth16_zkproof.ts`. Este script genera la prueba de conocimiento cero y la prepara para su verificación.

### Descripción general del código

#### Cargando archivos:

- Lee los archivos R1CS y WASM generados a partir del circuito.
- Carga la llave de prueba final (`zkey_final`) y verifica la llave (`vKey`).

#### Definiciones de Entradas (Inputs):

- Conjunto de valores privados (`value1`, `value2`, `value3`, `value4`).
- Calcula el `hash` usando Poseidon desde [CircomLib](https://github.com/iden3/circomlib).

#### Cálculo de Testigo y Generación de Prueba:

- Calcula el testigo (`wtns`).
- Compara el testigo contra el `R1CS`.
- Genera la prueba usando `Groth16`.
- Verifica la prueba.

#### Exportando Contratos e Inputs de Verificador:

- Genera un Contrato verificador en Solidity.
- Exporta los inputs de prueba hacía `input.json`.

### Propósito

- Generar una prueba de conocimiento cero que el probador conocen los valores de hash de un hash en específico.
- Prepara el contrato del verificador y sus inputs para una verificación en cadena.

### Ejecuta el Script

- Dale click al botón de empezar en el editor, o click derecho en el archivo y selecciona "Ejecutar".
- Espera a que el script se complete y a que la "validez de pruebas zk" inicie sesion en el terminal.