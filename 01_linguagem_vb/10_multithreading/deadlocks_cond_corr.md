# Problemas Comuns: Deadlocks e Condições de Corrida em VB.NET

- Em aplicações que utilizam múltiplas threads, podem ocorrer problemas como deadlocks e condições de corrida, que afetam a confiabilidade do sistema. 
- Esses problemas surgem devido ao acesso simultâneo a recursos compartilhados.
- Ambos os problemas são comuns em aplicações multithread e devem ser tratados corretamente para garantir a estabilidade do sistema.

##  Deadlocks

- Um deadlock ocorre quando duas ou mais threads ficam esperando indefinidamente por recursos que estão bloqueados por outras threads. 
- Isso pode paralisar a aplicação.

#### Exemplo de Deadlock em VB.NET

No exemplo abaixo, duas threads tentam acessar os mesmos objetos bloqueados, causando um impasse.

~~~vb
Imports System.Threading

Module Program
    Dim lock1 As New Object()
    Dim lock2 As New Object()

    Sub Thread1()
        SyncLock lock1
            Thread.Sleep(100)
            SyncLock lock2
                Console.WriteLine("Thread 1 executando")
            End SyncLock
        End SyncLock
    End Sub

    Sub Thread2()
        SyncLock lock2
            Thread.Sleep(100)
            SyncLock lock1
                Console.WriteLine("Thread 2 executando")
            End SyncLock
        End SyncLock
    End Sub

    Sub Main()
        Dim t1 As New Thread(AddressOf Thread1)
        Dim t2 As New Thread(AddressOf Thread2)
        t1.Start()
        t2.Start()
        t1.Join()
        t2.Join()
    End Sub
End Module
~~~

- No exemplo acima:
    - A Thread 1 bloqueia lock1 e tenta acessar lock2, que já está bloqueado pela Thread 2.
    - A Thread 2 bloqueia lock2 e tenta acessar lock1, que já está bloqueado pela Thread 1.
    - Nenhuma das threads consegue continuar, gerando um deadlock.
- Solução
    - Para evitar deadlocks, recomenda-se:
        - Usar sempre a mesma ordem de bloqueio para os recursos compartilhados.
        - Utilizar timeouts para evitar esperas indefinidas.

## Condições de Corrida

- Uma condição de corrida ocorre quando duas ou mais threads acessam uma variável compartilhada simultaneamente e o resultado depende da ordem de execução das threads.

#### Exemplo de Condição de Corrida em VB.NET

Aqui, duas threads tentam incrementar uma variável ao mesmo tempo, causando inconsistências.

~~~vb
Imports System.Threading

Module Program
    Dim contador As Integer = 0

    Sub Incrementar()
        For i As Integer = 1 To 10000
            contador += 1
        Next
    End Sub

    Sub Main()
        Dim t1 As New Thread(AddressOf Incrementar)
        Dim t2 As New Thread(AddressOf Incrementar)
        t1.Start()
        t2.Start()
        t1.Join()
        t2.Join()
        Console.WriteLine("Valor final do contador: " & contador)
    End Sub
End Module
~~~

- No exemplo acima:
    - Duas threads incrementam contador simultaneamente.
    - Como a operação de incremento não é atômica, pode haver perda de contagens, resultando em um valor menor do que o esperado.
- Solução
    - Para evitar condições de corrida:
    - Usar SyncLock para garantir exclusão mútua:
        ~~~vb
        SyncLock Me
            contador += 1
        End SyncLock
        ~~~
    - Utilizar Interlocked para garantir operações atômicas:
        ~~~vb
        Interlocked.Increment(contador)
        ~~~    
        