# Construtores

- Um construtor é um método especial usado para inicializar objetos de uma classe. 
- Ele é chamado automaticamente quando um objeto é criado. 
- Em VB.NET, existem dois tipos principais de construtores: padrão e parametrizado.
- Resumo
    - Construtor Padrão: Não aceita parâmetros e é usado para inicializações simples ou com valores padrão.
    - Construtor Parametrizado: Aceita argumentos para inicializar os atributos da classe com valores específicos no momento da criação do objeto.
    - Combinação: Utilizar ambos oferece flexibilidade para criar objetos com ou sem parâmetros.

## Construtor Padrão

- O construtor padrão não aceita parâmetros e geralmente é usado para inicializar membros da classe com valores padrão.

~~~vb
Public Class Produto
    Public Nome As String
    Public Preco As Double

    ' Construtor padrão
    Public Sub New()
        Nome = "Desconhecido"
        Preco = 0.0
    End Sub
End Class

' Uso do construtor padrão
Dim produto As New Produto()
Console.WriteLine($"Nome: {produto.Nome}, Preço: {produto.Preco}")
~~~

## Construtor Parametrizado

- O construtor parametrizado permite passar valores ao criar um objeto, possibilitando inicializações personalizadas.

~~~vb
Public Class Produto
    Public Nome As String
    Public Preco As Double

    ' Construtor parametrizado
    Public Sub New(nomeProduto As String, precoProduto As Double)
        Nome = nomeProduto
        Preco = precoProduto
    End Sub
End Class

' Uso do construtor parametrizado
Dim produto As New Produto("Notebook", 2500.0)
Console.WriteLine($"Nome: {produto.Nome}, Preço: {produto.Preco}")
~~~

## Combinação de Construtores

- Você pode definir ambos os tipos de construtores na mesma classe, permitindo mais flexibilidade.

~~~vb
Public Class Produto
    Public Nome As String
    Public Preco As Double

    ' Construtor padrão
    Public Sub New()
        Nome = "Desconhecido"
        Preco = 0.0
    End Sub

    ' Construtor parametrizado
    Public Sub New(nomeProduto As String, precoProduto As Double)
        Nome = nomeProduto
        Preco = precoProduto
    End Sub
End Class

' Usando ambos os construtores
Dim produto1 As New Produto() ' Construtor padrão
Dim produto2 As New Produto("Smartphone", 1200.0) ' Construtor parametrizado

Console.WriteLine($"Produto 1: Nome = {produto1.Nome}, Preço = {produto1.Preco}")
Console.WriteLine($"Produto 2: Nome = {produto2.Nome}, Preço = {produto2.Preco}")
~~~

## Construtor Estático

- No VB.NET, um construtor estático é um método especial que é executado automaticamente uma única vez antes de qualquer membro estático (ou compartilhado) da classe ser acessado. 
- Ele é definido usando a palavra-chave `Shared` no construtor.
- Características do Construtor Estático:
    - Executado apenas uma vez: O construtor estático é chamado automaticamente pelo .NET runtime antes do primeiro uso da classe.
    - Sem parâmetros: Ele não pode aceitar argumentos.
    - Inicialização de membros compartilhados: O construtor estático é usado principalmente para inicializar membros compartilhados da classe.
- Quando usar um Construtor Estático?
    - Quando você precisa realizar uma inicialização de configuração estática ou carregar recursos necessários para a classe antes que ela seja usada pela primeira vez.
    - Exemplo: Configuração de constantes, conexões estáticas ou cache de dados.


#### Exemplo

- `ValorCompartilhado` é um campo estático da classe Exemplo. Ele é compartilhado entre todas as instâncias da classe.
- O `Shared Sub New()` é executado automaticamente antes que qualquer membro compartilhado da classe seja acessado pela primeira vez.
- Quando acessamos Exemplo.ValorCompartilhado no Main(), o construtor estático é executado primeiro, e então o valor inicializado (42) é exibido.

~~~vb
Public Class Exemplo
    ' Membro compartilhado (estático)
    Public Shared ValorCompartilhado As Integer

    ' Construtor estático
    Shared Sub New()
        Console.WriteLine("Executando o construtor estático...")
        ' Inicializa o membro compartilhado
        ValorCompartilhado = 42
    End Sub
End Class

Module Program
    Sub Main()
        ' O construtor estático será chamado automaticamente antes do acesso ao membro estático
        Console.WriteLine("Valor inicial de ValorCompartilhado: " & Exemplo.ValorCompartilhado)

        ' Acessando novamente o membro estático
        Exemplo.ValorCompartilhado = 100
        Console.WriteLine("Novo valor de ValorCompartilhado: " & Exemplo.ValorCompartilhado)
    End Sub
End Module
~~~

## Finalizadores e Gerenciamento de Memória

- No VB.NET, finalizadores são métodos especiais usados para liberar recursos quando um objeto é destruído pelo Garbage Collector (GC). 
- Embora o Garbage Collector seja responsável pela maior parte do gerenciamento de memória, em alguns casos, como quando recursos não gerenciados (ex.: arquivos, conexões de banco de dados) são usados, é necessário implementar um finalizador para garantir que esses recursos sejam liberados corretamente.
- Um finalizador em VB.NET é definido usando o método especial Finalize. 
- Ele é automaticamente chamado pelo Garbage Collector antes que o objeto seja removido da memória.

~~~vb
' Sintaxe de um Finalizador
Protected Overrides Sub Finalize()
    Try
        ' Código para liberar recursos
        Console.WriteLine("Finalizador chamado.")
    Finally
        ' Chamar o finalizador da classe base
        MyBase.Finalize()
    End Try
End Sub
~~~

#### Quando usar finalizadores?

- Recursos não gerenciados: Use finalizadores para liberar memória, fechar arquivos ou desconectar conexões de banco de dados que não sejam gerenciados pelo runtime do .NET.
- Evite excessos: Finalizadores devem ser usados apenas quando estritamente necessário, pois adicionam sobrecarga ao Garbage Collector.

#### Gerenciamento de Recursos com IDisposable

- Em vez de depender apenas do finalizador, é recomendado usar a interface IDisposable para implementar a limpeza manual de recursos. Isso permite que o desenvolvedor controle quando os recursos são liberados.

~~~vb
Public Class Recurso
    Implements IDisposable

    Private recursoNaoGerenciado As IntPtr ' Exemplo de recurso não gerenciado
    Private disposed As Boolean = False

    ' Método para liberar recursos
    Protected Overridable Sub Dispose(disposing As Boolean)
        If Not disposed Then
            If disposing Then
                ' Libera recursos gerenciados
                Console.WriteLine("Liberando recursos gerenciados.")
            End If
            ' Libera recursos não gerenciados
            Console.WriteLine("Liberando recursos não gerenciados.")
            disposed = True
        End If
    End Sub

    ' Implementação de IDisposable
    Public Sub Dispose() Implements IDisposable.Dispose
        Dispose(True)
        GC.SuppressFinalize(Me) ' Evita que o finalizador seja chamado
    End Sub

    ' Finalizador
    Protected Overrides Sub Finalize()
        Dispose(False)
        MyBase.Finalize()
    End Sub
End Class
~~~

#### 

~~~vb
Module Program
    Sub Main()
        ' Criando e usando o objeto
        Dim recurso As New Recurso()
        recurso.Dispose() ' Liberação manual

        ' Finalizador será chamado se Dispose não for chamado
        Dim outroRecurso As New Recurso()
    End Sub
End Module
~~~

#### Boas Práticas

- Prefira o padrão Dispose: Ele é mais eficiente e dá controle ao desenvolvedor.
- Minimize o uso de finalizadores: Deixe o Garbage Collector lidar com a maioria dos recursos gerenciados.
- Garanta sempre a liberação de recursos não gerenciados: Isso evita vazamentos de memória e outros problemas.
- Com essas técnicas, você gerencia eficientemente a memória e evita problemas de desempenho em suas aplicações VB.NET.

~~~vb

~~~

~~~vb

~~~

~~~vb

~~~

~~~vb

~~~

~~~vb

~~~