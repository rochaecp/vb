## AddressOf

- O operador AddressOf retorna a referência para um método em VB.NET, permitindo que esse método seja passado como argumento para outros métodos ou delegados

## And

- Avalia ambas as condições, independentemente do resultado da primeira.

## AndAlso

- É um operador lógico de curto-circuito em VB.NET que realiza uma operação de e lógico entre duas expressões booleanas.
- Ele avalia as condições da esquerda para a direita e retorna True somente se ambas as condições forem verdadeiras.
- O termo curto-circuito significa que, se a primeira condição for False, a segunda condição não é avaliada, pois o resultado já é garantido como False.
- AndAlso é preferível quando a segunda condição é complexa, custosa, ou desnecessária se a primeira já for suficiente para determinar o resultado.

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

## IIf

- É uma função em VB.NET que realiza uma operação condicional semelhante ao operador ternário (? :) de outras linguagens, como C#. 
- Sintaxe: ```IIf(condição, valorSeVerdadeiro, valorSeFalso)```
- IIf sempre avalia ambos os valores (valorSeVerdadeiro e valorSeFalso), independentemente do resultado da condição, o que pode ser menos eficiente se um dos valores envolver uma operação complexa.
- Para evitar a avaliação desnecessária, If condicional é geralmente preferido para operações mais complexas.

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

## Of

- O Of em VB.NET é utilizado principalmente em dois contextos: genéricos e conversões de tipos específicos, especialmente na desserialização e em métodos que aceitam tipos parametrizados.
- O Of é usado para definir quais tipos um genérico irá utilizar, oferecendo flexibilidade para o código funcionar com vários tipos de dados.

## Or

- Operador lógico que avalia ambas as condições, independentemente do resultado da primeira.
- Of é usado em contextos genéricos para especificar tipos de dados a serem utilizados.
- Permite flexibilidade na criação de classes, métodos, e interfaces que podem ser reutilizadas com diferentes tipos de dados.

## OrElse

- É um operador lógico em VB.NET que realiza uma operação de ou lógico curto-circuito entre duas expressões booleanas.
- Ele é utilizado para avaliar duas condições e retorna True se pelo menos uma das condições for verdadeira.
- O termo curto-circuito significa que, se a primeira condição for True, a segunda condição não é avaliada, porque o resultado já é garantido como True.
- OrElse é preferível quando a segunda condição é complexa ou desnecessária caso a primeira já seja suficiente.

## Overrides

- O modificador Overrides em VB.NET é usado para indicar que um método, propriedade ou evento em uma classe está sobrescrevendo (substituindo) uma implementação de uma classe base.
- Quando uma classe herda de outra, ela pode "herdar" métodos e propriedades, e o Overrides permite que a classe derivada forneça sua própria implementação para esses membros herdados.

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

## With

- A instrução With...End With é uma estrutura que permite executar múltiplas operações em um mesmo objeto sem precisar repetir o nome desse objeto a cada linha.
- É uma ferramenta útil para simplificar o código, torná-lo mais legível e fácil de manter, especialmente quando várias propriedades ou métodos de um único objeto são acessados em sequência.
- A instrução With começa um bloco de código em que todas as instruções que começam com um ponto (.) referem-se ao objeto especificado no With.