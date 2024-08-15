# BrLessKoin Token (BRLK)
### Descrição

_BrLessKoin Token (BRLK) é um token ERC20 implementado em Solidity. Este contrato define um token padrão ERC20 com funcionalidades adicionais para minting e burning, permitindo que o proprietário emita ou queime tokens conforme necessário. O contrato também segue as melhores práticas de segurança e eficiência em Solidity, incluindo o uso de um padrão de propriedade (Ownable) para restringir o acesso a funções críticas._

### Características do Token
**Nome**: BrLessKoin Token
**Símbolo**: BRLK
**Decimais**: 18
**Oferta total inicial**: 1.000.000 BRLK

### Funcionalidades Principais
- ERC20 Padrão

## O contrato implementa as seguintes funções padrão de um token ERC20:

- **totalSupply()**: Retorna a oferta total de tokens.
- **balanceOf(address tokenOwner)**: Retorna o saldo de um endereço específico.
- **transfer(address to, uint tokens)**: Permite transferir tokens para outro endereço.
- **approve(address spender, uint tokens)**: Aprova um terceiro para gastar tokens em nome do proprietário.
- **allowance(address tokenOwner, address spender)**: Verifica quantos tokens um terceiro está autorizado a gastar em nome de um endereço.
- **transferFrom(address from, address to, uint tokens)**: Permite a um terceiro transferir tokens de um endereço aprovado.

### Funcionalidades de Minting e Burning

- **Minting**: O proprietário do contrato pode emitir novos tokens usando a função mint(uint256 amount). Esta função incrementa a oferta total e atribui os novos tokens ao saldo do proprietário.
- **Burning**: O proprietário do contrato pode queimar tokens usando a função burn(uint256 amount). Esta função reduz a oferta total e diminui o saldo do proprietário.

### Controle de Acesso com Ownable
O contrato utiliza um padrão de propriedade (Ownable) para restringir o acesso a funções críticas, como mint e burn. Apenas o proprietário do contrato pode executar essas funções. Além disso, o contrato permite transferir a propriedade para outro endereço, se necessário.

## Melhorias Implementadas
Em comparação com a _versão original do contrato_, sugerida pelo professor, foram realizadas as seguintes melhorias:

- **Uso do padrão Ownable**: Implementou-se o contrato Ownable para controlar o acesso às funções de mint e burn. Isso assegura que apenas o proprietário possa emitir ou queimar tokens, melhorando a segurança do contrato.

- **Proteção nas funções de transferência (transfer e transferFrom)**: Foram adicionadas mensagens de erro mais descritivas (require) para melhorar a clareza caso as transações falhem por falta de saldo ou excesso de allowance.

- **Manejo de decimais na oferta inicial**: Ajustou-se a oferta inicial para considerar os decimais, garantindo que a quantidade de tokens inicial seja consistente com o padrão ERC20.

- **Eventos de Transferência**: Foram adicionados eventos Transfer e Approval em locais estratégicos do contrato para assegurar a transparência e rastreabilidade de todas as operações que modifiquem saldos ou permissões.

> Observação: Esse repositório faz parte integral do projeto de criação de **Token ERC20** para a plataforma de ensino **DIO**, e o codigo aqui mostrado representa a customização e implementação de melhoras do codigo base sugerido pelo Instrutor **Ricardo Zago**:

Codigo original (base): [ver código](https://github.com/relsi/web3-blockchain-classes/blob/main/token.sol)