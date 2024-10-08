# Datas em VB.net

- DateTime: É o nome da estrutura utilizada no .NET Framework para representar uma data e hora.
- Date: Em VB.NET, Date é um alias para DateTime. Ou seja, quando você usa Date, você está, na verdade, utilizando o tipo DateTime.

## Classes para criar Datas e Horas em vb

- **DateTime**:         Classe principal para representar uma data e hora.
- **DateTimeOffset**:   Representa uma data e hora com um deslocamento de fuso horário.
- **TimeSpan**:         Representa um intervalo de tempo.

## Criar Datas e Horas - `DateTime`

- Para criar uma data ou hora específica, utilize o construtor New DateTime

~~~vb
Dim data1 As DateTime = New DateTime(1990, 6, 15)            ' Ano, Mês, Dia
Dim data2 As DateTime = New DateTime(2024, 10, 1, 14, 30, 0) ' Ano, Mês, Dia, Hora, Minuto, Segundo
Dim data3 As DateTime = DateTime.Now                         ' 02/10/2024 10:33:24   
Dim data4 As DateTime = DateTime.Today                       ' 02/10/2024 00:00:00   
~~~

## Criar Datas e Horas - `DateTimeOffset`

- O DateTimeOffset permite criar datas com informações de fuso horário.

~~~vb
Dim eventDate As DateTimeOffset = New DateTimeOffset(2024, 12, 31, 23, 59, 0, TimeSpan.FromHours(-3)) ' Inclui fuso horário
~~~

## Criar Datas e Horas - `TimeSpan`

- TimeSpan é útil para representar a diferença entre datas ou intervalos de tempo.

~~~vb
Dim ts1 As New TimeSpan(3, 45, 30)              ' 3h 45min 30seg
Dim ts2 As TimeSpan = New TimeSpan(3, 45, 30)   ' 3h 45min 30seg
Dim ts3 As TimeSpan = New TimeSpan(2, 6, 0, 0)  ' Intervalo de 2 dias e 6 horas

Dim ts4 As TimeSpan = TimeSpan.FromDays(30)     ' Intervalo de 30 dias
Dim ts5 As TimeSpan = TimeSpan.FromHours(2)     ' Intervalo de 2 horas
Dim ts6 As TimeSpan = TimeSpan.FromMinutes(15)  ' Intervalo de 15 minutos
Dim ts7 As TimeSpan = TimeSpan.FromSeconds(20)  ' Intervalo de 20 segundos
~~~

## Converter Strings em Datas e Horas - DateTime.Parse

- Converte uma string para uma data ou hora, lançando exceção se a conversão falhar.

~~~vb
Dim date1 As DateTime = DateTime.Parse("2024-10-01 14:30:00") 
Dim date2 As DateTime = DateTime.Parse("2024-10-01")          
Dim date2 As DateTime = DateTime.Parse("2024/10/01")          
Dim date2 As DateTime = DateTime.Parse("01-10-2024")          
Dim date2 As DateTime = DateTime.Parse("01/10/2024")          
~~~

~~~vb
Try
    Dim a As DateTime = DateTime.Parse("31/02/2024")
    Console.WriteLine(a)
Catch ex As Exception
    Console.WriteLine(ex.Message)
End Try
~~~

## Converter Strings em Datas e Horas - DateTime.TryParse

- Tenta converter a string e retorna True ou False, sem lançar exceção.

~~~vb
' Usando TryParse - seguro contra erros de formato
Dim validDate As DateTime
If DateTime.TryParse("2024-10-01", validDate) Then
    Console.WriteLine("Data válida: " & validDate.ToString())
Else
    Console.WriteLine("Formato de data inválido.")
End If
~~~

## Formatar Datas e Horas - Método `ToString` de `DateTime`

- O método `ToString` permite formatar uma data e hora de acordo com um padrão específico.
- Você pode fornecer um padrão de formatação personalizado para definir como a data será exibida.
- Usando Padrões Predefinidos
    - "d": Data curta.
    - "D": Data longa.
    - "t": Hora curta.
    - "T": Hora longa.

~~~vb
Console.WriteLine(data.ToString("dd/MM/yyyy"))             ' 02/10/2024
Console.WriteLine(data.ToString("HH:mm:ss"))               ' 09:01:03
Console.WriteLine(data.ToString("MMMM dd, yyyy HH:mm:ss")) ' outubro 02, 2024 09:01:03
Console.WriteLine(data.ToString("MMMM"))                   ' outubro

Console.WriteLine(data.ToString("d"))                      ' 02/10/2024
Console.WriteLine(data.ToString("D"))                      ' quarta-feira, 2 de outubro de 2024
Console.WriteLine(data.ToString("t"))                      ' 09:01
Console.WriteLine(data.ToString("T"))                      ' 09:01:03
~~~

## Formatar Datas e Horas - TimeSpan.ToString()

~~~vb
Dim ts As TimeSpan = New TimeSpan(45, 22, 15) '45h 22min 15seg
Console.WriteLine(ts.Days)
Console.WriteLine(ts.Hours)
Console.WriteLine(ts.Minutes)
Console.WriteLine(ts.Seconds)

Console.WriteLine(ts.TotalDays)
Console.WriteLine(ts.TotalHours)
Console.WriteLine(ts.TotalMinutes)
~~~

## Formatar Datas e Horas - String.Format

- Outra forma de formatar datas e horas é utilizando String.Format com placeholders.
- O {0:format} define como a data ou hora será formatada.

~~~vb
Dim currentDate As DateTime = DateTime.Now
Dim formatted As String = String.Format("Data: {0:dd/MM/yyyy}, Hora: {0:HH:mm:ss}", currentDate)
~~~

## Formatar Datas e Horas - Usando CultureInfo para Formatação Localizada

- A classe CultureInfo pode ser usada para aplicar formatos de datas e horas específicos de uma cultura.
- Isso é útil para garantir que a data seja exibida de acordo com convenções regionais.

~~~vb
Dim currentDate As DateTime = DateTime.Now
Dim culture As New System.Globalization.CultureInfo("en-US") ' Formatação para cultura dos EUA
Dim formattedDate As String = currentDate.ToString("D", culture) ' Exibe data no formato longo para cultura dos EUA
~~~

## Adicionar Dias, Meses, Horas, etc. a uma Data

- O `DateTime` tem métodos como `AddDays`, `AddMonths`, `AddHours`, entre outros, para adicionar intervalos de tempo a uma data ou hora.

~~~vb
Dim data As DateTime = DateTime.Now
Console.WriteLine(data)

Console.WriteLine(data.AddYears(1))
Console.WriteLine(data.AddMonths(1))
Console.WriteLine(data.AddDays(5))
Console.WriteLine(data.AddHours(3))
Console.WriteLine(data.AddMinutes(15))
Console.WriteLine(data.AddSeconds(10))
~~~

## Usando TimeSpan para Operações de Intervalos

- O TimeSpan é útil para representar intervalos de tempo e realizar cálculos entre datas e horas.

~~~vb
Dim interval As TimeSpan = TimeSpan.FromDays(5)
Dim futureDate As DateTime = DateTime.Now.Add(interval) ' Adiciona o intervalo de 5 dias à data atual
~~~

~~~vb
' Adicionando 2dias 1hora 10min a data atual
Dim ts As TimeSpan = New TimeSpan(2, 1, 10, 0) '2dias 1hora 10min 
Console.WriteLine(DateTime.Now.Add(ts))
~~~

## Subtrair Datas (Diferença de Datas) - Subtract

- Para calcular a diferença entre duas datas, você pode simplesmente subtrair uma DateTime de outra. O resultado é um TimeSpan, que representa o intervalo de tempo entre as duas datas.

~~~vb
Dim startDate As DateTime = New DateTime(2024, 10, 1)
Dim endDate As DateTime = New DateTime(2024, 12, 31)
Dim difference As TimeSpan = endDate.Subtract(startDate) ' Diferença entre as datas
Dim daysDifference As Double = difference.TotalDays      ' Número total de dias entre as datas
~~~

## Subtrair Datas (Diferença de Datas) - DateDiff

~~~vb
Dim startDate As DateTime = New DateTime(2024, 1, 1)
Dim endDate As DateTime = New DateTime(2024, 12, 31)
Dim diff As Integer = DateDiff(DateInterval.Day, startDate, endDate)
Console.WriteLine("Diferença em dias: " & diff)
~~~

## Comparação entre Datas

- Datas podem ser comparadas diretamente usando operadores como >, <, =, >=, <=.

~~~vb
Dim firstDate As DateTime = New DateTime(2024, 10, 1)
Dim secondDate As DateTime = New DateTime(2024, 12, 31)

If firstDate < secondDate Then
    Console.WriteLine("A primeira data é anterior à segunda.")
End If
~~~

## Funções Predefinidas para Manipulação de Datas e Horas

~~~vb
Dim currentDate As DateTime = DateTime.Now                  ' Retorna a data e hora atuais do sistema
Dim todayDate As DateTime = DateTime.Today                  ' Retorna apenas a data atual (sem a parte da hora)
Dim futureDate As DateTime = DateTime.Now.AddDays(30)       ' Adiciona 30 dias à data atual
Dim futureMonth As DateTime = DateTime.Now.AddMonths(1)     ' Adiciona 1 mês à data atual
Dim nextYear As DateTime = DateTime.Now.AddYears(1)         ' Adiciona 1 ano à data atual
Dim specificDate As DateTime = DateSerial(2024, 10, 1)      ' Retorna um valor de data construído a partir de valores numéricos para ano, mês e dia.
Dim dateFromString As DateTime = DateValue("01/10/2024")    ' Converte uma string que contém uma data em um valor de data.
Dim specificTime As DateTime = TimeSerial(14, 30, 0)        ' Cria um valor de hora a partir de valores numéricos para horas, minutos e segundos. 14:30:00
Dim currentTime As DateTime = Now                           ' Retorna a data e hora atuais.
~~~

~~~vb
' DatePart(): Retorna uma parte específica de uma data (como o ano, mês ou dia).
Dim currentYear As Integer = DatePart(DateInterval.Year, DateTime.Now)
Dim currentMonth As Integer = DatePart(DateInterval.Month, DateTime.Now)
Console.WriteLine("Ano atual: " & currentYear)
Console.WriteLine("Mês atual: " & currentMonth)
~~~
