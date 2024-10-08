# Exercícios Práticos - Datas

#### Criar Datas e Horas - `DateTime`

1. Criação de Datas Específicas
   - Crie uma instância de `DateTime` para o dia 1º de janeiro de 2025 e exiba no formato "dd/MM/yyyy".

1. Definir Data e Hora Específica
   - Crie uma data e hora específicas para o réveillon de 2024 (31/12/2024 23:59) e exiba no console.

#### Criar Datas e Horas - `DateTimeOffset`

1. Criação de `DateTimeOffset` com Fuso Horário
   - Crie uma instância de `DateTimeOffset` para representar 1º de janeiro de 2024 às 10h, com fuso horário UTC+1. Exiba o valor no console.

1. Adicionando Intervalos a `DateTimeOffset`
   - Crie uma instância de `DateTimeOffset` para representar 25 de dezembro de 2023 às 18h no fuso UTC-3, e adicione 2 dias. Exiba o resultado.

#### Criar Datas e Horas - `TimeSpan`

1. Criação de Intervalo de Tempo
   - Crie uma instância de `TimeSpan` para representar 3 horas, 45 minutos e 30 segundos. Exiba o valor no console.

1. Operação de Adição com `TimeSpan`
   - Adicione 2 dias e 6 horas à data e hora atual utilizando `TimeSpan`. Exiba o novo valor no console.

#### Converter Strings em Datas e Horas - `DateTime.Parse`

1. Conversão de String em `DateTime`
   - Converta a string "01/10/2024 14:30" para `DateTime` e exiba o resultado no formato "dd/MM/yyyy HH:mm:ss".

1. Tratamento de Strings com Formato Incorreto
   - Utilize `DateTime.Parse` para converter a string "31/02/2024" e exiba o erro resultante.

#### Converter Strings em Datas e Horas - `DateTime.TryParse`

1. Conversão Segura de String para Data
   - Utilize `DateTime.TryParse` para tentar converter a string "30/02/2024". Exiba uma mensagem indicando se a conversão foi bem-sucedida.

1. Verificação de Formato de Data
   - Tente converter a string "2024/10/01" usando `DateTime.TryParse` e exiba o resultado formatado ou uma mensagem de erro.

#### Formatar Datas e Horas - Método `ToString` de `DateTime`

1. Formatação Personalizada de Data
   - Crie uma instância de `DateTime` para o dia atual e formate-a no formato "MMMM dd, yyyy HH:mm:ss". Exiba o resultado.

1. Exibição de Hora no Formato 12 Horas
   - Crie uma instância de `DateTime` para o horário atual e formate-a no formato "hh:mm tt". Exiba o resultado.

#### Formatar Datas e Horas - `String.Format`

1. Formatação com `String.Format`
   - Formate a data atual utilizando `String.Format` para exibi-la no formato "Hoje é {0:dd/MM/yyyy} e agora são {0:HH:mm:ss}".

1. Formatando Data com Texto
   - Utilize `String.Format` para exibir "Estamos no mês de {0:MMMM}" com a data atual.

#### Formatar Datas e Horas - Usando `CultureInfo` para Formatação Localizada

1. Formatação de Data em Inglês
   - Utilize `CultureInfo` para formatar a data atual no formato longo para a cultura "en-US". Exiba o resultado.

1. Formatação Localizada para Cultura Brasileira
   - Formate a data atual utilizando `CultureInfo` no formato longo da cultura "pt-BR". Exiba o resultado no console.

#### Adicionar Dias, Meses, Horas, etc. a uma Data

1. Adicionando Dias à Data Atual
   - Adicione 15 dias à data atual e exiba o novo valor no formato "dd/MM/yyyy".

1. Adicionando Meses à Data Atual
   - Adicione 6 meses à data atual e exiba a nova data no console.

#### Usando `TimeSpan` para Operações de Intervalos

1. Criação e Adição de `TimeSpan`
   - Crie um `TimeSpan` de 3 horas e adicione à data atual. Exiba a nova data e hora.

1. Subtraindo Intervalos com `TimeSpan`
   - Subtraia 5 dias da data atual utilizando `TimeSpan`. Exiba o novo valor no console.

#### Subtrair Datas (Diferença de Datas) - `Subtract`

1. Cálculo de Diferença entre Datas
   - Calcule a diferença entre o dia de hoje e 1º de janeiro de 2025. Exiba o número total de dias.

1. Subtração de Datas
   - Subtraia a data de hoje da data do seu próximo aniversário e exiba o número de dias restantes.

1. Usando Variáveis de Data
    - Declare uma variável `Date` para armazenar a data de nascimento, calcule e exiba a idade aproximada da pessoa.

#### Subtrair Datas (Diferença de Datas) - `DateDiff`

1. Cálculo de Diferença em Meses
   - Utilize `DateDiff` para calcular a diferença em meses entre 1º de janeiro de 2024 e a data de hoje. Exiba o resultado.

1. Cálculo de Diferença em Anos
   - Calcule a diferença em anos entre duas datas, sendo uma 01/01/2000 e a outra a data atual. Exiba o resultado.

#### Comparação entre Datas

1. Verificação de Datas Futuras
   - Verifique se o dia de hoje é anterior ao dia 31 de dezembro de 2024. Exiba o resultado como `True` ou `False`.

1. Comparação de Datas
   - Compare se o próximo ano novo (01/01/2025) é posterior à data atual. Exiba o resultado.

#### Funções Predefinidas para Manipulação de Datas e Horas

1. Uso de `Date.Now`
   - Utilize `Date.Now` para obter a data e hora atuais e exiba o valor no console.

1. Uso de `Date.Today`
   - Utilize `Date.Today` para obter a data atual (sem a hora) e exiba o resultado no formato "dd/MM/yyyy".
