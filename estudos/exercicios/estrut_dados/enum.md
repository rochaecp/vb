## Exercícios Práticos: Enums em VB.NET

#### Criar Enum

1. Crie um `Enum` chamado `MesesDoAno` que contenha os meses de Janeiro a Dezembro com valores numéricos automáticos. Exiba o valor numérico correspondente ao mês de "Outubro" no console.

1. Crie um `Enum` chamado `NivelUsuario` com três níveis: Admin, Usuario, Visitante. Atribua explicitamente os valores 1, 2 e 3. Exiba o nível de usuário correspondente ao valor 2 no console.

1. Crie um `Enum` chamado `StatusEntrega` com os valores: Pendente = 0, EmAndamento = 1, Concluida = 2. Atribua o valor "Concluida" a uma variável e exiba a descrição no console.

1. Declare um `Enum` chamado `StatusOperacao` com os valores: Iniciado, Processando, Finalizado. Atribua o valor `Processando` a uma variável e exiba no console.

1. Crie um `Enum` chamado `TipoDocumento` com os valores: CPF, RG, CNH. Atribua o valor `RG` a uma variável e use `Console.WriteLine` para exibi-lo.

1. Declare um `Enum` chamado `EstadoCivil` com os valores: Solteiro, Casado, Divorciado. Atribua `Casado` a uma variável e exiba no console.

#### Converter Enum

1. Crie um `Enum` chamado `StatusPagamento` com os valores: Pendente, Pago, Cancelado. Converta um valor inteiro 1 para o tipo `StatusPagamento` e exiba o valor correspondente no console.

1. Declare um `Enum` chamado `DiasSemana` com os valores de Domingo a Sábado. Converta uma string "Segunda" para o tipo `Enum` e exiba o valor no console.

1. Crie um `Enum` chamado `CategoriaProduto` com os valores: Eletronico, Alimenticio, Vestuario. Converta um valor inteiro para o tipo `Enum` e exiba a categoria correspondente no console.

1. Crie um `Enum` chamado `PrioridadeTarefa` com os valores Baixa = 1, Media = 2 e Alta = 3. Converta o valor `Alta` para seu valor inteiro e exiba no console.

1. Declare um `Enum` chamado `NivelAcesso` com os valores: Leitura = 1, Escrita = 2, Administrador = 3. Converta o valor `Escrita` para inteiro e exiba no console.

#### Comparar Enum

1. Crie um `Enum` chamado `Prioridade` com os valores: Baixa = 1, Media = 2, Alta = 3. Atribua dois valores a variáveis e compare para verificar qual prioridade é maior.

1. Declare um `Enum` chamado `MesesAno` com os valores de Janeiro a Dezembro. Compare o valor de Fevereiro e Dezembro e exiba qual mês vem primeiro no console.

1. Crie um `Enum` chamado `TipoDocumento` com os valores: RG, CPF, CNH. Atribua dois valores diferentes e compare-os. Exiba se são iguais ou diferentes.

1. Crie um `Enum` chamado `DiaSemana` com os valores: Segunda = 1, Terça = 2, Quarta = 3, Quinta = 4, Sexta = 5. Compare `Segunda` com `Sexta` e exiba no console qual valor é maior.

1. Declare um `Enum` chamado `ClassificacaoFilme` com os valores: Livre = 1, DezAnos = 2, DozeAnos = 3, DezesseisAnos = 4, DezoitoAnos = 5. Compare `Livre` com `DezoitoAnos` e exiba a classificação etária maior no console.

1. Crie um `Enum` chamado `Meses` com os valores de Janeiro a Dezembro. Compare o valor de `Fevereiro` e `Dezembro` e exiba qual mês vem primeiro no console.

#### Definir Tipos Base para Enums

1. Crie um `Enum` chamado `TipoPagamento` como `Byte`, com os valores: Dinheiro = 1, Cartao = 2, Pix = 3. Exiba o valor numérico de `Cartao` no console.

1. Declare um `Enum` chamado `EstadoPedido` como `Short`, com os valores: Pendente = 1, Enviado = 2, Entregue = 3. Exiba o valor inteiro associado ao estado `Enviado`.

#### Verificar se a Enum foi Definida (`IsDefined`)

1. Declare um `Enum` chamado `CoresPrimarias` com os valores: Vermelho, Verde, Azul. Verifique se o valor `Amarelo` está definido no enum usando `IsDefined` e exiba o resultado no console.

1. Crie um `Enum` chamado `TipoTransporte` com os valores: Carro = 1, Bicicleta = 2, Onibus = 3. Verifique se o valor `4` está definido no enum e exiba uma mensagem de erro se não estiver.

1. Declare um `Enum` chamado `CategoriaProduto` com os valores: Eletronico, Alimenticio, Vestuario. Verifique se o valor `Eletronico` está definido no enum e exiba o resultado no console.
