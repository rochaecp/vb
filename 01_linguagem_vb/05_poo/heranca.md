## Herança

- A herança é um dos pilares da Programação Orientada a Objetos (POO) e permite que uma classe derive de outra, herdando suas características e comportamentos. 
- Em VB.NET, a herança facilita o reuso de código e a criação de hierarquias de classes que compartilham funcionalidades comuns.
- Quando uma classe herda de outra, dizemos que a classe "filha" (ou derivada) herda as propriedades, métodos e eventos da classe "pai" (ou base). 
- Isso significa que podemos definir comportamentos comuns em uma classe base e reutilizá-los nas classes filhas, evitando repetição de código.
- Em VB.NET, uma classe só pode herdar diretamente de uma única classe base (herança simples). No entanto, podemos usar interfaces para fornecer funcionalidades adicionais sem a necessidade de herança múltipla.
- Em VB.NET, utilizamos a palavra-chave Inherits para implementar a herança.

~~~vb
' Classe base
Public Class Animal
    Public Sub Comer()
        Console.WriteLine("O animal está comendo.")
    End Sub
End Class

' Classe derivada
Public Class Cachorro
    Inherits Animal

    Public Sub Latir()
        Console.WriteLine("O cachorro está latindo.")
    End Sub
End Class
~~~

- No exemplo acima:
    - Animal é a classe base que define o método Comer.
    - Cachorro é a classe derivada que herda de Animal usando a palavra-chave Inherits. Com isso, Cachorro possui o método Comer, herdado de Animal, além do método próprio Latir.
    - Agora podemos instanciar a classe Cachorro e acessar tanto o método Comer (herdado) quanto Latir (definido na própria classe Cachorro):

~~~vb
Dim meuCachorro As New Cachorro()
meuCachorro.Comer()  ' Saída: "O animal está comendo."
meuCachorro.Latir()  ' Saída: "O cachorro está latindo."
~~~
