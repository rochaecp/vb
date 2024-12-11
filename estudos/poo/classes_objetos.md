## Classes

- Em POO, uma classe é um modelo ou “molde” que define as propriedades (atributos) e os comportamentos (métodos) que os objetos criados a partir dela terão. 
- Pense na classe como uma planta de um edifício: ela descreve como um objeto deve ser, mas não é o próprio objeto.

~~~vb
Public Class Pessoa
    Public Nome As String
    Public Idade As Integer
End Class
~~~

## Objetos

- Um objeto é uma instância concreta de uma classe. 
- Usando a analogia da planta, o objeto seria o edifício real construído a partir daquela planta. 
- Em VB.NET, objetos são criados a partir de classes usando a palavra-chave ```New```.

~~~vb
Dim pessoa1 As New Pessoa()
pessoa1.Nome = "João"
pessoa1.Idade = 30
~~~

## Verificando se uma classe existe em um Projeto - Type.GetType()

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