# Stored Procedures e Funções em VB.NET com ADO.NET

- Stored Procedures (Procedimentos Armazenados):
    - São blocos de código SQL armazenados no banco de dados. 
    - Eles realizam operações como inserção, atualização, exclusão e consultas de forma otimizada.
- Funções: 
    - Também armazenadas no banco de dados, mas retornam um valor específico. 
    - São usadas para cálculos ou manipulação de dados em consultas SQL.
- Vantagens de Usar Stored Procedures e Funções
    - Melhor desempenho, pois o código SQL é pré-compilado.
    - Maior segurança, limitando o acesso direto às tabelas.
    - Facilidade de manutenção, permitindo centralizar a lógica no banco.
- Diferenças Principais:
    - Stored Procedures: 
        - Executam operações complexas, podem alterar dados e não retornam valores diretamente (usam OUTPUT ou resultados de consulta).
    - Funções: 
        - Sempre retornam um valor e são usadas principalmente em consultas (SELECT).
- Com esses exemplos, fica mais claro como integrar procedimentos armazenados e funções em aplicações VB.NET usando ADO.NET.    


## Exemplo - Stored Procedure   

#### Stored Procedure no SQL Server

~~~sql
CREATE PROCEDURE InserirPessoa
    @Nome NVARCHAR(50),
    @Idade INT
AS
BEGIN
    INSERT INTO Pessoas (Nome, Idade) VALUES (@Nome, @Idade)
END
~~~

#### Chamada da Stored Procedure em VB.NET

~~~vb
Imports System.Data.SqlClient

Module Program
    Sub Main()
        Dim conexao As New SqlConnection("Data Source=(localdb)\local;Initial Catalog=TestDB;Integrated Security=True")
        Dim comando As New SqlCommand("InserirPessoa", conexao)
        comando.CommandType = CommandType.StoredProcedure

        ' Adicionando parâmetros
        comando.Parameters.AddWithValue("@Nome", "João da Silva")
        comando.Parameters.AddWithValue("@Idade", 30)

        Try
            conexao.Open()
            comando.ExecuteNonQuery()
            Console.WriteLine("Pessoa inserida com sucesso!")
        Catch ex As Exception
            Console.WriteLine("Erro: " & ex.Message)
        Finally
            conexao.Close()
        End Try
    End Sub
End Module
~~~

## Exemplo - Função

#### Função no SQL Server

~~~vb
CREATE FUNCTION CalcularIdade(@AnoNascimento INT)
RETURNS INT
AS
BEGIN
    RETURN YEAR(GETDATE()) - @AnoNascimento
END
~~~

#### Chamada da Função em VB.NET

~~~vb
Dim comando As New SqlCommand("SELECT dbo.CalcularIdade(1990)", conexao)

Try
    conexao.Open()
    Dim idade As Integer = Convert.ToInt32(comando.ExecuteScalar())
    Console.WriteLine("Idade calculada: " & idade)
Finally
    conexao.Close()
End Try
~~~
