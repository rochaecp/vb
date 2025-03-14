# Menus

- Os menus são componentes essenciais em aplicações Windows Forms, permitindo ao usuário acessar funcionalidades organizadas em categorias. 
- Em VB.NET, utilizamos o controle `MenuStrip` para criar menus no formulário.
- O controle MenuStrip facilita a criação de menus interativos no VB.NET. 
- Podemos adicionar atalhos de teclado, ícones e eventos personalizados, tornando o menu mais funcional e intuitivo.

## Criando um Menu no Windows Forms

- Para adicionar um menu em um Windows Forms, siga estes passos:
    1. Abra o Visual Studio e crie um novo projeto Windows Forms
    1. Arraste o controle MenuStrip para o formulário (Form1)
    1. Adicione os itens do menu clicando no controle MenuStrip e editando os textos
    1. Crie eventos para cada item do menu

## Exemplo Prático: Criando um Menu de Arquivo

- O exemplo abaixo cria um menu com as opções "Arquivo" → "Abrir", "Salvar" e "Sair".    

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' Criando o MenuStrip
        Dim menuStrip As New MenuStrip()

        ' Criando o menu "Arquivo"
        Dim menuArquivo As New ToolStripMenuItem("Arquivo")

        ' Criando os submenus
        Dim menuAbrir As New ToolStripMenuItem("Abrir")
        Dim menuSalvar As New ToolStripMenuItem("Salvar")
        Dim menuSair As New ToolStripMenuItem("Sair")

        ' Adicionando os submenus ao menu "Arquivo"
        menuArquivo.DropDownItems.Add(menuAbrir)
        menuArquivo.DropDownItems.Add(menuSalvar)
        menuArquivo.DropDownItems.Add(New ToolStripSeparator()) ' Linha separadora
        menuArquivo.DropDownItems.Add(menuSair)

        ' Adicionando eventos aos itens do menu
        AddHandler menuAbrir.Click, AddressOf AbrirArquivo
        AddHandler menuSalvar.Click, AddressOf SalvarArquivo
        AddHandler menuSair.Click, AddressOf FecharAplicacao

        ' Adicionando o menu "Arquivo" ao MenuStrip
        menuStrip.Items.Add(menuArquivo)

        ' Adicionando o MenuStrip ao formulário
        Controls.Add(menuStrip)
        MainMenuStrip = menuStrip
    End Sub

    ' Métodos para tratar os cliques nos itens do menu
    Private Sub AbrirArquivo(sender As Object, e As EventArgs)
        MessageBox.Show("Abrir Arquivo clicado!")
    End Sub

    Private Sub SalvarArquivo(sender As Object, e As EventArgs)
        MessageBox.Show("Salvar Arquivo clicado!")
    End Sub

    Private Sub FecharAplicacao(sender As Object, e As EventArgs)
        Application.Exit()
    End Sub
End Class
~~~

#### Explicação do Código

1. Criamos um MenuStrip dinamicamente e adicionamos ao formulário.
1. Criamos um menu principal chamado "Arquivo".
1. Adicionamos os submenus "Abrir", "Salvar" e "Sair".
1. Associamos eventos (AddHandler) para capturar cliques e executar ações.
1. Quando o usuário clica em "Sair", o aplicativo fecha (Application.Exit()).
