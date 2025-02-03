# Criação e Gerenciamento de Threads em VB.NET

- A programação com threads permite a execução de múltiplas tarefas em paralelo, otimizando o desempenho do programa. 
- Em VB.NET, as threads são gerenciadas pela classe `Thread` do namespace `System.Threading`.
- Criar threads permite rodar múltiplas tarefas ao mesmo tempo, melhorando a performance.
- Podemos passar parâmetros, sincronizar execução com .Join() e interromper threads com variáveis de controle.
- Threads são úteis para tarefas longas, operações em segundo plano e processamento paralelo.
- Esses conceitos são essenciais para criar aplicações eficientes em VB.NET Multithreading.

## Criando Threads em VB.NET

- Para criar uma nova thread, utilizamos a classe Thread e passamos um método para ser executado paralelamente.

#### Exemplo 1: Criando e iniciando uma thread

~~~vb
Imports System
Imports System.Threading

Module Program
    Sub Main()
        ' Criando uma nova thread e associando-a ao método Trabalho()
        Dim novaThread As New Thread(AddressOf Trabalho)
        
        ' Iniciando a thread
        novaThread.Start()

        Console.WriteLine("Thread principal continua executando...")
        Console.ReadLine() ' Evita que o programa feche imediatamente
    End Sub

    Sub Trabalho()
        For i As Integer = 1 To 5
            Console.WriteLine($"Thread em execução: {i}")
            Thread.Sleep(1000) ' Simula um tempo de processamento
        Next
    End Sub
End Module
~~~

## Passando Parâmetros para Threads

- O método da thread pode receber parâmetros ao ser iniciado.

#### Exemplo 2: Thread com Parâmetro

~~~vb
Imports System
Imports System.Threading

Module Program
    Sub Main()
        ' Criando e iniciando a thread com um parâmetro
        Dim novaThread As New Thread(AddressOf ExibirMensagem)
        novaThread.Start("Olá, esta é uma thread com parâmetro!")

        Console.ReadLine()
    End Sub

    Sub ExibirMensagem(mensagem As Object)
        Console.WriteLine(mensagem)
    End Sub
End Module
~~~

## Controlando a Execução de Threads

- Podemos pausar, verificar o status e aguardar a finalização de uma thread.

#### Exemplo 3: Controle de Threads

~~~vb
Imports System
Imports System.Threading

Module Program
    Sub Main()
        Dim minhaThread As New Thread(AddressOf ContarAteDez)
        minhaThread.Start()

        ' Aguarda a thread terminar antes de continuar
        minhaThread.Join()

        Console.WriteLine("Thread finalizada. Programa encerrado.")
    End Sub

    Sub ContarAteDez()
        For i As Integer = 1 To 10
            Console.WriteLine(i)
            Thread.Sleep(500)
        Next
    End Sub
End Module
~~~

## Finalizando uma Thread

- Podemos solicitar que uma thread seja interrompida utilizando a variável de controle Volatile Boolean.

#### Exemplo 4: Encerrando uma Thread

~~~vb
Imports System
Imports System.Threading

Module Program
    Dim continuarExecutando As Boolean = True

    Sub Main()
        Dim t As New Thread(AddressOf LoopInfinito)
        t.Start()

        Console.WriteLine("Pressione ENTER para parar a thread...")
        Console.ReadLine()
        continuarExecutando = False

        t.Join()
        Console.WriteLine("Thread encerrada.")
    End Sub

    Sub LoopInfinito()
        While continuarExecutando
            Console.WriteLine("Thread em execução...")
            Thread.Sleep(1000)
        End While
    End Sub
End Module
~~~
