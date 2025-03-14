# Manipulação de Formulários

- Em aplicações Windows Forms com VB.NET, a interação com o usuário é fundamental, e isso é gerenciado por meio de eventos e manipulação de formulários. 
- Formulários são a base das interfaces gráficas em aplicações Windows Forms. 
- Manipular formulários envolve controlar sua exibição, fechamento e interação com outros formulários.

## Abrindo e Fechando Formulários

Para abrir um novo formulário:

~~~vb
' Cria uma nova instância do Form2 e o exibe
Dim frm As New Form2()
frm.Show()
~~~

- Para abrir o formulário como uma janela modal (que bloqueia a interação com outras janelas até ser fechada):

~~~vb
' Exibe o Form2 como uma janela modal
Dim frm As New Form2()
frm.ShowDialog()
~~~

- Para fechar um formulário:

~~~vb
' Fecha o formulário atual
Me.Close()
~~~

## Formulários MDI (Multiple Document Interface)

- Aplicações MDI permitem que um formulário principal contenha múltiplos formulários filhos. 
- Para configurar um formulário como MDI:

~~~vb
' Define o formulário atual como contêiner MDI
Me.IsMdiContainer = True
~~~

Para adicionar um formulário filho:

~~~vb
' Cria uma nova instância do FormChild e o define como filho do formulário MDI
Dim childForm As New FormChild()
childForm.MdiParent = Me
childForm.Show()
~~~