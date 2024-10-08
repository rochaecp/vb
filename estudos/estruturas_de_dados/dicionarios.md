# VB.NET - Dicionários

- Em VB.NET, um dicionário (Dictionary(Of TKey, TValue)) é uma coleção de pares chave-valor que permite armazenar e acessar dados de forma eficiente com base em uma chave única. 
- Ele faz parte do namespace System.Collections.Generic. 
- Características Principais:
    - Chave Única: Cada chave em um dicionário deve ser única. Se você tentar adicionar uma chave que já existe, ocorrerá uma exceção.
    - Acesso Rápido: Os valores podem ser acessados rapidamente fornecendo a chave correspondente.
    - Tipo Genérico: O Dictionary é genérico, então você pode definir o tipo da chave (TKey) e o tipo do valor (TValue).

## Criar

#### Integer, String

~~~vb
Dim dict As New Dictionary(Of String, Integer)()
~~~

~~~vb
Dim myDict2 As New Dictionary(Of Integer, String) From {
    {1, "Maurício"},
    {2, "Maria"},
    {3, "Joana"}
}
~~~

#### String, String

~~~vb
Dim myDict As New Dictionary(Of String, String) From {
    {"txt", "notepad"},
    {"bmp", "paint"},
    {"svg", "inkscape"}
}
~~~

## Tamanho

~~~vb
Dim myInt As Integer = myDict.Count
~~~

## Incluir

~~~vb
myDict.Add("dwg", "autocad") ' String, String
~~~

~~~vb
myDict2.Add(4, "Bernadete") ' Integer, String
~~~

## Remover

~~~vb
myDict.Remove("dwg") ' String, String - Pela Chave
~~~

## Indexar

~~~vb
Dim myStr As String = myDict("txt")
Dim myStr2 As String = myDict2(1)
~~~

## Exibir

#### Exibir Chaves

~~~vb
For Each key As String In myDict.Keys
    Console.WriteLine(key)
Next
~~~

#### Exibir Elementos

~~~vb
For Each value As String In myDict.Values
    Console.WriteLine(value)
Next
~~~

~~~vb
For Each key As String In myDict.Keys
    Console.WriteLine(myDict(key))
Next
~~~

## Verificar

#### Verificar se existe uma determinada chave

~~~vb
Dim myBool As Boolean = myDict.ContainsKey("txt")
~~~

#### Verificar se existe um determinado valor

~~~vb
Dim myBool As Boolean = myDict.ContainsValue("notepad")
~~~
