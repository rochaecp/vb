## Criar uma classe e instanciar um objeto a partir dela

- Observação: ao criar um construtor personalizado, o construtor padrão (o sem parâmetros) não é mais criado automaticamente

~~~vb
' Arquivo Pessoa.vb
Public Class Pessoa
    Public Property nome() As String

    ' construtor sem parâmetros
    Public Sub New()
        Me.nome = "Nome não fornecido"
    End Sub

    ' construtor com parâmetros
    Public Sub New(nome As String)
        Me.nome = nome
    End Sub

    Public Sub DizerOla()
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
        pessoa1.DizerOla()


        ' Instanciando e inicializando o objeto em uma única linha
        Dim pessoa2 As Pessoa = New Pessoa() With {
            .nome = "Pessoa 2"
        }
        pessoa2.DizerOla()


        ' Declarando a variável sem instanciar imediatamente
        Dim pessoa3 As Pessoa ' ou ainda Dim pessoa3 As Pessoa = Nothing
        pessoa3 = New Pessoa() ' Instanciando depois
        pessoa3.nome = "Pessoa 3"
        pessoa3.DizerOla()


        ' Instanciando usando o construtor
        Dim pessoa4 As New Pessoa("Pessoa 4")
        pessoa4.DizerOla() ' Saída: Ola, me chamo Ana


        Console.ReadKey() ' Espera que o usuário pressione qualquer tecla para continuar
    End Sub

End Class
~~~