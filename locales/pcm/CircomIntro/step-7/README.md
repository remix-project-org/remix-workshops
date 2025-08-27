As the witness don dey computed, d final step na to generate proof wey other people fit verify.

## To Generate d Proof

1. Inside the **Generate Proof** section, you d option to **Export Verifier Calldata**.
    - Enable d **Export Verifier Calldata** checkbox if you dey plan to verify d proof on-chain.
2. Click ontop d **Generate Proof** button.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/generate_proof.png" alt="generate-proof" width=280 height=120>

## To understand d Output

- After yu generate the proof, the plugin go display d proof data.
- If yu enable **Export Verifier Calldata**, e go also provide d calldata wey yu need for on-chain verification.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/proof_generated.png" alt="proof-generated" width=310 height=350>

## Next things yu go do na

- **Verification:** You fit use d verification key abi contract wey yu export earlier to verify d proof.
- **On-Chain Verification:** If yu dey familiar with smart contracts, you fit deploy d verification contract and use d calldata to perform on-chain verification.

**Congratulations!** You don successfully write Circom circuit, compile am, perform trusted setup, compute witness, nd still generate proof using Remix-IDE.

## Resources to join

- [Circom Documentation](https://docs.circom.io/)
- [Remix-IDE Documentation](https://remix-ide.readthedocs.io/)
- [Zero-Knowledge Proofs Explained](https://zkproof.org/)

Make yu feel free to experiment with more complex circuits nd explore wetn Circom and Remix-IDE still fit do.
