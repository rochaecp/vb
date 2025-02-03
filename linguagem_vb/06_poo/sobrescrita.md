## Sobrescrita

- Em VB.NET, a sobrescrita de métodos é um conceito central em polimorfismo. 
- Ele permite que uma classe derivada forneça uma implementação diferente para um método que foi previamente definido em sua classe base. 
- A sobrescrita é feita utilizando a palavra-chave `Overrides`.
- Funcionamento
    - Método na Classe Base:
        - O método na classe base é marcado com a palavra-chave `Overridable` para indicar que ele pode ser sobrescrito por classes derivadas.
    - Método na Classe Derivada:
        - Na classe derivada, o método é sobrescrito usando a palavra-chave `Overrides`, que indica que ele está substituindo o método da classe base.

#### Exemplo Prático

Vamos entender a sobrescrita de métodos com um exemplo prático de uma classe base e uma classe derivada.

**Passo 1: Definir a Classe Base**

Na classe base, temos um método que pode ser sobrescrito. 
Vamos criar uma classe chamada Animal e um método chamado Falar.

~~~vb
Public Class Animal
    ' Método da classe base que pode ser sobrescrito
    Public Overridable Sub Falar()
        Console.WriteLine("O animal faz um som.")
    End Sub
End Class
~~~

**Passo 2: Definir a Classe Derivada**

Agora, criamos uma classe derivada chamada Cachorro, que sobrescreve o método Falar.

~~~vb
Public Class Cachorro
    Inherits Animal

    ' Sobrescreve o método Falar da classe base
    Public Overrides Sub Falar()
        Console.WriteLine("O cachorro late.")
    End Sub
End Class
~~~

**Passo 3: Utilizar as Classes no Programa Principal**

Agora, podemos testar as classes em um programa principal:

~~~vb
Module Program
    Sub Main()
        ' Criando um objeto da classe base
        Dim animal As Animal = New Animal()
        animal.Falar()  ' Saída: O animal faz um som.

        ' Criando um objeto da classe derivada
        Dim cachorro As Animal = New Cachorro()
        cachorro.Falar()  ' Saída: O cachorro late.
    End Sub
End Module
~~~