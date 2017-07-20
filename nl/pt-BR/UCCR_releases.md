---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Sobre as liberações
{: #releases_overview}

Uma liberação é um contêiner para planos de implementação, eventos e tags.

{:shortdesc}

Geralmente, uma liberação contém planos de implementação e eventos que estão relacionados de uma maneira significativa aos negócios. Por exemplo, os planos de implementação podem representar as fases em um ciclo de vida de desenvolvimento de software, como desenvolvimento, QA e produção. Um evento pode representar um blecaute que afeta a liberação.

Se você incluir eventos em uma liberação, será possível usar o calendário para filtrar a página Liberações para exibir liberações e planos de implementação.

## Criando liberações
{: #releases_create}

Para criar uma liberação, conclua as etapas a seguir:

1. Na página Liberações, clique em **Criar Liberação**.

1. Na janela Criar liberação, no campo **Nome**, insira um nome para a liberação. Um nome é necessário.

3. Na lista **Equipe**, selecione uma equipe para gerenciar a liberação. É possível incluir planos de implementação de outras equipes no evento de liberação, não somente da equipe pertencente à equipe que gerencia a liberação. Todas as equipes às quais você pertence estão disponíveis. Uma equipe é necessária.

3. No campo **Horário de início**, selecione uma data e hora de início. Os horários de início são necessários para todas as liberações.

3. No campo **Horário de encerramento**, selecione a data e hora de encerramento.

3. Na lista **Tags**, selecione um evento ou tag. Permite selecionar múltiplos itens.  Se você desejar que o evento apareça no calendário, [selecione um evento criado na página Configurar calendário](UCCR_events.html#events_tagCreate).

1. Opcionalmente, é possível criar uma tag digitando o nome da tag no campo **Tags**. As tags que você cria com a janela Criar liberação não são exibidas no calendário, o que pode evitar confusão no calendário.

5. Clique em **Salvar**.

Para exibir a liberação na lista Atividades, assegure-se de que o intervalo de data inclua datas dentro dos horários de início ou encerramento da liberação. 

Após a liberação ser criada, é possível incluir planos de implementação, eventos e tags nela.

## Incluindo planos de implementação para uma liberação
{: #releases_planAdd}

É possível incluir planos de implementação existentes em uma liberação ou criar novos.

Para incluir planos de implementação existentes em uma liberação, conclua as etapas a seguir:

1. Na página Liberações, selecione a liberação.

1. Na página Detalhes da liberação, clique em **Criar plano de implementação**.

1. Na janela Incluir plano, selecione o plano que você deseja incluir na liberação. Os planos planejados que pertencem à suas equipes são listados.

3. Clique em **Salvar**.

[Para criar um plano](UCCR_deployPlan.html#plan_create), clique em **Criar plano de implementação**. Os planos criados com a página de detalhes da Liberação são designados automaticamente à liberação. Ao criar um plano de implementação independente de uma liberação, é possível selecionar a liberação na qual você deseja incluir o plano.

## Gerenciando releases
{: #releases_manage}

A página Detalhes da liberação exibe os planos de implementação que pertencem à liberação. Para gerenciar uma liberação ou os planos de implementação que pertencem a ela, abra a página Detalhes da liberação e, em seguida, conclua uma das tarefas a seguir:
<ul>
<li>Clique em **Editar** para modificar a definição de liberação. Com essa opção, é possível incluir eventos e tags no evento de liberação.
</li>
<li>Selecione **Editar este plano** para editar um plano de implementação. A janela Editar plano de implementação é exibida.
</li>
<li>Selecione **Reagendar este plano** para mudar os horários de início e encerramento planejados.
</li>
<li>Selecione **Copiar este plano** para copiar um plano de implementação. Uma cópia do plano selecionado é incluída na liberação.</li>
<li>Selecione **Remover da liberação** para remover o plano de implementação da liberação. Os planos que são removidos de uma liberação não são excluídos e podem ser incluídos em outra liberação.
</li>
</li>
<li>Selecione **Arquivar este plano** para mover o plano de implementação para o archive. Os planos arquivados podem ser restaurados.
</li>
</ul>

Para iniciar uma implementação, [veja Executando implementações.](UCCR_deployRun.html#deployment_run)

## Arquivando e Restaurando as liberações
{: #releases_archiveRelease}

Embora não seja possível excluir uma liberação, é possível armazená-la no archive. As liberações arquivadas não são exibidas na página Liberações.

Para arquivar uma liberação, conclua as etapas a seguir:

1. Na página Liberações, selecione a ação **Arquivar** para a liberação.

1. Na janela de evento de liberação Archive, determine quais planos de implementação arquivar selecionando uma das opções a seguir:
<ul>
<li>Selecione **Arquivar todos os planos de implementação** para arquivar a liberação e todos os planos de implementação, independentemente de seus status.</li>
<li>Selecione **Arquivar somente os planos de implementação concluídos** para arquivar a liberação e somente os planos de implementação que têm o status de Concluído. Os planos de implementação com outros status não são arquivados e mantêm seu status atuais.</li>
</ul>

3. Clique em **Archive**.

Para restaurar uma liberação arquivada, conclua estas etapas:

1. Na página Liberações, clique em **Arquivado**.

2. Na lista de liberações arquivadas, clique na ação **Restaurar** para a liberação.

Uma liberação restaurada retém todos os seus planos de implementação original.
