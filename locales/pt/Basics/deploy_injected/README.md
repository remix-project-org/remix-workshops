1. Se você não tem uma carteira de navegador como a **MetaMask**, baixe e instale uma agora.

2. Clique no ícone da MetaMask no seu navegador. Entre e escolha a rede de testes Ephemery. Talvez seja necessário atualizar as configurações da sua carteira para poder ver **redes de teste**.  Como alternativa, você pode ir ao módulo de Implantar e Executar transação do Remix e, na seção AMBIENTE, selecionar Ephemery.

3. Obtendo ETH de teste para redes de teste públicas costuma ser irritante.  Ephemery é uma rede pública atualizada mensalmente, então obter ETH de teste deve ser tranquilo.  Aqui está um link para alguns <a href="https://github.com/ephemery-testnet/ephemery-resources?tab=readme-ov-file#faucets" target="_blank">faucets Ephemery</a>.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/testnet.png)

Sepolia é outra rede de testes popular que não é atualizada, então as implantações persistirão, mas os faucets Sepolia são mais difíceis de usar.

Na carteira do seu navegador, certifique-se de NÃO ter selecionado a mainnet ou qualquer rede que custe ETH real. No módulo Implantar e Executar, abaixo da caixa de seleção Ambiente, você verá um emblema com o ID da rede e, para redes populares, seu nome.  No caso abaixo é Sepolia.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/sepolia.png)

5. Certifique-se de ver 2_Owner.sol como uma opção na caixa de seleção **CONTRATO** e clique no botão **Implementar**.

Se a caixa de seleção **CONTRATO** estiver vazia, você precisará compilar 2_Owner novamente, tornando 2_Owner.sol o arquivo ativo no **editor** e então ir para o **Solidity Compiler** para compilá-lo.

6. Após clicar no botão `Implementar`, você verá o pop-up da carteira do navegador solicitando que você pague pelas transações.  Se você tiver o tipo apropriado de ETH para esta rede, aprove esta transação.  Verifique a impressão no terminal.  Depois que o bloco for validado, a **instância implantada** aparecerá na parte inferior de Implantar e Executar

E com isso você concluiu este tutorial.  Agora você tem experiência com abertura, compilação, implantação e interação com contratos inteligentes no Remix IDE.
