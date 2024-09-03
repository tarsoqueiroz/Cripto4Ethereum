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

Renomear essa conta para: `MyEthNet Acc01`

> **POSIÇÃO CORRENTE:** ***06:48***
