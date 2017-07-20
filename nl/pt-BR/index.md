---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Introdução ao Release Contínua (Beta)

{: #gettingstartedtemplate}

O serviço {{site.data.keyword.uccr_full}} no IBM {{site.data.keyword.Bluemix_short}} é uma solução de gerenciamento de liberação abrangente. Com o {{site.data.keyword.uccr_short}}, é possível executar liberações e implementações para todos os aplicativos de software em seu ciclo de vida de desenvolvimento.
{:shortdesc}

[Depois de criar uma instância](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") do {{site.data.keyword.uccr_short}}, escolha como você deseja começar.

* Inicie **[criando uma liberação e executando uma implementação](#gs_create_plan)** se desejar aprofundar-se e começar a criar planos de implementação.

* Inicie **[instalando e configurando o DevOps Connect](#gs_install_dc)** se desejar integrar o {{site.data.keyword.uccr_short}} com sua instância do IBM UrbanCode&trade; Deploy no local. Depois de configurar uma integração, é possível usar tarefas do Continuous Release para gerenciar aplicativos UrbanCode Deploy.


## Criando uma liberação e executando uma implementação
{: #gs_create_plan}

1. [Criar uma liberação](/docs/services/UCCR/UCCR_releases.html##releases_create) e designe-a a uma das suas equipes. Qualquer membro da equipe pode criar planos de implementação para a liberação e executar implementações.

1. Inclua um plano de implementação para a liberação.

  * [Crie o plano](/docs/services/UCCR/UCCR_releases.html#releases_planAdd) e designe-o à liberação. 

  * [Incluir Tarefas no plano de implementação](/docs/services/UCCR/UCCR_tasks.html#tasks_create). Cada tarefa é listada em uma linha separada no plano de implementação. Tente incluir diferentes tipos de tarefas: manual, UrbanCode Deploy, pipeline de entrega contínua, atraso, E-mail e Slack.

  * É possível modificar a lista de tarefas no plano de várias maneiras. É possível reposicionar tarefas, copiar tarefas e excluí-las. 

4. Quando seu plano de implementação estiver pronto, execute uma implementação usando o plano de implementação que você criou na etapa anterior.

  * [Você executa uma implementação resolvendo as tarefas em um plano de implementação](/docs/services/UCCR/UCCR_deployRun.html). Resolva tarefas iniciando-as e, em seguida, mudando seu status para `Complete`, `Fail` ou `Skipped`. Depois que todas as tarefas em um plano de implementação são resolvidas, a implementação tem um status de Pronto.

  * As tarefas podem ser iniciadas quando elas são elegíveis para iniciar. A elegibilidade é determinada pelo padrão de execução do plano. Por padrão, o padrão de execução de um plano é sequencial. Inicialmente, a primeira tarefa, ou a superior, é elegível para iniciar. É possível modificar o padrão de execução agrupando tarefas. Um grupo de tarefas pode ter um padrão de execução paralela, o que significa que as tarefas do grupo podem ser iniciadas em qualquer ordem e podem ser executadas simultaneamente. Um plano de implementação pode ter múltiplos grupos e grupos aninhados em outros grupos.

  * Algumas tarefas, chamadas de tarefas automáticas, iniciam automaticamente assim que elas são elegíveis para execução. As tarefas do tipo UrbanCode Deploy e pipeline de entrega contínua iniciarão assim que forem elegíveis, sem intervenção manual. As tarefas automáticas também atualizam seus status sem intervenção manual.  

## Instalando e configurando o DevOps Connect
{: #gs_install_dc}

O IBM Bluemix DevOps Connect coordena a comunicação entre a instalação do IBM UrbanCode Deploy no local e o {{site.data.keyword.uccr_short}}. Depois de instalar o DevOps Connect, é possível criar integrações que permitem gerenciar aplicativos UrbanCode Deploy com tarefas do {{site.data.keyword.uccr_short}}.

**Pré-requisitos**

* Para registrar o DevOps Connect, deve-se ter um IBMid.

* Deve-se ter o [Java™ Runtime Environment versão 7 ou mais recente](https://java.com/en/download/){:new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") no sistema host e configure a variável PATH do sistema para seu local.

* Você precisa de um token de autorização de administrador do UrbanCode Deploy.   


1. Instale o DevOps Connect e use-o para integrar o {{site.data.keyword.uccr_short}} com o UrbanCode Deploy.

  1.  No {{site.data.keyword.uccr_short}}, na página Introdução, clique em **Configurar**.

  1.  Na caixa de diálogo Configuração de integração do UrbanCode Deploy, clique em **Download** para fazer download do DevOps Connect. Coloque o arquivo JAR em um computador que tenha acesso ao UrbanCode Deploy.

  1.  Usando a caixa de diálogo, copie o script de instalação do DevOps Connect. O script contém o comando para iniciar o DevOps Connect e as credenciais que são necessárias para identificar seu serviço Bluemix {{site.data.keyword.uccr_short}}.

  1.  No computador no qual você colocou o DevOps Connect, abra um shell de comando e cole e copie o script nele

  1.  Execute o script.  O DevOps Connect exibe mensagens de inicialização.

2. Registre o DevOps Connect.

  1.  Use um navegador da web para abrir o painel do DevOps Connect. A URL padrão é `https://localhost:8443`. Para mudar a URL e aprender sobre outras opções de inicialização, veja a [documentação do DevOps Connect](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

  1.  Na página de registro, especifique um nome para a instalação do DevOps Connect.

  1.  Clique em **Registrar**. Na primeira vez que você acessa o DevOps Connect, é solicitado que você registre-o com seu IBMid.

  1.  Na página **Conectar-se à IBM**, insira seu IBMid e senha e, em seguida, clique
em **Conectar**. Você se conecta toda vez que inicia o DevOps Connect.

3. Com o DevOps Connect, use o plug-in IBM UrbanCode Deploy for Cloud Reporting para criar uma integração entre o {{site.data.keyword.uccr_short}} e o UrbanCode Deploy.

    1.  No painel DevOps Connect, clique em **Integrações** e, em seguida, clique em **Incluir novo**.

    1.  No campo **Nome**, insira um nome para a integração.

    1.  Na lista **Tipo de integração**, selecione **IBM UrbanCode Deploy for Cloud Reporting**. O plug-in IBM UrbanCode Deploy for Cloud Reporting é incluído com o DevOps Connect.

    1.  No campo **URI do servidor**, insira a URL pública do servidor UrbanCode Deploy. Por exemplo, `https://my_UCD.example.com:8447`.

    1.  No campo **Token de autenticação**, insira ou cole o token de autenticação que foi gerado pelo UrbanCode Deploy.

    1.  No campo **E-mail do usuário administrativo**, insira seu endereço de e-mail.

    1.  Clique em **Salvar**.

4.  Execute a integração para confirmar que ela funciona.

    1.  Na página de integração, clique em **Executar**. O DevOps Connect se conecta à instância do UrbanCode Deploy especificada no campo **URI do servidor**. O DevOps Connect é autorizado pelo token colado no campo **Token de autenticação**.

    1.  No {{site.data.keyword.uccr_short}}, confirme que a integração é bem-sucedida criando uma tarefa do tipo UrbanCode Deploy. Se for possível selecionar um aplicativo UrbanCode Deploy, a integração será bem-sucedida. A instância do {{site.data.keyword.uccr_short}} usa os parâmetros de login e inicialização do DevOps Connect para identificar os aplicativos UrbanCode Deploy.  
