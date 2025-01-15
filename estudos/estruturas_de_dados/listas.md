# VB.net - Listas

- As listas são coleções ordenadas de elementos que podem ser acessados pelo índice. 
- Diferente de arrays, elas têm tamanho dinâmico e podem crescer ou diminuir conforme necessário.

## Criar

~~~vb
Dim lista1 As New List(Of Integer) From {10, 20, 30, 40}
Dim lista2 As New List(Of Integer)
Dim lista3 As New List(Of Integer)(10) ' Capacidade inicial de 10

Dim lista4 As New List(Of Integer)
lista4.AddRange({10, 20, 30})
~~~

## Tamanho

~~~vb
Dim total As Integer = lista.Count
~~~

## Incluir

~~~vb
lista.Add(1)
lista.Insert(1, 10) ' Insere no indice 1 o valor 10
~~~

## Remover

~~~vb
Dim lista As New List(Of Integer) From {10, 20, 30, 40, 20}
Boolean as removeu = lista.Remove(20)    ' remove so o primeiro 20
lista.RemoveAt(0)                        ' Remove o item no índice 0
~~~

## Indexar

~~~vb
Dim lista As New List(Of Integer) From {10, 20, 30, 40, 50}

' um elemento
Dim valor = lista(0) ' Acessa o primeiro item

' todos elementos - for simples
For i As Integer = 0 To lista.Count - 1
    Console.WriteLine(lista(i))
Next

' todos elementos - for each
For Each item As Integer In lista
    Console.WriteLine(item)
Next
~~~  

## Ordenar

#### Ordem Crescente

~~~vb
Dim lista As New List(Of Integer) From {40, 10, 30, 50, 20}
lista.Sort()
~~~

#### Ordem Decrescente

~~~vb
Dim lista As New List(Of Integer) From {40, 10, 30, 50, 20}
lista.Sort()
lista.Reverse()
~~~

## Coverter

#### Coverter listas em arrays

~~~vb
Dim minhaLista As New List(Of Integer) From {10, 20, 30, 40, 50}
Dim meuArray() As Integer = lista.ToArray()
~~~

#### Converter arrays em listas

~~~vb
Dim arr() As Integer = {1, 2, 3, 4}
Dim lista As New List(Of Integer)(arr)
~~~

## Lista aninhada

~~~vb
Dim listaDeListas As New List(Of List(Of Integer)) From {
    New List(Of Integer) From {1, 2, 3},
    New List(Of Integer) From {4, 5, 6}
}
~~~

## Lista de Objetos

~~~vb
Public Class Pessoa
    Public Property Nome As String
    Public Property Idade As Integer
End Class

Dim listaPessoas As New List(Of Pessoa) From 
{
    New Pessoa() With {.Nome = "Ana", .Idade = 25},
    New Pessoa() With {.Nome = "João", .Idade = 30}
}
~~~

## Verificar se um item existe

~~~vb
Dim frutas As New List(Of String) From {"Maçã", "Banana", "Laranja"}

If frutas.Contains("Banana") Then
    Console.WriteLine("Banana está na lista!")
End If
~~~
