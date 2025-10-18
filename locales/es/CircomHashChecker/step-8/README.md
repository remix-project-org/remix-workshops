## Comprender «groth16_trusted_setup.ts»

Navega hasta `scripts/groth16/groth16_trusted_setup.ts`. Este script realiza la configuración de confianza necesaria para generar pruebas.

### Desglose del código

#### Compilación de circuitos:

- Utiliza `remix.call(“circuit-compiler”, “generateR1cs”, ...)` para generar `R1CS` (sistema de restricciones de rango 1) a partir del circuito.

#### Pasos de configuración de confianza:

- `snarkjs.zKey.newZKey`: Inicializa la clave de prueba (`zkey_0`).
- `snarkjs.zKey.contribute`: Añade contribuciones a la clave de prueba (`zkey_1`).
- `snarkjs.zKey.beacon`: Finaliza la clave de prueba (`zkey_final`).

#### Verificación:

- `snarkjs.zKey.verifyFromR1cs`: Verifica la clave de prueba con respecto a `R1CS` y los parámetros iniciales.

#### Exportación de claves:

- Exporta la clave de verificación a `scripts/groth16/zk/keys/verification_key.json`.
- Exporta la clave de verificación final (`scripts/groth16/zk/keys/zkey_final.txt`).

### Propósito

- Realiza la configuración de confianza necesaria para el sistema de verificación `Groth16`.
- Genera las claves necesarias para la generación y verificación de pruebas.

### Ejecutar el script

- Haga clic en el botón de reproducción del editor o haga clic con el botón derecho del ratón en el archivo y seleccione «Ejecutar».
- Espera a que se complete el script y aparezca «setup done» en el terminal.