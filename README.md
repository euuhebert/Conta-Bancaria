# Projeto de Sistema Bancário em Java

Este projeto de sistema bancário em Java é uma implementação básica que representa um banco com clientes, contas correntes e contas poupança. A seguir, uma explicação detalhada de cada classe e sua funcionalidade dentro do sistema.

## Diagrama UML
![Diagrama em branco (3)](https://github.com/euuhebert/Conta-Bancaria/assets/112333883/0ecaf3e6-30ab-47b4-8b44-fe11ca665fd6)


## Classes

### 1. Cliente

A classe `Cliente` representa um cliente do banco. Atualmente, ela possui apenas um atributo `nome`, que é definido pelo método `setNome`. Em uma aplicação bancária completa, essa classe poderia conter mais informações sobre o cliente, como endereço, número de telefone, etc.

### 2. Conta

A classe abstrata `Conta` é a classe base para contas correntes e contas poupança. Ela implementa a interface `IConta`, contendo métodos para saque, depósito, transferência e impressão de extrato. Além disso, a classe `Conta` possui os seguintes atributos:

- **agencia:** O número da agência associado à conta (agência padrão é `1`).
- **numero:** Número único da conta, atribuído automaticamente.
- **saldo:** Saldo atual da conta.
- **cliente:** Objeto do tipo `Cliente` associado à conta.

A classe `Conta` também possui um método `imprimirInfoComuns` para imprimir informações comuns a todas as contas, como titular, agência, número da conta e saldo.

### 3. ContaCorrente

A classe `ContaCorrente` é uma subclasse de `Conta` e representa uma conta corrente. Ela possui uma implementação específica do método `imprimirExtrato`, que imprime as informações comuns da conta corrente.

### 4. ContaPoupanca

A classe `ContaPoupanca` é uma subclasse de `Conta` e representa uma conta poupança. Assim como `ContaCorrente`, ela possui uma implementação específica do método `imprimirExtrato`, que imprime as informações comuns da conta poupança.

### 5. Banco

A classe `Banco` representa um banco e possui atributos como `nome` e uma lista de `contas`. Atualmente, a classe possui apenas métodos getters e setters para o nome do banco. Em uma aplicação real, poderia incluir métodos para adicionar contas, pesquisar contas por titular, etc.

### 6. IConta (Interface)

A interface `IConta` define os métodos que todas as contas devem implementar: `sacar`, `depositar`, `transferir` e `imprimirExtrato`.

### 7. Main

A classe `Main` contém o método principal `main`, onde um cliente é criado e associado a uma conta corrente e uma conta poupança. Em seguida, são realizadas operações de depósito, transferência e impressão de extratos para ambas as contas.

## Como Usar o Sistema

1. **Criar um Cliente:**
   ```java
   Cliente anderson = new Cliente();
   anderson.setNome("Anderson");
   ```

2. **Criar Contas:**
   ```java
   Conta cc = new ContaCorrente(anderson);
   Conta contapoupanca = new ContaPoupanca(anderson);
   ```

3. **Realizar Operações:**
   ```java
   cc.depositar(100);
   cc.transferir(10, contapoupanca);
   ```

4. **Imprimir Extratos:**
   ```java
   cc.imprimirExtrato();
   contapoupanca.imprimirExtrato();
   ```

Este é um exemplo básico de um sistema bancário em Java. Para uma aplicação real, seria necessário adicionar mais funcionalidades, como validação de saldo suficiente para saques e transferências, tratamento de exceções, persistência de dados em um banco de dados, entre outros.
