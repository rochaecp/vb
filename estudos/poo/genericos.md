# Genéricos

- Os genéricos são uma funcionalidade que permite criar classes, métodos e coleções que podem funcionar com qualquer tipo de dado, mantendo tipagem segura. 
- Isso significa que o tipo de dado é definido no momento em que a classe ou método é usado, eliminando a necessidade de conversões explícitas e evitando erros em tempo de execução.
- Vantagens do Uso de Genéricos
    - Tipagem Segura: Evita erros de tipo em tempo de execução.
    - Flexibilidade: Permite reusar código com diferentes tipos de dados.
    - Performance: Elimina a necessidade de conversões de tipos, reduzindo a sobrecarga.
- Resumo
    - Genéricos aumentam a flexibilidade e segurança do código, permitindo reutilizar classes e métodos com diferentes tipos de dados.
    - Coleções genéricas, como List(Of T) e Dictionary(Of TKey, TValue), são fundamentais para manipulação eficiente de dados.
    - Criar classes e métodos genéricos personaliza ainda mais seu código, promovendo reusabilidade e legibilidade.

## Exemplos

#### Uso de List(Of T)

- O List(Of T) é uma coleção genérica amplamente usada em VB.NET. O tipo T é definido no momento da criação.

~~~vb
Dim numeros As New List(Of Integer) From {1, 2, 3, 4, 5}
Dim nomes As New List(Of String) From {"Ana", "João", "Maria"}

' Adicionando elementos
numeros.Add(6)
nomes.Add("Carlos")

' Iterando sobre a lista
For Each numero In numeros
    Console.WriteLine("Número: " & numero)
Next

For Each nome In nomes
    Console.WriteLine("Nome: " & nome)
Next
~~~

#### Criando uma Classe Genérica

- As classes genéricas permitem criar estruturas reutilizáveis para diferentes tipos.

~~~vb
Public Class CaixaDeArmazenamento(Of T)
    Private conteudo As T

    Public Sub Guardar(item As T)
        conteudo = item
    End Sub

    Public Function Obter() As T
        Return conteudo
    End Function
End Class

' Usando a classe genérica
Dim caixaDeInteiros As New CaixaDeArmazenamento(Of Integer)
caixaDeInteiros.Guardar(42)
Console.WriteLine("Conteúdo da caixa: " & caixaDeInteiros.Obter())

Dim caixaDeTexto As New CaixaDeArmazenamento(Of String)
caixaDeTexto.Guardar("VB.NET")
Console.WriteLine("Conteúdo da caixa: " & caixaDeTexto.Obter())
~~~

#### Métodos Genéricos

- Métodos genéricos permitem criar funções que aceitam qualquer tipo de dado.

~~~vb
Public Function RetornaMaior(Of T As IComparable)(a As T, b As T) As T
    If a.CompareTo(b) > 0 Then
        Return a
    Else
        Return b
    End If
End Function

' Usando o método genérico
Console.WriteLine(RetornaMaior(10, 20))  ' Saída: 20
Console.WriteLine(RetornaMaior("Ana", "João"))  ' Saída: João
~~~