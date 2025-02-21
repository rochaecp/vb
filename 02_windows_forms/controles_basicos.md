# Controles básicos em Windows Forms: `Button`, `TextBox`, `Label`

- Os controles básicos do Windows Forms são essenciais para a criação de interfaces interativas em aplicações VB.NET. 
- Entre os mais comuns estão:
    - Button (`Button`): Um botão que pode ser clicado para executar uma ação.
    - TextBox (`TextBox`): Uma caixa de entrada onde o usuário pode digitar texto.
    - Label (`Label`): Um rótulo usado para exibir texto estático na interface.
- No Visual Studio, os controles podem ser adicionados ao formulário de duas formas:
    - Arrastando os componentes da *Toolbox* para o formulário.
    - Criando os controles via código no evento `Form_Load`.

## Exemplo prático

- Criaremos um formulário com um `TextBox`, um `Button` e um `Label`. 
- O usuário digita um texto e, ao clicar no botão, o conteúdo é exibido no `Label`.

##### Passo 1: Criando os controles no designer

- Abra o *Form1* no Visual Studio.
- Arraste um `TextBox`, um `Button` e um `Label` da Toolbox para o formulário.
- Altere as propriedades:
   - `TextBox`: `Name = txtEntrada`
   - `Button`: `Name = btnExibir`, `Text = "Exibir"`
   - `Label`: `Name = lblResultado`, `Text = ""`

##### Passo 2: Criando o evento do botão

- Clique duas vezes no botão para gerar o evento `Click` e adicione este código:

~~~vb
Public Class Form1
    Private Sub btnExibir_Click(sender As Object, e As EventArgs) Handles btnExibir.Click
        ' Exibe o texto digitado no Label
        lblResultado.Text = "Você digitou: " & txtEntrada.Text
    End Sub
End Class
~~~

- Explicação
    - O método btnExibir_Click é chamado quando o botão é clicado.
    - O Text do Label (lblResultado) recebe o valor digitado no TextBox (txtEntrada).
    - O & concatena a string "Você digitou: " com o texto do TextBox.
