# Mapeamento objeto-relacional (ORM) com Entity Framework

- O Mapeamento Objeto-Relacional (ORM) é uma técnica que facilita a interação entre aplicações orientadas a objetos e bancos de dados relacionais, permitindo que desenvolvedores manipulem dados de forma mais intuitiva e produtiva. 
- No contexto do VB.NET, o Entity Framework (EF) é a principal ferramenta ORM utilizada para esse fim.
- O Entity Framework é uma biblioteca da Microsoft que permite aos desenvolvedores do .NET trabalhar com bancos de dados relacionais usando objetos do domínio específico, eliminando a necessidade de grande parte do código de acesso a dados que, tradicionalmente, seria escrito manualmente. 
- Com o EF, é possível mapear classes do .NET para tabelas do banco de dados, facilitando operações como inserção, atualização, deleção e consulta de dados.
- Principais abordagens do Entity Framework:
    - Database-First: O banco de dados já existe, e as classes de entidade são geradas com base na estrutura desse banco.
    - Model-First: O desenvolvedor cria um modelo conceitual, e o EF gera o banco de dados correspondente a esse modelo.
    - Code-First: As classes são definidas primeiro no código, e o EF cria o banco de dados com base nessas classes.

## Exemplo Prático: Implementando o Entity Framework no VB.NET

- A seguir, apresentamos um exemplo prático de como utilizar o Entity Framework no VB.NET seguindo a abordagem Code-First.
- Configuração do Projeto:
    - Crie um novo projeto do tipo "Console Application" no Visual Studio.
    - Adicione o Entity Framework ao projeto via NuGet Package Manager:
    - Clique com o botão direito no projeto e selecione "Manage NuGet Packages".
    - Procure por "EntityFramework" e instale o pacote.

#### Definição das Entidades:

- Crie uma classe que represente uma tabela no banco de dados. Por exemplo, uma tabela de produtos:

~~~vb
Public Class Produto
    Public Property ProdutoId As Integer
    Public Property Nome As String
    Public Property Preco As Decimal
End Class
~~~

#### Configuração do Contexto de Dados:

- Crie uma classe que herda de DbContext e representa a sessão com o banco de dados, permitindo a consulta e salvamento de dados:

~~~vb
Imports System.Data.Entity

Public Class MeuContexto
    Inherits DbContext

    Public Property Produtos As DbSet(Of Produto)
End Class
~~~

#### Configuração da String de Conexão:

- No arquivo App.config do projeto, adicione a string de conexão para o banco de dados:

~~~vb
<configuration>
    <connectionStrings>
        <add name="MeuContexto"
             connectionString="Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=MinhaBaseDeDados;Integrated Security=True"
             providerName="System.Data.SqlClient" />
    </connectionStrings>
</configuration>
~~~

#### Operações CRUD (Create, Read, Update, Delete):

- No método Main do módulo principal, implemente operações básicas de inserção, consulta, atualização e deleção de dados:

~~~vb
Module Module1
    Sub Main()
        Using contexto As New MeuContexto()
            ' Inserir um novo produto
            Dim novoProduto As New Produto With {
                .Nome = "Caneta",
                .Preco = 1.99D
            }
            contexto.Produtos.Add(novoProduto)
            contexto.SaveChanges()

            ' Consultar produtos
            Dim produtos = From p In contexto.Produtos
                           Select p

            For Each produto In produtos
                Console.WriteLine($"ID: {produto.ProdutoId}, Nome: {produto.Nome}, Preço: {produto.Preco}")
            Next

            ' Atualizar um produto
            Dim primeiroProduto = contexto.Produtos.FirstOrDefault()
            If primeiroProduto IsNot Nothing Then
                primeiroProduto.Preco = 2.49D
                contexto.SaveChanges()
            End If

            ' Deletar um produto
            Dim produtoParaDeletar = contexto.Produtos.FirstOrDefault()
            If produtoParaDeletar IsNot Nothing Then
                contexto.Produtos.Remove(produtoParaDeletar)
                contexto.SaveChanges()
            End If
        End Using
    End Sub
End Module
~~~

#### Considerações Finais:

- O Entity Framework simplifica significativamente o desenvolvimento de aplicações que interagem com bancos de dados, permitindo que os desenvolvedores trabalhem em um nível mais alto de abstração. 
- No entanto, é essencial entender como o EF funciona internamente para otimizar o desempenho e garantir a eficiência das operações de banco de dados. 
- Além disso, práticas como a utilização de migrações facilitam a evolução do esquema do banco de dados conforme o desenvolvimento da aplicação avança.
- Para aprofundar seu conhecimento sobre o Entity Framework e o mapeamento objeto-relacional no VB.NET, você pode consultar a documentação oficial da Microsoft e tutoriais especializados disponíveis online.