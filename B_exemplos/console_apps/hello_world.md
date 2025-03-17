# Exemplo: Aplicação de Console em VB.NET - Hello World

- Em VB.NET, o ponto de entrada de uma aplicação de console é o método `Main`. 
- Ele pode ser definido tanto em uma Classe quanto em um Módulo, com algumas diferenças importantes em relação à estrutura e ao uso.
- O método `Main` é o ponto de partida da execução do programa.
- Ele deve ser declarado corretamente para que o compilador o reconheça como o método principal.
- Pode ser declarado de duas formas: utilizando uma Classe ou um Módulo.
    - Use Classes quando estiver trabalhando com Programação Orientada a Objetos.
    - Use Módulos para aplicações simples ou scripts rápidos.
- Diferenças
    - Classe
        - Requer instância para membros não `Shared`
        - `Shared` Necessário para o `Main`
    - Módulo
        - Não requer instância; membros acessíveis diretamente
        - `Shared` Não é necessário

#### Exemplo 1: Usando uma Classe

- Classe (`Class`): 
    - Estrutura que define objetos com propriedades e métodos.
- Instanciação: 
    - Normalmente, para acessar membros de uma classe, é necessário criar uma instância da classe. 
    - Porém, métodos estáticos (em VB.NET, chamados de `Shared`) podem ser acessados diretamente, sem a necessidade de instanciar a classe.
- O método `Main` deve ser declarado com o modificador `Shared` para que possa ser executado sem a criação de objetos.
- O uso de `Shared` permite que o método `Main` seja acessado diretamente pelo compilador, sem precisar instanciar a classe `Program`.

~~~vb
Public Class Program

    Public Shared Sub Main()
        Console.WriteLine("Olá, Mundo!")
        Console.ReadKey() ' Aguarda o usuário pressionar uma tecla antes de fechar
    End Sub

End Class
~~~

#### Exemplo 2: Usando um Módulo

- Módulo (`Module`): 
    - Estrutura semelhante a uma classe, mas projetada para armazenar métodos e variáveis globais.
- Acesso Direto: 
    - Os membros de um módulo são acessíveis diretamente, sem a necessidade de instanciar ou usar o modificador `Shared`.
- O método `Main` é automaticamente tratado como o ponto de entrada da aplicação.
- Não é necessário o uso do modificador `Shared` em um módulo, pois **seus membros já são compartilhados por padrão**.
- O código é mais direto e simples para **aplicações de console pequenas** ou **scripts utilitários**.

~~~vb
Public Module Program

    Sub Main()
        Console.WriteLine("Olá, Mundo!")
        Console.ReadKey() ' Aguarda o usuário pressionar uma tecla antes de fechar
    End Sub

End Module
~~~


