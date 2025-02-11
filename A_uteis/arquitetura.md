## Classes de Regra de Negócio (RN)

- Lidam com a lógica do negócio, como validações, cálculos, e fluxos de processos. Elas não devem acessar diretamente o banco de dados.
- Representam a lógica de negócio que rege o comportamento da aplicação, ou seja, as decisões, operações e validações específicas ao domínio da aplicação.
- Essas classes encapsulam o que deve ou não ser permitido, de acordo com os processos da empresa ou organização.
- Função Principal: Implementar a lógica de negócio do sistema, ou seja, as regras que governam o comportamento e as operações da aplicação de acordo com as regras de negócio da empresa ou domínio.
- Foco
    - Validação de dados.
    - Cálculos e processos específicos do negócio.
    - Definir o fluxo de operações baseadas nas regras da empresa.

## Classes de Repositório

- São responsáveis pelo acesso ao banco de dados, executando queries e persistindo dados. Elas não devem conter lógica de negócio.    
