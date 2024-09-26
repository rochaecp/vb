# Casting em VB.NET

- Casting em VB.NET é o processo de converter um valor de um tipo de dado para outro. 
- Isso é importante quando você está lidando com variáveis de diferentes tipos de dados e precisa transformá-las para realizar operações ou armazenar os valores de maneira compatível.
- Existem dois tipos principais de casting em VB.NET:
    - Conversão implícita: A conversão é feita automaticamente pelo compilador, sem que o programador precise indicar explicitamente.
    - Conversão explícita: O programador indica explicitamente que deseja realizar a conversão de um tipo de dado para outro, utilizando funções de conversão.

## Conversão Implícita

- A conversão implícita ocorre quando o VB.NET consegue realizar a conversão de forma automática e segura, sem perda de dados. 
- Isso acontece geralmente ao converter de um tipo de dado menor para um tipo de dado maior (como Integer para Long ou Single para Double).

#### Exemplo de conversão implícita

- Neste exemplo, o Integer é automaticamente convertido para Long, porque o tipo Long pode armazenar todos os valores de um Integer sem perda de dados.

~~~vb
Dim numeroInteiro As Integer = 10
Dim numeroLong As Long = numeroInteiro  ' Conversão implícita de Integer para Long
~~~

## Conversão Explícita (Casting)

- Quando a conversão pode causar perda de dados ou quando o compilador não pode realizar a conversão de forma segura, é necessário realizar a conversão explícita.
- Existem várias maneiras de realizar o casting explícito em VB.NET:
    - Funções de conversão: As funções do VB.NET, como CInt(), CDbl(), CStr(), e outras, são usadas para conversões explícitas.
    - Método DirectCast(): Usado para converter objetos que estão relacionados por herança ou interfaces.
    - Método TryCast(): Usado para conversões seguras de objetos, retornando Nothing em caso de falha, em vez de gerar uma exceção.

### Funções de Conversão

- Funções de Conversão
    - CInt(): Converte para Integer
    - CLng(): Converte para Long
    - CStr(): Converte para String
    - CDbl(): Converte para Double
    - CDec(): Converte para Decimal
    - CByte(): Converte para Byte
    - CDate(): Converte para Date
- Neste exemplo, a função CInt() converte o valor 10.5 para o tipo Integer. Como Integer não pode armazenar decimais, ele trunca o valor para 10.

#### Exemplo de Funções de Conversão

~~~vb
Dim numeroDouble As Double = 10.5
Dim numeroInteiro As Integer = CInt(numeroDouble)  ' Converte de Double para Integer

Console.WriteLine("Número Inteiro: " & numeroInteiro)  ' Resultado: 10
~~~

#### Exemplo de Funções de Conversão (entre Tipos Numéricos e Strings)

~~~vb
Dim numero As Integer = 100
Dim texto As String = CStr(numero)  ' Converte de Integer para String
Console.WriteLine(texto)  ' Saída: "100"
~~~

- Atenção: Ao converter uma string para número, certifique-se de que a string realmente representa um valor numérico, ou ocorrerá uma exceção.

~~~vb
Dim texto As String = "1234"
Dim numero As Integer = CInt(texto)  ' Converte de String para Integer
Console.WriteLine(numero)  ' Saída: 1234
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

- Aqui, como o valor de obj é um número, TryCast() retorna Nothing, já que não é possível converter um número diretamente para String.

~~~vb
Dim obj As Object = 123
Dim str As String = TryCast(obj, String)  ' Tentativa de conversão de Object para String

If str Is Nothing Then
    Console.WriteLine("Conversão falhou.")
Else
    Console.WriteLine(str)
End If
~~~

### Casting Seguro com TryParse()

- Quando você precisa garantir que uma conversão de String para um tipo numérico seja segura (sem exceções), é melhor usar o método TryParse(). Ele retorna True ou False para indicar se a conversão foi bem-sucedida, e coloca o valor convertido na variável de saída.

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
