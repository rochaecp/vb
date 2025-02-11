# Executando comandos SQL (`SELECT`, `INSERT`, `UPDATE`, `DELETE`)

- No VB.NET, para interagir com bancos de dados, utilizamos o ADO.NET, que permite executar comandos SQL para consultar, inserir, atualizar e excluir dados.
- Boas Práticas
    - Sempre usar parâmetros para proteger contra injeção de SQL.
    - Fechar a conexão com o banco de dados usando Finally para garantir o fechamento mesmo em caso de erros.
    - Tratar exceções com Try...Catch para identificar problemas durante a execução dos comandos.

## Configurando o Ambiente

- Antes de começar, você precisa:
    - Ter um banco de dados configurado (como SQL Server).
    - Adicionar a referência ao System.Data.SqlClient para conectar ao banco.

## Criando o banco de dados e as tabelas

~~~sql
-- Cria o BD
CREATE DATABASE TestDB;

-- Cria uma tabela
CREATE TABLE Pessoas (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    Nome NVARCHAR(100),
    Idade INT
);

-- Insere dados na tabela
INSERT INTO Pessoas (Nome, Idade) VALUES ('João Silva', 30);
INSERT INTO Pessoas (Nome, Idade) VALUES ('Maria Oliveira', 25);
INSERT INTO Pessoas (Nome, Idade) VALUES ('Carlos Souza', 40);
INSERT INTO Pessoas (Nome, Idade) VALUES ('Ana Pereira', 35);
INSERT INTO Pessoas (Nome, Idade) VALUES ('Lucas Almeida', 28);
~~~

## Executando o Comando SELECT (Consulta de Dados)

- O SELECT é usado para buscar informações no banco de dados.

#### Exemplo: Consultando Dados de uma Tabela    

- Exemplo em .NET Framework 4.8.1

~~~vb
Imports System.Data.SqlClient

Module Module1

    Sub Main()
        Dim cmd As New SqlCommand()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("SELECT Nome, Idade FROM Pessoas", conexao)

        Try
            conexao.Open()
            Dim leitor As SqlDataReader = comando.ExecuteReader()

            While leitor.Read()
                Console.WriteLine("Nome: " & leitor("Nome") & ", Idade: " & leitor("Idade"))
            End While

            leitor.Close()
        Finally
            conexao.Close()
        End Try

        Console.ReadKey()

    End Sub

End Module
~~~

- Explicação
    - SqlConnection cria a conexão com o banco.
    - SqlCommand define o comando SQL a ser executado.
    - ExecuteReader() retorna um SqlDataReader para ler os dados.

#### Executando o Comando INSERT (Inserção de Dados)

- Exemplo em .NET Framework 4.8.1

~~~vb
Imports System.Data.SqlClient

Module Module1

    Sub Main()
        Dim cmd As New SqlCommand()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("INSERT INTO Pessoas (Nome, Idade) VALUES (@Nome, @Idade)", conexao)

        comando.Parameters.AddWithValue("@Nome", "Joana")
        comando.Parameters.AddWithValue("@Idade", 40)

        Try
            conexao.Open()
            comando.ExecuteNonQuery()
            Console.WriteLine("Registro inserido com sucesso!")
        Finally
            conexao.Close()
        End Try

        Console.ReadKey()

    End Sub

End Module
~~~

- Explicação
    - @Nome e @Idade são parâmetros para evitar injeção de SQL.
    - ExecuteNonQuery() executa comandos que não retornam dados, apenas afetam o banco.

#### Executando o Comando UPDATE (Atualização de Dados)

- Exemplo em .NET Framework 4.8.1

~~~vb
Imports System.Data.SqlClient

Module Module1

    Sub Main()
        Dim cmd As New SqlCommand()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("UPDATE Pessoas SET Idade = @Idade WHERE Nome = @Nome", conexao)

        comando.Parameters.AddWithValue("@Nome", "João Silva")
        comando.Parameters.AddWithValue("@Idade", 35)

        Try
            conexao.Open()
            comando.ExecuteNonQuery()
            Console.WriteLine("Registro atualizado com sucesso!")
        Finally
            conexao.Close()
        End Try

    End Sub

End Module
~~~

- Explicação
    - O comando altera a idade de "João" para 35.
    - O WHERE é essencial para limitar quais registros serão atualizados.

#### Executando o Comando DELETE (Exclusão de Dados)

- Exemplo em .NET Framework 4.8.1

~~~vb
Imports System.Data.SqlClient

Module Module1

    Sub Main()
        Dim cmd As New SqlCommand()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("DELETE FROM Pessoas WHERE Nome = @Nome", conexao)

        comando.Parameters.AddWithValue("@Nome", "Joana")

        Try
            conexao.Open()
            comando.ExecuteNonQuery()
            Console.WriteLine("Registro excluído com sucesso!")
        Finally
            conexao.Close()
        End Try

    End Sub

End Module
~~~

- Explicação
    - O comando exclui o registro onde o nome é "João".
    - Sempre use o WHERE para evitar apagar todos os registros da tabela acidentalmente.
