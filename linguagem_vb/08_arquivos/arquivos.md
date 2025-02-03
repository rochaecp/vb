# Arquivos de Texto

- Em VB.NET, a manipulação de arquivos de texto é realizada de forma simples utilizando classes como `File`, `FileStream`, `StreamReader`, e `StreamWriter`, disponíveis no namespace `System.IO`.
- Essas classes permitem criar, ler, e escrever arquivos com eficiência.

## Criando e Escrevendo em um Arquivo de Texto

- Para criar um arquivo e escrever dados nele, você pode usar a classe `StreamWriter`.

~~~vb
Imports System.IO

Module EscreverArquivo
    Sub Main()
        ' Caminho do arquivo
            ' obs.: se inserir apenas o nome do arquivo, ele será salvo na pasta bin/Debug
        Dim caminho As String = "C:\exemplo.txt" 

        ' Usando o StreamWriter para escrever no arquivo. 
        ' Using: garante que o arquivo seja fechado corretamente após o uso.
        Using escritor As New StreamWriter(caminho)
            ' WriteLine: adiciona uma nova linha no arquivo.
            escritor.WriteLine("Primeira linha do arquivo.")
            escritor.WriteLine("Segunda linha do arquivo.")
            Console.WriteLine("Arquivo criado e texto escrito com sucesso.")
        End Using
    End Sub
End Module
~~~

## Lendo um Arquivo de Texto

~~~vb
Imports System.IO

Module LerArquivo
    Sub Main()
        ' Caminho do arquivo
        Dim caminho As String = "C:\exemplo.txt"

        ' Usando StreamReader para ler o arquivo
        If File.Exists(caminho) Then
            Using leitor As New StreamReader(caminho)
                Dim linha As String

                ' EndOfStream: indica que o final do arquivo foi alcançado
                While (Not leitor.EndOfStream)
                    ' ReadLine: lê o arquivo linha por linha.
                    linha = leitor.ReadLine()
                    Console.WriteLine(linha)
                End While
            End Using
        Else
            Console.WriteLine("Arquivo não encontrado.")
        End If

        Console.ReadKey() ' para nao fechar a janela do console imediatamente

    End Sub
End Module
~~~

## Adicionando Conteúdo a um Arquivo Existente

- Para adicionar texto a um arquivo sem sobrescrever o conteúdo, utilize o modo de append.

~~~vb
Imports System.IO

Module AdicionarTexto
    Sub Main()
        ' Caminho do arquivo
        Dim caminho As String = "C:\exemplo.txt"

        ' Usando StreamWriter em modo append
        ' Parâmetro True no construtor de StreamWriter: ativa o modo de append (adicionar)
        Using escritor As New StreamWriter(caminho, True)
            escritor.WriteLine("Nova linha adicionada ao arquivo.")
            Console.WriteLine("Texto adicionado com sucesso.")
        End Using
    End Sub
End Module
~~~

## Excluindo um Arquivo

~~~vb
Imports System.IO

Module ExcluirArquivo
    Sub Main()
        ' Caminho do arquivo
        Dim caminho As String = "C:\exemplo.txt"

        ' Excluindo o arquivo
        If File.Exists(caminho) Then
            File.Delete(caminho)
            Console.WriteLine("Arquivo excluído com sucesso.")
        Else
            Console.WriteLine("Arquivo não encontrado.")
        End If
    End Sub
End Module
~~~

# Arquivos Binários

- A manipulação de arquivos binários em VB.NET é essencial quando você precisa lidar com dados em um formato mais compacto ou para manipular arquivos que não sejam de texto, como imagens, vídeos, ou outros tipos de dados estruturados.
- No VB.NET, você pode usar as classes `FileStream`, `BinaryReader`, e `BinaryWriter` para ler e gravar arquivos binários.

## Gravando Dados Binários 

- Para gravar dados binários em um arquivo, utilizamos a classe BinaryWriter.

~~~vb
Imports System.IO

Module GravarBinario
    Sub Main()
        ' Caminho do arquivo binário
        Dim caminho As String = "C:\arquivo.bin"

        ' Usando BinaryWriter para gravar dados binários
        Using escritor As New BinaryWriter(File.Open(caminho, FileMode.Create))
            escritor.Write(123)             ' Escreve um número inteiro
            escritor.Write(45.67)           ' Escreve um número de ponto flutuante
            escritor.Write("Texto binário") ' Escreve uma string
            Console.WriteLine("Dados binários gravados com sucesso.")
        End Using
    End Sub
End Module
~~~

## Lendo Dados Binários

- Para ler dados binários de um arquivo, utilizamos a classe BinaryReader.

~~~vb
Imports System.IO

Module LerBinario
    Sub Main()
        ' Caminho do arquivo binário
        Dim caminho As String = "C:\arquivo.bin"

        ' Verifica se o arquivo existe
        If File.Exists(caminho) Then
            ' Usando BinaryReader para ler dados binários
            Using leitor As New BinaryReader(File.Open(caminho, FileMode.Open))
                Dim numeroInteiro As Integer = leitor.ReadInt32()
                Dim numeroFlutuante As Double = leitor.ReadDouble()
                Dim texto As String = leitor.ReadString()

                Console.WriteLine($"Número inteiro: {numeroInteiro}")
                Console.WriteLine($"Número flutuante: {numeroFlutuante}")
                Console.WriteLine($"Texto: {texto}")
            End Using
        Else
            Console.WriteLine("Arquivo não encontrado.")
        End If
    End Sub
End Module
~~~

## Manipulando Fluxos com FileStream

- As classes `BinaryReader` e `BinaryWriter` dependem de um `FileStream`. 
- Você também pode usar o `FileStream` diretamente para manipular arquivos binários de forma mais flexível.

~~~vb
Imports System.IO

Module FluxoBinario
    Sub Main()
        ' Caminho do arquivo binário
        Dim caminho As String = "C:\arquivo_fluxo.bin"

        ' Gravando dados binários com FileStream
        Using fs As New FileStream(caminho, FileMode.Create)
            fs.WriteByte(255) ' Escreve um único byte
            fs.Write(New Byte() {1, 2, 3, 4}, 0, 4) ' Escreve uma matriz de bytes
        End Using

        ' Lendo dados binários com FileStream
        Using fs As New FileStream(caminho, FileMode.Open)
            Dim primeiroByte As Integer = fs.ReadByte() ' Lê um único byte
            Dim buffer(3) As Byte
            fs.Read(buffer, 0, buffer.Length) ' Lê uma matriz de bytes

            Console.WriteLine($"Primeiro byte: {primeiroByte}")
            Console.WriteLine($"Bytes lidos: {String.Join(", ", buffer)}")
        End Using
    End Sub
End Module
~~~