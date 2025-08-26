Con el testigo calculado, el paso final es generar una prueba que pueda ser verificada por otros.

## Generar la prueba

1. In the **Generate Proof** section, you have the option to **Export Verifier Calldata**.
    - Enable the **Export Verifier Calldata** checkbox if you plan to verify the proof on-chain.
2. Click on the **Generate Proof** button.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/generate_proof.png" alt="generate-proof" width=280 height=120>

## Understanding the Output

 - After generating the proof, the plugin will display the proof data.
 - If you enabled **Export Verifier Calldata**, it will also provide the calldata needed for on-chain verification.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/proof_generated.png" alt="proof-generated" width=310 height=350>

## Próximos pasos

 - **Verification:** You can use the verification key or contract exported earlier to verify the proof.
 - **On-Chain Verification:** If you're familiar with smart contracts, you can deploy the verification contract and use the calldata to perform on-chain verification.

**Congratulations!** You've successfully written a Circom circuit, compiled it, performed a trusted setup, computed a witness, and generated a proof using Remix-IDE.

## Recursos adicionales

 - [Documentación de Circom](https://docs.circom.io/)
 - [Documentación de Remix-IDE](https://remix-ide.readthedocs.io/)
 - [Explicación de las pruebas de conocimiento cero](https://zkproof.org/)

Siéntase libre de experimentar con circuitos más complejos y explorar aún más las capacidades de Circom y Remix-IDE.
