The Deploy property for `sampleContract.json` get everything wey you need to tell remix ide the address for the library for specific network.

- `<address>` get the address of the library wey dey already deployed. You gats specify this address for each network.
- `autoDeployLib` na boolean and e dey tell Remix IDE if e suppse autodeploy the library before deploying the contract.

Normally if `autoDeployLib` na true, we no go use `<address>` and Remix go automatically deploy the library before e deploy the contract.

For the sake of this demo- we go mimic situation wey be say the library don dey deployed based on say this na common situation.

So you go set autodeploy to false, for inside the `VM:-` entry.

Move go the next step.
