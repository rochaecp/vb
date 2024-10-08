# Tuplas em VB.net

- Em VB.NET, uma tupla (ou Tuple) é uma estrutura de dados que pode conter um conjunto fixo de valores de diferentes tipos. 
- As tuplas são usadas para armazenar vários itens em uma única estrutura, sem precisar definir uma classe ou estrutura específica para isso. 
- Elas podem conter de 1 até 8 elementos e são comumente utilizadas quando você deseja retornar múltiplos valores de um método ou armazenar pequenos conjuntos de dados.
- Características das Tuplas
    - Imutáveis: Os valores de uma tupla são imutáveis. Depois de criados, os elementos não podem ser alterados.
    - Elementos Nominados por Posição: As tuplas têm seus elementos acessados por meio de Item1, Item2, Item3, e assim por diante, até o Item8 para tuplas com até 8 elementos.
    - Tipos Heterogêneos: Cada item da tupla pode ter um tipo diferente.
- Limitação: Apenas 8 Elementos
    - Tuplas em VB.NET podem conter no máximo 8 elementos. 
    - Se você precisar armazenar mais valores, deverá aninhar tuplas dentro de outras tuplas.

## Criar

~~~vb
Dim minhaTupla As Tuple(Of String, Integer) = Tuple.Create("João", 25)
~~~

## Acessar

~~~vb
Dim tupla As Tuple(Of String, Integer, Boolean) = Tuple.Create("Maria", 30, True)
Console.WriteLine(tupla.Item1) ' Exibe "Maria"
Console.WriteLine(tupla.Item2) ' Exibe 30
Console.WriteLine(tupla.Item3) ' Exibe True
~~~

## Tuplas em Métodos

- Tuplas são úteis para retornar múltiplos valores de um método sem criar uma classe para isso. Veja um exemplo de método que retorna uma tupla:

~~~vb
Function ObterPessoa() As Tuple(Of String, Integer)
    Return Tuple.Create("Pedro", 40)
End Function

Dim pessoa As Tuple(Of String, Integer) = ObterPessoa()
Console.WriteLine(pessoa.Item1) ' Exibe "Pedro"
Console.WriteLine(pessoa.Item2) ' Exibe 40
~~~

## Tuplas Nomeadas (Introduzidas no .NET Framework 4.7 e posteriores)

- Em versões mais recentes do .NET (VB.NET 15.3 e superiores), tuplas nomeadas podem ser usadas, permitindo que os campos da tupla sejam referenciados por nomes, o que melhora a legibilidade:

~~~vb
Dim pessoa = (Nome: "Ana", Idade: 28)
Console.WriteLine(pessoa.Nome) ' Exibe "Ana"
Console.WriteLine(pessoa.Idade) ' Exibe 28
~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~

##

~~~vb

~~~