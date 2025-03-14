# Controles avançados: `DataGridView`, `TreeView`, `ListView`

- Os controles avançados no Windows Forms permitem exibir e organizar dados de maneira eficiente e interativa. 
- Nesta aula, abordaremos os três principais controles para manipulação de dados estruturados: DataGridView, TreeView e ListView.
- Esses três controles avançados são essenciais para exibir e organizar dados em Windows Forms.
    - Use DataGridView para tabelas e grandes volumes de dados.
    - Use TreeView para dados hierárquicos, como menus e categorias.
    - Use ListView para listas flexíveis de itens com colunas e diferentes modos de exibição.

## DataGridView

- O DataGridView é usado para exibir e manipular tabelas de dados, sendo muito útil para aplicações que lidam com grandes volumes de informação, como registros de banco de dados.
- Principais Propriedades e Métodos do DataGridView
    - ColumnCount: Define o número de colunas.
    - Rows.Add(): Adiciona uma nova linha ao grid.
    - DataSource: Pode ser vinculado a listas, arrays ou tabelas do banco de dados.
    - AutoSizeColumnsMode: Ajusta automaticamente o tamanho das colunas.

#### Exemplo Prático: Exibindo Dados em um DataGridView

~~~vb
Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
    ' Cria uma lista de produtos
    Dim produtos As New List(Of Produto) From {
        New Produto() With {.Id = 1, .Nome = "Notebook", .Preco = 3500.0},
        New Produto() With {.Id = 2, .Nome = "Mouse", .Preco = 50.0},
        New Produto() With {.Id = 3, .Nome = "Teclado", .Preco = 120.0}
    }

    ' Define o DataGridView como fonte de dados
    DataGridView1.DataSource = produtos
End Sub

' Classe Produto para representar os dados
Public Class Produto
    Public Property Id As Integer
    Public Property Nome As String
    Public Property Preco As Double
End Class
~~~

#### Exemplo: Exibir uma lista de produtos em um DataGridView

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' Criando colunas no DataGridView
        DataGridView1.ColumnCount = 3
        DataGridView1.Columns(0).Name = "ID"
        DataGridView1.Columns(1).Name = "Nome"
        DataGridView1.Columns(2).Name = "Preço"

        ' Adicionando dados manualmente
        Dim row1 As String() = {"1", "Notebook", "3500.00"}
        Dim row2 As String() = {"2", "Mouse", "50.00"}
        DataGridView1.Rows.Add(row1)
        DataGridView1.Rows.Add(row2)
    End Sub
End Class
~~~

## TreeView

- O TreeView é um controle que exibe uma estrutura hierárquica de dados, como um menu de navegação ou explorador de arquivos.
- Principais Propriedades e Métodos do TreeView
    - Nodes.Add(): Adiciona um nó principal ou subnó.
    - SelectedNode: Retorna o nó atualmente selecionado.
    - ExpandAll(): Expande todos os nós da árvore.
    - CollapseAll(): Recolhe todos os nós.

#### Exemplo Prático: Criando uma Estrutura Hierárquica

~~~vb
Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
    ' Adiciona nós principais
    Dim nodeRaiz As TreeNode = TreeView1.Nodes.Add("Categorias")
    
    ' Adiciona subnós
    nodeRaiz.Nodes.Add("Eletrônicos")
    nodeRaiz.Nodes.Add("Roupas")
    nodeRaiz.Nodes.Add("Livros")

    ' Expande o nó raiz para mostrar os subnós
    nodeRaiz.Expand()
End Sub
~~~

#### Exemplo: Criar um menu hierárquico de categorias

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' Criando nós principais
        Dim nodeEletronicos As TreeNode = TreeView1.Nodes.Add("Eletrônicos")
        Dim nodeMoveis As TreeNode = TreeView1.Nodes.Add("Móveis")

        ' Adicionando subcategorias
        nodeEletronicos.Nodes.Add("Computadores")
        nodeEletronicos.Nodes.Add("Celulares")
        nodeMoveis.Nodes.Add("Mesas")
        nodeMoveis.Nodes.Add("Cadeiras")
    End Sub
End Class
~~~

## ListView

- O ListView é utilizado para exibir listas de itens com múltiplas colunas e modos de exibição variados, como ícones grandes, detalhes e lista simples.
- Principais Propriedades e Métodos do ListView
    - View: Define o modo de exibição (Details, LargeIcon, SmallIcon, List).
    - Columns.Add(): Adiciona colunas ao ListView (usado no modo Details).
    - Items.Add(): Adiciona itens à lista.
    - SelectedItems: Retorna os itens selecionados.

#### Exemplo: Exibir uma lista de clientes

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' Definir o modo de exibição como detalhes
        ListView1.View = View.Details

        ' Criar colunas
        ListView1.Columns.Add("ID", 50, HorizontalAlignment.Left)
        ListView1.Columns.Add("Nome", 150, HorizontalAlignment.Left)
        ListView1.Columns.Add("Cidade", 100, HorizontalAlignment.Left)

        ' Adicionar itens
        Dim item1 As ListViewItem = New ListViewItem(New String() {"1", "Carlos", "Porto Alegre"})
        Dim item2 As ListViewItem = New ListViewItem(New String() {"2", "Mariana", "São Paulo"})

        ListView1.Items.Add(item1)
        ListView1.Items.Add(item2)
    End Sub
End Class
~~~
