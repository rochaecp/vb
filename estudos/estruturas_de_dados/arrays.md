# VB.net - Arrays Unidimensionais

- Um array é uma estrutura fixa de dados que armazena elementos do mesmo tipo. 
- Sua principal característica é que o tamanho é definido no momento da declaração e não pode ser alterado.
- Eles podem ser unidimensionais (linha única de dados) ou multidimensionais (matrizes, como tabelas ou cubos de dados).
- Características:
    - Tamanho fixo.
    - Acesso por índices baseados em zero.
    - Simples e eficiente para dados de tamanho conhecido.
- Limitações:
    - Não podem redimensionar o tamanho dinamicamente.
    - Limitados a armazenar elementos do mesmo tipo.    

# Arrays Unidimensionais

- Um array unidimensional é como uma lista de valores indexados.

## Criar

~~~vb
' criando e inicializando em uma única linha
Dim arr1() As Integer = {10, 20, 30}    ' modo 1
Dim arr2 As Integer() = {10, 20, 30}    ' modo 2

' criando um array com 2 posições e inicializando em uma linha diferente
Dim arr3(2) As Integer
arr3(0) = 10
arr3(1) = 20

' outra forma
Dim arr4() As Integer
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

~~~vb
' Declarando um array 2x3
Dim matriz(1, 2) As Integer

' Inicializando os valores manualmente
matriz(0, 0) = 1
matriz(0, 1) = 2
matriz(0, 2) = 3
matriz(1, 0) = 4
matriz(1, 1) = 5
matriz(1, 2) = 6

' Declarando e inicializando diretamente
Dim tabela(,) As String = {{"A1", "B1", "C1"}, {"A2", "B2", "C2"}}
~~~

## Indexar

#### Um elemento

~~~vb
Console.WriteLine(meuArr1(0, 0))
~~~        

#### Todos os elementos

~~~vb
For i As Integer = 0 To 1 ' Linha
    For j As Integer = 0 To 2 ' Coluna
        Console.WriteLine("Elemento ({0},{1}) = {2}", i, j, matriz(i, j))
    Next
Next

~~~

# VB.net - Arrays Tridimensionais

## Criar

~~~vb
Dim myIntArr(2, 1, 3) As Integer
~~~