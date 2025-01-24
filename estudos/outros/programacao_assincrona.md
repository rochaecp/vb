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

