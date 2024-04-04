# gherkin-cucumber-bdd

## Gherkin

Gherkin é uma linguagem natural que se baseia em um conjunto de palavras-chave traduzidas para vários idiomas, incluindo o português. Seu propósito fundamental é permitir que qualquer pessoa, independente de sua expertise técnica, compreenda o comportamento de uma funcionalidade de software.

### Palavras-Chave em Gherkin

Os cenários em Gherkin são descritos em arquivos no formato `.feature`.

Aqui estão algumas das palavras-chave principais:

- **Given (Dado)**: Define a pré-condição, estabelecendo o estado inicial do sistema antes da interação do usuário.
- **When (Quando)**: Descreve a ação a ser executada, aguardando uma resposta do sistema.
- **Then (Então)**: Valida se o resultado esperado foi alcançado.
- **And (E)**: Utilizado para complementar um fluxo.

Outras palavras-chave incluem:

- **But (Mas)**: Utilizado para complementar um fluxo negativo.
- **Feature (Funcionalidade)**: Nomeia a funcionalidade a ser testada.
- **Background (Contexto)**: Permite o reuso de passos em todos os cenários do arquivo `.feature`.
- **Scenario (Cenário)**: Descreve o comportamento testado em um cenário específico.
- **Scenario Outline (Esquema de Cenário)**: Utilizado em cenários com múltiplos exemplos.

### Exemplo de Cenário com Exemplos em Gherkin

Suponhamos um cenário onde estamos testando uma funcionalidade de login em um sistema. Podemos utilizar o recurso de `Scenario Outline` para descrever diferentes casos de teste.

```gherkin
Scenario Outline: Login no Sistema
  Given que estou na página de login
  When eu insiro o usuário "<username>" e a senha "<password>"
  Then devo ser redirecionado para a página inicial

  Examples:
    | username  | password  |
    | user1     | pass123   |
    | user2     | pass456   |
    | user3     | pass789   |

Neste exemplo, o Scenario Outline descreve um cenário genérico de login com variáveis <username> e <password>. Na seção de Examples, diferentes conjuntos de dados são fornecidos para testar o comportamento do sistema com diferentes credenciais de usuário.

Este formato permite executar o mesmo cenário com vários conjuntos de dados, facilitando a realização de testes abrangentes e identificando comportamentos inesperados.

```

## Cucumber

É uma ferramenta de testes que permite a tradução dos cenários de teste criados com Gherkin para testes automatizados.

```javascript
const { Given, When, Then } = require('cucumber');
const assert = require('assert');

Given('que estou na página de login', function () {
 // Implemente aqui a navegação para a página de login
});

When('eu insiro o usuário {string} e a senha {string}', function (username, password) {
 // Implemente aqui a lógica para inserir usuário e senha nos campos
});

Then('devo ser redirecionado para a página inicial', function () {
 // Implemente aqui a verificação de redirecionamento para a página inicial após o login
 // Exemplo com assert:
 const isLoggedIn = true; // Simulação de sucesso no login
 assert.strictEqual(isLoggedIn, true, 'Login bem-sucedido');
});


```

## BDD (Desenvolvimento Guiado por Comportamento)

BDD, ou Desenvolvimento Guiado por Comportamento, é uma técnica de desenvolvimento ágil que enfatiza a colaboração entre desenvolvedores, QA e indivíduos não técnicos. O objetivo é criar um entendimento compartilhado dos requisitos do sistema. Gherkin é frequentemente utilizado nesse processo para descrever comportamentos e cenários.