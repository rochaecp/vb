# Visual Basic .NET - História

- Construída a partir do Basic (linguagem popular nos anos 80).
- Visual Basic - Versões:
    - 1.0 (1991) a 6.0 (1998)
- Visual Basic .NET - Versões:    
    - Visual Basic .NET  (VB 7) - bem diferente do VB 6.0, lançado em 2002
    - Visual Basic .NET 2003  (VB 7.1)
    - Visual Basic 2005 (VB 8.0) 
        - A partir do VB 8.0, a Microsoft largou o termo .NET na designação do produto
    - Visual Basic 2005 Express
    - Visual Basic 2008 (VB 9.0)
    - Visual Basic 2010 (VB 10.0)
        - Juntamente com o Visual Basic 2010 obtemos o .NET Framework 4.
    - ...
    - Visual Basic 16 (2019)
    - Visual Basic 16.9 / Visual Studio 2019 Versão 16.9 - https://learn.microsoft.com/pt-br/dotnet/visual-basic/whats-new/#visual-basic-169

# Informações Gerais sobre Projetos

## Assembly

- Um assembly é um bloco fundamental de execução em .NET. Ele pode ser um arquivo executável (.exe) ou uma biblioteca (.dll) que contém código compilado, recursos, e metadados necessários para o .NET executar as aplicações.
- Componentes de um Assembly:
    - Código Compilado: Código em linguagem intermediária (IL) que será executado pelo runtime do .NET.
    - Metadados: Informações sobre tipos, métodos, classes, etc., que são necessárias para o .NET.
    - Manifesto: Contém informações sobre o assembly, como sua versão, dependências e cultura.
    - Recursos: Pode incluir imagens, strings, e outros arquivos usados pelo programa.

## Pasta bin (Binary)

- "Armazena os arquivos finais compilados"
- Descrição: A pasta bin é o local onde o compilador coloca os arquivos binários finais do projeto, como os executáveis (.exe) e bibliotecas (.dll), após a compilação.
- Uso: Contém o código compilado e pronto para execução ou distribuição. Existem subpastas como Debug e Release, que armazenam os arquivos de acordo com o modo de compilação selecionado.
- Conteúdo: Pode incluir os arquivos .exe, .dll, .pdb, e arquivos de configuração, dependendo do tipo do projeto.

## Pasta obj

- "Armazena arquivos temporários e intermediários da compilação."
- Descrição: A pasta obj é usada durante o processo de compilação para armazenar arquivos temporários. É um estágio intermediário antes dos binários serem movidos para bin.
- Uso: Guarda metadados, arquivos de objeto intermediário, e recursos que ajudam o compilador a gerar o output final. Não é necessária para o funcionamento da aplicação e pode ser limpa sem perder o funcionamento do código final.
- Conteúdo: Contém arquivos como .obj (arquivos de objeto) e outras saídas intermediárias da compilação.

## Arquivos com extensão .dll (Dynamic Link Library)

- "São assemblies, contendo o código, metadados, e manifestos necessários para a execução e interação do programa."
- Descrição: Uma DLL é uma biblioteca de código compilado que pode ser reutilizada por várias aplicações. Ela contém código, classes, métodos, e recursos que podem ser acessados por outras aplicações.
- Uso: Facilita a modularização e reutilização de código. Pode ser compartilhada entre diferentes projetos sem duplicar código.
- Assembly: Cada .dll é um assembly, contendo seu próprio código, metadados, e manifestos.

## Arquivos com extensão .exe (Executable)

- Descrição: Um arquivo executável que contém o código da aplicação pronta para ser executada pelo sistema operacional. É o ponto de entrada de programas .NET.
- Uso: Executa a aplicação. Contém o código principal que inicia a execução do programa.
- Assembly: Cada .exe é um assembly, que inclui o código e os recursos necessários para executar a aplicação.

## Arquivos com extensão .pdb (Program Database)

- "Arquivo de depuração, não é um assembly, mas auxilia no desenvolvimento"
- Descrição: Arquivo de banco de dados de programa que contém informações de depuração, como símbolos de depuração, mapas de código-fonte, e pontos de parada.
- Uso: Essencial para o debug; permite que o depurador do IDE associe o código executável às linhas de código-fonte, facilitando a identificação de erros.
- Não é um Assembly: Um .pdb é auxiliar para depuração e não é considerado um assembly.

## Arquivos com extensão .exe.config (Configuration File)

- "Arquivo de configuração da aplicação executável, não é um assembly."
- Descrição: Um arquivo de configuração XML associado ao executável (.exe). Define configurações específicas da aplicação, como strings de conexão, parâmetros de comportamento, e outras opções de configuração.
- Uso: Usado para modificar o comportamento da aplicação sem recompilá-la, ajustando configurações de tempo de execução.
- Não é um Assembly: É um arquivo de suporte para configurar a aplicação, sem código executável.