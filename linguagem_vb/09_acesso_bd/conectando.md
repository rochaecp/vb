# Conectando ao Banco de Dados em VB.NET

- O acesso a bancos de dados em VB.NET é feito por meio do ADO.NET, uma tecnologia que permite interagir com bancos relacionais como SQL Server, MySQL e SQLite. 
- Para conectar ao banco, utilizamos a classe SqlConnection (para SQL Server) ou outras classes específicas dependendo do banco de dados escolhido.

#### Passo 1: Importando as Bibliotecas Necessárias

Antes de iniciar a conexão, devemos importar o namespace do ADO.NET no VB.NET:

~~~vb
Imports System.Data.SqlClient
~~~

Esse namespace fornece todas as classes necessárias para manipulação do banco de dados.

#### Passo 2: Criando a String de Conexão

A string de conexão contém informações como o servidor, o nome do banco de dados, usuário e senha. Um exemplo para SQL Server:

~~~vb
Dim connectionString As String = "Server=SEU_SERVIDOR;Database=SEU_BANCO;User Id=USUARIO;Password=SENHA;"
~~~

Se o banco for local e autenticação integrada, pode ser algo assim:

~~~vb
Dim connectionString As String = "Server=.\SQLEXPRESS;Database=SEU_BANCO;Trusted_Connection=True;"
~~~

#### Passo 3: Criando e Abrindo a Conexão

Para estabelecer a conexão, usamos a classe SqlConnection e o método .Open():

~~~vb
Dim conexao As New SqlConnection(connectionString)

Try
    conexao.Open()
    Console.WriteLine("Conexão bem-sucedida!")
Catch ex As Exception
    Console.WriteLine("Erro ao conectar: " & ex.Message)
Finally
    conexao.Close()
    Console.WriteLine("Conexão fechada.")
End Try
~~~

Aqui, utilizamos um bloco Try...Catch...Finally para tratar erros e garantir que a conexão seja fechada corretamente, evitando vazamentos de recursos.

#### Passo 4: Testando a Conexão

Após rodar o código acima, devemos verificar a saída no console:
- Se a conexão foi bem-sucedida, a mensagem "Conexão bem-sucedida!" será exibida.
- Se houver erro, ele será capturado e exibido na tela.
