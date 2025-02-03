# Webservices

## O que são Webservices?

- Um webservice é uma forma de comunicação entre sistemas pela web
- Webservices são componentes de software que permitem a comunicação entre sistemas distintos, possibilitando que aplicações troquem dados e realizem operações de forma interoperável, independentemente das linguagens de programação ou plataformas utilizadas.
- Webservices são interfaces que permitem a comunicação entre sistemas, independentemente de plataformas e linguagens.
- Um webservice é um tipo específico de API que permite a comunicação entre sistemas através de uma rede, geralmente usando protocolos como HTTP, SOAP, ou REST.
- Ele requer que a comunicação ocorra pela web e segue padrões definidos para troca de dados, como XML ou JSON.

## Propósito dos Webservices

- O objetivo principal dos webservices é permitir a integração de diferentes sistemas e aplicações, promovendo a interoperabilidade. 
- Eles facilitam o compartilhamento de dados e funcionalidades, mesmo quando os sistemas envolvidos utilizam tecnologias, linguagens ou arquiteturas distintas.
- Facilitar a integração e o compartilhamento de dados entre aplicações diversas.

## Exemplo: Consumindo um Webservice RESTful

- Vamos criar um exemplo básico de consumo de um webservice RESTful que retorna informações de usuários em formato JSON.
- Passo 1: Webservice de Teste
    - O webservice usado será https://jsonplaceholder.typicode.com/users, que retorna uma lista de usuários.

~~~vb
Imports System.Net.Http 'usada para fazer a requisição HTTP ao webservice.
Imports System.Threading.Tasks

Module WebServiceExample
    Sub Main()
        Dim resultado As String = ConsumirWebService().Result
        Console.WriteLine("Resultado do Webservice:")
        Console.WriteLine(resultado)
    End Sub

    Async Function ConsumirWebService() As Task(Of String)
        Dim url As String = "https://jsonplaceholder.typicode.com/users" ' URL do Webservice
        Using client As New HttpClient()
            Dim response As HttpResponseMessage = Await client.GetAsync(url) ' O método GetAsync realiza uma chamada ao serviço de forma assíncrona.

            If response.IsSuccessStatusCode Then
                ' Obtém o conteúdo da resposta como uma string
                Return Await response.Content.ReadAsStringAsync() ' A resposta é convertida para string com ReadAsStringAsync
            Else
                Return $"Erro: {response.StatusCode}"
            End If
        End Using
    End Function
End Module
~~~

## Diferenças entre webservices e API

- A diferença entre webservice e API está principalmente no escopo, propósito e nas tecnologias utilizadas. 
- Embora os termos sejam frequentemente usados de forma intercambiável, eles têm distinções importantes.
- **Webservice**
    - Tipo de API que opera exclusivamente pela web e segue protocolos como SOAP ou REST.
    - Tipo específico de API que opera via web.
    - Baseado em protocolos como SOAP ou REST, geralmente via HTTP.
    - Geralmente usa XML (SOAP) ou JSON (REST).
    - Depende de chamada de rede.
    - Requer uma conexão de rede (geralmente web).
    - Um webservice é um tipo específico de API que permite a comunicação entre sistemas através de uma rede, geralmente usando protocolos como HTTP, SOAP, ou REST.
    - Ele requer que a comunicação ocorra pela web e segue padrões definidos para troca de dados, como XML ou JSON.
- **API** (Application Programming Interface)
    - Conceito mais amplo que inclui webservices, mas também abrange integrações locais ou offline.
    - Interface para integração de software, não limitada à web.
    - Pode usar HTTP/HTTPS, mas também outros, como IPC, TCP, etc.
    - Pode usar JSON, XML, texto simples, binário, entre outros.
    - Pode ser local ou via rede.
    - Pode funcionar localmente ou remotamente.
    - SDKs de bibliotecas (ex.: API gráfica, API de sistema operacional).
    - Uma API é um conjunto de regras e ferramentas que define como sistemas ou componentes de software podem se comunicar.
    - APIs não precisam operar exclusivamente pela web. Elas podem ser locais (no mesmo sistema) ou baseadas em redes internas, além de suportar diversas tecnologias.
    - Exemplos
        - A API de um sistema operacional, como a API do Windows, que permite acessar funcionalidades nativas (ex.: abrir arquivos).
            - Uma API de sistema operacional não é um webservice porque não usa a web para comunicação.
        - Uma API local de uma biblioteca gráfica, usada por um programa para renderizar imagens na tela.
- Atualmente, APIs RESTful são frequentemente chamadas de webservices devido à sua popularidade na web, mas nem toda API é um webservice.
- Webservices tradicionais (SOAP) têm aplicações específicas em sistemas legados e grandes corporações.
- APIs RESTful são webservices.
    - Um webservice é uma forma de comunicação entre sistemas pela web
    - Uma API RESTful é um tipo de webservice que segue os princípios REST (Representational State Transfer), utilizando protocolos da web, como HTTP, para realizar essa comunicação.
- Por que nem toda API é um Webservice?
    - Nem todas as APIs operam na web.
    - APIs podem ser locais (ex.: bibliotecas ou APIs do sistema operacional) e não dependem de protocolos de rede.
    - Já webservices, por definição, dependem de uma rede (geralmente a web) para funcionar.

## Webservices SOAP vs. APIs RESTful

- Webservices tradicionais, como os baseados em SOAP (Simple Object Access Protocol), eram os mais usados no passado.
- REST surgiu como uma alternativa mais leve, flexível e escalável.
- SOAP (Webservice)
    Formato de Dados: XML 
    Complexidade: Mais verboso 
    Estrutura: Baseado em operações fixas (WSDL) 
- RESTful API (Webservice)
    - Formato de dados: JSON, XML, Texto simples
    - Complexidade: Mais leve e simples
    - Estrutura: Baseado em recursos (URI e HTTP)

## WSDL (Web Services Description Language)

- WSDL é um formato padrão baseado em XML usado para descrever webservices SOAP. 
- Ele define como um serviço pode ser chamado, quais operações ele oferece, e quais dados espera e retorna.
- WSDL é essencial para webservices SOAP, pois descreve como eles funcionam.
- Ele detalha operações, mensagens e o local do serviço, permitindo integração entre sistemas.
- Principais Elementos do WSDL
    - <types>:
        - Define os tipos de dados usados no serviço (usando XML Schema).
    - <message>:
        - Especifica as mensagens de entrada e saída para cada operação.
    - <portType>:
        - Lista as operações disponíveis e suas mensagens associadas.
    - <binding>:
        - Detalha como as operações serão transmitidas (protocolo e formato).
    - <service>:
        - Especifica o endereço (URL) onde o serviço está disponível.
- Uso
    - Permite que sistemas entendam como interagir com um webservice SOAP, independentemente da linguagem de programação ou plataforma.
    - Serve como um "contrato" entre o cliente e o servidor. 
- Exemplo Simplificado
    ~~~xml
    <definitions>
    <types>...</types>
    <message name="GetDataRequest">...</message>
    <message name="GetDataResponse">...</message>
    <portType name="ServicePort">
        <operation name="GetData">
        <input message="GetDataRequest"/>
        <output message="GetDataResponse"/>
        </operation>
    </portType>
    <binding name="ServiceBinding" type="ServicePort">...</binding>
    <service name="MyService">
        <port name="MyPort" binding="ServiceBinding">
        <address location="http://example.com/service"/>
        </port>
    </service>
    </definitions>
    ~~~

## Benefícios e Aplicações dos Webservices

- Os webservices desempenham um papel fundamental na comunicação entre sistemas, permitindo a interoperabilidade e a integração de aplicações independentemente da plataforma ou linguagem de programação utilizada. 
- Eles oferecem diversos benefícios e são aplicados em vários contextos.
- Benefícios dos Webservices
    - Interoperabilidade: Sistemas desenvolvidos em linguagens diferentes podem se comunicar usando padrões abertos, como HTTP, XML e JSON.
    -Reutilização de Código: Funcionalidades podem ser expostas como serviços reutilizáveis para diferentes aplicações, reduzindo a duplicação de código.
    - Escalabilidade: APIs baseadas em webservices podem ser facilmente escaladas para atender a grandes volumes de requisições.
    - Facilidade de Integração: Permitem conectar aplicações legadas com novos sistemas sem necessidade de grandes mudanças na infraestrutura existente.
    - Padronização: O uso de protocolos como SOAP, REST e GraphQL garante que os serviços sigam padrões bem definidos e amplamente adotados.
    - Segurança: Mecanismos como autenticação via OAuth, JWT e criptografia TLS garantem a proteção dos dados transmitidos.
- Aplicações Práticas dos Webservices
    - Os webservices são utilizados em diversos setores e tipos de sistemas.
    - Integração entre Sistemas Corporativos: Empresas utilizam webservices para conectar ERPs, CRMs e outros sistemas internos, garantindo um fluxo de informações eficiente.
    - E-commerce e Pagamentos: Plataformas de e-commerce usam webservices para processar pagamentos, consultar estoques e integrar sistemas de logística.
    - Serviços Bancários e Financeiros: APIs bancárias permitem consultas de saldo, transferências e geração de boletos por meio de webservices seguros.
    - Aplicações Móveis: Aplicativos de celular consomem webservices para buscar e enviar informações em tempo real.
    - Internet das Coisas (IoT): Dispositivos IoT utilizam webservices para se comunicar com servidores e armazenar dados na nuvem.
    - Plataformas de Streaming: Serviços como Spotify e Netflix utilizam APIs para gerenciar conteúdo e personalizar recomendações.
    - Redes Sociais: Webservices possibilitam que aplicações acessem informações de redes sociais, permitindo compartilhamento e autenticação com credenciais de terceiros.
    - Monitoramento e Sensoriamento: Webservices são usados para coletar e processar dados de sensores em tempo real, como em aplicações meteorológicas ou sistemas de segurança.
- Exemplo Prático em VB.NET
    - A seguir, um exemplo de como consumir um webservice REST em VB.NET utilizando HttpClient:

~~~vb
Imports System.Net.Http
Imports System.Threading.Tasks

Public Class WebServiceExample
    Public Shared Async Function GetDataFromAPI() As Task
        Dim client As New HttpClient()
        Dim response As HttpResponseMessage = Await client.GetAsync("https://jsonplaceholder.typicode.com/todos/1")

        If response.IsSuccessStatusCode Then
            Dim data As String = Await response.Content.ReadAsStringAsync()
            Console.WriteLine("Dados recebidos: " & data)
        Else
            Console.WriteLine("Erro ao acessar o webservice: " & response.StatusCode)
        End If
    End Function
End Class
~~~

- Este exemplo faz uma requisição GET para um webservice público, retorna os dados em formato JSON e exibe a resposta no console. 
- Essa abordagem pode ser aplicada para consumo de APIs de terceiros, como serviços bancários, APIs de clima ou consultas de produtos em um e-commerce.
- Os webservices são essenciais para o desenvolvimento de sistemas modernos, permitindo integração eficiente entre aplicações e possibilitando a criação de soluções escaláveis e distribuídas.    
