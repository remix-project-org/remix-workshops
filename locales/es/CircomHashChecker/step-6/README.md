## Testigo informático

1. **Acceda a la sección «Compute Witness» (Testigo informático):**
    - Tras la configuración de confianza, la sección **Compute Witness** estará disponible.

2. **Valores de entrada**:
    - Verás campos de entrada para «valor1», «valor2», «valor3», «valor4» y «hash».
    - Introduzca los valores para cada entrada. Por ejemplo:
       - `valor1`: `1234`
       - `valor2`: `2`
       - `valor3`: `3`
       - `valor4`: `4`

3. **Calcular el hash**:

    - Calcula el hash Poseidon de los cuatro valores utilizando una herramienta externa o una biblioteca compatible con la función hash Poseidon.
    - Para los valores anteriores, aquí está el hash Poseidon calculado `16382790289988537028417564277589554649233048801038362947503054340165041751802`.
    - Introduzca el valor «hash» calculado en el campo de entrada «hash».

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/compute_witness.png" alt="compute-witness" width=250 height=400>

4. **Calcular el testigo**:

    - Haga clic en el botón **Compute Witness**.
    - Espere a que finalice el proceso. Aparecerá una insignia de éxito si el testigo se calcula correctamente.
    - Si se realiza correctamente, verás que se ha creado «calculate_hash.wtn» en el directorio «.bin» del explorador de archivos.

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/witness_computed.png" alt="witness-computed" width=300 height=100>