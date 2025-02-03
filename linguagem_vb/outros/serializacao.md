## Serialização

#### JavaScriptSerializer

- Presente no Assembly System.Web.Extensions, Version=4.0.0.0
    - Adicionar a referência System.Web.Extensions

~~~vb
Imports System.Web.Script.Serialization 

Public Class Program

    Public Shared Sub Main()

        Dim strJson As String = "{ ""Id"": 1, ""Nome"": ""Fulano de Tal"" }"

        Dim objSerializado = New JavaScriptSerializer().Deserialize(Of Exemplo)(strJson)

        Console.WriteLine(objSerializado.GetType())
        Console.WriteLine(objSerializado.Nome)

        Console.ReadKey()
    End Sub

End Class


Public Class Exemplo
    Public Property Id() As Integer
    Public Property Nome As String
End Class
~~~