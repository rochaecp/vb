# Enum

- Em VB.NET, Enum (abreviação de "enumeration") é um tipo de dado especial que permite definir um conjunto de constantes nomeadas que representam valores inteiros. 
- Ele é útil para trabalhar com valores que possuem um significado específico e que são limitados a um conjunto fixo de opções, tornando o código mais legível e fácil de manter.
- Características principais:
    - Enumeração de constantes nomeadas: As variáveis em um Enum recebem automaticamente valores inteiros sequenciais, a menos que sejam explicitamente atribuídos.
    - Legibilidade: Enums tornam o código mais fácil de ler, ao invés de trabalhar diretamente com números.
    - Organização: Agrupa um conjunto de valores relacionados.
- Vantagens de Usar Enums:
    - Legibilidade: O uso de constantes nomeadas (como Segunda, Aprovado) ao invés de números mágicos (como 1, 2) torna o código mais fácil de entender.
    - Organização: Enums ajudam a organizar um conjunto fixo de valores relacionados.
    - Segurança de tipo: Enums são fortemente tipados, o que significa que você não pode atribuir diretamente um número inválido a uma variável Enum sem conversão explícita.
    - Enums são muito úteis em casos onde há um conjunto limitado de opções, como status, dias da semana, tipos de usuário, entre outros.    

## Sintaxe Básica

- O Enum DiaDaSemana define sete constantes que representam os dias da semana.
- Se você não atribuir valores explícitos, o primeiro valor começa de 0 e os seguintes são incrementados automaticamente em 1.

~~~vb
Enum DiaDaSemana
    Domingo = 0
    Segunda = 1
    Terça = 2
    Quarta = 3
    Quinta = 4
    Sexta = 5
    Sábado = 6
End Enum
~~~

## Uso de Enums

- Você pode declarar uma variável de um tipo Enum e atribuir-lhe um valor definido no Enum:

~~~vb
Dim hoje As DiaDaSemana = DiaDaSemana.Quarta
Console.WriteLine(hoje)  ' Saída: Quarta
~~~

## Converter

#### Converter Enum para Inteiros

- Enums são baseados em números inteiros, então você pode converter um valor enum para o seu valor numérico subjacente.

~~~vb
Dim valorNumerico As Integer = CInt(DiaDaSemana.Quarta)
Console.WriteLine(valorNumerico)  ' Saída: 3
~~~

#### Converter Integer em Enum

~~~vb
Dim valorInt As Integer = 1
Dim prod As CategoriaProduto = CType(valorInt, CategoriaProduto)
Console.WriteLine(prod.ToString())

'(...)

Public Enum CategoriaProduto
    Alimenticio
    Eletronico
    Vestuario
End Enum
~~~

#### Converter String em Enum

~~~vb
Dim diaStr As String = "Segunda"
Dim diaEnum As DiasSemana = [Enum].Parse(GetType(DiasSemana), diaStr)
Console.WriteLine(diaEnum.ToString())

'(...)

Public Enum DiasSemana
    Domingo = 0
    Segunda = 1
    '(...)
End Enum
~~~

## Comparar

- Você pode comparar valores enum diretamente

~~~vb
If hoje = DiaDaSemana.Quarta Then
    Console.WriteLine("Hoje é quarta-feira.")
End If
~~~

~~~vb
Dim p1 As Prioridade = Prioridade.Alta
Dim p2 As Prioridade = Prioridade.Media

If p1 > p2 Then
    Console.WriteLine("p1 é maior")
ElseIf p1 < p2 Then
    Console.WriteLine("p2 é maior")
End If

'(...)

Public Enum Prioridade
    Baixa = 1
    Media = 2
    Alta = 3
End Enum
~~~

## Definir Tipos Base para Enums

Por padrão, os valores de enum são inteiros (Integer), mas você pode alterar o tipo base (como Byte, Short, etc.), se necessário:

~~~vb
Enum Status As Byte
    Inativo = 0
    Ativo = 1
    Pendente = 2
End Enum
~~~

## Verificar se a Enum foi definida `IsDefined()`

~~~vb
Module Program
    Sub Main(args As String())

        Dim codigo As MinhaEnum = 3 ' testar com 4

        If Not [Enum].IsDefined(GetType(MinhaEnum), codigo) Then
            Throw New Exception($"Código inválido: {CInt(codigo)}.")
        End If

        Console.ReadKey()
    End Sub

    Friend Enum MinhaEnum
        Valor1 = 1
        Valor2 = 2
        Valor3 = 3
    End Enum

End Module
~~~

## Escapando Palavras reservadas 

~~~vb
Public Enum MinhaEnum As Byte
    Debug = 0
    Information = 1
    Warning = 2
    [Error] = 3 ' colchetes utilizados para escapar a palavra reservada Error
End Enum
~~~

## Exemplo Prático

~~~vb
Enum StatusPedido
    Pendente = 1
    Aprovado = 2
    Cancelado = 3
End Enum

Dim pedidoStatus As StatusPedido = StatusPedido.Aprovado

If pedidoStatus = StatusPedido.Aprovado Then
    Console.WriteLine("O pedido foi aprovado.")
End If
~~~