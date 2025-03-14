# Passo a Passo: Criando um Formulário Simples em VB.NET (Windows Forms)

## 1. Criar um Novo Projeto

- Abra o Visual Studio.
- Clique em Arquivo > Novo > Projeto.
- Selecione Aplicativo Windows Forms (.NET Framework).
- Nomeie o projeto (ex: `MeuPrimeiroForm`) e escolha a versão .NET Framework 4.8.1.
- Clique em OK.

## 2. Projetar o Formulário

- Clique com o botão direito sobre o arquivo Form1.vb e clique em Abrir Com > Visual Basic Form Editor

### Adicionar Controles:

1. Arraste os seguintes controles da Caixa de Ferramentas para o formulário:
   - 1 `Button` (botão)
   - 1 `Label` (rótulo)
   - 1 `TextBox` (caixa de texto)

### Definir Propriedades:

~~~vb
' No código do formulário (Form1.vb):

Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        ' Configurar título do formulário
        Me.Text = "Formulário de Exemplo"
        
        ' Configurar propriedades dos controles
        Button1.Text = "Clique Aqui"
        Label1.Text = "Nome:"
        TextBox1.PlaceholderText = "Digite seu nome"
    End Sub
End Class
~~~

## 3. Implementar Eventos

### Evento Click do Botão:

~~~vb
Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
    If TextBox1.Text.Trim() = "" Then
        MessageBox.Show("Digite um nome!", "Aviso", MessageBoxButtons.OK, MessageBoxIcon.Warning)
    Else
        MessageBox.Show("Olá, " & TextBox1.Text & "!", "Mensagem", MessageBoxButtons.OK, MessageBoxIcon.Information)
    End If
End Sub
~~~

### Evento TextChanged da TextBox:

~~~vb
Private Sub TextBox1_TextChanged(sender As Object, e As EventArgs) Handles TextBox1.TextChanged
    Label1.Text = "Digitando: " & TextBox1.Text
End Sub
~~~

### Evento FormClosing do Formulário:

~~~vb
Private Sub Form1_FormClosing(sender As Object, e As FormClosingEventArgs) Handles MyBase.FormClosing
    Dim resposta As DialogResult = MessageBox.Show("Deseja realmente sair?", "Confirmação", MessageBoxButtons.YesNo)
    If resposta = DialogResult.No Then
        e.Cancel = True
    End If
End Sub
~~~

## 4. Executar o Projeto

- Pressione F5 ou clique em Iniciar Depuração.
- Teste:
    - Digite na caixa de texto.
    - Clique no botão para ver a mensagem.
    - Tente fechar o formulário para testar a confirmação.

## Código Completo (Form1.vb)

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        Me.Text = "Formulário de Exemplo"
        Button1.Text = "Clique Aqui"
        Label1.Text = "Nome:"
        TextBox1.PlaceholderText = "Digite seu nome"
    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        If TextBox1.Text.Trim() = "" Then
            MessageBox.Show("Digite um nome!", "Aviso", MessageBoxButtons.OK, MessageBoxIcon.Warning)
        Else
            MessageBox.Show("Olá, " & TextBox1.Text & "!", "Mensagem", MessageBoxButtons.OK, MessageBoxIcon.Information)
        End If
    End Sub

    Private Sub TextBox1_TextChanged(sender As Object, e As EventArgs) Handles TextBox1.TextChanged
        Label1.Text = "Digitando: " & TextBox1.Text
    End Sub

    Private Sub Form1_FormClosing(sender As Object, e As FormClosingEventArgs) Handles MyBase.FormClosing
        Dim resposta As DialogResult = MessageBox.Show("Deseja realmente sair?", "Confirmação", MessageBoxButtons.YesNo)
        If resposta = DialogResult.No Then
            e.Cancel = True
        End If
    End Sub
End Class
~~~
