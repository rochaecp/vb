## AndAlso

- 

## ByRef

- Modificador de parâmetros que indica que indica que o argumento é passado por referência.
- Passa o argumento como uma referência, permitindo que o método altere o valor original.

## ByVal

- Modificador de parâmetros que indica que indica que o argumento é passado por valor.
- Isso significa que uma cópia do valor do argumento é passada para o método, e qualquer alteração feita nesse valor dentro do método não afeta o valor original passado.

## Friend

- É um modificador de acesso equivalente ao internal do C#.
- Define que o membro é acessível apenas dentro do mesmo assembly.
- Isso significa que qualquer código dentro do mesmo projeto ou DLL pode acessar membros Friend, mas o acesso é restrito para fora desse contexto.

## Function

- Uma Function é um método que executa um bloco de código e retorna um valor.
- O tipo do valor de retorno é especificado após a palavra-chave As.

## Is

- Verifica se dois objetos referenciam a mesma instância

## IsNot

- Operador usado para comparar referências de objetos, verificando se dois objetos não são o mesmo.
- É geralmente usado para garantir que um objeto não seja Nothing ou para verificar se duas referências de objetos não apontam para o mesmo objeto.

## Me

- Equivalente ao this do C#. Refere-se à instância atual da classe.

## Module

- É uma estrutura que agrupa código, como métodos, variáveis, e constantes, que podem ser acessados globalmente sem a necessidade de instanciar um objeto.
- Módulos são semelhantes a classes, mas com algumas diferenças importantes.
- É um contêiner para membros estáticos, que podem ser funções (Sub), métodos (Function), variáveis, e outras estruturas de código que são compartilhadas em todo o programa.
- Acesso Global: Tudo dentro de um Module é acessível diretamente sem criar uma instância do módulo, funcionando como se os membros fossem Shared (estáticos).
- Uso Comum: Utilizado para agrupar funções auxiliares, constantes, e variáveis que são usadas em vários lugares do código.
- Em C#, não existe exatamente um equivalente direto ao Module, mas a funcionalidade pode ser replicada usando classes estáticas (static class). 

## MustOverride

- Equivalentes a classes abstratas (ou "obrigatórias") em C#.

## Nothing 

- É amplamente equivalente a null em C#, com a flexibilidade adicional de inicializar variáveis de tipos de valor ao seu padrão.

## Or

- Operador lógico que avalia ambas as condições, independentemente do resultado da primeira.

## OrElse

- É um operador lógico em VB.NET que realiza uma operação de ou lógico curto-circuito entre duas expressões booleanas.
- Ele é utilizado para avaliar duas condições e retorna True se pelo menos uma das condições for verdadeira.
- O termo curto-circuito significa que, se a primeira condição for True, a segunda condição não é avaliada, porque o resultado já é garantido como True.
- OrElse é preferível quando a segunda condição é complexa ou desnecessária caso a primeira já seja suficiente.

## Property 

- É equivalente a uma propriedade em C#.
- o compilador automaticamente cria métodos Get (para leitura) e Set (para escrita), que permitem acessar e modificar o valor da propriedade.
- Ex. (vb): ```Public Property TaskName() As String```
- Ex. (c#): ```public string TaskName { get; set; }```

## Protected

- Nível de acesso protegido: a propriedade pode ser acessada pela própria classe e também por suas classes derivadas, mas não é acessível fora dessas classes.

## ReadOnly 

- Usado para definir propriedades ou campos que podem ser atribuídos um valor apenas uma vez, geralmente durante a inicialização ou no construtor da classe. Após isso, o valor não pode ser alterado.
- Define que a propriedade é somente leitura, ou seja, ela pode ser lida, mas não pode ser modificada diretamente (não possui um Set).

## Shared

- Equivalente ao static do C#.

## Sub

- Uma Sub (Sub-rotina) é um método que executa um bloco de código, mas não retorna nenhum valor.
- Ela é usada para realizar uma ação ou processo, como modificar variáveis, chamar outros métodos, etc.

## Summary

- A tag ```<summary>``` é usada para criar um resumo descritivo sobre o elemento de código (como um método ou propriedade) ao qual está anexado. É uma convenção de documentação usada amplamente em VB.NET e outras linguagens como C#.
- Quando o desenvolvedor passa o mouse sobre o método ou propriedade no editor de código, esse comentário é exibido, ajudando a fornecer informações contextuais.