- quando uma classe herda de ServiceBase, ela se torna um serviço do Windows.
- Herdando de ServiceBase, a classe implementa os métodos e eventos necessários para controlar o comportamento do serviço, como iniciar (OnStart), parar (OnStop), pausar (OnPause), e continuar (OnContinue).
- No entanto, para funcionar como um serviço, a classe precisa ser registrada como um serviço no Windows e iniciada através do Gerenciador de Serviços do Windows.

## Service Control Manager (SCM)

- É um componente fundamental do sistema operacional Windows que gerencia a instalação, execução e controle de serviços do Windows. 
- Ele é responsável por iniciar, parar, pausar, continuar e controlar o status dos serviços instalados no sistema.
- Para que um serviço Windows seja inicializado pelo Gerenciador de Serviços do Windows (Service Control Manager - SCM) é necessário:
    - Implementação de um Serviço Windows (herdar do System.ServiceProcess.ServiceBase)
        - O serviço deve implementar o método onStart, que define o seu comportamento ao ser chamado pelo SCM
        - Método Main com ServiceBase.Run()
    - Registro do Serviço no Sistema Operacional
        - Para que o SCM reconheça e gerencie o serviço, ele precisa estar registrado no sistema operacional. Isso é feito utilizando a ferramenta sc.exe, InstallUtil.exe ou outras formas de instalação como scripts PowerShell ou pacotes MSI.