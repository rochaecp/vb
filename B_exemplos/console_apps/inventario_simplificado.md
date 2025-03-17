# Exemplo: Inventário Simplificado

- Aplicativo de **Console** em VB.NET como solução para o exercício:
    - [Sistema de Controle de Inventário Simplificado](https://github.com/rochaecp/engsw/blob/main/B_exercicios/01_introducao/variaveis.md#1-sistema-de-controle-de-invent%C3%A1rio-simplificado)

#### Implementação utilizando programação estruturada

~~~vb
Imports System

Public Class Program
    Public Shared Sub Main()
        ' Definição de variáveis para três produtos
        Dim nomeProduto1 As String
        Dim qtdProduto1 As Integer
        Dim precoUnitario1 As Decimal

        Dim nomeProduto2 As String
        Dim qtdProduto2 As Integer
        Dim precoUnitario2 As Decimal

        Dim nomeProduto3 As String
        Dim qtdProduto3 As Integer
        Dim precoUnitario3 As Decimal

        ' Solicitação de dados ao usuário para o primeiro produto
        Console.Write("Informe o nome do produto 1: ")
        nomeProduto1 = Console.ReadLine()

        Console.Write("Informe a quantidade em estoque de " & nomeProduto1 & ": ")
        qtdProduto1 = Convert.ToInt32(Console.ReadLine())

        Console.Write("Informe o preço unitário de " & nomeProduto1 & ": ")
        precoUnitario1 = Convert.ToDecimal(Console.ReadLine())

        ' Solicitação de dados ao usuário para o segundo produto
        Console.Write(vbCrLf & "Informe o nome do produto 2: ")
        nomeProduto2 = Console.ReadLine()

        Console.Write("Informe a quantidade em estoque de " & nomeProduto2 & ": ")
        qtdProduto2 = Convert.ToInt32(Console.ReadLine())

        Console.Write("Informe o preço unitário de " & nomeProduto2 & ": ")
        precoUnitario2 = Convert.ToDecimal(Console.ReadLine())

        ' Solicitação de dados ao usuário para o terceiro produto
        Console.Write(vbCrLf & "Informe o nome do produto 3: ")
        nomeProduto3 = Console.ReadLine()

        Console.Write("Informe a quantidade em estoque de " & nomeProduto3 & ": ")
        qtdProduto3 = Convert.ToInt32(Console.ReadLine())

        Console.Write("Informe o preço unitário de " & nomeProduto3 & ": ")
        precoUnitario3 = Convert.ToDecimal(Console.ReadLine())

        ' Cálculo do valor total de cada produto
        Dim totalProduto1 As Decimal = qtdProduto1 * precoUnitario1
        Dim totalProduto2 As Decimal = qtdProduto2 * precoUnitario2
        Dim totalProduto3 As Decimal = qtdProduto3 * precoUnitario3

        ' Cálculo do valor total do inventário
        Dim valorTotalInventario As Decimal = totalProduto1 + totalProduto2 + totalProduto3

        ' Exibição do relatório
        Console.WriteLine(vbCrLf & "Relatório do Inventário:")
        Console.WriteLine($"Produto: {nomeProduto1} | Quantidade: {qtdProduto1} | Preço Unitário: {precoUnitario1:F2} | Valor Total: {totalProduto1:F2}")
        Console.WriteLine($"Produto: {nomeProduto2} | Quantidade: {qtdProduto2} | Preço Unitário: {precoUnitario2:F2} | Valor Total: {totalProduto2:F2}")
        Console.WriteLine($"Produto: {nomeProduto3} | Quantidade: {qtdProduto3} | Preço Unitário: {precoUnitario3:F2} | Valor Total: {totalProduto3:F2}")

        ' Exibição do valor total do inventário
        Console.WriteLine(vbCrLf & $"Valor total do inventário: {valorTotalInventario:F2}")

        Console.ReadKey()
    End Sub
End Class
~~~

#### Implementação utilizando programação orientada a objetos

~~~vb
Imports System.Globalization

Public Class Program
    Public Shared Sub Main()

        Dim valorTotal As Decimal = 0
        Dim listaProdutos As New List(Of Produto)

        For i As Integer = 1 To 3
            Dim prod As New Produto()
            prod.LeProduto()
            listaProdutos.Add(prod)
            Console.WriteLine()
        Next

        Console.WriteLine("Relatório do Inventário:")

        For Each prod As Produto In listaProdutos
            prod.Inventario()
            valorTotal += prod.ValorTotal()
        Next

        ' Exibindo valor total do inventário
        Console.WriteLine(vbCrLf & $"Valor total do inventário: {valorTotal.ToString("F2", CultureInfo.InvariantCulture)}") ' vbCrLf = quebra linha

        Console.ReadKey()
    End Sub

End Class

Public Class Produto
    ' Atributo estático para gerar IDs únicos (Identity)
    Private Shared _contadorID As Integer = 0

    ' Atributo privado para armazenar o ID do produto
    Private ReadOnly _ID As Integer

    ' Atributos encapsulados
    Private _NomeProduto As String
    Private _Quantidade As Integer
    Private _PrecoUnitario As Decimal

    ' Propriedades para acessar os atributos de forma segura
    Public ReadOnly Property ID As Integer
        Get
            Return _ID
        End Get
    End Property

    Public Property NomeProduto As String
        Get
            Return _NomeProduto
        End Get
        Set(value As String)
            _NomeProduto = value
        End Set
    End Property

    Public Property Quantidade As Integer
        Get
            Return _Quantidade
        End Get
        Set(value As Integer)
            _Quantidade = If(value >= 0, value, 0) ' Evita valores negativos
        End Set
    End Property

    Public Property PrecoUnitario As Decimal
        Get
            Return _PrecoUnitario
        End Get
        Set(value As Decimal)
            _PrecoUnitario = If(value >= 0, value, 0) ' Evita valores negativos
        End Set
    End Property

    ' Construtor que gera o ID automaticamente
    Public Sub New()
        _contadorID += 1
        _ID = _contadorID ' Armazena o ID no campo privado
    End Sub

    ' Método para capturar entrada do usuário com validação
    Public Sub LeProduto()

        Console.Write($"Informe o nome do produto #{ID}: ")
        NomeProduto = Console.ReadLine()

        ' Valida a entrada da quantidade
        Do
            Console.Write($"Informe a quantidade em estoque de {NomeProduto}: ")
            If Integer.TryParse(Console.ReadLine(), Quantidade) AndAlso Quantidade >= 0 Then Exit Do
            Console.WriteLine("Erro: Digite um número inteiro válido para a quantidade.")
        Loop

        ' Valida entrada do preço unitário
        Do
            Console.Write($"Informe o preço unitário de {NomeProduto}: ")
            If Decimal.TryParse(Console.ReadLine(), PrecoUnitario) AndAlso PrecoUnitario >= 0 Then Exit Do
            Console.WriteLine("Erro: Digite um número decimal válido para o preço unitário.")
        Loop

    End Sub

    ' Método para exibir o inventário
    Public Sub Inventario()
        Console.WriteLine($"ID: {ID} | Produto: {NomeProduto} | Quantidade: {Quantidade} | Preço Unitário: {PrecoUnitario.ToString("F2", CultureInfo.InvariantCulture)} | Valor Total: {ValorTotal().ToString("F2", CultureInfo.InvariantCulture)}")
    End Sub

    ' Método para calcular o valor total do produto
    Public Function ValorTotal() As Decimal
        Return Quantidade * PrecoUnitario
    End Function

End Class
~~~

