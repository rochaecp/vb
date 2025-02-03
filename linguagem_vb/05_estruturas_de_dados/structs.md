# VB.NET - Structs

- Em VB.NET, uma struct (ou Structure) é um tipo de dados que permite armazenar vários valores em uma única entidade. 
- Ela é semelhante a uma classe (ou Class), mas é mais leve e geralmente usada para representar dados simples que são agrupados logicamente, como coordenadas em um plano (x, y) ou dados de uma pessoa (nome, idade).
- Alguns exemplos comuns são coordenadas (x, y), pontos de cores (r, g, b), ou outras estruturas de dados simples.

## Diferença entre Struct e Class

- Structs são tipos de valor e classes são tipos de referência.
- Structs armazenam dados diretamente na variável e, quando são passadas para um método, uma cópia é criada.
- Classes armazenam uma referência (um ponteiro) para o objeto na memória, então, ao passar uma classe para um método, estamos passando um ponteiro para a mesma posição na memória, e não uma cópia dos dados.

## Exemplo

~~~vb
Structure Pessoa
    ' Campos da Struct
    Public Nome As String
    Public Idade As Integer

    ' Construtor (opcional)
    Public Sub New(nome As String, idade As Integer)
        Me.Nome = nome
        Me.Idade = idade
    End Sub

    ' Método
    Public Sub ExibirInfo()
        Console.WriteLine($"Nome: {Nome}, Idade: {Idade}")
    End Sub
End Structure

Module Program
    Sub Main(args As String())
        Dim p1 As New Pessoa("Joao", 25)
        p1.ExibirInfo()

        Console.ReadKey()
    End Sub
End Module
~~~