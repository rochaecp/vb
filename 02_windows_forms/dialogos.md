# Trabalhando com Diálogos no Windows Forms (VB.NET)

- No desenvolvimento de aplicações Windows Forms em VB.NET, os diálogos são usados para interagir com o usuário, permitindo ações como abrir arquivos, salvar documentos, escolher cores e exibir mensagens.
- Tipos de Diálogos em Windows Forms
    - MessageBox – Exibe mensagens para o usuário.
    - OpenFileDialog – Permite abrir arquivos do sistema.
    - SaveFileDialog – Permite salvar arquivos.
    - FolderBrowserDialog – Permite selecionar uma pasta.
    - ColorDialog – Permite escolher uma cor.
    - FontDialog – Permite escolher uma fonte de texto.
- Os diálogos no VB.NET são fundamentais para interações com o usuário. 
- Usando MessageBox, OpenFileDialog, SaveFileDialog, FolderBrowserDialog, ColorDialog e FontDialog, podemos criar uma interface mais amigável e funcional. 

## Exibindo Mensagens com MessageBox

- O MessageBox é usado para exibir mensagens e coletar respostas do usuário.

#### Exemplo - Mensagem Simples

- "Mensagem" → Título da janela
- MessageBoxButtons.OK → Apenas um botão OK
- MessageBoxIcon.Information → Ícone de informação

~~~vb
MessageBox.Show("Bem-vindo ao sistema!", "Mensagem", MessageBoxButtons.OK, MessageBoxIcon.Information)
~~~


#### Exemplo - Perguntar ao Usuário

- Retorna DialogResult.Yes ou DialogResult.No com base na escolha do usuário.
- Application.Exit() fecha a aplicação se o usuário confirmar.

~~~vb
Dim resposta As DialogResult
resposta = MessageBox.Show("Deseja sair do programa?", "Confirmação", MessageBoxButtons.YesNo, MessageBoxIcon.Question)

If resposta = DialogResult.Yes Then
    Application.Exit()
End If
~~~

## Selecionando Arquivos com OpenFileDialog

- Permite que o usuário escolha um arquivo para abrir.

#### Exemplo - Abrir um Arquivo

- Filter define os tipos de arquivos aceitos.
- Se o usuário selecionar um arquivo, FileName retorna o caminho completo.

~~~vb
Dim abrirArquivo As New OpenFileDialog()
abrirArquivo.Filter = "Arquivos de Texto|*.txt|Todos os Arquivos|*.*"

If abrirArquivo.ShowDialog() = DialogResult.OK Then
    MessageBox.Show("Arquivo selecionado: " & abrirArquivo.FileName)
End If
~~~

## Salvando Arquivos com SaveFileDialog

- Permite escolher um local e nome para salvar um arquivo.

#### Exemplo - Salvar um Arquivo

- Cria um arquivo de texto e escreve conteúdo nele.
- Garante que o usuário escolheu um local válido antes de salvar.

~~~vb
Dim salvarArquivo As New SaveFileDialog()
salvarArquivo.Filter = "Arquivos de Texto|*.txt"

If salvarArquivo.ShowDialog() = DialogResult.OK Then
    IO.File.WriteAllText(salvarArquivo.FileName, "Conteúdo salvo!")
    MessageBox.Show("Arquivo salvo com sucesso!")
End If
~~~

## Escolhendo uma Pasta com FolderBrowserDialog

- Permite ao usuário selecionar uma pasta do sistema.

#### Exemplo - Escolher uma Pasta

- SelectedPath retorna o caminho da pasta escolhida.

~~~vb
Dim selecionarPasta As New FolderBrowserDialog()

If selecionarPasta.ShowDialog() = DialogResult.OK Then
    MessageBox.Show("Pasta selecionada: " & selecionarPasta.SelectedPath)
End If
~~~

## Escolhendo Cores com ColorDialog

- Permite ao usuário selecionar uma cor.

#### Exemplo - Escolher uma Cor

- ColorDialog.Color retorna a cor escolhida.
- O exemplo altera a cor de fundo do formulário.

~~~vb
Dim corDialog As New ColorDialog()

If corDialog.ShowDialog() = DialogResult.OK Then
    Me.BackColor = corDialog.Color ' Muda a cor de fundo do formulário
End If
~~~

## Escolhendo uma Fonte com FontDialog

- Permite selecionar um tipo de fonte e tamanho.

#### Exemplo - Escolher uma Fonte

- FontDialog.Font retorna a fonte escolhida.

~~~vb
Dim fonteDialog As New FontDialog()

If fonteDialog.ShowDialog() = DialogResult.OK Then
    Label1.Font = fonteDialog.Font ' Aplica a fonte escolhida a um Label
End If
~~~