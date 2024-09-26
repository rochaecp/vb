# Estrutura Exit (Break)

- A instrução Exit é usada para interromper a execução de loops ou estruturas de controle como For, While, Do e também pode ser usada para sair de Sub, Function, ou Select Case. 
- Em outras palavras, ela termina o loop ou a estrutura atual imediatamente.

#### Sintaxe

~~~vb
Exit For     ' Para sair de um loop For
Exit While   ' Para sair de um loop While
Exit Do      ' Para sair de um loop Do
Exit Select  ' Para sair de um Select Case
~~~

#### Exemplo com Exit For

~~~vb
For i As Integer = 1 To 10
    If i = 5 Then
        Exit For  ' Sai do loop quando i for 5
    End If
    Console.WriteLine(i)
Next
~~~

#### Exemplo com Exit While

~~~vb
Dim contador As Integer = 1
While contador <= 10
    If contador = 5 Then
        Exit While  ' Sai do loop quando contador for 5
    End If
    Console.WriteLine(contador)
    contador += 1
End While
~~~

#### Exemplo com Exit Sub

- A instrução Exit Sub é usada para interromper a execução de um Sub (sub-rotina) e sair imediatamente, sem continuar a execução das linhas subsequentes.

~~~vb
Sub ExemploSub()
    Console.WriteLine("Início da Sub")

    If True Then
        Console.WriteLine("Saindo da Sub...")
        Exit Sub  ' Sairá da Sub neste ponto
    End If

    Console.WriteLine("Este código não será executado")
End Sub
~~~

#### Exemplo com Exit Function

- A instrução Exit Function é usada para interromper a execução de uma Function e retornar imediatamente, sem continuar a execução das linhas subsequentes. Pode ser usada para retornar um valor específico ou para sair da função antecipadamente.

~~~vb
Function ExemploFunction() As Integer
    Console.WriteLine("Início da Function")

    If True Then
        Console.WriteLine("Saindo da Function...")
        Exit Function  ' Sairá da Function neste ponto, retornando o valor padrão (0)
    End If

    Console.WriteLine("Este código não será executado")
    Return 10
End Function
~~~

#### Exemplo com Exit Select

- A instrução Exit Select é usada para sair de uma estrutura Select Case imediatamente, ignorando o restante dos casos e saindo da estrutura de seleção.
- Quando o Exit Select é encontrado, ele sai da estrutura Select Case imediatamente, sem verificar os outros casos.

~~~vb
Dim dia As Integer = 2

Select Case dia
    Case 1
        Console.WriteLine("Domingo")
    Case 2
        Console.WriteLine("Segunda-feira")
        Exit Select  ' Sai do Select Case
    Case 3
        Console.WriteLine("Terça-feira")
    Case Else
        Console.WriteLine("Outro dia")
End Select
~~~
