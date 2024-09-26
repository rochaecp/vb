# Operadores Aritméticos, Lógicos e Relacionais

- Em VB.NET, os operadores são símbolos especiais usados para realizar operações em variáveis e valores. 
- Eles são divididos em três principais categorias: 
    - Aritméticos
    - Lógicos (ou Booleanos)
    - Relacionais

## Operadores Aritméticos

- Os operadores aritméticos são usados para realizar operações matemáticas em números.

#### Exemplo de Operadores Aritméticos

~~~vb
Dim a As Integer = 10
Dim b As Integer = 3
Dim nome As String = "abc"

'+: Adição
Dim soma As Integer = a + b

'-: Subtração
Dim subtracao As Integer = a - b

'*: Multiplicação
Dim multiplicacao As Integer = a * b

'/: Divisão (resultado decimal)
Dim divisao As Double = a / b

'\: Divisão inteira
Dim divisaoInteira As Integer = a \ b

'Mod: Resto da divisão inteira
Dim resto As Integer = a Mod b

'^: Exponenciação (potência)
Dim potencia As Integer = a ^ b

'&: Concatenação de strings
Dim concat As String = nome & " abcdefg"
~~~

## Operadores Relacionais

- Os operadores relacionais são usados para comparar dois valores. 
- O resultado dessas comparações é sempre um valor Booleano: True ou False.

#### Exemplo de Operadores Relacionais

~~~vb
Dim a As Integer = 10
Dim b As Integer = 5
Dim c As New Object()
Dim d As New Object()
Dim e As String = "teste"

'Igualdade
Console.WriteLine("a = b: " & (a = b)) ' Falso

'<>: Diferença (não igual)
Console.WriteLine("a <> b: " & (a <> b)) ' Verdadeiro

'Maior que
Console.WriteLine("a > b: " & (a > b)) ' Verdadeiro

'Menor que
Console.WriteLine("a < b: " & (a < b)) ' Falso

'Maior ou igual a
Console.WriteLine("a >= b: " & (a >= b)) ' Verdadeiro

'Menor ou igual a
Console.WriteLine("a <= b: " & (a <= b)) ' Falso

'Is: Verifica se dois objetos referem-se à mesma instância (comparação de referência)
Console.WriteLine("c Is d: " & (c Is d)) ' Falso

'IsNot: Verifica se dois objetos referem-se a instâncias diferentes (comparação de referência)
Console.WriteLine("c IsNot d: " & (c IsNot d)) ' True

'Like: Verifica se uma string corresponde a um padrão
Console.WriteLine("e Like 'teste': " & (e Like "teste")) ' True
~~~

## Operadores Lógicos

- Os operadores lógicos são usados para combinar expressões Booleanas. 
- Eles são particularmente úteis em estruturas de controle de fluxo (como If e While), quando você deseja verificar várias condições ao mesmo tempo.
- Diferença entre And/Or e AndAlso/OrElse
    - AndAlso e OrElse realizam a avaliação curta (short-circuit evaluation). 
    - Isso significa que, se a primeira condição em uma expressão AndAlso for False, a segunda condição não será avaliada, pois o resultado já será False.
    - O mesmo ocorre com OrElse: se a primeira condição for True, a segunda não será avaliada.

#### Exemplo de Operadores Lógicos

~~~vb
Dim x As Boolean = True
Dim y As Boolean = False

'And: E lógico
Console.WriteLine("x And y: " & (x And y)) ' Falso

'Or: Ou lógico
Console.WriteLine("x Or y: " & (x Or y)) ' Verdadeiro

'Not: Negação lógica
Console.WriteLine("Not x: " & Not x) ' Falso

'Xor: Ou exclusivo
Console.WriteLine("x Xor y: " & (x Xor y)) ' Verdadeiro

'AndAlso: E lógico com avaliação curta (short-circuit)
Console.WriteLine("x AndAlso y: " & (x AndAlso y)) ' Falso

'OrElse: Ou lógico com avaliação curta (short-circuit)
Console.WriteLine("x OrElse y: " & (x OrElse y)) ' Verdadeiro
~~~

#### Exemplo de Operadores de Atribuição

~~~vb
Dim a As Integer = 10
Dim b As Integer = 5
Dim nome As String = "VB"

' =: Atribuição simples
b = a
Console.WriteLine("b = a: " & b) ' b passa a ser igual a 10

' +=: Soma e atribui
a += 5
Console.WriteLine("a += 5: " & a) ' a passa a ser 15

' -=: Subtrai e atribui
a -= 3
Console.WriteLine("a -= 3: " & a) ' a passa a ser 12

' *=: Multiplica e atribui
a *= 2
Console.WriteLine("a *= 2: " & a) ' a passa a ser 24

'/=: Divide e atribui
a /= 4
Console.WriteLine("a /= 4: " & a) ' a passa a ser 6

'\=: Divisão inteira e atribui
a \= 2
Console.WriteLine("a \= 2: " & a) ' a passa a ser 3

' &=: Concatenação de string e atribui
nome &= " .NET"
Console.WriteLine("nome &= ' .NET': " & nome) ' nome passa a ser "VB .NET"

'^=: Exponenciação e atribui
a ^= 3
Console.WriteLine("a ^= 3: " & a) ' a passa a ser 27 (3^3)
~~~

#### Exemplo de Operadores de Bitwise (ou Binários)

~~~vb
Dim x As Integer = 6 ' 110 em binário
Dim y As Integer = 3 ' 011 em binário

' And: E bit a bit
Console.WriteLine("x And y: " & (x And y)) ' Exibe 2 (010)

' Or: Ou bit a bit
Console.WriteLine("x Or y: " & (x Or y)) ' Exibe 7 (111)

' Not: Negação bit a bit
Console.WriteLine("Not x: " & Not x) ' Exibe -7 (complemento de 6)

' Xor: Ou exclusivo bit a bit
Console.WriteLine("x Xor y: " & (x Xor y)) ' Exibe 5 (101)

' <<: Deslocamento de bits à esquerda
Console.WriteLine("x << 1: " & (x << 1)) ' Exibe 12 (1100)

' >>: Deslocamento de bits à direita
Console.WriteLine("x >> 1: " & (x >> 1)) ' Exibe 3 (011)
~~~

#### Exemplo de Operadores de Comparação de Tipo

~~~vb
Dim obj As Object = "Hello, world!"
Dim numero As Integer = 42

' TypeOf...Is: Verifica se uma variável é de um tipo específico
If TypeOf obj Is String Then
    Console.WriteLine("obj é uma string.")
End If

If TypeOf numero Is Integer Then
    Console.WriteLine("numero é um Integer.")
End If
~~~
