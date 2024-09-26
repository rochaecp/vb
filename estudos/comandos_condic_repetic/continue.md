# Estrutura Continue

- A instrução Continue é usada para pular a iteração atual de um loop e avançar para a próxima iteração. 
- Ela pode ser usada em loops For, While, e Do.

#### Exemplo com For

~~~vb
For i As Integer = 1 To 10
    If i Mod 2 = 0 Then
        Continue For  ' Pula os números pares
    End If
    Console.WriteLine(i)
Next
~~~

#### Exemplo com While

~~~vb
Dim contador As Integer = 1
While contador <= 10
    contador += 1
    If contador = 5 Then
        Continue While  ' Pula a iteração quando contador for 5
    End If
    Console.WriteLine(contador)
End While
~~~
