## Polimorfismo

- O polimorfismo é um dos pilares da Programação Orientada a Objetos (POO) que permite a criação de métodos e propriedades que podem ser usados de forma consistente em diferentes tipos de objetos. 
- Em VB.NET, o polimorfismo é implementado principalmente por meio de classes abstratas e interfaces.

#### Classes Abstratas (MustInherit)

- Uma classe abstrata é uma classe que serve como modelo para outras classes. 
- Ela pode conter métodos implementados e métodos que precisam ser obrigatoriamente implementados nas classes derivadas.
- Você não pode criar instâncias de uma classe abstrata.
- Use o modificador `MustInherit` para declarar uma classe abstrata e `MustOverride` para declarar métodos abstratos.

~~~vb
' Classe abstrata
MustInherit Class Animal
    Public MustOverride Sub EmitirSom() ' Método abstrato
    Public Overridable Sub Dormir()
        Console.WriteLine("O animal está dormindo.")
    End Sub
End Class

' Classe derivada: implementa o método abstrato
Class Cachorro
    Inherits Animal
    Public Overrides Sub EmitirSom()
        Console.WriteLine("O cachorro late: Au Au!")
    End Sub
End Class

' Classe derivada: implementa o método abstrato
Class Gato
    Inherits Animal
    Public Overrides Sub EmitirSom()
        Console.WriteLine("O gato mia: Miau!")
    End Sub
End Class

' Programa principal
Module Program
    Sub Main()
        Dim animais As Animal() = {New Cachorro(), New Gato()}

        For Each animal As Animal In animais
            animal.EmitirSom() ' Polimorfismo: mesma chamada, comportamentos diferentes
            animal.Dormir()
        Next
    End Sub
End Module
~~~

#### Interfaces

- Uma interface define um conjunto de métodos e propriedades que uma classe deve implementar.
- Diferente de classes abstratas, as interfaces não podem conter nenhuma implementação.
- Use a palavra-chave Interface para declarar uma interface e Implements para implementá-la em uma classe.

~~~vb
' Definição da interface
Interface IVeiculo
    Sub Ligar()
    Sub Desligar()
    Sub Acelerar()
End Interface

' Classe que implementa a interface
Class Carro
    Implements IVeiculo

    Public Sub Ligar() Implements IVeiculo.Ligar
        Console.WriteLine("O carro está ligado.")
    End Sub

    Public Sub Desligar() Implements IVeiculo.Desligar
        Console.WriteLine("O carro está desligado.")
    End Sub

    Public Sub Acelerar() Implements IVeiculo.Acelerar
        Console.WriteLine("O carro está acelerando.")
    End Sub
End Class

' Classe que implementa a interface
Class Moto
    Implements IVeiculo

    Public Sub Ligar() Implements IVeiculo.Ligar
        Console.WriteLine("A moto está ligada.")
    End Sub

    Public Sub Desligar() Implements IVeiculo.Desligar
        Console.WriteLine("A moto está desligada.")
    End Sub

    Public Sub Acelerar() Implements IVeiculo.Acelerar
        Console.WriteLine("A moto está acelerando.")
    End Sub
End Class

' Programa principal
Module Program
    Sub Main()
        Dim veiculos As IVeiculo() = {New Carro(), New Moto()}

        For Each veiculo As IVeiculo In veiculos
            veiculo.Ligar()
            veiculo.Acelerar()
            veiculo.Desligar()
        Next
    End Sub
End Module
~~~

#### Diferença entre Classes Abstratas e Interfaces

- Classe Abstrata
    - Permite herança simples
    - Pode conter métodos implementados
    - Usada para fornecer funcionalidade padrão e exigir implementação de alguns métodos
    - **Use classes abstratas quando precisar fornecer uma implementação base para outras classes**.
- Interface
    - Permite múltiplas implementações
    - Não pode conter implementação
    - Usada para definir um contrato que as classes devem seguir
    - **Use interfaces para garantir que diferentes classes sigam um contrato comum, mesmo que elas não compartilhem hierarquia**.
