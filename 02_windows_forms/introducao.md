# Windows Forms no VB.NET

- Uma aplicação Windows Forms (WinForms) em VB.NET é baseada no paradigma de desenvolvimento de interfaces gráficas (GUI), onde cada elemento da interface é representado por um componente visual (como botões, caixas de texto e labels). 
- O WinForms fornece um modelo baseado em eventos, permitindo que a aplicação responda às ações do usuário.

## Criando um Projeto Windows Forms no Visual Studio

- Para iniciar um projeto Windows Forms no VB.NET:
    - Abra o Visual Studio.
    - Clique em Criar um novo projeto.
    - Escolha Windows Forms App (.NET Framework) e clique em Avançar.
    - Defina um nome para o projeto e escolha um local para salvá-lo.
    - Clique em Criar.
- O Visual Studio criará automaticamente uma estrutura básica contendo:
    - Form1.vb (a interface principal)
    - Program.vb (o ponto de entrada da aplicação)
    - Properties (configurações do projeto)
    - App.config (arquivo de configuração da aplicação)

##  Estrutura Principal de um Formulário Windows Forms

- O formulário (Form) é a base da aplicação, onde serão adicionados os componentes gráficos. 
- O código do formulário geralmente segue esta estrutura:

~~~vb
Public Class Form1
    ' Este evento é disparado quando o formulário é carregado
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        MessageBox.Show("Bem-vindo ao Store Manager!")
    End Sub
End Class
~~~

- Neste exemplo, quando o formulário Form1 for carregado, ele exibirá uma mensagem de boas-vindas.

## Estrutura do Código no Arquivo Program.vb

- O arquivo Program.vb contém o código que inicia a aplicação. 
- Ele define o ponto de entrada do programa e executa o formulário principal:

~~~vb
Module Program
    Sub Main()
        Application.EnableVisualStyles()
        Application.SetCompatibleTextRenderingDefault(False)
        Application.Run(New Form1())
    End Sub
End Module
~~~

- Aqui, Application.Run(New Form1()) define Form1 como o primeiro formulário a ser exibido ao iniciar o programa.

## Ciclo de Vida de um Formulário

- Um formulário no WinForms segue um ciclo de vida baseado em eventos, que inclui:
    - Load: Ocorre quando o formulário é carregado.
    - Activated: Disparado quando o formulário ganha foco.
    - Closing: Ocorre antes do formulário ser fechado.
    - Closed: Ocorre após o fechamento do formulário.

#### Exemplo de um evento Closing

~~~vb
Private Sub Form1_FormClosing(sender As Object, e As FormClosingEventArgs) Handles MyBase.FormClosing
    If MessageBox.Show("Deseja realmente sair?", "Confirmação", MessageBoxButtons.YesNo) = DialogResult.No Then
        e.Cancel = True ' Cancela o fechamento do formulário
    End If
End Sub
~~~

- Este código exibe uma mensagem de confirmação antes de fechar o formulário.

## Adicionando Componentes Visuais ao Formulário

- O Windows Forms permite adicionar diversos componentes como botões, caixas de texto e labels arrastando-os do Toolbox para o formulário.

#### Exemplo de um formulário com um botão (Button)

~~~vb
Public Class Form1
    Private Sub btnCliqueAqui_Click(sender As Object, e As EventArgs) Handles btnCliqueAqui.Click
        MessageBox.Show("Botão clicado!")
    End Sub
End Class
~~~