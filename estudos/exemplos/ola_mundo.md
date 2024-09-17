## Aplicação de Console

- Em ambos os casos (Module ou Class), o método Main será identificado pelo compilador como o ponto de entrada da aplicação, desde que esteja declarado corretamente.

#### Jeito 1

- Class: Precisa ser instanciada para acessar membros não estáticos, mas métodos estáticos (Shared em VB.NET) como Main podem ser chamados sem instanciar.
- O Main deve ser declarado como Shared para que possa ser acessado sem criar uma instância da classe.

~~~vb
Public Class Program

    Public Shared Sub Main()
        Console.WriteLine("Olá Mundo")
        Console.ReadKey() ' Espera que o usuário pressione qualquer tecla para continuar
    End Sub

End Class
~~~

#### Jeito 2

- Module: Não pode ser instanciado. Os membros do módulo são acessíveis diretamente.
- O Main é acessível globalmente e não requer modificadores adicionais.

~~~vb
Public Module Program

    Sub Main()

        Console.WriteLine("Olá Mundo!")
        Console.ReadKey() ' espera que o usuário pressione qualquer tecla para continuar
    End Sub

End Module

~~~