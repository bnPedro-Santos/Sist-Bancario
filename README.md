# Sistema Bancário Digital

Sistema de gerenciamento bancário desenvolvido em Python que simula operações de uma conta corrente integrada com poupança e cheque especial.

## 📋 Funcionalidades

### Operações Básicas
- **Depósito**: Adicionar valores à conta corrente
- **Saque**: Retirar valores da conta corrente
- **Extrato**: Visualizar histórico completo de transações com data e hora
- **Consulta de Dados**: Ver informações da conta, saldo e poupança

### Poupança
- **Transferência para Poupança**: Mover valores da conta corrente para poupança
- **Resgate da Poupança**: Resgatar valores da poupança para conta corrente
- **Rendimento Automático**: Taxa de rendimento mensal de 0,5%

### Cheque Especial
- **Configuração de Limite**: Definir limite de crédito disponível
- **Taxa de Juros Personalizável**: Ajustar percentual de juros mensal
- **Débito de Juros**: Aplicar juros sobre valores utilizados do limite


## 📊 Estrutura do Código

### Classes Principais

#### `ContaCorrente`
Classe principal que gerencia a conta bancária.

**Atributos:**
- `nome_cliente`: Nome do titular
- `numero_conta`: Número da conta
- `saldo`: Saldo da conta corrente
- `extrato`: Lista de transações
- `poupanca`: Instância da classe Poupanca
- `credito`: Instância da classe ChequeEspecial

**Métodos principais:**
- `depositar(valor)`
- `sacar(valor)`
- `transferir_poupanca(valor)`
- `resgatar_poupanca(valor)`
- `ver_extrato()`
- `dados()`

#### `Poupanca`
Gerencia a conta poupança vinculada.

**Atributos:**
- `saldo`: Saldo da poupança
- `taxa_rendimento_mensal`: Taxa de rendimento (padrão 0,5%)

**Métodos:**
- `calcular_rendimento()`: Aplica rendimento mensal sobre o saldo

#### `ChequeEspecial`
Gerencia o limite de crédito e juros.

**Atributos:**
- `limite`: Limite de crédito disponível
- `juros_mensal`: Taxa de juros mensal (padrão 5%)
- `valor_ultilizado`: Valor utilizado do limite

**Métodos:**
- `def_limite(novo_limite)`: Define o limite de crédito
- `taxa_juros(nova_taxa_percent)`: Configura taxa de juros
- `juros_debitar()`: Calcula juros sobre valor utilizado


## 📝 Menu Interativo

O sistema oferece um menu com as seguintes opções:

```
1. Ver Extrato
2. Depositar
3. Sacar
4. Transferir para Poupança
5. Resgatar da Poupança
6. Aplicar Rendimento da Poupança
7. Debitar Juros do Cheque Especial
8. Definir Limite do Cheque Especial
0. Sair do Sistema
```


## ⚠️ Validações

O sistema inclui validações para:
- Valores negativos em operações
- Saldo insuficiente para saques e transferências
- Entrada de dados inválidos no menu interativo
- Configurações de limite e taxas negativas


## 🔍 Extrato Detalhado

Cada transação registra:
- Data e hora no formato `DD/MM/YYYY HH:MM:SS`
- Tipo de operação
- Valor da transação
- Saldo atual da conta corrente e poupança


## 📌 Observações

- Todas as transações são registradas no extrato com timestamp
- O rendimento da poupança deve ser aplicado manualmente (operação administrativa)
- Os juros do cheque especial são calculados apenas sobre o valor utilizado
- O sistema não persiste dados entre execuções (sem banco de dados)

---

Projeto desenvolvido por Pedro Henrique dos Santos como parte do curso SENAI
