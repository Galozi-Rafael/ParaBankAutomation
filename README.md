# ParaBankAutomation

Repositório para automatizar tarefas no Parabank: https://parabank.parasoft.com/parabank/index.htm

## Objetivo

Criar uma automação que percorra toda a caminhada de um usuário em um Internet Bank:

- **Registrar** no site;
- **Criar** uma conta;
- **Visualizar** os detalhes das contas;
- **Transferir** fundos de uma conta para outra;
- **Encontrar** transações que foram feitas;
- **Requisitar** um emprestimo;
- **Pagar** contas;
- **Editar** os detalhes do usuário;
- **Realizar** o logout da conta;



## Tecnologias

- **UiPath**;
- **.NET**.

## Pages

- [x] Open Home;
- [x] Open New Account;
- [x] Accounts Overview;
- [x] Transfer Funds;
- [x] Bill Pay;
- [x] Find Transaction;
- [x] Update Contact Info;
- [x] Request Loan;
- [x] Register;
- [x] Forgot Login Info.

## Test Cases

- [x] TC_01: Login\Logout;
- [x] TC_02: Register New User;
- [x] TC_03: Open New Account;
- [x] TC_04: Transfer Funds;
- [x] TC_05: Bill Pay;
- [x] TC_06: Find Transactions;
- [x] TC_07: Update Contact Info;
- [x] TC_08: Apply for a Loan.


## TC_01_Login\Logout

### Descrição
Validar que um usuário previamente cadastrado consegue realizar login com sucesso no sistema e efetuar logout corretamente.

### Objetivo
- Validar autenticação com credenciais válidas;
- Validar redirecionamento para página de conta;
- Validar encerramento correto da sessão após logout;

### Pré-condição
- Usuário previamente cadastrado no sistema;
- Sistema disponível e acessível via navegador;

### Passo a Passo do Teste

1. Abrir o navegador;
2. Navegar até: `https://parabank.parasoft.com/parabank/index.htm`;
3. Inserir username válido;
4. Inserir password válida;
5. Clicar no botão **Log In**;
6. Validar que a página **Accounts Overview** foi exibida;
7. Clicar no botão **Log Out**;

### Resultado Esperado

- Login realizado com sucesso;
- Página **Accounts Overview** visível;
- Após logout, usuário redirecionado para tela inicial;
- Sessão encerrada corretamente;


## TC_02_Register New User

### Descrição
Validar que um novo usuário consegue se registrar corretamente no sistema.

### Objetivo
- Validar preenchimento de formulário de cadastro;
- Validar criação de novo usuário;
- Validar login automático após registro;

### Pré-condição
- Usuário ainda não cadastrado;
- Sistema acessível;

### Passo a Passo do Teste

1. Abrir o navegador;
2. Navegar até: `https://parabank.parasoft.com/parabank/index.htm`;
3. Clicar em **Register**;
4. Preencher todos os campos obrigatórios:
   - First Name;
   - Last Name;
   - Address;
   - City;
   - State;
   - Zip Code;
   - Phone;
   - SSN;
   - Username;
   - Password;
   - Confirm Password;
5. Clicar no botão **Register**;

### Resultado Esperado

- Conta criada com sucesso;
- Mensagem de boas-vindas exibida;
- Usuário autenticado automaticamente após registro;


## TC_03_Open New Account

### Descrição
Validar que um usuário autenticado consegue abrir uma nova conta bancária.

### Objetivo
- Validar criação de nova conta corrente ou poupança;
- Validar geração automática de número de conta;
- Validar que nova conta aparece em Accounts Overview;

### Pré-condição
- Usuário autenticado;
- Usuário já possui pelo menos uma conta;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Open New Account**;
3. Selecionar tipo de conta (Checking ou Savings);
4. Selecionar conta base para funding;
5. Clicar em **Open New Account**;
6. Validar que o número da nova conta foi gerado;
7. Navegar até **Accounts Overview**;

### Resultado Esperado

- Nova conta criada com sucesso;
- Número da conta exibido;
- Conta listada em Accounts Overview;


## TC_04_Transfer Funds

### Descrição
Validar que um usuário autenticado consegue transferir fundos entre duas contas próprias com sucesso.

### Objetivo
- Validar funcionalidade de transferência interna entre contas;
- Validar débito da conta de origem;
- Validar crédito na conta de destino;
- Validar exibição da mensagem de sucesso da operação;

### Pré-condição
- Usuário autenticado no sistema;
- Usuário possui pelo menos duas contas ativas;
- Contas com saldo suficiente para transferência;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Transfer Funds** no menu principal;
3. Informar o valor da transferência no campo **Amount**;
4. Selecionar a conta de origem no campo **From Account**;
5. Selecionar a conta de destino no campo **To Account**;
6. Clicar no botão **Transfer**;

### Resultado Esperado

- Página de confirmação exibida;
- Mensagem indicando que a transferência foi concluída com sucesso;
- Valor debitado da conta de origem;
- Valor creditado na conta de destino;
- Transação registrada no histórico das contas envolvidas;

## TC_05_Bill Pay

### Descrição
Validar que um usuário autenticado consegue realizar o pagamento de uma conta (Bill Payment) com sucesso utilizando uma de suas contas bancárias.

### Objetivo
- Validar preenchimento do formulário de pagamento;
- Validar débito do valor na conta selecionada;
- Validar exibição da mensagem de confirmação;
- Validar registro da transação no histórico da conta;

### Pré-condição
- Usuário autenticado no sistema;
- Usuário possui pelo menos uma conta ativa;
- Conta com saldo suficiente para realizar o pagamento;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Bill Pay** no menu principal;
3. Preencher os dados do beneficiário:
   - Payee Name;
   - Address;
   - City;
   - State;
   - Zip Code;
   - Phone Number;
   - Account Number;
   - Verify Account Number;
4. Informar o valor no campo **Amount**;
5. Selecionar a conta de origem no campo **From Account**;
6. Clicar no botão **Send Payment**;



## TC_06_FindTransaction

### Descrição
Validar que um usuário autenticado consegue buscar transações utilizando o filtro por intervalo de datas, considerando como data inicial 10 dias antes da data atual.

### Objetivo
- Validar funcionalidade de busca por intervalo de datas;
- Validar preenchimento dinâmico de datas (Today - 10 dias);
- Validar retorno das transações dentro do período informado;
- Validar exibição correta da lista de resultados;

### Pré-condição
- Usuário autenticado no sistema;
- Usuário possui histórico de transações nos últimos 10 dias;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Find Transactions** no menu principal;
3. Selecionar uma conta válida;
4. Selecionar a opção de busca por **Date Range**;
5. Informar a data inicial como:
   - Data atual menos 10 dias;
6. Informar a data final como:
   - Data atual;
7. Clicar no botão **Find Transactions**;

### Resultado Esperado

- Lista de transações exibida na tela;
- Todas as transações apresentadas devem estar dentro do intervalo informado;
- Nenhuma transação fora do período deve ser exibida;
- Sistema não deve apresentar erro ao utilizar datas dinâmicas;



## TC_07_UpdateContactInfo

### Descrição
Validar que um usuário autenticado consegue atualizar suas informações de contato com sucesso.

### Objetivo
- Validar edição dos dados cadastrais do usuário;
- Validar persistência das informações atualizadas;
- Validar exibição de mensagem de confirmação;
- Garantir que os dados alterados permanecem salvos após navegação ou novo login;

### Pré-condição
- Usuário autenticado no sistema;
- Usuário previamente cadastrado;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Update Contact Info** no menu principal;
3. Alterar um ou mais campos de contato, como:
   - First Name;
   - Last Name;
   - Address;
   - City;
   - State;
   - Zip Code;
   - Phone Number;
4. Clicar no botão **Update Profile**;
5. Navegar para outra página;
6. Retornar à página **Update Contact Info** para validar persistência;

### Resultado Esperado

- Mensagem de confirmação indicando atualização bem-sucedida;
- Dados alterados exibidos corretamente na tela;
- Informações persistidas após navegação ou novo login;


## TC_08_Apply for a Loan

### Descrição
Validar que um usuário autenticado consegue solicitar um empréstimo (Loan) com sucesso através do sistema.

### Objetivo
- Validar preenchimento dos campos obrigatórios da solicitação;
- Validar envio da requisição de empréstimo;
- Validar exibição do status da solicitação (Approved ou Denied);
- Validar geração de nova conta de empréstimo quando aprovado;

### Pré-condição
- Usuário autenticado no sistema;
- Usuário possui pelo menos uma conta ativa;
- Conta com saldo ou histórico válido para solicitação;

### Passo a Passo do Teste

1. Realizar login com usuário válido;
2. Clicar em **Request Loan** no menu principal;
3. Informar o valor desejado no campo **Loan Amount**;
4. Informar o valor da entrada no campo **Down Payment**;
5. Selecionar a conta de origem no campo **From Account**;
6. Clicar no botão **Apply Now**;

### Resultado Esperado

- Página de resposta exibida;
- Status da solicitação informado (Approved ou Denied);
- Em caso de aprovação:
- Nova conta de empréstimo gerada;
- Conta listada em **Accounts Overview**;
- Em caso de reprovação:
- Mensagem informando que o empréstimo não foi aprovado;



### Resultado Esperado

- Página de confirmação exibida;
- Mensagem indicando que o pagamento foi enviado com sucesso;
- Valor debitado da conta selecionada;
- Transação registrada no histórico da conta;

## Arquitetura de pastas

