#### Exemplo de Type.GetType()

- O parâmetro passado para Type.GetType é uma string que contém o nome completo (fully qualified name) da classe, incluindo o namespace.
- O método Type.GetType("ConsoleApp01Intro.Exemplo") tenta localizar a classe Exemplo dentro do namespace ConsoleApp01Intro e retorna uma instância do tipo Type que descreve essa classe, se ela for encontrada.
- Se a classe não for encontrada, tipo será Nothing (nulo), e nenhuma informação de tipo será retornada.
- O código Type.GetType("ConsoleApp01Intro.Exemplo") vai procurar a classe Exemplo e, se encontrada, permitirá que você use informações sobre essa classe em tempo de execução, como criar instâncias, acessar propriedades e métodos, etc.
- Se o nome da classe ou o namespace não estiver correto ou não for qualificado totalmente, Type.GetType retornará Nothing, pois o método não encontrará o tipo.

~~~vb
Public Class Program

    Public Shared Sub Main()

        Dim ex As Exemplo = New Exemplo()

        Dim tipo = Type.GetType("ConsoleApp01Intro.Exemplo") 'namespace (ou projeto?).NomeClasse

        If tipo IsNot Nothing Then

            Console.WriteLine(ex.GetType())

        End If

        Console.ReadKey()
    End Sub

End Class


Public Class Exemplo
    Public Property Id() As Integer
    Public Property Nome As String
End Class
~~~