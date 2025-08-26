## Compute Witness

1. **Acceda a la sección «Compute Witness» (Testigo informático):**
    - Tras la configuración de confianza, la sección **Compute Witness** estará disponible.

2. **Valores de entrada**:
    - Verás campos de entrada para «valor1», «valor2», «valor3», «valor4» y «hash».
    - Introduzca los valores para cada entrada. Por ejemplo:
       - `valor1`: `1234`
       - `valor2`: `2`
       - `valor3`: `3`
       - `value4`: `4`

3. **Calculate the Hash**:

    - Compute the Poseidon hash of the four values using an external tool or library compatible with the Poseidon hash function.
    - For the values above, here is the computed Poseidon hash `16382790289988537028417564277589554649233048801038362947503054340165041751802`.
    - Enter the calculated `hash` value in the `hash` input field.

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/compute_witness.png" alt="compute-witness" width=250 height=400>

4. **Compute the Witness**:

    - Click on the **Compute Witness** button.
    - Wait for the process to complete. A success badge will appear if the witness is computed successfully.
    - Si se realiza correctamente, verás que se ha creado «calculate_hash.wtn» en el directorio «.bin» del explorador de archivos.

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/witness_computed.png" alt="witness-computed" width=300 height=100>