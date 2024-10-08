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

## Conversão para Inteiros

- Enums são baseados em números inteiros, então você pode converter um valor enum para o seu valor numérico subjacente.

~~~vb
Dim valorNumerico As Integer = CInt(DiaDaSemana.Quarta)
Console.WriteLine(valorNumerico)  ' Saída: 3
~~~

## Comparação

- Você pode comparar valores enum diretamente

~~~vb
If hoje = DiaDaSemana.Quarta Then
    Console.WriteLine("Hoje é quarta-feira.")
End If
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