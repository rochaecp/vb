# Exemplo - Calculadora de Salário com Impostos Fixos

- Implementação do exercício:
    - [Calculadora de Salário com Impostos Fixos](https://github.com/rochaecp/engsw/blob/main/B_exercicios/01_introducao/constantes.md#1-calculadora-de-sal%C3%A1rio-com-impostos-fixos)

#### Versão sem bônus

~~~vb
Imports System.Globalization

Public Class Program

    Public Shared Sub Main()

        Const TAXA_IR As Double = 0.15
        Const TAXA_INSS As Double = 0.11
        Const TAXA_SAUDE As Double = 0.05

        Dim salarioBruto As Double = 0
        Dim totalDescontos As Double = 0

        Do
            Console.Write("Informe o salário bruto do funcionário: ")
            If Double.TryParse(Console.ReadLine(), salarioBruto) AndAlso salarioBruto >= 0 Then Exit Do
            Console.WriteLine("Valor digitado inválido. Informe um valor válido." & Environment.NewLine)
        Loop

        Console.WriteLine(Environment.NewLine & "Descontos: ")
        Console.WriteLine($"- Imposto de Renda ({Int(TAXA_IR * 100)}%): {(salarioBruto * TAXA_IR).ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"- INSS             ({Int(TAXA_INSS * 100)}%): {(salarioBruto * TAXA_INSS).ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"- Plano de Saúde   ({Int(TAXA_SAUDE * 100)}%): {(salarioBruto * TAXA_SAUDE).ToString("F2", CultureInfo.InvariantCulture)}")

        totalDescontos = salarioBruto * (TAXA_IR + TAXA_INSS + TAXA_SAUDE)

        Console.WriteLine(Environment.NewLine & $"Salário Bruto: {salarioBruto.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Total de Descontos: {totalDescontos.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Salário Líquido: {(salarioBruto - totalDescontos).ToString("F2", CultureInfo.InvariantCulture)}")

    End Sub

End Class
~~~

#### Versão com bônus

~~~vb
Imports System.Globalization

Public Class Program

    Public Shared Sub Main()

        Const TAXA_IR As Double = 0.15
        Const TAXA_INSS As Double = 0.11
        Const TAXA_SAUDE As Double = 0.05

        Dim totalDescontoIR As Double = 0
        Dim totalDescontoInss As Double = 0
        Dim totalDescontoSaude As Double = 0

        Do
            Console.Write("Informe o salário bruto do funcionário (Digite ""sair"" para encerrar): ")

            Dim entrada = Console.ReadLine()

            If entrada.ToLower() = "sair" Then
                Console.WriteLine("Saindo ...")
                Exit Do
            End If


            Dim salarioBruto As Double = 0
            If Double.TryParse(entrada, NumberStyles.Number, CultureInfo.InvariantCulture, salarioBruto) AndAlso salarioBruto >= 0 Then
                Dim descontoIR As Double = salarioBruto * TAXA_IR
                Dim descontoInss As Double = salarioBruto * TAXA_INSS
                Dim descontoSaude As Double = salarioBruto * TAXA_SAUDE
                Dim totalDescontos As Double = descontoIR + descontoSaude + descontoInss
                Dim salarioLiquido As Double = salarioBruto - totalDescontos

                Console.WriteLine(Environment.NewLine & "Descontos: ")
                Console.WriteLine($"- Imposto de Renda ({Int(TAXA_IR * 100)}%): {descontoIR.ToString("F2", CultureInfo.InvariantCulture)}")
                Console.WriteLine($"- INSS             ({Int(TAXA_INSS * 100)}%): {descontoInss.ToString("F2", CultureInfo.InvariantCulture)}")
                Console.WriteLine($"- Plano de Saúde   ({Int(TAXA_SAUDE * 100)}%): {descontoSaude.ToString("F2", CultureInfo.InvariantCulture)}")

                Console.WriteLine(Environment.NewLine & $"Salário Bruto: {salarioBruto.ToString("F2", CultureInfo.InvariantCulture)}")
                Console.WriteLine($"Total de Descontos: {totalDescontos.ToString("F2", CultureInfo.InvariantCulture)}")
                Console.WriteLine($"Salário Líquido: {salarioLiquido.ToString("F2", CultureInfo.InvariantCulture)}" & Environment.NewLine)

                totalDescontoIR += descontoIR
                totalDescontoInss += descontoInss
                totalDescontoSaude += descontoSaude

            Else
                Console.WriteLine("Valor digitado inválido. Informe um valor válido." & Environment.NewLine)

            End If

        Loop

        Dim totalGlobalDescontos = totalDescontoIR + totalDescontoInss + totalDescontoSaude

        Console.WriteLine(Environment.NewLine & "Total de descontos")
        Console.WriteLine($"Total IR: {totalDescontoIR.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Total INSS: {totalDescontoInss.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Total Saúde : {totalDescontoSaude.ToString("F2", CultureInfo.InvariantCulture)}")
        Console.WriteLine($"Total global : {totalGlobalDescontos.ToString("F2", CultureInfo.InvariantCulture)}")

    End Sub

End Class
~~~