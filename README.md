# Desafio de Projeto - Criação de esquema conceitual do zero.

## Modelando cenário de Oficina

O diagrama EER (Enhanced Entity-Relationship) apresenta esquema conceitual para o contexto de oficina com base na narrativa fornecida.


### Narrativa

- Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
- Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas
- Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
- A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
- O valor de cada peça também irá compor a OS
- O cliente autoriza a execução dos serviços
- A mesma equipe avalia e executa os serviços
- Os mecânicos possuem código, nome, endereço e especialidade
- Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

### Relacionamento

- Cliente - Veiculo: Relacionamento: 1:N (Cliente para Veiculo). Um cliente pode ter vários veículos
- Veiculo - Ordem de Servico (OS): Relacionamento: 1:N (Veiculo para OS). Um veículo pode ter várias ordens de serviço.
- Ordem de Servico (OS) - Servico: Relacionamento: N:M (OS para Servico - gerando tabela associativa). Uma OS pode incluir vários serviços.
- Ordem de Servico (OS) - Mecanico: Relacionamento: N:M (OS para Mecânico - gerando tabelada associativa). Uma OS pode ser atendida por vários mecânicos.
- Ordem de Servico (OS) - Peca: Relacionamento: N:M (OS para Peça - gerando tabela associativa). Uma OS pode incluir várias peças.
- Ordem de Servico (OS) - Pagamento: Relacionamento: 1:1 (OS para Pagamento). Uma OS pode ter um pagamento associado.
- Pagamento - Forma de Pagamento: Relacionamento: 1:N (Pagamento para Forma de Pagamento). Um pagamento pode ter várias formas de pagamento. Cada Forma de Pagamento pertence a um único Pagamento.

### Vantagens da Estrutura de Pagamento

 - **Flexibilidade:** Permite inserir novas formas de pagameto sem alterar a lógica do BD
 - **Organização:** Evita a mistura de informações, pois cada tipo de pagamento tem seus campos específicos.
 - **Escalabilidade:** Se no futuro surgirem novos métodos de pagamento, basta adicionar na entidade Forma_Pagamento.


### Melhorias e Implementações

- Validar de dados e segurança

### Considerações:

A estrutura está bem organizada e atende aos requisitos de um sistema de oficina, com suporte a múltiplos métodos de pagamento.
