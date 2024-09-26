# Estrutura If...Then...Else

- A estrutura If...Then...Else é usada para executar um bloco de código se uma condição for verdadeira. Se a condição for falsa, outro bloco de código pode ser executado opcionalmente com o Else.

#### Exemplo

~~~vb
If condição Then
    ' Bloco de código executado se a condição for verdadeira
ElseIf outraCondição Then
    ' Bloco de código executado se a outraCondição for verdadeira
Else
    ' Bloco de código executado se todas as condições forem falsas
End If
~~~

~~~vb
Dim idade As Integer = 20

If idade >= 18 Then
    Console.WriteLine("Você é maior de idade.")
Else
    Console.WriteLine("Você é menor de idade.")
End If
~~~
