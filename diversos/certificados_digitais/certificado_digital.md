# Certificados Digitais

## O que são certificados digitais?

- Os certificados digitais são documentos eletrônicos que servem como uma identidade digital para pessoas físicas, jurídicas, ou sistemas. 
- Eles garantem a autenticidade, integridade e validade de informações em meios digitais, funcionando de forma semelhante a um documento oficial em papel.
- Os certificados digitais são amplamente usados em áreas como transações financeiras, emissão de notas fiscais eletrônicas, e autenticação em sistemas governamentais, como o e-CAC no Brasil.
- O certificado digital não é um XML, mas ele pode ser representado ou transportado em formatos baseados em XML dependendo do contexto.
- Um certificado digital é um arquivo eletrônico que segue padrões internacionais, como o X.509

## Principais Elementos de um Certificado Digital

- Nome do Titular
    - pessoa física ou jurídica
- Chave Pública 
    - Um componente usado para criptografar ou verificar informações. 
    - Está associada à identidade do titular.
- Chave Privada 
    - Exclusiva do titular, usada para assinar digitalmente ou descriptografar dados.
- Nome da Autoridade Certificadora (CA) que o emitiu
    - Uma entidade confiável que emite e valida os certificados, assegurando que eles são autênticos.
- Assinatura Digital da CA 
    - Uma garantia de que o certificado foi emitido pela autoridade certificadora correspondente.
- O número de série
- O período de validade    

## Características Importantes

- Autenticação
    - Confirma a identidade de quem está acessando ou enviando informações.
- Criptografia
    - Garante que os dados transmitidos sejam protegidos contra acessos não autorizados.
- Assinatura Digital
    - Assegura que o conteúdo não foi alterado após ser assinado.

## Exemplo Prático

- Imagine que você deseja assinar um contrato online
    - Seu certificado digital é usado para comprovar sua identidade.
    - A assinatura digital vinculada ao certificado garante que o contrato não foi alterado após a assinatura.
    - A outra parte pode verificar a autenticidade do documento por meio da autoridade certificadora.

## Principais Formatos de Certificados Digitais

- DER (Distinguished Encoding Rules):
    - Binário.
    - Usado em sistemas que precisam de arquivos compactos.
    - Extensão: .cer ou .der.
- PEM (Privacy Enhanced Mail):
    - Texto base64 com cabeçalhos como -----BEGIN CERTIFICATE-----.
    - Fácil de transportar em texto puro.
    - Extensão: .pem.
- PFX ou PKCS#12:
    - Formato binário que armazena tanto a chave pública quanto a chave privada.
    - Protegido por senha.
    - Extensão: .pfx ou .p12.
- P7B ou PKCS#7:
    - Formato usado para armazenar a cadeia de certificados (não inclui a chave privada).
    - Extensão: .p7b.

## XML

- Certificados digitais podem ser incorporados em arquivos XML dependendo do protocolo ou aplicação. Alguns exemplos:
    - XMLDSig (XML Digital Signature): Um padrão para assinar digitalmente documentos XML. Nesse caso, o certificado digital é usado para criar e verificar a assinatura.
    - e-CNPJ e e-CPF: Em sistemas governamentais, o certificado pode ser utilizado para assinar arquivos XML, como notas fiscais eletrônicas (NF-e), mas o próprio certificado continua no formato X.509.
- O certificado digital em si não é um XML, mas pode ser usado para:
    - Assinar arquivos XML.
    - Ser representado ou referenciado dentro de um XML em aplicações específicas.
    - Se você precisar trabalhar com certificados digitais em XML, é provável que esteja lidando com uma aplicação que encapsula o certificado (como XMLDSig) ou utiliza sua chave pública para assinar/verificar documentos.

## História e evolução no Brasil

- A história dos certificados digitais no Brasil começa com a necessidade de criar um sistema confiável para garantir a segurança e a autenticidade das transações digitais. 
- A implementação desse sistema foi possível graças à criação da Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil).

- 1. Criação da ICP-Brasil (2001):
    - A ICP-Brasil foi estabelecida pela Medida Provisória nº 2.200-2, de 24 de agosto de 2001.
    - Objetivo: Garantir a autenticidade, integridade e validade jurídica de documentos digitais por meio de assinaturas digitais.
    - A ICP-Brasil é composta por uma hierarquia de confiança:
        - ITI (Instituto Nacional de Tecnologia da Informação): Autoridade máxima da cadeia.
    - Autoridades Certificadoras (ACs): Responsáveis por emitir os certificados digitais.
    - Autoridades de Registro (ARs): Fazem a validação presencial dos dados de quem solicita um certificado.
- 2. Expansão e Adoção Inicial:
    - Nos primeiros anos, os certificados digitais foram utilizados principalmente para fins corporativos, como:
        - Envio de notas fiscais eletrônicas (NF-e).
        - Integração com o Sistema Público de Escrituração Digital (SPED).
    - Grandes empresas começaram a adotar certificados para garantir segurança em transações financeiras e autenticação de documentos.
- 3. Popularização:
    - Com o avanço da digitalização, o uso de certificados se expandiu para pessoas físicas e pequenas empresas, principalmente para:
        - e-CPF e e-CNPJ: Ferramentas para autenticação no portal da Receita Federal e envio de declarações.
        - e-Social: Integração de obrigações trabalhistas e previdenciárias.
    - A emissão de certificados em formatos mais acessíveis, como os certificados em nuvem, facilitou a adoção.
- 4. Inovações Recentes:
    - O desenvolvimento de soluções como certificados digitais em dispositivos móveis e integração com aplicativos de assinatura eletrônica trouxe ainda mais praticidade.
    - A adoção cresceu com a obrigatoriedade de sistemas digitais em setores governamentais e empresariais, como no Portal Gov.br.
- Impacto e Relevância:
    - A evolução dos certificados digitais no Brasil consolidou a ICP-Brasil como referência em segurança digital, permitindo maior confiabilidade nas transações eletrônicas e fortalecendo o uso de tecnologias digitais no setor público e privado. 
    - Hoje, o Brasil é um dos países com maior adoção de certificados digitais em diversas áreas da economia.

## Benefícios e aplicações dos certificados digitais

- Os certificados digitais são ferramentas fundamentais para garantir a segurança e a autenticidade das transações eletrônicas. 
- Benefícios dos Certificados Digitais
    - Segurança:
        - Garante a proteção de informações, utilizando criptografia para evitar acessos não autorizados.
        - Previne fraudes ao validar identidades e transações.
    - Autenticidade:
        - Certifica que um documento ou comunicação digital é de fato originado pela entidade ou pessoa declarada.
    - Validade Jurídica:
        - Documentos assinados digitalmente têm a mesma validade legal que os assinados de forma manuscrita, conforme a legislação brasileira (Lei nº 12.682/2012).
    - Eficiência e Economia:
        - Reduz o uso de papel, custos com transporte e tempo em processos burocráticos, como assinaturas de contratos e envio de documentos.
    - Conectividade com Sistemas Governamentais:
        - Simplifica o acesso a plataformas como e-CAC, SPED, e-Social e sistemas de notas fiscais eletrônicas.
- Aplicações dos Certificados Digitais
    - Assinatura Digital de Documentos:
        - Contratos, procurações e declarações podem ser assinados digitalmente, garantindo validade jurídica e autenticidade.
    - Emissão de Notas Fiscais Eletrônicas (NF-e):
        - Empresas utilizam certificados digitais para emitir e validar notas fiscais eletrônicas junto aos órgãos fiscais.
    - Acesso a Sistemas Governamentais:
        - Pessoas físicas e jurídicas podem acessar plataformas como Receita Federal (e-CAC), e-Social, e sistemas estaduais.
    - Autenticação em Ambientes Seguros:
        - Certificados são usados para autenticar acessos em redes corporativas, VPNs e servidores web, evitando acessos não autorizados.
    - Proteção de E-mails e Comunicações:
        - Garantem que mensagens de e-mail não sejam interceptadas ou adulteradas, garantindo a integridade e confidencialidade.
    - Transações Bancárias e Comerciais:
        - Certificados digitais são usados para validar transações financeiras e compras online de forma segura.
- Resumo
    - Os certificados digitais trazem benefícios claros em termos de segurança, eficiência e validade jurídica, sendo amplamente aplicados em empresas, governo e transações pessoais. 
    - Essas ferramentas são essenciais para modernizar e proteger processos digitais no Brasil e no mundo.

## Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil)

- A ICP-Brasil (Infraestrutura de Chaves Públicas Brasileira) é um sistema nacional que organiza a emissão e o gerenciamento de certificados digitais no Brasil. 
- Ela garante a autenticidade, integridade, e validade jurídica de documentos e transações realizadas por meio eletrônico.
- A ICP-Brasil é uma estrutura hierárquica formada por órgãos e entidades que seguem normas técnicas e regulatórias específicas para emitir e gerenciar certificados digitais. 
- Ela é regulamentada pela Lei nº 12.682/2012 e tem como objetivo principal assegurar a confiança nas transações digitais.
- A ICP-Brasil é a base para a certificação digital no país, proporcionando segurança, confiança e validade jurídica para as transações digitais no âmbito público e privado. 
- Componentes da ICP-Brasil
    - Autoridade Certificadora Raiz (AC Raiz):
        - É o topo da hierarquia e responsável por credenciar, auditar e supervisionar as Autoridades Certificadoras (ACs).
        - No Brasil, a AC Raiz é gerida pelo ITI (Instituto Nacional de Tecnologia da Informação).
    - Autoridades Certificadoras (ACs):
        - Entidades responsáveis por emitir e gerenciar os certificados digitais para usuários finais.
        - Exemplo: Certisign, Serasa Experian, Valid, entre outras.
    - Autoridades de Registro (ARs):
        - Atuam como intermediárias das ACs, realizando a validação da identidade dos solicitantes antes da emissão de certificados.
    - Repositórios e Diretórios:
        - Locais onde informações e certificados revogados (listas de CRL) são armazenados e disponibilizados para consulta.
- Como Funciona a ICP-Brasil?
    - Solicitação:
        - O usuário solicita um certificado digital a uma Autoridade de Registro (AR).
    - Validação:
        - A AR verifica a identidade do solicitante presencialmente ou por meio de videoconferência.
    - Emissão:
        - Após validação, a Autoridade Certificadora (AC) emite o certificado digital, que é entregue ao usuário.
    - Uso e Verificação:
        - O certificado é utilizado para assinar documentos, acessar sistemas, ou realizar transações seguras.
        - Qualquer pessoa pode verificar a validade do certificado consultando os repositórios da ICP-Brasil.
- Benefícios da ICP-Brasil
    - Segurança: Garante que transações e documentos digitais são autênticos e não foram alterados.
    - Validade Jurídica: Certificados emitidos pela ICP-Brasil têm o mesmo valor legal que documentos assinados fisicamente.
    - Padronização: Segue normas técnicas rigorosas que asseguram a interoperabilidade entre sistemas e entidades.
    - Confiabilidade: Sistema auditado e supervisionado pelo ITI.
- Exemplo Prático:
    - Imagine que uma empresa precisa emitir notas fiscais eletrônicas (NF-e). 
    - Para isso, ela utiliza um certificado digital A1 ou A3 emitido por uma AC credenciada pela ICP-Brasil. 
    - Esse certificado assegura a integridade das notas fiscais e a autenticidade da assinatura eletrônica do emissor.   

## e-CPF, e-CNPJ e e-Social