# Uso de DataReader, DataSet, DataAdapter em VB.NET

- No contexto do ADO.NET, o acesso e manipulação de dados são realizados por meio de diferentes objetos, cada um com finalidades específicas. 
- Resumo:
    - DataReader: Leitura rápida e direta (forward-only), ideal para consultas simples e de alta performance.
    - DataSet: Estrutura desconectada, ótima para trabalhar com dados offline e múltiplas tabelas.
    - DataAdapter: Facilita o carregamento e a atualização de dados entre o banco e o DataSet.
- Cada um tem seu uso ideal dependendo do cenário. 
- Para leitura simples, prefira o DataReader; para manipulação offline de dados complexos, use DataSet com DataAdapter.
- Vamos entender o papel de cada um:

##  DataReader

- O DataReader é um objeto usado para ler dados do banco de forma rápida e eficiente. 
- Ele funciona de maneira forward-only (somente leitura e avanço para frente), ideal para consultas simples e de alta performance.
- Vantagem: Rápido e consome pouca memória.
- Limitação: Apenas leitura e não permite navegar para trás.

#### Exemplo Prático

~~~vb
Imports System.Data.SqlClient

Module Program
    Sub Main()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("SELECT Nome, Idade FROM Pessoas", conexao)

        conexao.Open()
        Dim leitor As SqlDataReader = comando.ExecuteReader()

        While leitor.Read()
            Console.WriteLine("Nome: " & leitor("Nome") & ", Idade: " & leitor("Idade"))
        End While

        leitor.Close()
        conexao.Close()
    End Sub
End Module
~~~

## DataSet

- O DataSet é uma estrutura de dados desconectada do banco, ou seja, ele armazena os dados em memória após a consulta. 
- Ele pode conter múltiplas tabelas, facilitando o trabalho com dados complexos.
- Vantagem: Trabalha offline após carregar os dados, ideal para operações desconectadas.
- Limitação: Consome mais memória em comparação ao DataReader.

#### Exemplo Prático

~~~vb
Imports System.Data
Imports System.Data.SqlClient

Module Program
    Sub Main()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim adaptador As New SqlDataAdapter("SELECT Nome, Idade FROM Pessoas", conexao)
        Dim ds As New DataSet()

        adaptador.Fill(ds, "Pessoas")

        For Each linha As DataRow In ds.Tables("Pessoas").Rows
            Console.WriteLine("Nome: " & linha("Nome") & ", Idade: " & linha("Idade"))
        Next
    End Sub
End Module
~~~

## DataAdapter

- O DataAdapter atua como uma ponte entre o banco de dados e o DataSet, permitindo carregar dados e também atualizar o banco com as alterações feitas no DataSet.
- Vantagem: Gerencia facilmente operações de CRUD em conjunto com o DataSet.
- Limitação: Menos eficiente para grandes volumes de dados em comparação com o DataReader.


#### Exemplo Prático de Inserção

~~~vb
Imports System.Data.SqlClient

Module Program
    Sub Main()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim adaptador As New SqlDataAdapter("SELECT * FROM Pessoas", conexao)
        Dim builder As New SqlCommandBuilder(adaptador)
        Dim ds As New DataSet()

        adaptador.Fill(ds, "Pessoas")

        ' Adicionando um novo registro
        Dim novaLinha As DataRow = ds.Tables("Pessoas").NewRow()
        novaLinha("Nome") = "Carlos"
        novaLinha("Idade") = 30
        ds.Tables("Pessoas").Rows.Add(novaLinha)

        ' Salvando as alterações no banco de dados
        adaptador.Update(ds, "Pessoas")
        Console.WriteLine("Registro inserido com sucesso!")
    End Sub
End Module
~~~