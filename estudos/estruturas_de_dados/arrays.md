# VB.net - Arrays Unidimensionais

## Criar

~~~vb
Dim arr1() As Integer = {10, 20, 30}    ' modo 1
Dim arr2 As Integer() = {10, 20, 30}    ' modo 2
Dim arr3(2) As Integer                  ' modo 3

Dim arr4() As Integer                   ' modo 4
arr4 = New Integer() {10, 20, 30}
~~~

## Tamanho

~~~vb
Dim myInt As Integer = myStrArr.Length
~~~

## Indexar

#### Um elemento

~~~vb
Dim arr() As String = {"aaa", "bbb"}
Dim str As String = arr(0)
~~~

#### Todos elementos

~~~vb
Dim arr() As Integer = {10, 20, 30, 40, 50}
For i As Integer = 0 To numeros.Length - 1
    Console.WriteLine(arr(i))
Next
~~~

~~~vb
Dim arr() As Integer = {10, 20, 30, 40, 50}
For Each item As Integer In arr
    Console.WriteLine(item)
Next
~~~

## Alterar

~~~vb
myStrArr(0) = "Mauricio"
~~~

## Ordenar

#### Ordenar de modo crescente

~~~vb
Dim meuArray() As String = {"ddd", "aaa", "bbb", "ccc"}
Array.Sort(meuArray)
~~~

#### Ordenar de modo decrescente

~~~vb
Dim meuArray() As Integer = {5, 3, 8, 1, 4}
Array.Sort(meuArray)
Array.Reverse(meuArray)
~~~

## Exibir

#### Utilizando linq com foreach (converte em lista)

~~~vb
Imports System.Linq
' ...
Dim meuArray() As Integer = {5, 3, 8, 4, 1}
meuArray.ToList().ForEach(Sub(e) Console.WriteLine(e))
~~~

## Max()

~~~vb
Imports System.Linq
' ...
Dim myInt As Integer = myIntArr.Max()
~~~        

## Min()

~~~vb
Imports System.Linq
' ...
Dim myInt As Integer = myIntArr.Min()
~~~        

## Sum()

~~~vb
Imports System.Linq
' ...
Dim myInt As Integer = myIntArr.Sum()
~~~ 

## Coverter String em Array de Char

~~~vb
Dim myStr As String = "This is String example"
Dim myCharArr() As Char = myStr.ToCharArray()
~~~

## Converter Array de Char em String

~~~vb
myStr = String.Join("", myCharArr)
~~~

# VB.net - Arrays Bidimensionais

## Criar

- Se inserir a dimensão do array como em `Dim meuArr1(2, 1) As Integer`, não será possível inicializar o array na mesma instrução.

~~~vb
Dim meuArr1(2, 1) As Integer ' array 3x2
Dim meuArr2(9, 9) As Integer ' array 10x10
Dim meuArr3(,) As Integer = {{1, 2}, {3, 4}, {5, 6}}
~~~

## Indexar

~~~vb
Console.WriteLine(meuArr1(0, 0))
~~~        

# VB.net - Arrays Tridimensionais

## Criar

~~~vb
Dim myIntArr(2, 1, 3) As Integer
~~~