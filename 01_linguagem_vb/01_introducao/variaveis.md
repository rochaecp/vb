# Variáveis

## Declaração de Variáveis

- Para declarar uma variável em VB.NET, usamos a palavra-chave Dim (abreviação de "Dimension").

~~~vb
' Dim nomeDaVariavel As TipoDeDado
Dim idade As Integer
Dim nome As String
Dim altura As Double
~~~

## Atribuição de Valores

~~~vb
idade = 25
nome = "João"
altura = 1.75
~~~

## Declaração de Variáveis com Atribuição

~~~vb
Dim nome As String = "Ana"
Dim idade As Integer = 30
Dim altura As Double = 1.65
Dim salario As Decimal = 3500.75D
Dim casado As Boolean = True
Dim dataNascimento As Date = #03/15/1990#
~~~

## Tipos de Dados Implícitos (Inferência de Tipo)

- VB.NET tem um recurso chamado inferência de tipo. 
- Isso significa que você pode deixar o compilador determinar o tipo da variável com base no valor atribuído a ela. 
- Para isso, basta não especificar o tipo ao declarar a variável:

~~~vb
Dim x = 10       ' O tipo de x será Integer
Dim y = 3.14     ' O tipo de y será Double
Dim texto = "Oi" ' O tipo de texto será String
~~~

- Observação: A inferência de tipo é controlada pela diretiva Option Infer. 
- Se Option Infer estiver ativada (o que é padrão), a inferência de tipo estará disponível.
