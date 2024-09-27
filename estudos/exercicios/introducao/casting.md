## Exercícios Práticos: Conversão Implícita

1. **Conversão Implícita de Integer para Long**
    - Declare uma variável `Integer`, atribua-lhe um valor, e faça a conversão implícita para `Long`. Exiba os valores antes e depois da conversão no console.

1. **Conversão Implícita de Single para Double**
    - Declare uma variável `Single` com um valor decimal, e faça a conversão implícita para `Double`. Exiba o resultado no console.

1. **Conversão Implícita de Short para Integer**
    - Declare uma variável `Short`, atribua-lhe um valor, e faça a conversão implícita para `Integer`. Exiba os valores antes e depois da conversão no console.

1. **Conversão Implícita de Byte para Short**
    - Declare uma variável `Byte` com valor máximo permitido e faça a conversão implícita para `Short`. Exiba os valores no console.

1. **Conversão Implícita de Decimal para Double**
    - Declare uma variável `Decimal` com valor decimal e faça a conversão implícita para `Double`. Exiba o resultado no console.

## Exercícios Práticos: Conversão Explícita - Funções de Conversão

#### CByte()

1. **Convertendo `Integer` para `Byte`**
    - Declare um número inteiro e converta-o para `Byte` usando `CByte()`. Exiba o valor resultante no console.

1. **Convertendo Limites de `Byte`**
    - Receba um número como `Integer`, verifique se está dentro do intervalo de `Byte` (0 a 255), e faça a conversão usando `CByte()`. Exiba o resultado.

#### CShort()

1. **Convertendo `Integer` para `Short`**
    - Declare um número inteiro e converta-o para `Short` usando `CShort()`. Exiba o valor no console.

1. **Verificando Limites de `Short`**
    - Receba um valor como `Integer`, verifique se está dentro do intervalo de `Short` (-32.768 a 32.767), e faça a conversão usando `CShort()`. Exiba o resultado.

#### CUShort()

1. **Convertendo `Integer` para `UShort`**
    - Declare um número inteiro positivo e converta-o para `UShort` usando `CUShort()`. Exiba o valor no console.

1. **Verificando Limites de `UShort`**
    - Receba um valor como `Integer`, verifique se está dentro do intervalo de `UShort` (0 a 65.535), e faça a conversão usando `CUShort()`. Exiba o resultado.

#### CInt()

1. **Casting de `String` para `Integer`**
    - Receba uma entrada do usuário como texto, converta-a para `Integer` e exiba o resultado multiplicado por 2.

1. **Convertendo `String` para `Integer`**
    - Receba um número digitado pelo usuário como texto, converta-o para `Integer` e exiba o valor multiplicado por 10.

1. Casting de Tipos de Dados
    - Receba uma entrada do usuário como texto, converta-a para `Integer` e exiba o resultado da multiplicação por 2.

1. Convertendo `String` para `Integer`
    - Receba um número digitado pelo usuário como texto, converta-o para `Integer` e exiba o valor multiplicado por 10.   

#### CUInt()

1. **Convertendo `Long` para `UInteger`**
    - Declare um número `Long` e converta-o para `UInteger` usando `CUInt()`. Exiba o valor resultante.

1. **Limites de `UInteger`**
    - Verifique se um número `Long` está dentro do intervalo de `UInteger` e faça a conversão para `UInteger`. Exiba o resultado.

#### CLng()

1. **Convertendo `Integer` para `Long`**
    - Declare um número inteiro e converta-o para `Long` usando `CLng()`. Exiba o valor no console.

1. **Limites de `Long`**
    - Receba um número como `Integer`, verifique se está dentro do intervalo de `Long`, e faça a conversão usando `CLng()`. Exiba o resultado.

#### CULng()

1. **Convertendo `Long` para `ULong`**
    - Declare um número `Long` positivo e converta-o para `ULong` usando `CULng()`. Exiba o valor no console.

1. **Verificando Limites de `ULong`**
    - Receba um valor `Long`, verifique se está dentro do intervalo de `ULong`, e faça a conversão usando `CULng()`. Exiba o resultado.

#### CSng()

1. **Convertendo `Double` para `Single`**
    - Declare um número `Double` e converta-o para `Single` usando `CSng()`. Exiba o valor resultante.

1. **Operações com `Single`**
    - Receba um valor `Double`, converta para `Single` usando `CSng()` e multiplique por 2. Exiba o resultado.

#### CDbl()

1. **Convertendo `Single` para `Double`**
    - Declare um número `Single` e converta-o para `Double` usando `CDbl()`. Exiba o valor resultante.

1. **Operações com `Double`**
    - Receba um valor `Single`, converta para `Double` usando `CDbl()` e divida por 2. Exiba o resultado.

#### CDec()

1. **Convertendo `Double` para `Decimal`**
    - Declare um número `Double` e converta-o para `Decimal` usando `CDec()`. Exiba o valor resultante.

1. **Operações com `Decimal`**
    - Receba um valor `Double`, converta para `Decimal` usando `CDec()` e multiplique por 10. Exiba o resultado.

#### CChar()

1. **Convertendo `String` para `Char`**
    - Declare uma string e converta o primeiro caractere para `Char` usando `CChar()`. Exiba o valor no console.

1. **Verificando Converção de `String` para `Char`**
    - Receba um texto como `String` e verifique se a conversão para `Char` é válida usando `CChar()`. Exiba o caractere no console.

#### CStr()

1. **Convertendo `Integer` para `String`**
    - Declare um número inteiro e converta-o para `String` usando `CStr()`. Exiba o valor no console.

1. **Concatenação com `String`**
    - Receba um número `Integer`, converta-o para `String` usando `CStr()`, e concatene com outro texto. Exiba o resultado.

#### CDate()

1. **Convertendo `String` para `Date`**
    - Declare uma data em formato `String` e converta-a para `Date` usando `CDate()`. Exiba o valor no console.

1. **Verificando Conversão de Data**
    - Receba uma data em formato `String`, converta para `Date` usando `CDate()` e exiba no console.

#### CObj()

1. **Convertendo `Integer` para `Object`**
    - Declare um número `Integer` e converta-o para `Object` usando `CObj()`. Exiba o valor no console.

1. **Armazenando Diferentes Tipos em `Object`**
    - Declare um número `Integer`, converta para `Object`, depois armazene uma `String` no mesmo objeto. Exiba os valores.

#### CBool()

1. **Convertendo `Integer` para `Boolean`**
    - Receba um número inteiro e converta-o para `Boolean` usando `CBool()`. Exiba o valor no console (1 = `True`, 0 = `False`).

1. **Validando `Boolean` com `Integer`**
    - Receba um número `Integer`, converta para `Boolean` usando `CBool()` e exiba o resultado da operação lógica.

## Exercícios Práticos: Conversão Explícita - Método DirectCast()

1. **Casting de `Object` para `String`**
    - Declare uma variável do tipo `Object` contendo uma `String` e use `DirectCast()` para convertê-la de volta para `String`. Exiba o valor no console.

1. **Casting de `Object` para `Integer`**
    - Declare uma variável do tipo `Object` contendo um valor `Integer` e use `DirectCast()` para convertê-lo de volta para `Integer`. Exiba o valor no console.

1. **Casting com `DirectCast()` para Conversão de Formulários**
    - Crie um formulário Windows Forms e use `DirectCast()` para converter um objeto `Control` genérico para um tipo específico, como `Button`. Altere o texto do botão e exiba no formulário.

1. **Casting de `Object` para Classe Personalizada**
    - Declare uma classe personalizada e uma variável do tipo `Object` que armazena uma instância dessa classe. Use `DirectCast()` para convertê-la de volta para a classe personalizada e exiba as propriedades no console.

1. **Usando `DirectCast()` para Converter Componentes de Interface**
    - Em uma aplicação Windows Forms, use `DirectCast()` para converter um componente de interface como `Label` ou `TextBox` de um objeto `Control` genérico. Altere as propriedades do componente convertido e exiba a modificação na interface.

## Exercícios Práticos: Conversão Explícita - Método TryCast()

1. **Casting de `Object` para `String` com `TryCast()`**
    - Declare uma variável do tipo `Object` contendo uma `String` e use `TryCast()` para tentar convertê-la para `String`. Exiba o valor no console se a conversão for bem-sucedida, ou uma mensagem de erro se falhar.

1. **Casting de `Object` para `Integer` com Verificação**
    - Declare uma variável do tipo `Object` contendo um valor não numérico. Use `TryCast()` para tentar convertê-la para `Integer`. Verifique se a conversão foi bem-sucedida e exiba uma mensagem correspondente no console.

1. **Casting de Controle Genérico para `Button` em Windows Forms**
    - Em uma aplicação Windows Forms, use `TryCast()` para tentar converter um objeto `Control` genérico para `Button`. Se a conversão for bem-sucedida, altere o texto do botão. Exiba uma mensagem caso a conversão falhe.

1. **Casting de `Object` para Classe Personalizada com `TryCast()`**
    - Declare uma classe personalizada e uma variável do tipo `Object` que armazena uma instância de outra classe. Use `TryCast()` para tentar converter o objeto para a classe personalizada e exiba uma mensagem de sucesso ou falha no console.

1. **Casting de Componente de Interface com `TryCast()`**
    - Em um formulário Windows Forms, use `TryCast()` para tentar converter um componente de interface como `TextBox` a partir de um objeto `Control` genérico. Se a conversão for bem-sucedida, altere o texto do `TextBox` e exiba a mudança na interface.


## Exercícios Práticos: Conversão Explícita - Método TryParse()

1. **Convertendo String para Integer com `TryParse()`**
    - Receba uma entrada do usuário como `String` e use `Integer.TryParse()` para tentar convertê-la para `Integer`. Se a conversão for bem-sucedida, exiba o valor multiplicado por 2; caso contrário, exiba uma mensagem de erro.

1. **Verificando Conversão de String para Double**
    - Receba uma entrada do usuário como `String` e use `Double.TryParse()` para tentar convertê-la para `Double`. Exiba o valor com 2 casas decimais se a conversão for bem-sucedida, ou uma mensagem informando o erro de conversão.

1. **Validando Conversão de String para Data com `TryParse()`**
    - Receba uma data como `String` do usuário e use `DateTime.TryParse()` para tentar convertê-la para um valor de data válido. Se a conversão for bem-sucedida, exiba a data formatada; caso contrário, informe o erro de conversão.

1. **Convertendo String para Boolean com `TryParse()`**
    - Receba uma entrada do usuário como `String` ("true" ou "false") e use `Boolean.TryParse()` para tentar convertê-la para `Boolean`. Exiba o resultado da conversão ou uma mensagem de erro.

1. **Verificação de Conversão de String para Decimal com `TryParse()`**
    - Receba um valor monetário como `String` e use `Decimal.TryParse()` para tentar convertê-lo para `Decimal`. Se a conversão for bem-sucedida, exiba o valor formatado como moeda; caso contrário, exiba uma mensagem de erro.

