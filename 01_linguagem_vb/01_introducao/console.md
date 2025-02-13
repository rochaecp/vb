# Escrita no Console

#### Console.WriteLine()

- Escreve uma linha de texto no console e move o cursor para a próxima linha.

~~~vb
Console.WriteLine("Olá, Mundo!")  ' Exibe o texto e pula para a linha seguinte
~~~

~~~vb
Dim valor As Decimal = 3.5432
Console.WriteLine($"Valor = {valor.ToString("F2")}") ' Valor = 3,54
~~~

#### Console.Write()

- Escreve um texto no console, mas mantém o cursor na mesma linha.

~~~vb
Console.Write("Digite seu nome: ")  ' Exibe o texto sem pular de linha
~~~

# Leitura no Console

#### Console.ReadLine()

- Lê uma linha de texto digitada pelo usuário até que ele pressione a tecla Enter.

~~~vb
Dim nome As String = Console.ReadLine()  ' Lê a entrada do usuário e armazena na variável nome

' Lê o valor do console como string e converte para Integer
Dim numero As Integer = CInt(Console.ReadLine())

' Lê o valor do console como string e converte para Double (deve digitar com vírgula para demarcar as casas decimais)
Dim x As Double = CDbl(Console.ReadLine())
~~~

#### Console.Read()

- Lê o próximo caractere da entrada, mas retorna o valor inteiro correspondente ao código do caractere.

~~~vb
Dim codigo As Integer
codigo = Console.Read()  ' Lê o próximo caractere como código ASCII
Console.WriteLine("Código ASCII: " & codigo)
~~~