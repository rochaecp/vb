# Programação Assíncrona

## O que é Programação Assíncrona?

- Programação assíncrona é um modelo de execução que permite que seu programa realize múltiplas tarefas simultaneamente, sem bloquear a execução principal enquanto aguarda a conclusão de operações demoradas. 
- Em vez de pausar o programa, as tarefas são executadas em segundo plano, permitindo que a aplicação permaneça responsiva.
- Esse conceito é amplamente utilizado para melhorar o desempenho e a experiência do usuário em operações que podem levar tempo, como:
    - Acesso a bancos de dados.
    - Comunicação com APIs ou serviços externos.
    - Operações de leitura e escrita em arquivos.

## Por que usar Programação Assíncrona?

1. **Performance**: 
    - Executa tarefas demoradas sem bloquear o restante do programa.
1. **Responsividade**: 
    - Especialmente útil em aplicações com interface gráfica (UI), evitando "travamentos".
1. **Paralelismo**: 
    - Permite executar várias tarefas ao mesmo tempo.

## Exemplo prático de Programação Assíncrona em VB.NET

- No exemplo abaixo, vamos simular uma tarefa que leva tempo (como acessar um banco de dados) e usar a programação assíncrona para evitar o bloqueio da execução principal.

~~~vb
Imports System.Threading.Tasks

Module Program
    Sub Main()
        ' Chamada assíncrona
        Dim resultado = ExecutarTarefaDemoradaAsync().Result

        ' Imprimir resultado após a execução
        Console.WriteLine($"Resultado: {resultado}")
        Console.WriteLine("Programa Finalizado")
        Console.ReadLine()
    End Sub

    ' Método assíncrono
    Async Function ExecutarTarefaDemoradaAsync() As Task(Of String)
        Console.WriteLine("Iniciando tarefa demorada...")
        
        ' Simula uma operação demorada (aguarda 3 segundos)
        Await Task.Delay(3000)
        
        Console.WriteLine("Tarefa concluída!")
        Return "Sucesso"
    End Function
End Module
~~~

## Uso de Async e Await em VB.NET

- O uso de `Async` e `Await` no VB.NET é essencial para implementar programação assíncrona de maneira simples e eficiente. 
- Usar `Async` e `Await` ajuda a criar programas responsivos e eficientes, especialmente em cenários onde há operações demoradas que podem impactar a experiência do usuário.
- Esses recursos permitem que você execute tarefas demoradas (como chamadas de APIs ou operações de leitura/escrita) sem bloquear a thread principal, garantindo que a aplicação permaneça responsiva.
- Como Funciona?
    - `Async`: 
        - Indica que um método é assíncrono. 
        - Ele permite o uso de `Await` dentro do método.
    - `Await`: 
        - Pausa a execução do método até que a tarefa seja concluída. 
        - Durante essa pausa, o controle é liberado para que outras operações sejam executadas.
- Cuidados
    - Sempre use `Await` para garantir que o método realmente seja assíncrono.
    - Métodos `Async` podem retornar:
    - `Task`: Para métodos que não retornam valores.
    - `Task(Of T)`: Para métodos que retornam valores.
    - `Void` (apenas para `Async Sub`, usado em eventos ou métodos não esperados).


## Exemplo Prático de Async e Await

- A seguir, criamos um exemplo que simula uma operação demorada (aguardar 3 segundos) e exibe mensagens antes e depois da execução.

~~~vb
Imports System.Threading.Tasks

Module Program
    Sub Main()
        ' Chamando o método assíncrono
        IniciarProcesso()

        ' Mensagem exibida enquanto a tarefa é executada em segundo plano
        Console.WriteLine("Aguardando o término do processo...")
        Console.ReadLine()
    End Sub

    ' Método assíncrono
    Async Sub IniciarProcesso()
        Console.WriteLine("Processo iniciado.")

        ' Aguarda a conclusão de uma tarefa demorada
        Await Task.Delay(3000)

        Console.WriteLine("Processo concluído após 3 segundos.")
    End Sub
End Module
~~~

- Explicação do Exemplo
    - O método IniciarProcesso é declarado com a palavra-chave Async, permitindo o uso de Await em seu corpo.
    - Await Task.Delay(3000):
        - Simula uma operação que demora 3 segundos.
        - Enquanto isso, a execução da thread principal continua, exibindo "Aguardando o término do processo...".
    - Após os 3 segundos, a mensagem "Processo concluído após 3 segundos." é exibida.

## Exemplo com retorno

- Um método que retorna um valor após um atraso:

~~~vb
Imports System.Threading.Tasks

Module Program
    Sub Main()
        Dim resultado = ObterResultadoAsync().Result
        Console.WriteLine($"Resultado: {resultado}")
        Console.ReadLine()
    End Sub

    ' Método assíncrono com retorno
    Async Function ObterResultadoAsync() As Task(Of String)
        Await Task.Delay(2000) ' Simula operação demorada
        Return "Concluído com sucesso!"
    End Function
End Module
~~~

## Task-based Asynchronous Pattern (TAP) em VB.NET

- O Task-based Asynchronous Pattern (TAP) é o modelo moderno para programação assíncrona em .NET, introduzido no .NET Framework 4.5. 
- Ele utiliza as palavras-chave Async e Await para simplificar o uso de tarefas assíncronas (Task).
- O TAP substitui padrões antigos de programação assíncrona, como Asynchronous Programming Model (APM) e Event-based Asynchronous Pattern (EAP), tornando o código mais legível, fácil de manter e menos propenso a erros.
- O TAP é a abordagem moderna para programação assíncrona em VB.NET.
- Ele simplifica operações como esperas não bloqueantes, concorrência e tratamento de exceções.
- O uso correto de Async e Await melhora a performance e escalabilidade dos aplicativos.

#### Criando Métodos Assíncronos com TAP

- A principal forma de usar o TAP em VB.NET é criando métodos que retornam Task ou Task(Of T), utilizando Async e Await.

Exemplo 1: Método Assíncrono Simples

~~~vb
Imports System
Imports System.Threading.Tasks

Module Program
    Sub Main()
        ExecutarTarefa().Wait()
    End Sub

    Async Function ExecutarTarefa() As Task
        Console.WriteLine("Iniciando tarefa...")
        Await Task.Delay(2000) ' Simula uma operação demorada (2 segundos)
        Console.WriteLine("Tarefa concluída!")
    End Function
End Module
~~~

#### Retornando Valores com Task(Of T)

- Se o método precisar retornar um valor, utilizamos Task(Of T).

Exemplo 2: Retornando um Valor Assíncronamente

~~~vb
Imports System
Imports System.Threading.Tasks

Module Program
    Sub Main()
        Dim resultado As Integer = ObterNumeroAleatorio().Result
        Console.WriteLine($"Número gerado: {resultado}")
    End Sub

    Async Function ObterNumeroAleatorio() As Task(Of Integer)
        Await Task.Delay(1000) ' Simula um processamento
        Return New Random().Next(1, 100) ' Retorna um número aleatório
    End Function
End Module
~~~

#### Executando Múltiplas Tarefas Paralelamente

- Podemos rodar várias tarefas ao mesmo tempo usando Task.WhenAll().

Exemplo 3: Executando Várias Tarefas Simultaneamente

~~~vb
Imports System
Imports System.Threading.Tasks

Module Program
    Sub Main()
        Task.WhenAll(Tarefa1(), Tarefa2()).Wait()
        Console.WriteLine("Todas as tarefas foram concluídas!")
    End Sub

    Async Function Tarefa1() As Task
        Console.WriteLine("Iniciando Tarefa 1...")
        Await Task.Delay(3000)
        Console.WriteLine("Tarefa 1 concluída!")
    End Function

    Async Function Tarefa2() As Task
        Console.WriteLine("Iniciando Tarefa 2...")
        Await Task.Delay(2000)
        Console.WriteLine("Tarefa 2 concluída!")
    End Function
End Module
~~~

#### Tratamento de Exceções em TAP

- Como métodos assíncronos rodam em background, devemos capturar exceções dentro de Try...Catch.

Exemplo 4: Lidando com Exceções

~~~vb
Imports System
Imports System.Threading.Tasks

Module Program
    Sub Main()
        Try
            Dim resultado = ExecutarComErro().Result
        Catch ex As AggregateException
            Console.WriteLine("Erro capturado: " & ex.InnerException.Message)
        End Try
    End Sub

    Async Function ExecutarComErro() As Task(Of Integer)
        Await Task.Delay(1000)
        Throw New Exception("Ocorreu um erro na tarefa.")
    End Function
End Module
~~~

#### 

~~~vb

~~~

#### 

~~~vb

~~~
