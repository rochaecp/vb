# Exceções

- Exceções em programação são eventos inesperados ou erros que ocorrem durante a execução de um programa, interrompendo seu fluxo normal. 
- Elas indicam situações excepcionais, como divisão por zero, tentativa de acessar arquivos inexistentes, ou entrada de dados inválidos.
- São gerenciadas por mecanismos de tratamento, como o bloco `Try...Catch...Finally` no VB.NET.
- O tratamento de exceções permite que o programa lide com problemas sem encerrar abruptamente.

## Estrutura Try...Catch...Finally

- A estrutura Try...Catch...Finally é usada em VB.NET para lidar com erros e exceções que podem ocorrer durante a execução de um programa. - Ela permite que o código capture e trate problemas de forma controlada, evitando que o programa termine abruptamente.
- Com essa estrutura, você pode escrever programas mais robustos, seguros e fáceis de manter.
- Benefícios: 
    - Tratamento de Erros Controlado: Permite tratar erros sem interromper a execução do programa.
    - Manutenção e Depuração: Facilita a localização e a correção de problemas.
    - Liberação de Recursos: Garante que recursos, como arquivos abertos, sejam liberados mesmo em caso de erro.
- Dicas de Uso
    - Sempre use o bloco Catch mais específico antes do mais genérico.
    - Utilize o bloco Finally para ações de limpeza, como fechar conexões com bancos de dados ou liberar memória.
    - Evite capturar exceções genéricas sem necessidade, pois isso pode mascarar problemas mais graves.

#### Estrutura Básica

- `Try`: Define o bloco de código onde erros podem ocorrer.
- `Catch`: Captura e trata a exceção. O objeto ex contém informações sobre o erro.
- `Finally`: Opcional; contém código que sempre será executado, seja uma exceção lançada ou não. Geralmente usado para liberar recursos, como fechar arquivos ou conexões.

~~~vb
Try
    ' Código que pode causar uma exceção
Catch ex As Exception
    ' Código para tratar a exceção
Finally
    ' Código que será executado sempre, independentemente de erro
End Try
~~~

#### Exemplo Prático - Divisão por Zero

~~~vb
Module TryCatchExample
    Sub Main()
        
        ' Tenta realizar a divisão que pode causar um erro de divisão por zero.
        Try
            ' Entrada de dados
            Dim numerador As Integer = 10
            Dim denominador As Integer = 0
            Dim resultado As Integer

            ' Tentativa de divisão
            resultado = numerador / denominador
            Console.WriteLine($"Resultado: {resultado}")
        
        ' Captura especificamente o erro de divisão por zero
        Catch ex As DivideByZeroException
            ' Tratamento específico para divisão por zero
            Console.WriteLine("Erro: Não é possível dividir por zero.")
        
        ' Captura qualquer outra exceção não tratada
        Catch ex As Exception
            ' Tratamento genérico para outras exceções
            Console.WriteLine($"Erro: {ex.Message}")
        
        ' Executa independentemente de ter ocorrido um erro ou não, garantindo que o programa finalize corretamente.
        Finally
            ' Código que será executado sempre
            Console.WriteLine("Operação concluída.")
        End Try
    End Sub
End Module
~~~

## Principais Tipos de Exceções

- Como Escolher o Tipo de Exceção
    - Use exceções específicas, como NullReferenceException ou DivideByZeroException, para tratar cenários conhecidos.
    - Reserve System.Exception para capturar exceções genéricas ou inesperadas.
- Os tipos de exceções comuns em VB.NET ajudam a identificar e corrigir problemas específicos no código, tornando-o mais robusto. Com a prática, você aprenderá a identificar qual exceção usar em cada cenário.


#### System.Exception

- Exceção base de todas as outras exceções. Captura qualquer tipo de erro.

~~~vb
Try
    Throw New Exception("Erro genérico!")
Catch ex As Exception
    Console.WriteLine($"Exceção capturada: {ex.Message}")
End Try
~~~

#### System.NullReferenceException

- Ocorre quando você tenta acessar um membro de um objeto que não foi instanciado.

~~~vb
Dim obj As Object = Nothing
Try
    Console.WriteLine(obj.ToString()) ' Erro aqui
Catch ex As NullReferenceException
    Console.WriteLine("Objeto não instanciado!")
End Try
~~~

#### System.IndexOutOfRangeException

- Ocorre quando você tenta acessar um índice inválido em um array ou coleção.

~~~vb
Dim arr() As Integer = {1, 2, 3}
Try
    Console.WriteLine(arr(5)) ' Índice inválido
Catch ex As IndexOutOfRangeException
    Console.WriteLine("Índice fora do intervalo!")
End Try
~~~

#### System.DivideByZeroException

- Lançada quando uma divisão por zero é tentada.

~~~vb
Try
    Dim resultado = 10 / 0
Catch ex As DivideByZeroException
    Console.WriteLine("Não é possível dividir por zero.")
End Try
~~~

#### System.IO.IOException

- Relacionada a erros de entrada e saída, como leitura ou gravação de arquivos.

~~~vb
Try
    Dim conteudo = IO.File.ReadAllText("arquivo_inexistente.txt")
Catch ex As IO.IOException
    Console.WriteLine("Erro ao acessar o arquivo.")
End Try
~~~

#### System.FormatException

- Ocorre quando uma conversão de formato inválida é tentada.

~~~vb
Try
    Dim numero = Integer.Parse("abc") ' Formato inválido
Catch ex As FormatException
    Console.WriteLine("Formato inválido para conversão.")
End Try
~~~

#### System.ArgumentException

- Lançada quando um argumento inválido é passado para um método.

~~~vb
Try
    Dim str As String = Nothing
    Console.WriteLine(str.Substring(5)) ' Argumento inválido
Catch ex As ArgumentException
    Console.WriteLine("Argumento inválido passado ao método.")
End Try
~~~

#### System.OverflowException:

- Ocorre quando uma operação aritmética resulta em um valor que excede o limite permitido.

~~~vb
Try
    Dim valor As Integer = Integer.MaxValue
    valor += 1 ' Causa overflow
Catch ex As OverflowException
    Console.WriteLine("Valor excede o limite permitido.")
End Try
~~~

## Criando Exceções Personalizadas

- No VB.NET, além de utilizar exceções padrão, você pode criar suas próprias exceções para representar erros específicos em sua aplicação. 
- Isso ajuda a tornar o código mais legível e facilita o tratamento de erros em cenários específicos.
- Uma exceção personalizada é uma classe que herda de `System.Exception` (ou de outra classe derivada) e pode conter propriedades, métodos ou informações adicionais.
- Vantagens de Usar Exceções Personalizadas
    - Melhor legibilidade: Identifica erros específicos diretamente pela classe da exceção.
    - Diagnóstico mais preciso: Permite adicionar informações detalhadas para depuração.
    - Reuso: Pode ser usada em diferentes partes do sistema que compartilhem o mesmo tipo de erro.
- Com exceções personalizadas, seu código ganha flexibilidade e clareza, facilitando a identificação e o tratamento de erros em cenários complexos.

#### Exemplo de Criação

- A classe MinhaExcecao herda de Exception, permitindo que ela seja tratada como qualquer outra exceção.
- A propriedade Detalhes armazena informações adicionais sobre o erro, facilitando o diagnóstico.
- No bloco Catch, podemos capturar e tratar a exceção personalizada separadamente de exceções genéricas.

~~~vb
' Classe de exceção personalizada
Public Class MinhaExcecao
    Inherits Exception

    ' Propriedade personalizada para armazenar detalhes adicionais
    Public Property Detalhes As String

    ' Construtor padrão
    Public Sub New()
        MyBase.New("Erro personalizado ocorrido.")
    End Sub

    ' Construtor com mensagem
    Public Sub New(mensagem As String)
        MyBase.New(mensagem)
    End Sub

    ' Construtor com mensagem e detalhes
    Public Sub New(mensagem As String, detalhes As String)
        MyBase.New(mensagem)
        Me.Detalhes = detalhes
    End Sub
End Class
~~~

#### Exemplo de Uso

- Após criar a classe, você pode usá-la em qualquer parte do código onde seja necessário lançar uma exceção específica.

~~~vb
Module ExcecoesPersonalizadas
    Sub Main()
        Try
            ' Lança a exceção personalizada
            Throw New MinhaExcecao("Algo deu errado!", "Detalhes adicionais do erro.")
        Catch ex As MinhaExcecao
            ' Captura e trata a exceção personalizada
            Console.WriteLine($"Exceção: {ex.Message}")
            Console.WriteLine($"Detalhes: {ex.Detalhes}")
        Catch ex As Exception
            ' Captura outras exceções genéricas
            Console.WriteLine($"Erro genérico: {ex.Message}")
        End Try
    End Sub
End Module
~~~



