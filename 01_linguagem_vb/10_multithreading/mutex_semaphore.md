# Sincronização com Mutex e Semaphore em VB.NET

- Quando trabalhamos com threads em VB.NET, um dos desafios mais comuns é evitar que múltiplas threads acessem um mesmo recurso simultaneamente de forma descontrolada. 
- Para resolver esse problema, utilizamos mecanismos de sincronização, como Mutex e Semaphore.
- Use Mutex quando precisar garantir que apenas uma thread por vez execute um bloco de código crítico.
- Use Semaphore quando precisar limitar o número de threads que acessam simultaneamente um recurso compartilhado.
- Essas técnicas são essenciais para evitar condições de corrida, deadlocks e garantir a segurança e integridade dos dados em aplicações multithread.
- Diferença entre Mutex e Semaphore
    - O Mutex e o Semaphore são ambos mecanismos de sincronização, mas possuem diferenças fundamentais no controle de acesso e no comportamento.
    - Controle de Acesso: O Mutex permite que apenas uma única thread acesse o recurso protegido por vez, enquanto o Semaphore permite que múltiplas threads acessem o recurso simultaneamente, até um limite predefinido.
    - Propriedade e Liberação: O Mutex pode ser liberado apenas pela thread que o adquiriu, garantindo que o controle do recurso não seja perdido inadvertidamente. Já o Semaphore pode ser liberado por qualquer thread, independentemente de qual a tenha adquirido.
    - Uso Comum: O Mutex é ideal para cenários onde apenas uma única thread deve acessar um recurso por vez, como a escrita em um arquivo ou atualização de uma variável compartilhada. O Semaphore é útil quando há um limite de acessos simultâneos, como no controle de conexões simultâneas a um banco de dados ou no gerenciamento de filas de requisições.
    - Comportamento: O Mutex funciona como um bloqueio exclusivo, impedindo que outras threads entrem na região crítica até que ele seja liberado. O Semaphore, por outro lado, pode permitir um número específico de acessos concorrentes antes de bloquear novas threads que tentem acessar o recurso.


## O que é Mutex?

- O Mutex (Mutual Exclusion) é um mecanismo que garante que apenas uma única thread por vez possa acessar um determinado recurso. 
- Ele funciona como um cadeado exclusivo: se uma thread adquire o Mutex, nenhuma outra pode acessá-lo até que ele seja liberado.

#### Exemplo prático com Mutex

No exemplo abaixo, criamos um Mutex para evitar que duas threads executem um mesmo bloco de código ao mesmo tempo.

~~~vb
Imports System.Threading

Module Program
    Dim mutex As New Mutex()

    Sub Main()
        Dim t1 As New Thread(AddressOf Tarefa)
        Dim t2 As New Thread(AddressOf Tarefa)

        t1.Start()
        t2.Start()

        t1.Join()
        t2.Join()
    End Sub

    Sub Tarefa()
        ' Aguarda até que o Mutex esteja disponível
        mutex.WaitOne()
        
        Console.WriteLine("Thread {0} está acessando o recurso...", Thread.CurrentThread.ManagedThreadId)
        Thread.Sleep(2000) ' Simula um processamento
        Console.WriteLine("Thread {0} liberou o recurso.", Thread.CurrentThread.ManagedThreadId)
        
        ' Libera o Mutex
        mutex.ReleaseMutex()
    End Sub
End Module
~~~

## O que é Semaphore?

- O Semaphore é um mecanismo que permite que múltiplas threads acessem um recurso até um limite pré-definido. 
- Ele é útil quando queremos restringir o número de threads que acessam simultaneamente um recurso compartilhado.

#### Exemplo prático com Semaphore

No exemplo abaixo, usamos um Semaphore para permitir que apenas duas threads acessem um recurso ao mesmo tempo.

~~~vb
Imports System.Threading

Module Program
    Dim semaphore As New Semaphore(2, 2) ' Permite até 2 threads simultaneamente

    Sub Main()
        Dim threads(4) As Thread

        For i As Integer = 0 To 4
            threads(i) = New Thread(AddressOf Tarefa)
            threads(i).Start()
        Next

        For Each t In threads
            t.Join()
        Next
    End Sub

    Sub Tarefa()
        ' Aguarda liberação no semáforo
        semaphore.WaitOne()

        Console.WriteLine("Thread {0} acessando recurso...", Thread.CurrentThread.ManagedThreadId)
        Thread.Sleep(3000) ' Simula processamento
        Console.WriteLine("Thread {0} liberou o recurso.", Thread.CurrentThread.ManagedThreadId)

        ' Libera o semáforo
        semaphore.Release()
    End Sub
End Module
~~~





