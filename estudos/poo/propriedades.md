- Em Public Property TaskName() As String, os parênteses não são obrigatórios e podem ser omitidos sem alterar o funcionamento da propriedade.
- Se TaskName fosse um array, a declaração seria diferente. Para um array de String, por exemplo, seria:

~~~vb
Public Property TaskNames() As String()
~~~