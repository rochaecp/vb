# Estrutura Select Case

- A estrutura Select Case é usada para avaliar uma expressão e executar diferentes blocos de código com base no valor da expressão. 
- Ela é semelhante ao Switch em outras linguagens.

#### Sintaxe

~~~vb
Select Case expressão
    Case valor1
        ' Bloco de código executado se expressão = valor1
    Case valor2
        ' Bloco de código executado se expressão = valor2
    Case Else
        ' Bloco de código executado se nenhum dos casos for verdadeiro
End Select
~~~

#### Exemplo

~~~vb
Dim diaSemana As Integer = 3

Select Case diaSemana
    Case 1
        Console.WriteLine("Domingo")
    Case 2
        Console.WriteLine("Segunda-feira")
    Case 3
        Console.WriteLine("Terça-feira")
    Case Else
        Console.WriteLine("Outro dia")
End Select
~~~

#### Exemplo de Select Case True

- Quando você escreve Select Case True, o Select Case está avaliando expressões booleanas e comparando o resultado com True. 
- Indica que o Select Case vai avaliar expressões booleanas

~~~vb
Dim x As Object = "True"

Select Case True
    Case TypeOf x Is Integer
        Console.WriteLine("Inteiro")
    Case TypeOf x Is String
        Console.WriteLine("String")
    Case TypeOf x Is Boolean
        Console.WriteLine("Booleano")
    Case Else
        Console.WriteLine("Outro tipo")
End Select
~~~
