# Strings em VB.NET

- Definição: Uma string é uma sequência de caracteres que pode armazenar texto.
- Imutabilidade: Strings em VB.NET são imutáveis (não podem ser alteradas diretamente após a criação, qualquer alteração cria uma nova string).
- Operações básicas: Exibir, concatenar e comparar strings.

~~~vb
Dim texto As String = "Olá, Mundo!"
Console.WriteLine("Texto: " & texto)
~~~

## Concatenação de Strings

- Uso do operador `&` para juntar strings.
- Uso do método `String.Concat()` para múltiplas strings.

~~~vb
Dim saudacao As String = "Olá"
Dim nome As String = "João"
Dim frase As String = saudacao & ", " & nome
Console.WriteLine(frase)
~~~

## Interpolação de Strings (a partir do VB 14.0)

~~~vb
Dim nome As String = "João"
Console.WriteLine($"Bem-vindo, {nome}!")
~~~

## Comprimento da String (`Length`)

~~~vb
Dim texto As String = "VB.NET"
Console.WriteLine(texto.Length) ' Exibe: 6
~~~

## Método `ToUpper()`

- Convertendo strings para letras maiúsculas.

~~~vb
Dim texto As String = "Olá, Mundo!"
Console.WriteLine(texto.ToUpper()) ' Exibe: OLÁ, MUNDO!
~~~

## Método `ToLower()`

- Convertendo strings para letras minúsculas.

~~~vb
Dim texto As String = "Olá, Mundo!"
Console.WriteLine(texto.ToLower()) ' Exibe: olá, mundo!
~~~

## Método Substrings (`Substring()`)

- Extrair uma parte da string a partir de uma posição.
- Primeiro parâmetro: posição inicial, segundo parâmetro: quantos caracteres pegar a partir da posição inicial

~~~vb
Dim texto As String = "Olá, Mundo!"
Console.WriteLine(texto.Substring(0, 3)) ' Exibe: Olá
~~~

## Método Busca de Substrings (`IndexOf()`)

- Encontrar a posição de uma substring com `IndexOf()`.

~~~vb
Dim texto As String = "Bem-vindo ao VB.NET"
Dim posicao As Integer = texto.IndexOf("VB.NET")
Console.WriteLine(posicao) ' Exibe: 13
~~~

## Método Trim

- Remover espaços em branco no início ou fim da string com `Trim()`, `TrimStart()`, e `TrimEnd()`.

~~~vb
Dim texto As String = "  Espaços Extras  "
Console.WriteLine(texto.Trim()) ' Exibe: "Espaços Extras"
~~~

## Comparação de Strings

- Operadores de Igualdade (`=` e `<>`):
- Comparando duas strings diretamente.

~~~vb
Dim texto1 As String = "VB.NET"
Dim texto2 As String = "VB.NET"
Console.WriteLine(texto1 = texto2) ' Exibe: True
~~~

## Função `Equals()`

- Comparação usando o método `Equals()`.

~~~vb
Dim texto1 As String = "VB.NET"
Dim texto2 As String = "VB.Net"
Console.WriteLine(texto1.Equals(texto2, StringComparison.OrdinalIgnoreCase)) ' Exibe: True
    'StringComparison.OrdinalIgnoreCase é parâmetro opcional
~~~

## Formatação de Strings

- Método `String.Format()`:
- Formatação de strings com parâmetros.

~~~vb
Dim nome As String = "João"
Dim idade As Integer = 25
Console.WriteLine(String.Format("Meu nome é {0} e tenho {1} anos.", nome, idade))
~~~

~~~vb
Dim valorDecimal As Decimal = 25.4758
Dim valorFormatado As String = String.Format("{0:F2}", valorDecimal)
Console.WriteLine(valorFormatado) ' 25,48
~~~

## Formatação de Datas 

- Método `ToString()`:

~~~vb
Dim data As DateTime = "2024-10-01"
Console.WriteLine(data.ToString("dd/MM/yyyy")) '01/10/2024
~~~

## Interpolação de Strings (a partir do VB 14.0)

~~~vb
Dim nome As String = "João"
Console.WriteLine($"Olá, {nome}!")
~~~

## Divisão de Strings (`Split()`)

- Quebrar uma string em partes com base em um delimitador.

~~~vb
Dim texto As String = "Maçã, Banana, Pera"
Dim frutas() As String = texto.Split(","c)
For Each fruta In frutas
    Console.WriteLine(fruta.Trim())
Next
~~~

## Junção de Strings (`String.Join()`)

- Unir uma matriz de strings em uma única string com um delimitador.

~~~vb
Dim frutas() As String = {"Maçã", "Banana", "Pera"}
Dim listaDeFrutas As String = String.Join(", ", frutas)
Console.WriteLine(listaDeFrutas) ' Exibe: Maçã, Banana, Pera
~~~

## Substituição de Caracteres (`Replace()`)

- Substituir partes de uma string por outra.

~~~vb
Dim texto As String = "Olá, Mundo!"
Console.WriteLine(texto.Replace("Mundo", "VB.NET")) ' Exibe: Olá, VB.NET!
~~~

## Tratamento de Strings Nulas e Vazio

- Verificação de String Vazia ou Nula:
- Uso de `String.IsNullOrEmpty()` e `String.IsNullOrWhiteSpace()` para verificar strings vazias ou com espaços em branco.

~~~vb
Dim texto As String = ""
If String.IsNullOrEmpty(texto) Then
    Console.WriteLine("A string está vazia.")
End If
~~~

## Escapando Caracteres Especiais

- Uso de `"` dentro de strings:
- Uso de caracteres de escape (`""`) ou `Chr(34)` para inserir aspas dentro de strings.

~~~vb
Dim texto As String = "Ela disse: ""Olá!"""
Console.WriteLine(texto) ' Exibe: Ela disse: "Olá!"
~~~

## Práticas Comuns de String em Loops

- Uso eficiente de strings com `StringBuilder` em loops para evitar a criação de múltiplas strings.

~~~vb
Dim sb As New System.Text.StringBuilder()
For i As Integer = 1 To 5
    sb.Append("Texto " & i & " ")
Next
Console.WriteLine(sb.ToString())
~~~

## Caracteres de Escape

- vbCrLf: Quebra de linha
- vbTab: tab

## Verificar Conteúdo 

- Determinar se uma string contém uma palavra ou caractere com `Contains`.

~~~vb
Dim texto As String = "Bem-vindo ao curso de VB.NET"
If texto.Contains("VB.NET") Then
    Console.WriteLine("A palavra 'VB.NET' foi encontrada!")
End If
~~~