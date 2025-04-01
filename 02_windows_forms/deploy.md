# Deploy de Aplicações Windows

- Preparar uma aplicação para distribuição envolve transformar o código fonte em um formato que possa ser facilmente instalado e executado por usuários finais em diferentes máquinas. 
- Para isso, é necessário configurar e compilar o projeto de forma que ele possa ser facilmente distribuído. 
- Vamos ver como realizar isso em VB.NET.

## Configuração do Projeto para Deploy:

- Antes de compilar a aplicação para distribuição, é necessário garantir que o projeto esteja configurado corretamente. 
- Isso envolve definir as configurações de build e incluir todos os arquivos necessários para a execução da aplicação.
- Ajustes de Configuração: 
    - No Visual Studio, acesse as propriedades do projeto. 
    - Em "Build", verifique a configuração (por exemplo, "Release") e o destino de saída. 
    - É importante que a configuração esteja em "Release" para otimizar o desempenho e garantir que a aplicação esteja pronta para produção.
- Incluir Arquivos de Dependência: 
    - Certifique-se de que todos os arquivos necessários para a execução, como bibliotecas externas ou arquivos de recursos, estejam incluídos no projeto. 
    - Você pode fazer isso em "Referências" dentro do Visual Studio, onde será possível verificar se todas as dependências estão corretas.
- Gerando o Executável:
    - Quando o projeto estiver pronto para ser distribuído, a próxima etapa é gerar o executável (.exe) que será distribuído. 
    - Isso é feito no Visual Studio, onde você pode selecionar a opção de "Compilar" o projeto.
    - Para compilar o projeto, clique com o botão direito sobre o projeto no "Solution Explorer" e selecione "Build". 
    - O Visual Studio vai gerar os arquivos do projeto na pasta de saída configurada (geralmente a pasta "bin\Release").
    - O arquivo .exe gerado pode ser distribuído diretamente, mas é importante garantir que ele funcione em outras máquinas. 
    - Isso pode envolver a inclusão de dependências como .NET Framework ou versões específicas de bibliotecas.
- Verificação de Configurações de Compatibilidade:
    - Certifique-se de que a aplicação funcionará corretamente em diferentes sistemas operacionais ou versões. 
    - O Visual Studio permite configurar diferentes alvos de versão do .NET Framework, o que garante que a aplicação seja compatível com as versões que você deseja suportar.
- Compatibilidade de Sistema Operacional: 
    - Se a aplicação precisar ser executada em várias versões do Windows, pode ser necessário verificar a compatibilidade com versões mais antigas do sistema operacional (por exemplo, Windows 7, Windows 10, etc.).
- Exemplo Prático:
    - Imagine que você está criando uma aplicação simples de cálculo de área de um retângulo. 
    - Após concluir o desenvolvimento, você deseja preparar a aplicação para distribuição.

Abra o Visual Studio e compile a aplicação selecionando a configuração "Release".
Verifique se todas as dependências, como bibliotecas adicionais ou recursos de imagem, estão incluídas no projeto.
Após a compilação, vá até a pasta bin\Release e encontre o arquivo executável (.exe). Este será o arquivo que você distribuirá para seus usuários.
Com isso, a aplicação estará pronta para ser distribuída e instalada nos sistemas dos usuários finais.

## Preparando a aplicação para distribuição

- Antes de distribuir sua aplicação Windows Forms em VB.NET, é essencial garantir que ela esteja otimizada, livre de dados de debug e pronta para execução em outros ambientes. 
- Veja os passos práticos:

#### 1. Compilação em Modo Release

- Objetivo: Gerar um executável otimizado e sem informações de debug.
- Como fazer:
    - No Visual Studio, altere a configuração de Debug para Release na barra de ferramentas.
    - Clique em Build > Build Solution (ou Ctrl + Shift + B).

~~~vb
' Verifique o modo de compilação no código (opcional):
If Debugger.IsAttached Then
    MessageBox.Show("Modo Debug ativo!")
Else
    MessageBox.Show("Modo Release ativo!")
End If
~~~

#### 2. Gerenciamento de Dependências

- Objetivo: Garantir que todas as DLLs e recursos externos estejam incluídos.
- Passos:
    - Verifique referências no Solution Explorer (ex.: Newtonsoft.Json.dll).
    - Para bibliotecas externas, defina a propriedade Copy Local como True.

#### 3. Configurações de Arquivo App.config

- Objetivo: Centralizar configurações como strings de conexão.

~~~xml
<!-- App.config -->
<configuration>
    <connectionStrings>
        <add name="ConexaoBD" 
             connectionString="Server=.;Database=MeuBD;Integrated Security=True"/>
    </connectionStrings>
</configuration>
~~~

~~~vb
' Acesse a configuração no código:
Dim conexao As String = ConfigurationManager.ConnectionStrings("ConexaoBD").ConnectionString
~~~

#### 4. Inclusão de Recursos Externos

- Objetivo: Empacotar arquivos necessários (imagens, templates, etc.).
- Como fazer:
    - Adicione os arquivos ao projeto.
    - Defina a propriedade Build Action como Content e Copy to Output Directory como Copy always.

#### 5. Versionamento da Aplicação

- Objetivo: Facilitar atualizações e suporte.
- Defina a versão:
    - Abra as propriedades do projeto (Project > Properties).
    - Na aba Application, clique em Assembly Information e defina Version.

~~~vb
' Recupere a versão programaticamente:
Dim versao As Version = My.Application.Info.Version
MessageBox.Show($"Versão: {versao.ToString()}")
~~~

#### 6. Teste em Ambiente Limpo

- Objetivo: Simular a experiência do usuário final.
- Passo:
    - Copie a pasta bin\Release para outro computador (sem o Visual Studio instalado) e execute o aplicativo.
    - Pronto! Sua aplicação está preparada para a criação de instaladores (próximo tópico).
- Dica final: 
    - Use ferramentas como ILMerge para mesclar DLLs em um único executável, se necessário.

