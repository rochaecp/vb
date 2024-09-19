## Arrays

- a notação () após o nome da variável indica que ela é um array.

## Caractere '_'

- O _ é uma convenção de VB.NET para dividir linhas longas, mantendo a legibilidade do código e organizando melhor os atributos ou instruções extensas.

## Case sensitive

- VB.NET não é case sensitive (não diferencia maiúsculas de minúsculas). Isso significa que, em VB.NET, os identificadores como nomes de variáveis, classes, métodos, propriedades, etc., são tratados da mesma forma, independentemente de como você usa maiúsculas ou minúsculas.

## Classes (nomenclatura)

- Em VB.NET, não é necessário que a classe tenha o mesmo nome do arquivo que a contém.
- Embora não seja obrigatório, é considerado uma boa prática nomear o arquivo de acordo com o nome da classe principal que ele contém. 
- Um único arquivo pode conter múltiplas classes, módulos, estruturas, ou interfaces. O nome do arquivo não precisa refletir todos os tipos que ele contém.

## Referências

- No VB.NET, objetos são passados por referência por padrão
- Um objeto é uma instância de uma classe, e classes são tipos por referência no .NET.
- Para um tipo de valor (como um Integer ou Boolean), uma cópia é passada por padrão, a menos que seja explicitamente passada por referência usando a palavra-chave ByRef.

## Summary

- A tag ```<summary>``` é usada para criar um resumo descritivo sobre o elemento de código (como um método ou propriedade) ao qual está anexado. É uma convenção de documentação usada amplamente em VB.NET e outras linguagens como C#.
- Quando o desenvolvedor passa o mouse sobre o método ou propriedade no editor de código, esse comentário é exibido, ajudando a fornecer informações contextuais.

~~~vb
''' <summary>
''' Descrição do método
''' </summary>
~~~