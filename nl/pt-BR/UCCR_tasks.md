---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gerenciando Tarefas
{: #tasks_overview}

Uma tarefa representa alguma atividade significativa aos negócios que está associada a uma implementação de software. As tarefas são definidas em planos de implementação.

{:shortdesc}

A maioria das tarefas tem um ponto inicial e final e uma duração mensurável. Uma tarefa pode ser de um dos tipos a seguir:

<ul>
<li>Uma tarefa **Manual** pode representar qualquer atividade que esteja associada a uma implementação de software, como tornar um servidor off-line ou atualizar um banco de dados.</li>
<li>Uma tarefa **UrbanCode Deploy** representa um aplicativo IBM&reg; UrbanCode&reg; Deploy. É possível executar aplicativos UrbanCode Deploy com esse tipo de tarefa.</li>
<li>Uma tarefa **Pipeline de entrega contínua** representa um pipeline do {{site.data.keyword.contdelivery_full}}. É possível gerenciar os pipelines do {{site.data.keyword.contdelivery_short}} com esse tipo de tarefa.</li>
<li>Uma tarefa **Atrasada** representa um evento crítico que ocorre em um horário específico.</li>
<li>Uma tarefa **Cabeçalho** é um elemento organizacional. Por exemplo, é possível usar uma tarefa de cabeçalho para identificar um grupo de tarefas.</li>
<li>Uma tarefa **E-mail** envia uma mensagem de e-mail quando ela é executada.</li>
<li>Uma tarefa **Executar outro plano** executa implementações para outros planos de implementação que participam do mesmo evento de liberação. Este é um tipo de tarefa experimental.</li>
<l1>Uma tarefa **Slack** envia uma mensagem para um canal Slack quando ele é executado. </l1>
</ul>

É possível incluir tarefas em planos de implementação criando tarefas ou importar tarefas de arquivos CSV que são criados pelo IBM UrbanCode Release ou outro aplicativo. Também é possível copiar tarefas de outros planos de implementação. Veja [Importando tarefas](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) para obter informações sobre o formato do arquivo CSV.

## Criando Tarefas
{: #tasks_create}

Ao criar uma tarefa, você seleciona o plano de implementação no qual deseja incluir a tarefa. Por padrão, novas tarefas são inseridas na parte inferior do plano de implementação. Após uma tarefa ser criada, é possível mover, copiar e colá-la em outro plano de implementação. [Também é possível criar dependências com outras tarefas](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies).

Depois de salvar uma tarefa, ícones de ação são exibidos para a tarefa. Você usa ícones de ação para mudar o status da tarefa durante uma implementação. Todas as tarefas possuem o ícone de ação **Ignorar**. Outros ícones, como **Iniciar**, são exibidos quando o contexto é apropriado para eles.

![](images/deploy-plan-intro.png "Typical deployment plan")

Figura 1. Plano de implementação simples com tarefas e botões de ação

Cada tarefa em um plano de implementação está contido em uma linha separada. As informações exibidas para cada tarefa estão descritas na tabela a seguir.

### Tabela 1. Propriedades da tarefa

| Propriedade  | Descrição  |
| ------------------ | ------------------ |
| Nome               |Nome da Tarefa       |
| Tipo               |Tipo de tarefa: manual, UrbanCode Deploy, Atrasada, Cabeçalho |             
| Status             |Status da tarefa: não iniciada, concluída, com falha, ignorada, não aplicável |
| Proprietário              |Pessoa a quem a tarefa é designada                                                        |
| Horário de Início  |Horário de início ou horário de início esperado com base no início planejado ou na duração estimada de outras tarefas        |
| horário de término               |A hora em que a tarefa foi resolvido        |
| Duração               |Comprimento de tempo de início da tarefa até a resolução da tarefa (o tempo é em minutos)        |
| Dependências               |Indica o número de tarefas que são pré-requisitos para a tarefa e dependentes da tarefa        |

---
Após as tarefas serem incluídas nos planos de implementação, é possível gerenciá-las de várias maneiras.

Para mover uma tarefa, clique em qualquer lugar na tarefa e arraste-a para um novo local.

Para copiar uma tarefa ou grupo, selecione a tarefa e clique em **Copiar** <img class="inline" src="images/copy-group.png"  alt="botão copiar"> e, em seguida, coloque o cursor onde você deseja inserir a tarefa copiada e clique em **Colar** <img class="inline" src="images/paste-group.png"  alt="botão colar">.

Para recortar uma tarefa ou um grupo de um plano de implementação, selecione a tarefa e clique em **Recortar** <img class="inline" src="images/cut-group.png"  alt="botão recortar">.

Para excluir uma tarefa, selecione a tarefa e clique em **Excluir** <img class="inline" src="images/trash-group.png"  alt="botão excluir">. A tarefa é removida do plano de implementação.

## Criando tarefas UrbanCode Deploy
{: #tasks_UDTasks}

As tarefas do UrbanCode Deploy gerenciam aplicativos UrbanCode Deploy. Quando você executa uma tarefa do UrbanCode Deploy, o aplicativo UrbanCode Deploy associado é executado usando o processo, versão e ambiente especificado pela tarefa. É possível configurar a versão e o ambiente no tempo de design ou aguardar e selecioná-los no tempo de execução.

Durante as implementações, as tarefas do UrbanCode Deploy iniciam automaticamente quando elas se tornam elegíveis para execução.   

**Importante** Os aplicativos se tornam disponíveis após o {{site.data.keyword.uccr_short}} ser integrado ao UrbanCode Deploy. Os aplicativos que estão disponíveis para um plano de implementação dependem da equipe que é designada ao plano. Os aplicativos que são gerenciados pela equipe no UrbanCode Deploy também estão disponíveis no {{site.data.keyword.uccr_short}}.

Conclua as tarefas a seguir para criar uma tarefa do UrbanCode Deploy.

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar **Criar tarefa**. A nova tarefa é inserida acima da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **UrbanCode Deploy**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **Duração (minutos)**, insira o número de minutos que você espera que a tarefa seja executada até que seja concluída. A duração estimada é usada para calcular os tempos de implementação esperados.

3. Na lista **Tags**, anexe uma tag à tarefa. É possível selecionar diversas identificações. Para criar uma tag, digite o nome da tag no campo de texto da lista.

3. Na lista **Nome do aplicativo**, selecione um aplicativo.

3. Na lista **Processo**, selecione um processo de aplicativo. Os processos que pertencem ao aplicativo UrbanCode Deploy selecionado estão disponíveis.

3. Na lista **Ambiente**, selecione um ambiente de aplicativos. Os ambientes que pertencem ao aplicativo UrbanCode Deploy selecionado estão disponíveis. Para adiar a seleção de um ambiente até que você esteja pronto para executar a implementação, selecione **Usar guia de versão**.

3. Na lista **Versão**, selecione uma versão do aplicativo. As versões se referem a capturas instantâneas de aplicativos IBM UrbanCode Deploy. As versões que pertencem ao aplicativo selecionado estão disponíveis. Para adiar a seleção de uma versão, selecione **Usar guia de versão**. Se o processo de aplicativo não requer uma versão, selecione **Sem versão**. Você poderá selecionar essa última opção se você estiver executando um processo de tipo de configuração que não requer componentes.

3. Na lista **Grupos e usuários designados**, designe a tarefa a um usuário ou um grupo. O usuário designado executa a tarefa durante a implementação.

3. Na lista **Proprietário**, selecione o proprietário da tarefa. O proprietário padrão é o usuário que criou a tarefa. A lista **Proprietário** é exibida depois que a tarefa é designada a um usuário ou um grupo.    

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

Após a tarefa ser criada, a guia **Versão** do plano é atualizada com informações sobre o aplicativo designado à tarefa. Se você selecionou **Usar guia de versão** para o ambiente de aplicativo e versão, use a guia Versão para configurar essas opções antes de executar a implementação.

## Criando tarefas manuais
{: #tasks_manual}

Geralmente, as tarefas manuais representam alguma atividade que está associada a uma liberação de software que tem um ponto de início, um ponto final e uma duração mensurável.

Conclua as tarefas a seguir para criar uma tarefa manual:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar **Criar tarefa**. A nova tarefa é inserida acima da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Manual**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **Duração (minutos)**, insira o número de minutos que você espera que a tarefa seja executada até que seja concluída. A duração estimada é usada para calcular os tempos de implementação esperados.

3. Na lista **Tags**, anexe uma tag à tarefa. É possível selecionar diversas identificações. Para criar uma tag, digite o nome da tag no campo de texto da lista.

3. Na lista **Grupos e usuários designados**, designe a tarefa a um usuário ou um grupo. O usuário designado executa a tarefa durante a implementação.

3. Na lista **Proprietário**, selecione o proprietário da tarefa. O proprietário padrão é o usuário que criou a tarefa. A lista **Proprietário** é exibida depois que a tarefa é designada a um usuário ou um grupo.    

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

## Criando tarefas atrasadas
{: #tasks_delayed}

As tarefas do tipo atrasada representam marcos ou eventos críticos durante uma implementação. Com as tarefas atrasadas, é possível assegurar que tarefas importantes sejam iniciadas no momento esperado. Geralmente, as tarefas atrasadas são pré-requisitos para outras tarefas importantes.

Uma tarefa atrasada inicia assim que esteja elegível para ser executada e é concluída em um horário especificado pelo usuário. Uma tarefa iniciada do tipo atrasada iniciada tem um status de `In Progress` até atingir seu tempo planejado, quando então muda seu status para `Complete`. Quando uma tarefa adiada é concluída, as tarefas automáticas que são dependentes dela iniciam a execução.

Conclua as tarefas a seguir para criar uma tarefa atrasada:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar **Criar tarefa**. A nova tarefa é inserida acima da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Atrasada**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **Horário**, insira ou selecione o horário em que a tarefa será concluída.

3. Na lista **Fuso horário**, selecione o fuso horário para o valor que será inserido no campo **Horário**.    

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

## Criando tarefas de cabeçalho
{: #tasks_header}

As tarefas de cabeçalho representam elementos da organização que podem ser incluídos em planos de implementação. Se você criar um grupo de tarefas, será possível identificar o grupo com uma tarefa de cabeçalho. As tarefas de cabeçalho podem ter dependências como qualquer outra tarefa.

Quando você importa um plano de implementação do IBM UrbanCode Release, as tarefas de segmento são agrupadas por Segmento Inicial e Segmento Final do tipo nota. As dependências do segmento são representadas por dependências para tarefas de Segmento Final.

Para criar uma tarefa de cabeçalho, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar **Criar tarefa**. A nova tarefa é inserida acima da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Cabeçalho**.

1. No campo **Nome**, insira um nome para a tarefa. O nome pode representar um nome do grupo de tarefas.

3. No campo **Descrição**, insira ou cole uma descrição. Você pode inserir uma nota, um lembrete ou outras instruções no campo.

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

## Criando tarefas Continuous Delivery Pipeline
{: #tasks_pipelineCD}

{{site.data.keyword.contdelivery_full}} pipelines automatizam o DevOps fluxos de trabalho. Um pipeline é uma sequência de estágios que recuperam tarefas de entrada e execução. É possível gerenciar os pipelines do {{site.data.keyword.contdelivery_short}} com tarefas de pipeline. As tarefas do pipeline de entrega contínua são tarefas automáticas e executadas assim que ficam elegíveis.

Para criar uma tarefa de pipeline de entrega contínua, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar a ação **Criar tarefa**. A nova tarefa é inserida antes da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Pipeline de entrega contínua**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **Descrição**, insira ou cole uma descrição. Você pode inserir uma nota, um lembrete ou outras instruções no campo.

3. No campo **Pipeline**, insira ou selecione o pipeline.

3. No campo **Nome do estágio**, insira ou selecione o nome do estágio. Os estágios definidos para o pipeline selecionado estão disponíveis.

3. Na lista **Tags**, anexe uma tag à tarefa. É possível selecionar diversas identificações. Para criar uma tag, digite o nome da tag no campo de texto da lista.

3. Na lista **Grupos e usuários designados**, designe a tarefa a um usuário ou um grupo. O usuário designado executa a tarefa durante a implementação.

3. Na lista **Proprietário**, selecione o proprietário da tarefa. O proprietário padrão é o usuário que criou a tarefa. A lista **Proprietário** é exibida depois que a tarefa é designada a um usuário ou um grupo.    

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

Quando uma tarefa de pipeline de entrega contínua é executada, ela executa as tarefas no estágio especificado para o pipeline selecionado.

## Criando tarefas de email
{: #tasks_email}

Uma tarefa de e-mail envia uma mensagem de e-mail quando a tarefa é executada. Você especifica os destinatários e a mensagem do e-mail quando cria a tarefa. As tarefas de e-mail são tarefas automáticas e executadas assim que ficam elegíveis.

Para criar uma tarefa de e-mail, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar a ação **Criar tarefa**. A nova tarefa é inserida antes da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **E-mail**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **Destinatários**, insira ou selecione o destinatário do e-mail. A lista de destinatários disponíveis incluem os usuários e grupos que são membros de sua equipe. Também é possível digitar os endereços de e-mail de membros que não são da equipe. Você pode especificar vários destinatários.

3. No campo **Assunto do e-mail**, insira o tópico do e-mail.

3. No campo **Mensagem de e-mail**, insira ou cole a mensagem de e-mail.

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

Quando a tarefa é executada, os destinatários recebem um e-mail de **IBM Continuous Release** com o assunto que você especificou quando criou a tarefa.

## Criando executar outro plano de tarefas
{: #tasks_runAnother}

Uma tarefa executar outro plano executa uma implementação para outro plano de implementação. O plano de destino deve ser criado por meio de um modelo. O modelo e o plano de destino devem estar no mesmo evento de liberação que o plano com a tarefa executar outro plano.

Observe que este é um tipo de tarefa experimental.

Para criar uma tarefa executar outro plano, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar a ação **Criar tarefa**. A nova tarefa é inserida antes da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Executar outro plano**.

1. No campo **Nome**, insira um nome para a tarefa.

3. Na lista **Nome do modelo de planejamento**, selecione um modelo de planejamento de implementação. O modelo deve estar no mesmo evento de liberação que o plano pai da tarefa.

3. Na lista **Tags**, anexe uma tag à tarefa. É possível selecionar diversas identificações. Para criar uma tag, digite o nome da tag na caixa de texto.

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

Quando a tarefa é executada, uma implementação é iniciada para o plano de implementação que é criado por meio do modelo selecionado e no mesmo evento de liberação. Se múltiplos planos no evento de liberação forem criados por meio do modelo, as implementações serão iniciadas para todos eles. Enquanto outras implementações são executadas, as informações de status são fornecidas pela tarefa executar outro plano. Expanda a tarefa para ver as informações de status. É possível abrir as outras implementações usando links na tarefa. Enquanto as outras implementações são executadas, a tarefa executar outro plano tem um status de **Em andamento**.

## Criando tarefas de tempo
{: #tasks_slack}

Uma tarefa do Slack envia uma mensagem para um canal Slack quando ele é executado. A mensagem pode conter texto e hiperlinks. Uma tarefa do Slack inicia assim que fica elegível para execução.

Para criar uma tarefa do Slack, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, clique em **Criar tarefa**. Se você desejar inserir uma tarefa em uma posição específica no plano, selecione uma tarefa antes de usar a ação **Criar tarefa**. A nova tarefa é inserida antes da tarefa selecionada.

1. Na caixa de diálogo Criar tarefa, na lista **Tipo**, selecione **Slack**.

1. No campo **Nome**, insira um nome para a tarefa.

3. No campo **URL do webhook**, insira a URL do canal Slack em que você deseja que a mensagem seja entregue, por exemplo, `https://hooks.slack.com/services/my_webhook`.

3. Na caixa **Mensagem**, insira o corpo da mensagem. A mensagem pode conter texto e hiperlinks.

3. No campo **Duração (minutos)**, insira o número de minutos que você espera que a tarefa seja executada até que seja concluída. A duração estimada é usada para calcular os tempos de implementação esperados.

3. Na lista **Tags**, anexe uma tag à tarefa. É possível selecionar diversas identificações. Para criar uma tag, digite o nome da tag na caixa de texto.

3. Na lista **Grupos e usuários designados**, designe a tarefa a um usuário ou um grupo. O usuário designado executa a tarefa durante a implementação.

5. Clique em **Salvar**. A tarefa é inserida no plano de implementação.

Quando a tarefa é executada, a mensagem definida no campo Mensagem é enviada para o canal Slack especificado no campo URL do webhook.

## Gerenciando grupos de tarefas
{: #tasks_groups}

É possível combinar duas ou mais tarefas em um grupo de tarefas. Ao criar um grupo, você define o padrão de execução do grupo, sequencial ou paralelo. É possível executar as tarefas em um grupo de padrão paralelo em qualquer ordem e, a menos que haja dependências, simultaneamente. As tarefas em grupos sequenciais são executadas na ordem da lista iniciando com a primeira tarefa ou aquela mais no alto.

É possível integrar grupos em outros grupos. É possível integrar um grupo de padrão sequencial em um grupo de padrão paralelo e vice-versa. No entanto, não é possível integrar um grupo de padrão sequencial em outro grupo sequencial ou um grupo de padrão paralelo dentro de outro grupo paralelo.  

Conclua as etapas a seguir para criar um grupo de tarefas.

1. Na página Detalhes do plano de implementação, selecione duas ou mais tarefas.

1. Dependendo do tipo de grupo que você deseja criar, conclua uma das etapas a seguir.

  <ul>
  <li>Para criar um grupo paralelo, clique no botão **Paralelo** <img class="inline" src="images/para-icon.png"  alt="botão grupo paralelo">. Se não for possível criar um grupo paralelo com as tarefas selecionadas, o botão será desativado. Talvez você não consiga criar um grupo paralelo se todas as tarefas selecionadas já estiverem em um grupo paralelo, por exemplo.
  </li>
  <li>Para criar um grupo sequencial, clique no botão **Sequencial** <img class="inline" src="images/seq-icon.png"  alt="botão grupo sequencial">.
  </li>
  </ul>

O grupo é formado e uma **barra de seleção de grupo** é incluída no plano de implementação. Se você selecionou tarefas não contíguas, as tarefas formarão uma lista contígua iniciando com a tarefa selecionada mais no alto.

A figura a seguir mostra um grupo paralelo. A **barra de seleção de grupo** identifica o tipo de grupo: paralelo <img class="inline" src="images/para-select.png"  alt="seleção de grupo paralelo"> ou sequencial <img class="inline" src="images/seq-select.png"  alt="seleção de grupo sequencial">.

![](images/group-select.png "Typical deployment plan")

Figura 2.  Grupo Paralelo

Para mover um grupo, selecione a **barra de seleção de grupo** ou clique em qualquer lugar no grupo e, em seguida, arraste-o para um novo local.

Para copiar um grupo, selecione o grupo e clique em **Copiar** <img class="inline" src="images/copy-group.png"  alt="botão copiar"> e, em seguida, coloque o cursor onde você deseja inserir o grupo copiado e clique em **Colar** <img class="inline" src="images/paste-group.png"  alt="botão colar">.

Para recortar um grupo, selecione o grupo e clique em **Recortar** <img class="inline" src="images/cut-group.png"  alt="botão recortar">.

Para desagrupar um grupo, selecione o grupo e clique no ícone **Desagrupar** <img class="inline" src="images/ungroup-icon.png"  alt="ícone desagrupar"> na **barra de seleção de grupo**.

Para excluir as tarefas em um grupo, selecione o grupo e clique em **Excluir** <img class="inline" src="images/trash-group.png"  alt="botão excluir">. As tarefas são removidas do plano de implementação.

## Gerenciando tags de tarefas
{: #tasks_tags}

As tarefas estão organizando elementos que podem ser incluídos em tarefas. É possível filtrar planos de implementação por tag. Por exemplo, durante uma implementação em um ambiente de produção, você pode desativar tarefas com a tag `DEV_only`, que destina-se a ser usada somente em ambientes de desenvolvimento.

Para incluir uma tag em uma tarefa, conclua as etapas a seguir.

1. Na página Detalhes do plano de implementação, selecione uma tarefa ou um grupo de tarefas e, em seguida, clique em **Gerenciar tags**  <img class="inline" src="images/task-tag.png"  alt="gerenciar tags">. É possível selecionar múltiplas tarefas e grupos.

1. Na caixa de diálogo Gerenciar tags para tarefas selecionadas, na lista **Tags comuns**, selecione as tags. É possível criar uma nova tag digitando um nome na caixa de texto da lista.

1. Clique em **Salvar**.

As tags são exibidas nas linhas de tarefa na página Detalhes do plano de implementação. Na figura a seguir, a tarefa **Implementar WAR** tem duas tags designadas a ela, `Deployment` e `Critical`.

As tags usadas por um plano de implementação são exibidas na guia **Versões** da página Detalhes do plano de implementação. Para renderizar tarefas com uma tag específica `Not Applicable` para uma implementação, limpe a tag. As tarefas com o status `Not Applicable` não podem ser iniciadas.  

![](images/task-tag-labels.png "Typical deployment plan")

Figura 3.  Dependências da Tarefa

## Criando dependências de tarefa
{: #tasks_dependencies}

É possível tornar uma tarefa um pré-requisito para outras tarefas. Se uma tarefa for um pré-requisito, as tarefas dependentes não poderão ser iniciadas, mesmo se, de outra forma, forem elegíveis, até que a tarefa de pré-requisito seja resolvida.

Uma tarefa pode ter múltiplas tarefas dependentes e múltiplas tarefas de pré-requisito. É possível definir dependências para uma tarefa com qualquer outra tarefa no plano de implementação. No entanto, você não pode criar dependências circulares. Não é possível, por exemplo, tornar uma tarefa dependente de uma tarefa que ela própria dependa da primeira tarefa.

Ao controlar as dependências de tarefas, é possível assegurar que os eventos ocorram em sua ordem esperada.

Para tornar uma tarefa um pré-requisito para outras tarefas, conclua as etapas a seguir:

1. Na página Detalhes do plano de implementação, selecione uma tarefa ou um grupo de tarefas e, em seguida, clique em **Gerenciar pré-requisitos** <img class="inline" src="images/task-depend.png"  alt="pré-requisito de tarefa">. É possível selecionar múltiplas tarefas e grupos.

1. Na caixa de diálogo Gerenciar pré-requisitos para tarefas selecionadas, na lista **Tarefas de pré-requisito para tarefas selecionadas**, selecione a tarefa de pré-requisito.

1. Clique em **Salvar**.

As dependências de tarefa são mostradas na coluna **Dependências** na página Detalhes do plano de implementação. As setas para cima indicam pré-requisitos de tarefas; as setas para baixo indicam dependências de tarefas.

Na figura a seguir, a primeira tarefa não tem nenhum pré-requisito e tem duas tarefas dependentes dela. A segunda tarefa tem uma tarefa de pré-requisito e não há tarefas dependentes dela.

(![](images/plan-w-depend.png "Plano de implementação típico"))

Figura 4.  Dependências da Tarefa

Para revisar ou modificar dependências, selecione a tarefa e, em seguida, clique em **Gerenciar pré-requisitos** <img class="inline" src="images/task-depend.png"  alt="pré-requisito de tarefa">. Use a caixa de diálogo Gerenciar pré-requisitos para tarefas selecionadas para modificar ou remover dependências.
