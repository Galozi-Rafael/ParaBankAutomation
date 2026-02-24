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


## Arquitetura de pastas

