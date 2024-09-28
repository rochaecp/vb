# Casting em VB.NET

- Casting em VB.NET é o processo de converter um valor de um tipo de dado para outro. 
- Isso é importante quando você está lidando com variáveis de diferentes tipos de dados e precisa transformá-las para realizar operações ou armazenar os valores de maneira compatível.
- Existem dois tipos principais de casting em VB.NET:
    - Conversão implícita
        - A conversão é feita automaticamente pelo compilador, sem que o programador precise indicar explicitamente.
    - Conversão explícita
        - O programador indica explicitamente que deseja realizar a conversão de um tipo de dado para outro, utilizando funções de conversão.

## Conversão Implícita

- A conversão implícita ocorre quando o VB.NET consegue realizar a conversão de forma automática e segura, sem perda de dados. 
- Isso acontece geralmente ao converter de um tipo de dado menor para um tipo de dado maior (como Integer para Long ou Single para Double).

#### Exemplos de conversão implícita

~~~vb
Dim numeroInteiro As Integer = 10
Dim numeroLong As Long = numeroInteiro  ' Conversão implícita de Integer para Long

Dim numeroFloat As Single = 3.14F
Dim numeroDouble As Double = numeroFloat  ' Conversão implícita de Single para Double

Dim numeroShort As Short = 100
Dim numeroInteiro2 As Integer = numeroShort  ' Conversão implícita de Short para Integer

Dim numeroByte As Byte = 255
Dim numeroShort2 As Short = numeroByte  ' Conversão implícita de Byte para Short

Dim numeroDecimal As Decimal = 100.5D
Dim numeroDouble2 As Double = numeroDecimal  ' Conversão implícita de Decimal para Double
~~~

## Conversão Explícita (Casting)

- Quando a conversão pode causar perda de dados ou quando o compilador não pode realizar a conversão de forma segura, é necessário realizar a conversão explícita.
- Existem várias maneiras de realizar o casting explícito em VB.NET:
    - Funções de conversão: As funções do VB.NET, como CInt(), CDbl(), CStr(), e outras, são usadas para conversões explícitas.
    - Método DirectCast(): Usado para converter objetos que estão relacionados por herança ou interfaces.
    - Método TryCast(): Usado para conversões seguras de objetos, retornando Nothing em caso de falha, em vez de gerar uma exceção.

### Funções de Conversão

- Funções de Conversão
    - CByte(): Converte para Byte
    - CShort: Converte para Short.
    - CUShort: Converte para UShort.
    - CInt(): Converte para Integer
    - CUInt: Converte para UInteger.
    - CLng(): Converte para Long
    - CULng: Converte para ULong.
    - CSng: Converte para Single.
    - CDbl: Converte para Double.
    - CDec: Converte para Decimal.
    - CChar: Converte para Char.
    - CStr(): Converte para String
    - CDate: Converte para Date.
    - CObj: Converte para Object.
    - CBool: Converte para Boolean.

#### Exemplos de Funções de Conversão

~~~vb
' CByte(): Converte para Byte.
Dim valorOriginal As Integer = 123
Dim valorByte As Byte = CByte(valorOriginal)

' CShort: Converte para Short.
Dim valorOriginalShort As Integer = 32000
Dim valorShort As Short = CShort(valorOriginalShort)

' CUShort: Converte para UShort.
Dim valorOriginalUShort As Integer = 60000
Dim valorUShort As UShort = CUShort(valorOriginalUShort)

' CInt(): Converte para Integer.
Dim textoInt As String = "1234" ' Se não for numérico gera uma exceção
Dim numeroInt As Integer = CInt(textoInt)

' CUInt: Converte para UInteger.
Dim valorOriginalUInteger As Long = 1234567890
Dim valorUInteger As UInteger = CUInt(valorOriginalUInteger)

' CLng(): Converte para Long.
Dim valorOriginalLong As Integer = 123456789
Dim valorLong As Long = CLng(valorOriginalLong)

' CULng: Converte para ULong.
Dim valorOriginalULong As Long = 1234567890123456789
Dim valorULong As ULong = CULng(valorOriginalULong)

' CSng: Converte para Single.
Dim valorOriginalSingle As Double = 123.456
Dim valorSingle As Single = CSng(valorOriginalSingle)

' CDbl: Converte para Double.
Dim valorOriginalDouble As Single = 123.456
Dim valorDouble As Double = CDbl(valorOriginalDouble)

' CDec: Converte para Decimal.
Dim valorOriginalDecimal As Double = 12345.6789
Dim valorDecimal As Decimal = CDec(valorOriginalDecimal)

' CChar: Converte para Char.
Dim textoChar As String = "A"
Dim valorChar As Char = CChar(textoChar)

' CStr(): Converte para String
Dim numero As Integer = 100
Dim texto As String = CStr(numero)

' CDate: Converte para Date.
Dim textoData As String = "01/01/2024"
Dim valorDate As Date = CDate(textoData)

' CObj: Converte para Object.
Dim valorOriginalObj As Integer = 123
Dim valorObject As Object = CObj(valorOriginalObj)

' CBool: Converte para Boolean.
Dim valorOriginalBool As Integer = 1
Dim valorBoolean As Boolean = CBool(valorOriginalBool)  ' Retorna True
~~~

### Método DirectCast()

- DirectCast() é usado para realizar o casting entre tipos de objetos que estão relacionados, como classes que herdam de uma base comum ou implementam uma interface.
- O DirectCast() deve ser usado quando você tem certeza de que a conversão será bem-sucedida, caso contrário, ocorrerá uma exceção em tempo de execução.

#### Exemplo de DirectCast

~~~vb
Dim obj As Object = "Texto"
Dim str As String = DirectCast(obj, String)  ' Converte de Object para String

Console.WriteLine(str)
~~~

### Método TryCast()

- TryCast() é semelhante ao DirectCast(), mas ele retorna Nothing caso a conversão falhe, em vez de lançar uma exceção.

#### Exemplo

~~~vb
'Aqui, como o valor de obj é um número, TryCast() retorna Nothing, já que não é possível converter um número diretamente para String.
Dim obj As Object = 123
Dim str As String = TryCast(obj, String)  ' Tentativa de conversão de Object para String

If str Is Nothing Then
    Console.WriteLine("Conversão falhou.")
Else
    Console.WriteLine(str)
End If
~~~

### Casting Seguro com TryParse()

- Quando você precisa garantir que uma conversão de **String** para um **tipo numérico** seja segura (sem exceções), é melhor usar o método TryParse(). 
- Ele retorna True ou False para indicar se a conversão foi bem-sucedida, e coloca o valor convertido na variável de saída.

#### Exemplo com Integer.TryParse()

- Se a conversão for bem-sucedida, TryParse() armazena o valor convertido em numero. Caso contrário, ele não altera o valor de numero e evita exceções.

~~~vb
Dim texto As String = "1234"
Dim numero As Integer

If Integer.TryParse(texto, numero) Then
    Console.WriteLine("Conversão bem-sucedida: " & numero)
Else
    Console.WriteLine("Falha na conversão")
End If
~~~
