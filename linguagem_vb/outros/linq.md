# LINQ (Language Integrated Query)

## Where - exemplo

~~~vb
Dim numeros As List(Of Integer) = New List(Of Integer) From {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
Dim numerosPares = numeros.Where(Function(num) num Mod 2 = 0).ToList()

For Each numero In numerosPares
    Console.WriteLine(numero)
Next
~~~