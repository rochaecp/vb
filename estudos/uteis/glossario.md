## ByRef

- Modificador de parâmetros que indica que indica que o argumento é passado por referência.
- Passa o argumento como uma referência, permitindo que o método altere o valor original.

## ByVal

- Modificador de parâmetros que indica que indica que o argumento é passado por valor.
- Isso significa que uma cópia do valor do argumento é passada para o método, e qualquer alteração feita nesse valor dentro do método não afeta o valor original passado.

## Friend

- Equivalentes ao modificadores internal em C#.
- São acessíveis dentro do mesmo assembly

## Me

- Equivalente ao this do C#. Refere-se à instância atual da classe.

## MustOverride

- Equivalentes a classes abstratas em C#.

## Nothing 

- É amplamente equivalente a null em C#, com a flexibilidade adicional de inicializar variáveis de tipos de valor ao seu padrão.

## Property 

- É equivalente a uma propriedade em C#.
- o compilador automaticamente cria métodos Get (para leitura) e Set (para escrita), que permitem acessar e modificar o valor da propriedade.
- Ex. (vb): Public Property TaskName() As String
- Ex. (c#): public string TaskName { get; set; }

## ReadOnly 

- Usado para definir propriedades ou campos que podem ser atribuídos um valor apenas uma vez, geralmente durante a inicialização ou no construtor da classe. Após isso, o valor não pode ser alterado.

## Shared

- Equivalente ao static do C#.