# Estrutura If...Then...Else

- A estrutura If...Then...Else é usada para executar um bloco de código se uma condição for verdadeira. Se a condição for falsa, outro bloco de código pode ser executado opcionalmente com o Else.

#### If Simples

~~~vb
Dim idade As Integer = 18

If idade >= 18 Then
    Console.WriteLine("Você é maior de idade.")
End If
~~~

#### If...Else

~~~vb
Dim idade As Integer = 16

If idade >= 18 Then
    Console.WriteLine("Você é maior de idade.")
Else
    Console.WriteLine("Você é menor de idade.")
End If
~~~

#### If...ElseIf...Else

~~~vb
Dim temperatura As Integer = 30

If temperatura < 15 Then
    Console.WriteLine("Está frio.")
ElseIf temperatura >= 15 AndAlso temperatura < 25 Then
    Console.WriteLine("Está agradável.")
ElseIf temperatura >= 25 AndAlso temperatura < 35 Then
    Console.WriteLine("Está calor.")
Else
    Console.WriteLine("Está muito quente.")
End If
~~~

#### Aninhamento de If

~~~vb
Dim idade As Integer = 20
Dim habilitado As Boolean = True

If idade >= 18 Then
    If habilitado Then
        Console.WriteLine("Você pode dirigir.")
    Else
        Console.WriteLine("Você é maior de idade, mas não pode dirigir.")
    End If
Else
    Console.WriteLine("Você não pode dirigir.")
End If
~~~

