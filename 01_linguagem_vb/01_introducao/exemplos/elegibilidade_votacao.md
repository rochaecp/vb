# Sistema de Verificação de Elegibilidade para Votação

- Aplicativo de **Console** em VB.NET como solução para o exercício:
    - [Sistema de Verificação de Elegibilidade para Votação](https://github.com/rochaecp/engsw/blob/main/B_exercicios/01_introducao/operadores_relacionais.md#1-sistema-de-verifica%C3%A7%C3%A3o-de-elegibilidade-para-vota%C3%A7%C3%A3o)


~~~vb
Imports System.Globalization

Public Class Program

    Const IdadeMinimaVoto As Integer = 16
    Const IdadeVotoObrigatorioMin As Integer = 18
    Const IdadeVotoObrigatorioMax As Integer = 70

    Public Shared Sub Main()


        Dim continuar As Boolean = True

        While continuar

            Console.Clear()
            Console.WriteLine("=== Sistema de Verificação de Elegibilidade para Votação ===")

            Dim idade As Integer = ObterIdade()
            Dim ehCidadao As Boolean = ObterRespostaSimNao("Você é cidadão do país? (sim/não): ")
            Dim possuiTitulo As Boolean = ObterRespostaSimNao("Você possui título de eleitor ativo? (sim/não): ")
            VerificarElegibilidade(idade, ehCidadao, possuiTitulo)
            continuar = ObterRespostaSimNao("Deseja verificar outra pessoa? (sim/não): ")

        End While

        Console.WriteLine("Programa encerrado.")

    End Sub

    Public Shared Function ObterIdade() As Integer

        Dim idade As Integer
        Dim entradaValida As Boolean = False

        While Not entradaValida
            Console.Write("Informe sua idade: ")
            Dim entrada As String = Console.ReadLine()

            If Integer.TryParse(entrada, NumberStyles.Number, CultureInfo.CurrentCulture, idade) AndAlso idade > 0 Then
                entradaValida = True
            Else
                Console.WriteLine("Idade inválida. Por favor, insira um número inteiro não negativo.")
            End If
        End While

        Return idade

    End Function

    Public Shared Function ObterRespostaSimNao(mensagem As String) As Boolean
        Do
            Console.Write(mensagem)
            Dim entrada As String = Console.ReadLine().Trim().ToLower()

            Select Case entrada
                Case "sim"
                    Return True
                Case "nao", "não"
                    Return False
                Case Else
                    Console.WriteLine("Resposta inválida. Utilize 'sim' ou 'não'.")
            End Select
        Loop While True

        Return False
    End Function

    Public Shared Sub VerificarElegibilidade(idade As Integer, ehCidadao As Boolean, possuiTitulo As Boolean)
        Console.WriteLine()
        Console.WriteLine("===== Resultado da Verificação =====")

        If idade >= IdadeMinimaVoto AndAlso ehCidadao AndAlso possuiTitulo Then
            Console.WriteLine("Você está apto(a) a votar!")

            If (idade >= IdadeVotoObrigatorioMin AndAlso idade <= IdadeVotoObrigatorioMax) Then
                Console.WriteLine("O seu voto é obrigatório.")
            Else
                Console.WriteLine("O seu voto é facultativo.")
            End If
        Else
            Console.WriteLine("Você NÃO está apto(a) a votar.")
            If idade < IdadeMinimaVoto Then
                Console.WriteLine($"Motivo: Idade mínima para votar é {IdadeMinimaVoto} anos.")
            End If
            If Not ehCidadao Then
                Console.WriteLine("Motivo: É necessário ser cidadão do país.")
            End If
            If Not possuiTitulo Then
                Console.WriteLine("Motivo: É necessário possuir título de eleitor ativo.")
            End If
        End If

        Console.WriteLine("====================================")
        Console.WriteLine()
    End Sub

End Class
~~~