# Ferramentas de Diagnóstico no VB.NET

#### Classe Debug

- A classe Debug é usada para monitorar e diagnosticar o comportamento do programa durante o desenvolvimento.
- Métodos comuns
    - `Debug.WriteLine`: Escreve mensagens no console de depuração (não no terminal).
        - As mensagens são ignoradas em versões de produção (quando o código é compilado em modo Release)
    - `Debug.Assert`: Avalia uma condição e pausa o programa se a condição for falsa.

~~~vb
Imports System.Diagnostics

Module DiagnosticExample
    Sub Main()
        Dim valor As Integer = 10

        ' Escrevendo no console de depuração
        Debug.WriteLine("O programa iniciou.")

        ' Verificando uma condição
        Debug.Assert(valor > 0, "O valor deve ser maior que zero.")

        ' Mensagem de depuração
        Debug.WriteLine("O valor é: " & valor)
    End Sub
End Module
~~~

#### Classe Trace

- A classe Trace funciona de forma semelhante ao Debug, mas pode ser usada tanto em tempo de desenvolvimento quanto em produção, dependendo da configuração.
- Métodos Comuns:
    - `Trace.WriteLine`: Escreve mensagens no rastreamento.
    - `Trace.Listeners`: Permite adicionar listeners personalizados para registrar logs.

> Este código cria um arquivo log.txt com as mensagens de rastreamento.

~~~vb
Imports System.Diagnostics

Module TraceExample
    Sub Main()
        ' Adicionando um listener para gravar em arquivo
        Dim arquivoLog As New TextWriterTraceListener("log.txt")
        Trace.Listeners.Add(arquivoLog)

        ' Mensagens de rastreamento
        Trace.WriteLine("O programa iniciou.")
        Trace.WriteLine("Este é um registro de rastreamento.")

        ' Liberar recursos
        Trace.Flush()
        Trace.Close()
    End Sub
End Module
~~~

# Logging no VB.NET

#### Uso de EventLog

- O EventLog permite gravar eventos no Log de Eventos do Windows, útil para aplicativos que precisam registrar informações críticas.

> O log será visível no Visualizador de Eventos do Windows.

~~~vb
Imports System.Diagnostics

Module EventLogExample
    Sub Main()
        ' Criar ou usar um log de evento personalizado
        If Not EventLog.SourceExists("MeuAppFonte") Then
            EventLog.CreateEventSource("MeuAppFonte", "MeuLog")
        End If

        ' Registrar um evento
        Dim log As New EventLog("MeuLog") With {.Source = "MeuAppFonte"}
        log.WriteEntry("Mensagem de teste no log de eventos.", EventLogEntryType.Information)
    End Sub
End Module
~~~

~~~vb

~~~