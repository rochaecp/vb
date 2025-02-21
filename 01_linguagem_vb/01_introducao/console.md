# Escrita no Console

## **Console.WriteLine()**

- Escreve uma linha de texto no console e move o cursor para a próxima linha.

#### Exibir uma String no console

~~~vb
Console.WriteLine("Olá, Mundo!")  ' Exibe o texto e pula para a linha seguinte
~~~

#### Exibir um número com 2 casas decimais

~~~vb
Dim valor As Decimal = 3.5432
Console.WriteLine($"Valor = {valor.ToString("F2")}") ' Valor = 3,54
~~~

#### Exibir um número omitindo as suas casas decimais

~~~vb
Dim valor As Double = 15.95456

' Função Int: retorna a parte inteira do número, truncando a parte decimal.
Console.WriteLine($"Valor com Int = {Int(valor)}") ' Saída: 15

' Função Fix: retorna a parte inteira do número, truncando a parte decimal.
Console.WriteLine($"Valor com Fix = {Fix(valor)}") ' Saída: 15

' Função Math.Truncate: remove a parte decimal do número, retornando apenas a parte inteira.
Console.WriteLine($"Valor com Math.Truncate = {Math.Truncate(valor)}") ' Saída: 15

' Método ToString("F0"): formata o número como ponto flutuante com zero casas decimais, arredondando o valor.
Console.WriteLine($"Valor com ToString(""F0"") = {valor.ToString("F0")}") ' Saída: 16

' Função CInt: converte o número para Integer, arredondando para o inteiro mais próximo.
Console.WriteLine($"Valor com CInt = {CInt(valor)}") ' Saída: 16
~~~

## **Console.Write()**

- Escreve um texto no console, mas mantém o cursor na mesma linha.

~~~vb
Console.Write("Digite seu nome: ")  ' Exibe o texto sem pular de linha
~~~

# Leitura no Console

## **Console.ReadLine()**

- Lê uma linha de texto digitada pelo usuário até que ele pressione a tecla Enter.

~~~vb
Dim nome As String = Console.ReadLine()  ' Lê a entrada do usuário e armazena na variável nome

' Lê o valor do console como string e converte para Integer
Dim numero As Integer = CInt(Console.ReadLine())

' Lê o valor do console como string e converte para Double (deve digitar com vírgula para demarcar as casas decimais)
Dim x As Double = CDbl(Console.ReadLine())
~~~

## **Console.Read()**

- Lê o próximo caractere da entrada, mas retorna o valor inteiro correspondente ao código do caractere.

~~~vb
Dim codigo As Integer
codigo = Console.Read()  ' Lê o próximo caractere como código ASCII
Console.WriteLine("Código ASCII: " & codigo)
~~~