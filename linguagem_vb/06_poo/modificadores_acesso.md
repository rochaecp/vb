## Encapsulamento

- É o princípio de esconder os detalhes internos de uma classe e permitir que os dados sejam acessados ou modificados apenas por métodos públicos apropriados. 
- Em outras palavras, o encapsulamento protege o estado interno de um objeto para evitar modificações indesejadas.

## Modificadores de Acesso

- Em VB.NET, os modificadores de acesso controlam a visibilidade dos membros de uma classe (propriedades, métodos e eventos).
- **Public**
    - Permite que membros sejam acessados de qualquer lugar no código.
- **Private**
    - Restringe o acesso aos membros dentro da própria classe.
- **Friend**
    - Permite o acesso a membros dentro do mesmo assembly, mas não fora dele.

## Modificadores de acesso default (caso nenhum tenha sido fornecido?)

- Private: Variável de Classe, Constante;
- Friend: Classe, Interface, Módulo, struct, delegate;
- Public: Método (Sub / Function), Propriedade (Property), Enum, Evento;