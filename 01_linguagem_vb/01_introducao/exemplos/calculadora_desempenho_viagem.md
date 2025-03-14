# Exemplo: Calculadora de Desempenho de Viagem

- Aplicativo de **Console** em VB.NET como solução para o exercício:
    - [Calculadora de Desempenho de Viagem](https://github.com/rochaecp/engsw/blob/main/B_exercicios/01_introducao/operadores_aritmeticos.md#1-calculadora-de-desempenho-de-viagem)

~~~vb
Imports System.Globalization

Public Class Program

    Public Shared Sub Main()
        Dim odometroInicial As Double = 0
        Dim odometroFinal As Double = 0
        Dim qtdCombustivel As Double = 0
        Dim precoLitro As Double = 0

        Dim distTotal As Double = 0
        Dim combustTotal As Double = 0
        Dim custoTotal As Double = 0

        Do

            Console.Write("Tecle enter para iniciar ou digite 'sair para encerrar': ")

            Dim entrada As String = Console.ReadLine()
            If entrada.ToLower() = "sair" Then
                Console.WriteLine(Environment.NewLine & "Obrigado. Saindo ...")
                Exit Do
            End If

            Do
                Console.Write(Environment.NewLine & "Informe o odômetro inicial (km): ")
                If Double.TryParse(Console.ReadLine(), NumberStyles.Number, CultureInfo.InvariantCulture, odometroInicial) Then Exit Do
                Console.WriteLine(vbTab & "Erro. Informe um valor correto para o odômetro inicial")
            Loop

            Do
                Console.Write("Informe o odômetro final (km): ")
                Dim entradaOdometroFinal As String = Console.ReadLine()
                If Double.TryParse(entradaOdometroFinal, NumberStyles.Number, CultureInfo.InvariantCulture, odometroFinal) Then
                    If odometroFinal > odometroInicial Then Exit Do
                    Console.WriteLine(vbTab & "O valor do odômetro final precisa ser maior do que o valor do odômetro inicial")
                End If
                Console.WriteLine(vbTab & "Erro. Informe um valor correto para o odômetro final")
            Loop

            Do
                Console.Write("Informe a quantidade de combustível consumido (litros): ")
                If Double.TryParse(Console.ReadLine(), NumberStyles.Number, CultureInfo.InvariantCulture, qtdCombustivel) Then Exit Do
                Console.WriteLine(vbTab & "Erro. Informe um valor correto para a quantidade de combustível")
            Loop

            Do
                Console.Write("Informe o preço por litro do combustível: ")
                If Double.TryParse(Console.ReadLine(), NumberStyles.Number, CultureInfo.InvariantCulture, precoLitro) Then Exit Do
                Console.WriteLine(vbTab & "Erro. Informe um valor correto para o preço do litro do combustível")
            Loop

            Dim distPercorrida As Double = odometroFinal - odometroInicial
            Dim consumoMedio As Double = distPercorrida / qtdCombustivel
            Dim custo As Double = qtdCombustivel * precoLitro

            Console.WriteLine(Environment.NewLine & "===== Relatório da Viagem =====")
            Console.WriteLine($"Distância Percorrida: {distPercorrida.ToString("F1", CultureInfo.InvariantCulture)} km")
            Console.WriteLine($"Consumo Médio de Combustível: {consumoMedio.ToString("F1", CultureInfo.InvariantCulture)} km/l")
            Console.WriteLine($"Custo Total da Viagem: R$ {custo.ToString("F2", CultureInfo.InvariantCulture)}")
            Console.WriteLine("==============================" & Environment.NewLine)

            distTotal += distPercorrida
            combustTotal += qtdCombustivel
            custoTotal += custo

        Loop

        Console.WriteLine("===== Relatório Final da Viagem =====")
        Console.WriteLine($"Distância Total: {distTotal.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Combustível Total: {combustTotal.ToString("F2", CultureInfo.InvariantCulture)} l")
        Console.WriteLine($"Custo Total: {custoTotal.ToString("F1", CultureInfo.InvariantCulture)}")

    End Sub

End Class
~~~