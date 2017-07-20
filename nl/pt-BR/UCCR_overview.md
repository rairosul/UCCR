---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}


# Sobre o {{site.data.keyword.uccr_short}}
{: #about_UCCR}


## O que é {{site.data.keyword.uccr_short}}
{: #what}

{{site.data.keyword.uccr_full}} é uma ferramenta de gerenciamento de liberação corporativa escalado. O {{site.data.keyword.uccr_short}} funciona perfeitamente com outros serviços Bluemix e seus produtos UrbanCode&reg; no local.

Com o {{site.data.keyword.uccr_short}} é possível fazer o seguinte:

<ul>
<li>Orquestrar várias implementações de aplicativos
</li>
<li>Visualizar as dependências do projeto e do aplicativo
</li>
<li>Automatizar promoção de qualidade de código base
</li>
<li>Simplificar o planejamento para eventos de liberação principal
</li>
</ul>


## Termos Principais
{: #keyterms}

Os termos a seguir são usados frequentemente com o {{site.data.keyword.uccr_short}}:

**Atividades**: as Atividades referem-se aos itens que podem ser exibidos na lista **Atividades** na página Liberações. As atividades incluem liberações, eventos e planos de implementação. É possível filtrar a lista **Atividades** por status, tempo e tag.  

**Aplicativo**: o Aplicativo refere-se aos aplicativos IBM UrbanCode Deploy que o {{site.data.keyword.uccr_short}} gerencia. No {{site.data.keyword.uccr_short}}, você designa aplicativos integrados para tarefas do tipo UrbanCode Deploy. Você seleciona os processos, versões e ambientes de aplicativos. Quando uma tarefa do UrbanCode Deploy é executada, ela também executa os aplicativos associados no IBM UrbanCode Deploy.

**Tarefa automática**: durante as implementações, as tarefas automáticas iniciam automaticamente assim que elas ficam elegíveis para execução. As tarefas automáticas incluem os tipos de tarefas a seguir: UrbanCode Deploy, pipeline de entrega contínua, e-mail, Slack, executar outro plano e atrasada.

**Tarefas dependentes**: a capacidade de uma tarefa iniciar pode depender da conclusão de outras tarefas. Uma tarefa esperando que outras tarefas sejam concluídas é chamada de tarefa dependente. Uma tarefa que uma tarefa dependente aguarda é chamada de tarefa de pré-requisito. As tarefas dependentes não podem iniciar até que todas as suas tarefas de pré-requisito sejam resolvidas. Geralmente, você usa dependências para assegurar que as tarefas sejam executadas na ordem esperada.

**Duração**: o tempo necessário para a execução das tarefas. A duração é medida do momento que uma tarefa inicia até que seja resolvida. Ao criar alguns tipos de tarefa, é possível estimar sua duração esperada. Duração é relatado em minutos.

**Ambiente**: representa ambientes de aplicativos IBM UrbanCode Deploy. No UrbanCode Deploy, os ambientes definem destinos de implementação. No {{site.data.keyword.uccr_short}}, ao executar tarefas do UrbanCode Deploy, você seleciona o ambiente. É possível especificar o ambiente quando você cria a tarefa ou no tempo de execução.

**Padrão de execução**: refere-se à ordem na qual as tarefas em um plano de implementação se tornam elegíveis para execução. Por padrão, o padrão de execução de um plano é sequencial. As tarefas sequenciais são executadas em ordem iniciando com a primeira tarefa no plano de implementação. É possível combinar tarefas em grupos e designar o padrão de execução paralela ao grupo. As tarefas paralelas podem ser executadas em qualquer ordem e simultaneamente.

Você designa o padrão paralelo a grupos quando cria os grupos. O padrão de execução esperado pode ser afetado por dependências de tarefa.

**Integração**: refere-se à comunicação regularizada entre o {{site.data.keyword.uccr_short}} e outros produtos e serviços. A comunicação entre o {{site.data.keyword.uccr_short}} e os produtos integrados pode ser bidirecional. Por exemplo, IBM UrbanCode Deploy pode enviar dados do aplicativo para o {{site.data.keyword.uccr_short}} e o {{site.data.keyword.uccr_short}} pode então executar os aplicativos. As integrações são configuradas com o IBM Bluemix DevOps Connect.

**Processo**: refere-se aos processos de aplicativo UrbanCode Deploy. No UrbanCode Deploy, os processos definem as atividades de automação, como implementar componentes. No {{site.data.keyword.uccr_short}}, ao executar tarefas do UrbanCode Deploy, você seleciona o processo. É possível selecionar o processo ao criar a tarefa ou no tempo de execução.

**Tag**: uma tag é um rótulo que pode ser aplicado a tarefas ou liberações. Quando aplicadas a tarefas, as tags podem determinar a aplicabilidade de tarefa para uma determinada implementação. Quando aplicadas a liberações, as tags podem ser usadas para organizar e filtrar liberações.

**Grupo de tarefas**: é possível combinar duas ou mais tarefas em um grupo de tarefas. Ao formar um grupo, você define o padrão de execução do grupo, sequencial ou paralelo.

**Equipe**: uma equipe é uma coleção de usuários e grupos. No {{site.data.keyword.uccr_short}}, as equipes gerenciam liberações, eventos e planos de implementação. As equipes podem ser importadas do IBM UrbanCode Deploy.

**Versão**: representa uma captura instantânea de aplicativo IBM UrbanCode Deploy. Quando você cria uma tarefa do UrbanCode Deploy, as versões que pertencem ao aplicativo que está designado à tarefa são armazenadas no plano de implementação. É possível usar a guia Versão para selecionar as versões e os ambientes de aplicativos que são usados quando uma tarefa é executada.

## Conceitos-chave
{: #keyconcepts}

**Implementação**:
a implementação do termo refere-se às atividades usadas para entregar um projeto de software para um destino de implementação. Normalmente, você executa implementações para cada estágio de seu ciclo de vida de liberação, terminando com o estágio de produção. As atividades que são executadas durante uma implementação, chamadas de tarefas, são definidas em planos de implementação. É possível iniciar uma implementação, iniciando uma das tarefas elegíveis do plano. Você conclui uma implementação resolvendo todas as tarefas no plano de implementação

**Plano de implementação**: um plano de implementação é um plano repetido que é usado para orientar as liberações de software. Os planos de implementação contêm as tarefas que você usa para executar implementações. Ao incluir uma tarefa em um plano de implementação, você define seu tipo e duração.

Quando você estiver pronto para executar uma implementação, iniciará uma das tarefas elegíveis do plano. A elegibilidade de início de uma tarefa é determinada por seu padrão de execução. As tarefas automáticas iniciarão automaticamente, assim que estiverem elegíveis para execução. As tarefas manuais são iniciados manualmente.  

**Evento**: os Eventos são atividades relacionadas à liberação que são aplicadas a liberações e controladas com o calendário. É possível usar eventos para organizar suas liberações e outras atividades dependentes de tempo, como feriados e blecautes.

**Tarefa**: geralmente, uma tarefa representa uma atividade significativa para os negócios que tem pontos de início e término e uma duração mensurável. As durações são usadas para estimar os tempos de implementação. Você inclui tarefas para planos de implementação. Ao executar uma implementação, você conclui as tarefas no plano.

É possível definir vários tipos de tarefas.
<ul>
<li>As tarefas do UrbanCode Deploy executam processos de aplicativos no IBM UrbanCode Deploy. O Continuous Release controla as versões (capturas instantâneas) e ambientes que são usados pelos aplicativos. Essas tarefas iniciam automaticamente quando se tornam elegíveis para execução.
</li>
<li>As tarefas manuais podem representar qualquer atividade que esteja relacionada a uma implementação, como iniciar um servidor. As tarefas manuais, como o nome implica, são iniciadas manualmente.
</li>
<li>As tarefas representam marcos importantes. Uma tarefa atrasada, porque é uma tarefa automática, inicia assim que fica elegível e termina no tempo especificado para a tarefa. Geralmente, as tarefas atrasadas são pré-requisitos para outras tarefas.
</li>
<li>As tarefas de cabeçalho fornecem elementos organizacionais para planos de implementação. É possível usar uma tarefa de cabeçalho para identificar um grupo de tarefas ou incluir notas ou instruções para um grupo. As tarefas de cabeçalho são tarefas automáticas e terminam assim que iniciam. Não é possível definir durações para tarefas de cabeçalho.
</li>
<li>As tarefas de e-mail enviam mensagens para as contas de e-mail.
</li>
<li>As tarefas do Slack enviam mensagens para um canal Slack especificado pelo usuário.
</li>
<li>As tarefas de pipeline de entrega contínua automatizam seus fluxos de trabalho do DevOps. É possível gerenciar seus pipelines com tarefas de pipeline.
</li>
</ul>

**Liberação**:
uma liberação é um contêiner para planos de implementação, eventos e tags. Geralmente, uma liberação contém vários planos de implementação, embora não haja nenhum requisito de que uma liberação contenha mais de um plano. De um modo geral, cada plano em uma liberação representa um estágio no ciclo de vida de desenvolvimento, como QA ou Produção. Os estágios, ou planos de implementação, são coletivamente referidos como o ciclo de vida de liberação.
