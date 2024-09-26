# Regions em VB.NET

- As Regions são usadas para organizar o código em seções dobráveis no editor do Visual Studio, facilitando a navegação em blocos de código extensos.
- Elas são úteis para agrupar funções, propriedades, variáveis ou qualquer outro trecho de código que você deseje manter mais organizado e visualmente simplificado.

#### Sintaxe de uma Region

~~~vb
#Region "Nome da Região"
    ' Aqui vai o código agrupado
#End Region
~~~

~~~vb
Module Module1

    #Region "Variáveis Globais"
    Dim nome As String = "Mauricio"
    Dim idade As Integer = 32
    #End Region

    #Region "Métodos"
    Sub Main()
        Console.WriteLine("Nome: " & nome)
        Console.WriteLine("Idade: " & idade)
        Console.ReadLine()
    End Sub
    #End Region

End Module

~~~