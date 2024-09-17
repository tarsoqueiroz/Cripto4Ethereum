# Criptomoeda para uma rede Ethereum

Criando uma Criptomoeda (token padrão ERC-20) para Rede Ethereum.

## Tecnologias

- Solidity
- Truffle
- Ganache
- Remix IDE
- Metamask

## Tarefas

- Criar o token ERC-20
- Publicar no Ganache
- Realizar algumas transações

## Carteira

Instalar a extensão do Metamask no Chrome e criar uma carteira.

## Ganache

Download do Ganache em `https://archive.trufflesuite.com/ganache/`

Ativar o Ganache com a seguinte configuração:

- `NEW WORKSPACE`
- WORKSPACE
  - WORKSPACE NAME: `myethnet`
- SERVER
  - HOSTNAME: `127.0.0.1`
  - PORT NUMBER: `7545`
  - NETWORK ID: `5777`
- `START`

## Adicionar rede ao Metamask

Acessar no **Metamask**: 

- `Configurações`
- `Redes`
- `Adicionar uma rede`
- `Add a network manually`

Preencher com as seguintes informações:

- Nome da rede: `MyEthNet`
- Novo URL da RPC: `HTTP://127.0.0.1:7545`
- ID da cadeia: `1337`
- Símbolo da moeda: `TQH`

## Importar conta ao Metamask

No **Metamask** em `Selecione uma conta` e:

- `Add account or hardware wallet`
- `Importar conta`

Importe uma chave privada de `ACCOUNTS` no **Ganache** informando no **Metamask** o seguinte:

- Selecione o tipo: `Chave privada`
- Cole a string da sua chave privada aqui: `<PEGAR DO GANACHE>`

Renomear essa conta para: `DIOAcc01`

## Conectar Metamask ao Remix

No `https://remix.ethereum.org/` selecionar:

- `Deploy & run transactions`
- `ENVIRONMENT`
- `Injected Provider - Metamask`

Para conectar a conta ao **Remix** seguir as orientações a seguir:

> [Manually connecting to a dapp](https://support.metamask.io/third-party-platforms-and-dapps/manually-connecting-to-a-dapp/)

## Primeiro Smartcontract

No `https://remix.ethereum.org/`:

- `FILE EXPLORER`
- `contracts`

Criar o arquivo `DIOCoin.sol` e nele colocar o código:

- [`DIOCoin.sol`](./DIOCoin.sol)

No `https://remix.ethereum.org/` em `SOLIDITY COMPILER`:

- Em `COMPILER` selecionar `0.8.15+commit.e14f2714`
- Clicar em `Compile DIOCoin.sol`
- Se tudo estiver OK irá aparecer um **tick verde**

## Fazendo algumas transações

No `https://remix.ethereum.org/` em `DEPLOY & RUN TRANSACTIONS`:

- Selecionar em `CONTRACT` o contrato `DIOToken - contracts/DIOCoin.sol`
- Clicar em `Deploy`

O **MetaMask** irá surgir solicitando confirmação:

- Clicar em `Confirmar`

No **Ganache** será possível ver a transação do contrato.

No `https://remix.ethereum.org/` em `Deployed/Unpinned Contracts` pode-se visualizar os `getters` e `functions` do contrato.

Clicando em `decimals`, `name` e `symbol` vemos os valores atribuidos a esse contrato.

Em `balanceOf` usando a conta que criamos o contrato (`DIOAcc01`) vemos o valor de `totalSupply`.

Seguindo as instruções de [Importar conta ao Metamask](#importar-conta-ao-metamask), importe a segunda conta disponibilizada no **Ganache** identificando-a como `DIOAcc02`.

Em `balanceOf` usando esta segunda conta importada (`DIOAcc02`) vemos o valor zerado.

## Visualizando o Token DIO no Metamask

Na visão expandida do Metamask no browser, selecione em `Tokens` para as duas contas (`DIOAcc01` e `DIOAcc02`):

- `Importar`
- `Endereço de contrato do token`: inserir o endereço do contrato criado no **Ganache**
- `Seguinte`

Conseguiremos visualizar no **Metamask** o saldo do token DIO.

## Executando transações de uma conta para a outra

No `REMIX` em `DEPLOY & RUN TRANSACTIONS`:

- Em `ACCOUNT` colocar o endereço de `DIOAcc01`
- Em `Deployed/Unpinned Contracts` - `transfer`:
  - Para `receiver` colocar o endereço de `DIOAcc02`
  - Em `numTokens` o valor 500000000000000000 
  - Clicar em `transact`
  - Confirmar no **Metamask**

Transferindo 0.5 DIO de `DIOAcc01` para `DIOAcc02`. Verifique o token `DIO` no **Metamask** nas duas contas para confirmar os saldos.

No `REMIX` em `DEPLOY & RUN TRANSACTIONS`:

- Em `ACCOUNT` colocar o endereço de `DIOAcc02`
- Em `Deployed/Unpinned Contracts` - `transfer`:
  - Para `receiver` colocar o endereço de `DIOAcc01`
  - Em `numTokens` o valor 250000000000000000 
  - Clicar em `transact`
  - Confirmar no **Metamask**

Transferindo 0.25 DIO de `DIOAcc02` para `DIOAcc01`. Verifique o token `DIO` no **Metamask** nas duas contas para confirmar os saldos.

## That't all

...folks!!!
