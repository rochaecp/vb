## With

- A instrução With...End With é uma estrutura que permite executar múltiplas operações em um mesmo objeto sem precisar repetir o nome desse objeto a cada linha.
- É uma ferramenta útil para simplificar o código, torná-lo mais legível e fácil de manter, especialmente quando várias propriedades ou métodos de um único objeto são acessados em sequência.
- A instrução With começa um bloco de código em que todas as instruções que começam com um ponto (.) referem-se ao objeto especificado no With.
- Observações
    - É diferente do ```using``` do C#

#### Exemplo sem With

~~~vb
Dim pessoa As New Pessoa()
pessoa.Nome = "João"
pessoa.Idade = 30
pessoa.DizerOla()
~~~

#### Exemplo com With

~~~vb
Dim pessoa As New Pessoa()
With pessoa
    .Nome = "João"
    .Idade = 30
    .DizerOla()
End With
~~~