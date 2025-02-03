# Tipos de Dados

## Tipos de Dados Comuns em VB.NET

- Byte
    - Armazena valores inteiros de 0 a 255
    - Tamanho: 8 bits
    - Ex.: 0, 255
- SByte
    - Armazena valores inteiros de -128 a 127
    - Tamanho: 8 bits
    - Ex.: -128, 127    
- Short
    - Armazena números inteiros menores (de -32.768 a 32.767)
    - Tamanho: 16 bits
    - Ex.: 30000, -20000
- UShort
    - Armazena números inteiros não negativos menores (de 0 a 65.535)
    - Tamanho: 16 bits
    - Ex.: 65535, 0        
- Integer
    - Armazena números inteiros de -2.147.483.648 a 2.147.483.647
    - Tamanho: 32 bits
    - Ex.: 10, -5, 1000    
- UInteger
    - Armazena números inteiros não negativos de 0 a 4294967295
    - Tamanho: 32 bits
    - Ex.: 0, 4294967295
- Long
    - Armazena números inteiros de grande magnitude de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807
    - Tamanho: 64 bits
    - Ex.: 2147483648, -9223372036854775808   
- ULong
    - Armazena números inteiros não negativos de grande magnitude de 0 a ???
    - Tamanho: 64 bits
    - Ex.: 9223372036854775808, 18446744073709551615
- Single
    - Armazena números de ponto flutuante com precisão simples de ??? a ???
    - Tamanho: 32 bits
    - Ex.: 3.14F, -1.5F    
- Double
    - Armazena números com casas decimais de -1.7976931348623157E+308 a 1.7976931348623157E+308
    - Tamanho: 64 bits
    - Ex.: 10.5, -3.14, 0.99
- Decimal
    - Armazena valores monetários com alta precisão de -79.228.162.514.264.337.593.543.950.335 a 79.228.162.514.264.337.593.543.950.335 com 28-29 casas decimais
    - Tamanho: 128 bits
    - Ex.: 1000.75D, 50.99D
- String
    - Armazena texto (sequência de caracteres)
    - Tamanho: Variável (depende do número de caracteres). Cada caractere ocupa 16 bits (2 bytes) em Unicode.
    - Ex.: "Olá, mundo!", "João"
- Boolean
    - Armazena valores lógicos (verdadeiro/falso)
    - Tamanho: 8 bits
    - Ex.: True, False
- Date
    - Armazena datas e horas
    - Tamanho: 64 bits
    - Ex.: #01/01/2024#, Now
- Char
    - Armazena um único caractere, em Unicode, que é o padrão para VB.NET.
    - Tamanho: 16 bits
    - Ex.: "A", "B", "9"
- Object
    - Armazena qualquer tipo de dados. Todos os tipos de dados em VB.NET derivam de Object.
    - Ex.: Pode armazenar números, strings, objetos personalizados, etc.

#### Exemplo de Uso

~~~vb
Dim valorByte As Byte = 255
Dim valorSByte As SByte = -128
Dim valorShort As Short = 30000
Dim valorUShort As UShort = 65535
Dim valorInteger As Integer = 1000
Dim valorUInteger As UInteger = 4294967295
Dim valorLong As Long = 2147483648
Dim valorULong As ULong = 9223372036854775808
Dim valorSingle As Single = 3.14F
Dim valorDouble As Double = 10.5
Dim valorDecimal As Decimal = 1000.75D
Dim valorString As String = "Olá, mundo!"
Dim valorBoolean As Boolean = True
Dim valorDate As Date = #03/15/1990# ' 15/03/1990 ou #1990-03-15#
Dim valorChar As Char = "A"c ' sem o c vira String
Dim valorObject As Object = 12345 ' Pode armazenar qualquer valor
~~~

## Operador TypeOf

- O operador TypeOf é usado em VB.NET para verificar se uma variável ou objeto é de um determinado tipo. 
- Ele é frequentemente utilizado em conjunto com a instrução Is para testar o tipo de uma variável em uma estrutura condicional, como If ou Select Case.

#### Sintaxe

~~~vb
TypeOf variavel Is TipoDeDado
~~~

#### Exemplo de Uso

~~~vb
Dim valor As Object = "Olá, Mundo!"

If TypeOf valor Is String Then
    Console.WriteLine("A variável é uma string.")
ElseIf TypeOf valor Is Integer Then
    Console.WriteLine("A variável é um inteiro.")
Else
    Console.WriteLine("A variável é de outro tipo.")
End If
~~~

## Função GetType

- A função GetType em VB.NET permite descobrir o tipo exato de uma variável ou objeto em tempo de execução. Ela retorna um objeto do tipo System.Type que contém informações sobre o tipo da variável.

#### Sintaxe

~~~vb
variavel.GetType()
~~~

#### Exemplo de Uso

~~~vb
Dim numero As Integer = 42
Console.WriteLine(numero.GetType()) ' Saída: System.Int32

Dim texto As String = "Olá, Mundo!"
Console.WriteLine(texto.GetType()) ' Saída: System.String
~~~
