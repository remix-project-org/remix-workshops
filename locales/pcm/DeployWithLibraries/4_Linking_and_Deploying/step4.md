Switch go d `Deploy & Run` module
![Run transaction](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/remix_runtransaction.png "Run Transaction")

- Make yu select d Remix VM Environment nd select d `sampleContract` contract inside d list of compiled contracts.

- Tap ontop `Deploy`

The terminal suppose output something like `creation of sample errored: <address> no b valid address. Abeg check d address way dem provide if e valid.`
E dey expected: **We don set `autoDeployLib` to false, so Remix expects to get address nd no be just `<address>`**

So we go need deploy d library to get hin address.

- Select d library `aLib` inside d list of compiled contract con hit `deploy`

  ![Choose aLib](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/contract_alib.png "Choose aLib")

- Click d clipboard icon to fit copy d address of d library.

  ![Copy lib1](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/alib_copy.png "Copy")

- Paste am inside d **contract sample's** metadata JSON.

- Sti select d `sampleContract` contract fr d `Run transaction` module con hit deploy.

- By now deploy suppose show successful.

