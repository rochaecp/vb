# Geração de Números Aleatórios em VB.NET

## Classe `Random`

- A classe `Random` em VB.NET é usada para gerar números aleatórios. 

### Exemplos Básicos

```vb
Dim rand As New Random()
Dim numeroAleatorio As Integer = rand.Next(100) ' Gera número entre 0 e 99
```

```vb
Dim rand As New Random(42) ' Gera sempre a mesma sequência de números
Dim numeroAleatorio As Integer = rand.Next(100) ' Gera número entre 0 e 99
```

```vb
Dim rand As New Random()
Dim numeroAleatorio As Integer = rand.Next(50, 100) ' Gera número entre 50 e 99
```

```vb
Dim rand As New Random()
Dim numeroDecimalAleatorio As Double = rand.NextDouble() 'Gera um número decimal (tipo `Double`) entre 0.0 e 1.0
```
