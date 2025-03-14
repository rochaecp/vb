# Eventos

- Em aplicações Windows Forms, eventos são ações disparadas por interações do usuário (cliques, digitação) ou pelo sistema (carregamento de formulário). 
- A manipulação desses eventos permite criar aplicações interativas. 

## Associando Eventos a Controles

- Todo controle (botão, caixa de texto) possui eventos embutidos. 
- Para usá-los, você pode:
    - Usar a palavra-chave Handles na declaração do método.
    - Utilizar AddHandler para vincular eventos dinamicamente.

#### Exemplo: Botão com evento Click usando Handles

~~~vb
Private Sub btnExemplo_Click(sender As Object, e As EventArgs) Handles btnExemplo.Click
    MessageBox.Show("Botão clicado!")
End Sub
~~~

#### Exemplo: Evento TextChanged em uma TextBox

~~~vb
Private Sub txtNome_TextChanged(sender As Object, e As EventArgs) Handles txtNome.TextChanged
    lblMensagem.Text = "Digitado: " & txtNome.Text
End Sub
~~~

## Eventos Comuns de Formulário

- Load: Executado quando o formulário é carregado.
- FormClosing: Disparado antes do formulário fechar.
- Activated: Quando o formulário ganha foco.

#### Exemplo: Inicialização no evento Load

~~~vb
Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
    Me.Text = "Formulário Carregado"
    txtData.Text = DateTime.Now.ToString()
End Sub
~~~

#### Exemplo: Validar fechamento do formulário

~~~vb
Private Sub Form1_FormClosing(sender As Object, e As FormClosingEventArgs) Handles MyBase.FormClosing
    Dim resposta As DialogResult = MessageBox.Show("Deseja realmente sair?", "Confirmação", MessageBoxButtons.YesNo)
    
    If resposta = DialogResult.No Then
        e.Cancel = True ' Impede o fechamento
    End If
End Sub
~~~

## Manipulação Dinâmica de Eventos com AddHandler

- Útil para vincular eventos em tempo de execução (ex.: controles criados dinamicamente).

#### Exemplo: Criar botão e associar evento Click

~~~vb
Dim btnDinamico As New Button()
btnDinamico.Text = "Clique-me"
btnDinamico.Location = New Point(50, 50)

' Associa o evento Click
AddHandler btnDinamico.Click, AddressOf MetodoClique

Me.Controls.Add(btnDinamico)

' Método que será chamado
Private Sub MetodoClique(sender As Object, e As EventArgs)
    MessageBox.Show("Botão dinâmico clicado!")
End Sub
~~~

#### Exemplo completo: gerando botão dinâmicamente

~~~vb
Public Class Form1

    Private Sub Form_Load(Sender As Object, e As EventArgs) Handles MyBase.Load
        Me.Text = "Meu Formulário"
    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        Dim btnDinamico As New Button()
        btnDinamico.Text = "Clique-me (botão gerado dinamicamente)"
        btnDinamico.Location = New Point(50, 50)

        ' Associa o evento Click
        AddHandler btnDinamico.Click, AddressOf MetodoClique

        Me.Controls.Add(btnDinamico)

    End Sub
    ' Método que será chamado
    Private Sub MetodoClique(sender As Object, e As EventArgs)
        MessageBox.Show("Botão dinâmico clicado!")
    End Sub

End Class
~~~

## Passando Dados Entre Formulários

- Para comunicação entre formulários, use propriedades ou construtores.

#### Exemplo: Abrir segundo formulário e passar dados

~~~vb
' No Form1:
Private Sub btnAbrirForm2_Click(sender As Object, e As EventArgs) Handles btnAbrirForm2.Click
    Dim form2 As New Form2()
    form2.Mensagem = txtMensagem.Text ' Define uma propriedade pública no Form2
    form2.ShowDialog()
End Sub

' No Form2:
Public Property Mensagem As String

Private Sub Form2_Load(sender As Object, e As EventArgs) Handles MyBase.Load
    lblTexto.Text = Mensagem ' Exibe a mensagem recebida
End Sub
~~~

## Acessando Controles de Outro Formulário

- Evite expor controles diretamente. 
- Use métodos ou propriedades públicas para interagir.

#### Exemplo: Atualizar dados no Form1 a partir do Form2

~~~vb
' No Form2:
Public Sub AtualizarLabel(texto As String)
    Form1.lblStatus.Text = texto ' Supondo que Form1 é a instância principal
End Sub

' Chamada no Form2:
AtualizarLabel("Dados atualizados!")
~~~

## Eventos Personalizados

- Você pode criar eventos customizados em classes ou formulários.

#### Exemplo: Definindo um evento personalizado

~~~vb
' Declaração do evento em uma classe
Public Event TarefaConcluida As EventHandler(Of String)

' Método que dispara o evento
Private Sub FinalizarTarefa()
    RaiseEvent TarefaConcluida(Me, "Tarefa concluída com sucesso!")
End Sub

' Assinando o evento em outro formulário
AddHandler minhaClasse.TarefaConcluida, AddressOf TratarConclusao

' Método de tratamento
Private Sub TratarConclusao(sender As Object, mensagem As String)
    MessageBox.Show(mensagem)
End Sub
~~~

## Declarando e Manipulando Eventos

- Para responder a eventos, você precisa associar procedimentos (subs) a esses eventos. 
- Isso pode ser feito de duas maneiras principais: utilizando a cláusula Handles ou o método AddHandler.

#### Usando a Cláusula Handles

- A maneira mais comum e direta é declarar o manipulador de eventos com a cláusula Handles. 
- Por exemplo, para manipular o evento Click de um botão:

~~~vb
Public Class Form1
    ' Este método será executado quando o botão for clicado
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        MessageBox.Show("Botão clicado!")
    End Sub
End Class
~~~

- Nesse exemplo, o método Button1_Click é automaticamente associado ao evento Click do Button1 devido à cláusula Handles Button1.Click.

#### Usando AddHandler e RemoveHandler

- Para uma associação mais dinâmica, especialmente útil quando os controles são criados em tempo de execução, utiliza-se AddHandler:

~~~vb
Public Class Form1
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        Dim Button2 As New Button()
        Button2.Text = "Clique Aqui"
        Button2.Location = New Point(50, 50)
        Me.Controls.Add(Button2)
        ' Associa o evento Click do Button2 ao manipulador Button2_Click
        AddHandler Button2.Click, AddressOf Button2_Click
    End Sub

    ' Manipulador do evento Click do Button2
    Private Sub Button2_Click(sender As Object, e As EventArgs)
        MessageBox.Show("Button2 foi clicado!")
    End Sub
End Class
~~~

- Aqui, AddHandler associa o evento Click do Button2 ao método Button2_Click. Para remover essa associação, utiliza-se RemoveHandler:

~~~vb
' Remove a associação do evento Click do Button2
RemoveHandler Button2.Click, AddressOf Button2_Click
~~~