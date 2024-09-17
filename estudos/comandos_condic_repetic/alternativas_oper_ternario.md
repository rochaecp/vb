## Função IIf

- A função IIf é a forma mais antiga de simular o comportamento de um operador ternário em VB.NET.
- No entanto, ela avalia ambas as expressões (valueIfTrue e valueIfFalse), independentemente da condição, o que pode ser menos eficiente e, em alguns casos, problemático.

~~~vb
'Dim resultado = IIf(condição, valorSeVerdadeiro, valorSeFalso)
Dim resultado = IIf(2 < 10, "V", "F")
~~~

## Operador If (Introduzido no .NET 3.5) - Operador (Curto-Circuito)

- A partir do .NET Framework 3.5, foi introduzido o operador If, que funciona de forma semelhante ao operador ternário do C#.
- O operador If em VB.NET faz curto-circuito, ou seja, avalia apenas a expressão necessária com base na condição.

~~~vb
' Dim resultado = If(condição, valorSeVerdadeiro, valorSeFalso)
Dim resultado = If(2 < 10, "V", "F")
~~~

## Uso do If com Nulos

- Além de usar o If para expressões ternárias comuns, ele também pode ser utilizado para verificar valores nulos de forma semelhante ao operador de coalescência nula (??) do C#.

~~~vb
' resultado = If(valorPossivelmenteNulo, valorSeNulo)
Dim nome As String = Nothing
Dim nomeFinal As String = If(nome, "Nome padrão")
Console.WriteLine(nomeFinal) ' Saída: Nome padrão
~~~

