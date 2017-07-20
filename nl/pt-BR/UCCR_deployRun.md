---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Executando implementações
{: #deployment_run}

Use {{site.data.keyword.uccr_short}} para executar implementações de software. Conclua as implementações resolvendo as tarefas em um plano de implementação.
{:shortdesc}

Uma implementação é iniciada quando uma das tarefas elegíveis do plano inicia. Uma implementação planejada iniciará automaticamente no tempo de planejamento se uma de suas tarefas elegíveis for uma tarefa automática, como tarefas do UrbanCode Deploy ou do tipo Atrasada. Caso contrário, inicie uma implementação, iniciando uma das tarefas elegíveis do plano. Se o plano contiver várias tarefas elegíveis, será possível iniciar qualquer uma delas. É possível iniciar manualmente uma implementação a qualquer momento. É possível iniciar manualmente uma implementação planejada antes de seu tempo de planejamento.   

O padrão de execução do plano de implementação determina quando as tarefas são elegíveis para iniciar. Se o plano tiver o padrão de execução sequencial, que é o padrão, as tarefas se tornarão elegíveis na ordem em que elas estiverem listadas no plano, iniciando com a primeira tarefa. Após a primeira tarefa ser resolvida, a segunda tarefa se tornará elegível. Inicie as tarefas manuais elegíveis clicando no botão **Iniciar** da tarefa. As tarefas automáticas, como tarefas do UrbanCode Deploy, iniciam automaticamente assim que elas se tornam elegíveis.

As tarefas em um grupo com um padrão de execução paralela se tornam elegíveis simultaneamente. As tarefas em grupos paralelos podem ser iniciadas em qualquer ordem. Grupos e tarefas aninhadas com dependências ad hoc podem afetar o padrão de execução.

É possível modificar um plano de implementação após você iniciar uma implementação. É possível incluir, excluir e modificar tarefas.

Depois que todas as tarefas estiverem resolvidas, a implementação será concluída. Uma tarefa será resolvida se tiver um status de `Complete`, `Failed` ou `Skipped`. Se você reabrir uma tarefa ou incluir uma tarefa após a implementação ser concluída, o status da implementação mudará para `In Progress`.

## Iniciando implementações manualmente
{: #deployment_start}

É possível iniciar uma implementação manualmente a qualquer momento, incluindo implementações que estão planejadas para iniciarem mais tarde.

As tarefas em um plano de implementação podem ser inaplicáveis para implementação. As tarefas do UrbanCode Deploy serão inaplicáveis se nenhum ambiente ou versão for especificado para as tarefas. Ao criar tarefas do UrbanCode Deploy, é possível atrasar a seleção do ambiente e da versão usando a opção **Usar versão**. Antes que a implementação inicie, assegure-se de que todas as tarefas do UrbanCode Deploy sejam aplicáveis para a implementação futura.    

É possível excluir deliberadamente as tarefas de uma implementação. É possível tornar as tarefas identificadas inaplicáveis excluindo suas tags da implementação. As tarefas com tags excluídas são inaplicáveis para implementação.  

As tarefas inaplicáveis têm o status de `Not Applicable`. As tarefas com o status `Not Applicable` não podem ser iniciadas. Se uma tarefa inaplicável for um pré-requisito para uma tarefa ativa, a dependência será ignorada.  

Para iniciar uma implementação, conclua as etapas a seguir:

1. Na página Planos de implementação, clique no plano de implementação que você deseja usar para a implementação. A página de detalhes de implementação é exibido.

2. Para tornar as tarefas identificadas inaplicáveis para a implementação atual, clique em **Versões** e, em seguida, na área **Tags**, limpe as tags. Se uma tarefa tiver mais de uma tag, limpe todas elas.

2. Para selecionar a versão ou o ambiente para quaisquer tarefas inaplicáveis do UrbanCode Deploy, clique em **Versões** e, em seguida, selecione o ambiente e versão. Também é possível mudar suas opções para tarefas que possuem seus ambientes e versões já selecionados.

1. Opcionalmente, clique em **Ocultar tarefas não aplicáveis** para remover tarefas inaplicáveis da lista de tarefas exibidas. As tarefas ocultas não são removidas do plano de implementação.

1. Clique na ação **Iniciar** <img class="inline" src="images/task-start.png"  alt="iniciar ação de tarefa"> para uma das tarefas elegíveis do plano. Se mais de uma tarefa for elegível, será possível iniciar qualquer uma delas. Somente tarefas elegíveis exibem o botão iniciar. Uma tarefa iniciada tem o status de `In Progress` até que ela seja resolvida.

Depois que uma implementação inicia, o status do plano muda para `In Progress`. O status permanece `In Progress` até que todas as tarefas sejam resolvidas. Quando todas as tarefas forem resolvidas, o status do plano mudará para `Done`.

## Resolvendo tarefas
{: #deployment_taskComplete}

Conclua uma implementação resolvendo as tarefas no plano de implementação. Uma tarefa iniciada é resolvida quando seu status muda para `Complete`, `Failed` ou `Skipped`.

É possível resolver as tarefas manuais usando a ação de status apropriada. As tarefas automáticas, como tarefas do UrbanCode Deploy, mudam o status automaticamente quando as condições mudam. No entanto, é possível resolver manualmente as tarefas automáticas. Por exemplo, você pode falhar manualmente uma tarefa do UrbanCode Deploy que está levando muito tempo para ser concluída.

Para resolver uma tarefa iniciada, aplique um dos status a seguir:

<ul>
<li>Clique em **Concluir** <img class="inline" src="images/task-complete.png"  alt="concluir ação de tarefa"> para concluir uma tarefa. `Complete` significa que a tarefa foi concluída com os resultados esperados.
</li>
<li>Clique em **Ignorar** <img class="inline" src="images/task-skip.png"  alt="ignorar ação de tarefa"> para ignorar uma tarefa para a implementação atual.
</li>
<li>Clique em **Falhar** <img class="inline" src="images/task-fail.png"  alt="falhar ação de tarefa"> para terminar uma tarefa. `Fail` significa que a tarefa não concluiu ou concluiu com resultados inesperados.
</li>
<li>Clique em **Reabertura de tarefa** <img class="inline" src="images/task-reopen.png"  alt="ação de tarefa de reabertura de tarefa"> para abrir uma tarefa resolvida. Se todas as tarefas estiverem concluídas, reabrir uma tarefa reabre a implementação.
</li>
</ul>

## Executando implementações planejadas
{: #deployment_startSchedule}

Uma implementação planejada iniciará automaticamente em seu tempo de planejamento se qualquer uma das suas tarefas automáticas for elegível para iniciar. Se um plano de implementação não contiver quaisquer tarefas automáticas elegíveis, inicie a implementação iniciando manualmente uma das tarefas elegíveis.

Será possível iniciar manualmente uma implementação planejada a qualquer momento, mesmo se o plano tiver tarefas automáticas elegíveis.
