## Propriedades

- São características de uma classe que armazenam informações sobre o estado do objeto. 
- No exemplo acima, Nome e Idade são propriedades da classe Pessoa.
- Em Public Property TaskName() As String, os parênteses não são obrigatórios e podem ser omitidos sem alterar o funcionamento da propriedade.
- Se TaskName fosse um array, a declaração seria diferente. Para um array de String, por exemplo, seria:

~~~vb
Public Class Pessoa
    Public Nome As String
    Public Idade As Integer
End Class
~~~

~~~vb
Public Class Produto
    ' Campo privado para armazenar o valor da propriedade
    Private precoValue As Decimal

    ' Propriedade pública para acessar e modificar o preço
    Public Property Preco() As Decimal
        Get
            Return precoValue
        End Get
        Set(ByVal value As Decimal)
            ' Validação: o preço não pode ser negativo
            If value >= 0 Then
                precoValue = value
            Else
                Throw New ArgumentException("O preço não pode ser negativo.")
            End If
        End Set
    End Property
End Class


'utilizando
Module Module1
    Sub Main()
        Dim p As New Produto()

        ' Definindo o preço usando a propriedade
        Try
            p.Preco = 100D
            Console.WriteLine("Preço definido com sucesso: " & p.Preco)
        Catch ex As ArgumentException
            Console.WriteLine(ex.Message)
        End Try

        ' Tentando definir um preço negativo
        Try
            p.Preco = -50D
        Catch ex As ArgumentException
            Console.WriteLine("Erro: " & ex.Message)
        End Try
    End Sub
End Module
~~~

## Métodos

- São funções ou sub-rotinas que definem ações que um objeto pode realizar. 
- Eles representam o comportamento do objeto. 
- Por exemplo, você poderia adicionar um método Falar na classe Pessoa.

~~~vb
Public Sub Falar()
    Console.WriteLine("Olá, meu nome é " & Nome)
End Sub
~~~

## Eventos

- Eventos são notificações que ocorrem em resposta a ações específicas. 
- Em VB.NET, os eventos são úteis para criar interações entre objetos, principalmente em interfaces gráficas. 
- Eles permitem que a classe notifique outras partes do programa quando algo acontece (por exemplo, clicar em um botão).

## Exemplos

#### Exemplo 1

~~~vb
Public Class Pessoa
    ' Propriedade privada
    Private _idade As Integer

    ' Propriedade pública com encapsulamento
    Public Property Idade As Integer
        Get
            Return _idade
        End Get
        Set(value As Integer)
            If value >= 0 Then
                _idade = value
            Else
                Console.WriteLine("Idade inválida!")
            End If
        End Set
    End Property
End Class
~~~

#### Exemplo 2

~~~vb
' Arquivo Pessoa.vb
Public Class Pessoa
    Public Property nome() As String

    ' Construtor sem parâmetros
    Public Sub New()
        Me.nome = "Nome não fornecido"
    End Sub

    ' Construtor com parâmetros
    Public Sub New(nome As String)
        Me.nome = nome
    End Sub

    Public Sub ExibirInfo()
        Console.WriteLine($"Ola, me chamo {nome}")
    End Sub
End Class
~~~

~~~vb
' Arquivo Program.vb
Public Class Program

    Public Shared Sub Main()

        ' Forma básica de instanciar um objeto de Pessoa
        Dim pessoa1 As New Pessoa()
        pessoa1.nome = "Pessoa 1"
        pessoa1.ExibirInfo()

        ' Instanciando e inicializando o objeto em uma única linha
        Dim pessoa2 As Pessoa = New Pessoa() With {
            .nome = "Pessoa 2"
        }
        pessoa2.ExibirInfo()

        ' Declarando a variável sem instanciar imediatamente
        Dim pessoa3 As Pessoa ' ou ainda Dim pessoa3 As Pessoa = Nothing
        pessoa3 = New Pessoa() ' Instanciando depois
        pessoa3.nome = "Pessoa 3"
        pessoa3.ExibirInfo()

        ' Instanciando usando o construtor
        Dim pessoa4 As New Pessoa("Pessoa 4")
        pessoa4.ExibirInfo() ' Saída: Ola, me chamo Ana

        Console.ReadKey() ' Espera que o usuário pressione qualquer tecla para continuar
    End Sub

End Class
~~~

~~~vb
Public Property TaskNames() As String()
~~~

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

# Métodos

