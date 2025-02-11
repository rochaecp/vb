# Funcion (Funções)

- Function: Retorna um valor.
- Em VB.NET, funções (ou functions) são blocos de código que executam uma tarefa específica e podem retornar um valor.
- As funções são utilizadas para organizar e reutilizar código, melhorar a legibilidade, evitar duplicação e facilitar a manutenção.
- Estrutura de uma Função em VB.NET
    - A estrutura básica de uma função em VB.NET inclui a palavra-chave Function, seguida pelo nome da função, seus parâmetros (opcionais) e o tipo de retorno (se a função retornar um valor). 
    O corpo da função contém as instruções que ela executa.
- O tipo de retorno é especificado após a palavra-chave As. 
- Se a função não retornar um valor, deve-se usar uma sub-rotina (Sub) em vez de Function.
- A execução da função termina quando o Return é alcançado.

#### Exemplos

~~~vb
Function NomeDaFuncao(parametro1 As Integer, parametro2 As Integer) As Integer
    ' Corpo da função
    Dim resultado As Integer = parametro1 + parametro2
    Return resultado
End Function

'chamada
'Dim resultado As Integer = NomeDaFuncao(10, 20)
~~~

~~~vb
Function DobrarNumero(numero As Integer) As Integer
    Return numero * 2
End Function
~~~

# Sub (Subrotinas)

- Sub: Não retorna valor. É usada para realizar tarefas que não precisam devolver um resultado, como exibir mensagens ou realizar operações de arquivo.
- Em VB.NET, as subrotinas (ou subs) são blocos de código que executam uma tarefa específica, mas não retornam um valor. 
- Elas são usadas para realizar ações, como exibir informações no console, modificar variáveis ou executar operações que não exigem um resultado específico de volta ao chamador.
- Estrutura de uma Subrotina
    - A estrutura básica de uma subrotina em VB.NET começa com a palavra-chave Sub, seguida pelo nome da subrotina, seus parâmetros (opcionais), e o código que a subrotina executa.
- Ao contrário de uma função (Function), que retorna um valor, uma subrotina não retorna nada. Quando a subrotina termina, a execução do programa continua no próximo código.    

~~~vb
Sub Saudacao(nome As String)
    Console.WriteLine("Olá, " & nome & "!")
End Sub
~~~

# Passagem de Parâmetros 

- Conteúdo válido tanto para sub quanto para function.

#### Passagem de Parâmetros por Valor (ByVal)

- O parâmetro é copiado para dentro da subrotina, e qualquer modificação no valor dentro da subrotina não afeta o valor original fora da subrotina.
- ByVal é o comportamento padrão.

~~~vb
Sub IncrementarValor(ByVal numero As Integer)
    numero += 1
End Sub
~~~

#### Passagem de Parâmetros por Referência (ByRef)

- O parâmetro é passado como uma referência, permitindo que as modificações feitas dentro da subrotina afete o valor original fora da subrotina.

~~~vb
Sub IncrementarValor(ByRef numero As Integer)
    numero += 1
End Sub
~~~

#### Passagem de Parâmetros Opcionais (Optional)

- Parâmetros opcionais permitem que você defina valores padrão para um ou mais parâmetros de uma função ou subrotina. 
- Isso significa que, quando a função é chamada, o chamador pode omitir esses parâmetros, e os valores padrão serão usados.

~~~vb
Sub Saudacao(nome As String, Optional mensagem As String = "Seja bem-vindo!")
    Console.WriteLine("Olá, " & nome & "! " & mensagem)
End Sub

'chamadas
'Saudacao("Mauricio")
'Saudacao("Mauricio", "Como vai?")
~~~

#### Passagem de Parâmetros Out

- VB.NET não possui diretamente a palavra-chave Out como em C#, mas o comportamento de parâmetros Out pode ser simulado usando ByRef. 
- O conceito de um parâmetro Out é passar uma variável para uma função ou subrotina que não precisa ser inicializada antes da chamada, e a função deve atribuir um valor a ela.

~~~vb
Sub ObterDados(ByRef idade As Integer, ByRef nome As String)
    idade = 25
    nome = "Carlos"
End Sub
~~~
