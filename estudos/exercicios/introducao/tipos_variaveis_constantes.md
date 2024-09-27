## Exercícios Práticos: Tipos de Dados

#### Byte

1. **Armazenando um Valor Byte**
    - Declare uma variável do tipo `Byte` e atribua-lhe o valor máximo (255). Exiba o valor no console.
1. **Operações com Byte**
    - Declare duas variáveis `Byte`, some os valores e exiba o resultado no console.

#### SByte

1. **Armazenando um Valor SByte**
    - Declare uma variável do tipo `SByte` e atribua-lhe o valor mínimo (-128). Exiba o valor no console.
1. **Operações com SByte**
    - Declare duas variáveis `SByte`, subtraia uma da outra e exiba o resultado no console.

#### Short

1. **Armazenando um Valor Short**
    - Declare uma variável `Short` e atribua o valor 30.000. Exiba o valor no console.
1. **Operações com Short**
    - Declare duas variáveis `Short`, multiplique os valores e exiba o resultado no console.

#### UShort

1. **Armazenando um Valor UShort**
    - Declare uma variável `UShort` e atribua o valor 65.535. Exiba o valor no console.
1. **Operações com UShort**
    - Declare duas variáveis `UShort`, some os valores e exiba o resultado.

#### Integer

1. **Atribuição e Exibição de Integer**
    - Declare uma variável `Integer` com valor 1.000 e exiba-a no console.
1. **Operações com Integer**
    - Declare duas variáveis `Integer`, divida uma pela outra e exiba o quociente.

#### UInteger

1. **Atribuição de UInteger**
    - Declare uma variável `UInteger` e atribua-lhe o valor máximo (4.294.967.295). Exiba o valor.
1. **Operações com UInteger**
    - Declare duas variáveis `UInteger`, subtraia uma da outra e exiba o resultado no console.

#### Long

1. **Atribuição de Long**
    - Declare uma variável `Long` com valor 2.147.483.648. Exiba o valor no console.
1. **Operações com Long**
    - Declare duas variáveis `Long`, multiplique os valores e exiba o resultado no console.

#### ULong

1. **Atribuição de ULong**
    - Declare uma variável `ULong` com o valor máximo (18.446.744.073.709.551.615) e exiba o valor.
1. **Operações com ULong**
    - Declare duas variáveis `ULong`, divida uma pela outra e exiba o resultado.

#### Single

1. **Atribuição de Single**
    - Declare uma variável `Single` com valor 3.14. Exiba o valor no console.
1. **Operações com Single**
    - Declare duas variáveis `Single`, some os valores e exiba o resultado no console.

#### Double

1. **Atribuição de Double**
    - Declare uma variável `Double` com valor 10.5. Exiba o valor no console.
1. **Operações com Double**
    - Declare duas variáveis `Double`, multiplique os valores e exiba o resultado no console.

#### Decimal

1. **Atribuição de Decimal**
    - Declare uma variável `Decimal` com valor 1.000,75. Exiba o valor no console.
1. **Operações com Decimal**
    - Declare duas variáveis `Decimal`, divida uma pela outra e exiba o resultado no console.

#### String

1. **Atribuição de String**
    - Declare uma variável `String` com o valor "Olá, Mundo!" e exiba o valor.
1. **Concatenação de Strings**
    - Declare duas variáveis `String`, concatene-as e exiba o resultado.

#### Boolean

1. **Atribuição de Boolean**
    - Declare uma variável `Boolean` com valor `True`. Exiba o valor no console.
1. **Operações com Boolean**
    - Declare duas variáveis booleanas, combine-as com `And` e `Or`, e exiba os resultados.

#### Date

1. **Atribuição de Data**
    - Declare uma variável `Date` e atribua a data de nascimento de uma pessoa. Exiba o valor.
1. **Operações com Data**
    - Declare duas variáveis `Date`, calcule a diferença de dias entre elas e exiba o resultado.

#### Char

1. **Atribuição de Char**
    - Declare uma variável `Char` com o valor "A". Exiba o valor no console.
1. **Operações com Char**
    - Declare duas variáveis `Char`, concatene-as e exiba o resultado.

#### Object

1. **Armazenando em Object**
    - Declare uma variável `Object` e atribua-lhe um valor inteiro. Exiba o valor.
1. **Usando Object para Diversos Tipos**
    - Declare uma variável `Object`, armazene um valor string e, em seguida, um valor inteiro. Exiba os valores.

## Exercícios Práticos: Operadores para Tipos

#### Operador `TypeOf`

1. **Verificação de Tipo com `TypeOf`**
    - Declare uma variável `Object` que armazena uma string. Use `TypeOf` para verificar se é uma string e exiba a mensagem correspondente.

1. **Verificando Tipo de Número com `TypeOf`**
    - Declare uma variável `Object` que armazena um valor inteiro. Verifique se é do tipo `Integer` usando `TypeOf`.

1. **Uso de `TypeOf` com Estrutura `Select Case`**
    - Declare uma variável do tipo `Object`. Use `Select Case` junto com `TypeOf` para verificar se o valor é `Integer`, `String` ou outro tipo, e exiba a mensagem correspondente.

## Exercícios Práticos: Funções para Tipos

#### Função `GetType`

1. **Usando `GetType` com Inteiros**
    - Declare uma variável `Integer` e use `GetType` para exibir o tipo da variável no console.

1. **Verificando o Tipo de Uma String com `GetType`**
    - Declare uma variável `String` e use `GetType` para exibir o tipo no console.

1. **Verificando Tipo em Tempo de Execução**
    - Declare uma variável do tipo `Object` que inicialmente armazena um valor inteiro. Use `GetType` para exibir o tipo. Em seguida, altere o valor para uma string e verifique o tipo novamente.

## Exercícios Práticos: Constantes

#### Constantes

1. **Definindo e Usando Constantes**
    - Declare uma constante chamada `PI` do tipo `Double` com o valor `3.14159`. Em seguida, declare uma variável `raio` do tipo `Double` e calcule a área de um círculo (fórmula: `Área = PI * raio * raio`). Exiba o resultado no console.

1. **Constante para Taxa de Juros**
    - Declare uma constante `TAXA_JUROS` do tipo `Decimal` com o valor `0.05`. Em seguida, declare uma variável `principal` do tipo `Decimal` com valor `1000`, calcule os juros simples (fórmula: `Juros = principal * TAXA_JUROS`) e exiba o valor dos juros no console.

1. **Usando Constantes para Conversão de Unidades**
    - Declare uma constante `METROS_PARA_CM` do tipo `Integer` com o valor `100`. Em seguida, declare uma variável `alturaMetros` do tipo `Double`, atribua um valor a ela e converta essa altura para centímetros (fórmula: `alturaCm = alturaMetros * METROS_PARA_CM`). Exiba o valor convertido no console.

## Exercícios Práticos Diversos 

#### Tipos de Dados, Variáveis e Constantes

1. Declarando Variáveis de Diferentes Tipos
    - Declare variáveis para armazenar um nome, idade, altura e valor de salário, e imprima-os no console.

1. Atribuindo Valores a Variáveis
    - Atribua valores a uma variável de idade, nome, altura e salário, e mostre-os no console.

1. Usando Constantes
    - Declare uma constante para armazenar o valor de Pi e outro para a taxa de juros. Mostre-os no console.

1. Operações com Variáveis Inteiras
    - Declare duas variáveis do tipo `Integer`, some seus valores e exiba o resultado.

1. Operações com Números Decimais
    - Declare duas variáveis `Double` para armazenar valores monetários, realize a soma e exiba o resultado.

1. Manipulando Strings
    - Declare uma variável `String` para armazenar seu nome completo, concatene com uma saudação e exiba no console.

1. Verificando Valores Booleanos
    - Declare uma variável booleana para verificar se uma pessoa é maior de idade (idade >= 18) e exiba `True` ou `False`.

1. Inferência de Tipo
    - Declare uma variável sem especificar o tipo, atribua um valor inteiro e exiba o tipo inferido pelo compilador.

1. Operações com Variáveis `Char`
    - Declare uma variável `Char` para armazenar a primeira letra do seu nome e exiba-a no console.

1. Armazenando Dados em um Objeto
    - Declare uma variável do tipo `Object`, armazene uma `String` e exiba o tipo e valor no console.

1. Comparando Tipos de Dados
    - Declare duas variáveis de diferentes tipos (`Integer` e `Double`), compare seus valores e exiba o maior.

1. Criando e Usando Constantes
    - Crie uma constante para armazenar o valor de gravidade (9.81) e use-a para calcular o peso de um objeto.

1. Usando Variáveis de Ponto Flutuante
    - Declare uma variável `Single` e outra `Double`, realize operações matemáticas e exiba o resultado no console.

1. Trabalhando com Tipos Implícitos
    - Use a inferência de tipo para declarar uma variável, atribua um valor `Double` e exiba o tipo inferido.

1. Operações Matemáticas com `Decimal`
    - Declare duas variáveis do tipo `Decimal` para armazenar valores monetários, faça operações de multiplicação e exiba o total.
