# Exercícios Práticos - Strings

## Concatenação de Strings

1. Concatenando Nome e Sobrenome
    - Solicite ao usuário seu nome e sobrenome. Concatene as duas strings e exiba o nome completo.

1. Concatenando com Símbolos
    - Receba uma string do usuário e concatene-a com um símbolo especial (ex: `!`, `#`) no final.

1. Concatenando Números e Strings
    - Solicite um número ao usuário e concatene-o com uma mensagem de texto, exibindo a frase completa no console.

## Interpolação de Strings (a partir do VB 14.0)

1. Interpolação Simples
    - Solicite o nome do usuário e a idade, e use interpolação de strings para exibir uma frase que mostre essas informações.

1. Interpolação com Operações
    - Receba dois números do usuário e exiba o resultado da soma usando interpolação de strings.

1. Interpolando com Variáveis
    - Receba o nome de um produto e seu preço, e exiba a mensagem: "O produto [produto] custa R$ [preço]."

## Comprimento da String (`Length`)

1. Exibindo o Comprimento da String
    - Solicite ao usuário que digite uma palavra e exiba o número de caracteres usando `Length`.

1. Calculando Caracteres em uma Frase
    - Solicite uma frase e mostre quantos caracteres ela contém, excluindo os espaços.

1. Comparação de Comprimentos
    - Receba duas palavras do usuário, compare seus comprimentos e exiba qual delas é a maior.

## Método `ToUpper()`

1. Convertendo para Maiúsculas
    - Solicite ao usuário que digite uma palavra e converta-a para letras maiúsculas usando `ToUpper()`.

1. Comparando Case-Insensitive
    - Receba duas strings, converta ambas para maiúsculas e compare se são iguais, independentemente do case original.

1. Maiúsculas em uma Frase
    - Solicite uma frase ao usuário e converta-a para letras maiúsculas, exibindo o resultado.

## Método `ToLower()`

1. Convertendo para Minúsculas
    - Solicite uma palavra ao usuário e converta-a para minúsculas usando `ToLower()`.

1. Comparando Strings Case-Insensitive
    - Receba duas strings, converta ambas para minúsculas e exiba se são iguais, independentemente do case.

1. Minúsculas em uma Frase
    - Solicite uma frase ao usuário e converta-a para letras minúsculas, exibindo o resultado.

## Método Substrings (`Substring()`)

1. Extraindo Substring de uma Palavra
    - Solicite ao usuário uma palavra e extraia os primeiros três caracteres, exibindo o resultado.

1. Extraindo do Meio
    - Receba uma frase e extraia uma parte do meio dela, exibindo os caracteres entre a 3ª e a 8ª posição.

1. Cortando Sobrenome
    - Solicite o nome completo do usuário e exiba apenas o primeiro nome, usando `Substring()`.

## Método Busca de Substrings (`IndexOf()`)

1. Encontrando Posição de uma Palavra
    - Solicite ao usuário que insira uma frase e uma palavra, e exiba a posição em que a palavra começa na frase.

1. Verificando Existência de Substring
    - Receba uma string e verifique se ela contém uma determinada palavra, retornando a posição ou -1 se não for encontrada.

1. Posição da Primeira Letra
    - Solicite ao usuário uma frase e uma letra. Encontre a posição da primeira ocorrência da letra na frase.

## Método Trim

1. Removendo Espaços Extras
    - Solicite ao usuário que digite um texto com espaços extras no início e no fim, e remova esses espaços com `Trim()`.

1. Trimming com Comparação
    - Receba duas strings, remova os espaços de ambas com `Trim()` e verifique se são iguais.

1. Removendo Espaços de Nomes
    - Solicite o nome completo do usuário, remova os espaços extras ao redor, e exiba o resultado formatado.

## Método `TrimStart()`

1. Removendo Espaços no Início
    - Solicite ao usuário que digite um texto com espaços no início, e remova-os usando `TrimStart()`.

1. Comparando Strings Após `TrimStart()`
    - Receba duas strings, aplique `TrimStart()` e compare se são iguais após a remoção dos espaços iniciais.

1. Exibindo Texto Sem Espaços Iniciais
    - Receba uma frase e aplique `TrimStart()` para remover os espaços do início, exibindo o resultado.

## Método `TrimEnd()`

1. Removendo Espaços no Fim
    - Solicite ao usuário que digite um texto com espaços no fim, e remova-os usando `TrimEnd()`.

1. Comparando Strings Após `TrimEnd()`
    - Receba duas strings, aplique `TrimEnd()` e compare se são iguais após a remoção dos espaços finais.

1. Exibindo Texto Sem Espaços Finais
    - Receba uma frase e aplique `TrimEnd()` para remover os espaços do fim, exibindo o resultado.

## Comparação de Strings

1. Comparando Duas Palavras
    - Solicite duas palavras ao usuário e compare se são iguais, exibindo o resultado.

1. Verificando Se Uma String É Maior
    - Receba duas strings e verifique qual delas é "maior" em termos de ordem alfabética.

1. Comparação Case-Insensitive
    - Compare duas strings ignorando diferenças entre maiúsculas e minúsculas, e exiba se são iguais.

## Função `Equals()`

1. Comparando com `Equals()`
    - Solicite ao usuário duas strings e use `Equals()` para verificar se são iguais, exibindo o resultado.

1. Comparação Case-Insensitive com `Equals()`
    - Solicite duas strings e use `Equals()` com `StringComparison.OrdinalIgnoreCase` para comparar ignorando case.

1. Verificação de Igualdade com `Equals()`
    - Solicite ao usuário um nome e compare se ele é igual a um valor predefinido usando `Equals()`.

## Formatação de Strings

1. Formatação de Valores
    - Solicite ao usuário um valor monetário e formate-o para exibição com duas casas decimais.

1. Formatação de Data
    - Solicite ao usuário uma data e formate-a no formato `dd/MM/yyyy`, exibindo o resultado no console.

1. Formatação de Texto e Números
    - Solicite ao usuário um produto e seu preço, e formate a string para exibir: "O produto [produto] custa R$ [preço]".

## Divisão de Strings (`Split()`)

1. Dividindo uma Frase em Palavras
    - Solicite ao usuário uma frase e divida-a em palavras usando `Split()`, exibindo cada palavra separadamente.

1. Dividindo por Vírgulas
    - Receba uma lista de itens separada por vírgulas, e divida os itens usando `Split()`.

1. Dividindo Nome Completo
    - Solicite o nome completo do usuário e divida-o em nome e sobrenome, exibindo cada um separadamente.

## Junção de Strings (`String.Join()`)

1. Juntando Itens em uma Lista
    - Receba uma lista de itens do usuário, armazene-os em um array e use `String.Join()` para exibi-los como uma única string.

1. Juntando Palavras com Hífen
    - Solicite ao usuário três palavras e junte-as em uma única string separada por hífens.

1. Juntando Nomes
    - Solicite uma lista de nomes e use `String.Join()` para exibi-los separados por vírgulas.

## Substituição de Caracteres (`Replace()`)

1. Substituindo Palavras em uma Frase
    - Solicite uma frase e substitua todas as ocorrências de uma palavra por outra, exibindo o resultado.

1. Substituindo Caracteres Especiais
    - Receba um texto e substitua todos os pontos (`.`) por vírgulas (`,`), exibindo a string modificada.

1. Substituindo Espaços por Underlines
    - Solicite ao usuário que insira uma frase e substitua todos os espaços por underlines (`_`).

## Tratamento de Strings Nulas e Vazio

1. Verificação de String Vazia
    - Solicite uma entrada do usuário e verifique se a string está vazia, exibindo uma mensagem apropriada.

1. Verificação de String Nula
    - Declare uma string nula e use `String.IsNullOrEmpty()` para verificar se ela é nula ou vazia.

1. String Vazia ou com Espaços em Branco
    - Solicite uma string ao usuário e use `String.IsNullOrWhiteSpace()` para verificar se ela contém apenas espaços em branco.

## Escapando Caracteres Especiais

1. Inserindo Aspas Duplas
    - Solicite uma frase ao usuário e insira aspas duplas dentro da frase usando escape (`""`).

1. Exibindo uma Barra Invertida
    - Solicite um caminho de diretório e exiba-o com barras invertidas escapadas (`\\`).

1. Escapando Caracteres em um Texto
    - Receba uma string e insira caracteres de escape, como nova linha (`\n`) e tabulação (`\t`), exibindo o resultado.

## Práticas Comuns de String em Loops

1. Concatenando em Loop
    - Use um loop para concatenar os números de 1 a 5 em uma string, separados por espaços.

1. Construindo uma Frase com `StringBuilder`
    - Use `StringBuilder` para construir uma frase dentro de um loop que itera de 1 a 5, adicionando uma palavra a cada iteração.

1. Concatenando Itens de uma Lista
    - Solicite ao usuário uma lista de palavras e use um loop para concatenar todas as palavras em uma única string, separando por vírgulas.
