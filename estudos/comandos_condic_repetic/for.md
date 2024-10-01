# Estrutura For...Next

- A estrutura For...Next é usada para repetir um bloco de código um número específico de vezes. 
- O loop é controlado por uma variável de contagem (contador).
- Step: O parâmetro Step é opcional e especifica o incremento do contador. Por padrão, o incremento é 1.

~~~vb
For contador As Integer = valorInicial To valorFinal [Step incremento]
    ' Bloco de código a ser repetido
Next
~~~

~~~vb
For i As Integer = 1 To 5
    Console.WriteLine("Contador: " & i)
Next
~~~

~~~vb
For i As Integer = 10 To 1 Step -1
    Console.WriteLine("Contador: " & i)
Next
~~~

# Estrutura For Each...Next

~~~vb
Dim lista As New List(Of String) From {"aaa", "bbb", "ccc"}

For Each item As String In lista
    Console.Write(item & vbCrLf)
Next
~~~
