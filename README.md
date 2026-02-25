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

- [x] TC_01_Login\Logout;
- [x] TC_02_Register New User;
- [x] TC_03_Open New Account;
- [x] TC_04_Transfer Funds;


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

## Arquitetura de pastas

