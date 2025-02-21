# Estrutura While ... End While

- A estrutura While...End While repete um bloco de código enquanto uma condição for verdadeira. O loop continua até que a condição seja falsa.

~~~vb
While condição
    ' Bloco de código a ser repetido enquanto a condição for verdadeira
End While
~~~

~~~vb
Dim contador As Integer = 0

While contador < 5
    Console.WriteLine("Contador: " & contador)
    contador += 1
End While
~~~

# Estrutura Do While ... Loop

- A estrutura Do...Loop é outra forma de criar loops. Pode-se verificar a condição antes ou depois de executar o bloco de código.

~~~vb
Do While condição
    ' Bloco de código
Loop
~~~

~~~vb
Dim numero As Integer = 1

Do While numero <= 5
    Console.WriteLine("Número: " & numero)
    numero += 1
Loop
~~~

~~~vb
Do Until condição
    ' Bloco de código
Loop
~~~

~~~vb
Dim numero As Integer = 1

Do Until numero > 5
    Console.WriteLine("Número: " & numero)
    numero += 1
Loop
~~~

# Do ... Loop

~~~vb
Dim salarioBruto As Double = 0

Do
    Console.Write("Informe o salário bruto do funcionário: ")
    If Double.TryParse(Console.ReadLine(), salarioBruto) AndAlso salarioBruto >= 0 Then Exit Do
    Console.WriteLine("Erro. Informe um valor válido.")
Loop
~~~
