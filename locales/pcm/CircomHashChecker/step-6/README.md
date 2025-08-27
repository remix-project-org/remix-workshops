## Compute Witness

1. **Access the Compute Witness Section**:
    - After setup wey dey trusted, the **compute Witness** section go de available.

2. **Input Values**:
    - You go see input fields for `value1`, `value2`, `value3`, `value4`, and `hash`.
    - Enter values for each input. For example:
       - `value1`: `1234`
       - `value2`: `2`
       - `value3`: `3`
       - `value4`: `4`

3. **Calculate the Hash**:

    - Compute Poseidon hash of the whol four values as you dey use external tool or library wey dey compatible with the Poseidon hash function.
    - For the values wey dey above na the Poseidon hash wey dem don compute be this
      `16382790289988537028417564277589554649233048801038362947503054340165041751802`.
    - The `hash` value wey you don calculate finish write am put inside the `hash` input field.

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/compute_witness.png" alt="compute-witness" width=250 height=400>

4. **Compute the Witness**:

    - Press **Compute Witness** button.
    - Wait make the process complete. Success badge go appear if dem compute the witness successfully.
    - If e dey successful,you go see `calculate_hash.wtn` wey dem create inside the `.bin` directory for the file explorer.

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/witness_computed.png" alt="witness-computed" width=300 height=100>