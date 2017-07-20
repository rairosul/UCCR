---

Copyright: years: 2017 lastupdated: "2017-6-22"

---


<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gerenciando planos de implementação
{: #plan_overview}

Um plano de implementação é um contêiner para tarefas. As tarefas definem as atividades que sua equipe executa para concluir uma implementação de software.

{:shortdesc}

Você cria um plano de implementação designando uma equipe para gerenciá-lo e, em seguida, incluindo tarefas no plano. Os membros da equipe incluem tarefas no plano e executam as tarefas durante as implementações. A equipe de gerenciamento também determina quais aplicativos IBM UrbanCode Deploy estão disponíveis. Depois que uma integração é configurada com o DevOps Connect, todos os aplicativos que são gerenciados pela equipe no IBM UrbanCode Deploy estão disponíveis no {{site.data.keyword.uccr_short}}.  

As tarefas definem as atividades que a equipe executa para concluir uma implementação. É possível criar novas tarefas, copie tarefas de outros planos de implementação ou importar tarefas de arquivos CSV. Quando você estiver satisfeito com o plano, será possível planejar uma implementação. Também será possível executar uma implementação a qualquer momento iniciando uma tarefas do plano.

As tarefas são exibidas em linhas individuais em planos de implementação. Cada linha contém informações que identificam a tarefa e fornece seu status. Cada linha também contém ícones de ação que são usados durante implementações, como tarefa **Iniciar** ou tarefa **Ignorar**

Por padrão, as tarefas são executadas sequencialmente iniciando com a primeira tarefa, ou tarefa superior, no plano. Depois que a primeira tarefa é concluída, a segunda tarefa fica elegível para ser executada e assim por diante. A ordem na qual as tarefas são elegíveis para execução é chamada de ordem de execução.

A ordem de execução pode ser modificada combinando tarefas em grupos. [Ao criar um grupo](/docs/services/UCCR/UCCR_tasks.html#tasks_groups), você configura o padrão de execução dele, que pode ser sequencial ou paralelo. Se um grupo tiver um padrão de execução sequencial, suas tarefas serão executadas iniciando com a primeira tarefa. O padrão de execução padrão de um plano de implementação é sequencial. Se um grupo tiver um padrão de execução paralela, as tarefas no grupo poderão ser iniciadas em qualquer ordem e poderão ser executadas simultaneamente. Se um plano consistir inteiramente de tarefas paralelas, será possível iniciar qualquer tarefa independentemente de sua posição na lista.

A elegibilidade da tarefa também pode ser efetuada por dependências de tarefa. [Se uma tarefa tiver quaisquer pré-requisitos](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies), ela não poderá iniciar, mesmo se de outro modo for elegível, até que todas as tarefas de pré-requisito sejam resolvidas.

Algumas tarefas iniciam automaticamente assim que ficam elegíveis para execução, enquanto outras tarefas são iniciadas manualmente. Se uma tarefa é iniciada automaticamente ou não, isso depende de seu tipo. As tarefas manuais, como o nome implica, são iniciadas manualmente. As tarefas do UrbanCode Deploy e do tipo Atrasada iniciam automaticamente assim que ficam elegíveis. 

As tarefas elegíveis exibem um botão **Iniciar tarefa**. Para iniciar uma implementação, você inicia uma das tarefas elegíveis de um plano. As implementações planejadas iniciarão automaticamente no tempo de planejamento se uma tarefa elegível for de um tipo que pode iniciar automaticamente, como UrbanCode Deploy.

## Criando planos de implementação
{: #plan_create}
É possível iniciar com um plano em branco que não tenha tarefas definidas ou copiar um plano existente. Também é possível iniciar com um modelo de plano. Ao copiar um plano ou usar um modelo, muitas tarefas já estão definidas.

Conclua as etapas a seguir para criar um plano de implementação:

1. Na página Liberações ou na página Detalhes da liberação, clique em **Criar plano de implementação**.

2. Na janela Criar plano de implementação, na lista **Modelo**, especifique o modelo em que você deseja basear o plano. O valor padrão é **Nenhum**.

2. No campo **Nome do plano**, insira o nome do plano.

3. Na lista **Equipe**, selecione uma equipe para gerenciar o plano. Todas as equipes das quais você é um membro estão disponíveis. Os membros da equipe podem modificar o plano e gerenciar tarefas. Os aplicativos UrbanCode Deploy que são gerenciados pela equipe no UrbanCode Deploy estão disponíveis para serem designados a tarefas do tipo UrbanCode Deploy.

4. Para planejar uma implementação para o plano, clique em **Horário de início** e, então, selecione uma data e hora para a implementação. As implementações planejadas iniciarão automaticamente no tempo de planejamento se o plano contiver tarefas automáticas elegíveis. É possível planejar uma implementação para qualquer momento futuro.

5. Na lista **Liberação**, selecione a liberação na qual você deseja incluir o plano. As liberações que pertencem a uma das suas equipes estão disponíveis. Se você selecionar uma liberação, o plano de implementação será exibido na página de Detalhes da liberação.

6. Clique em **Salvar**. Se você criou o plano em uma página Detalhes da liberação, o plano é parte da liberação selecionada.

Depois de salvar o plano, clique em **Editar** para modificar os detalhes do plano.

## Importando tarefas em planos de implementação
{: #plan_importTasks}

É possível importar tarefas que são definidas em arquivos de valores separados por vírgula (CSV) em um plano de implementação. É possível usar arquivos CSV que são exportados do IBM UrbanCode Release ou outro aplicativo capaz de criar arquivos CSV.

**Importante:** quando você importa tarefas, as tarefas que já estão definidas no plano de implementação são sobrescritas e substituídas pelas tarefas no arquivo CSV.

Conclua as etapas a seguir para importar tarefas em um plano de implementação.

1. Na página Detalhes do plano de implementação, clique em **Importar tarefas**.

3. No diálogo Importar tarefas, clique em **Escolher arquivo** e, em seguida, selecione o arquivo CSV. Também é possível arrastar um arquivo para o campo **Escolher arquivo**.

6. Clique em **Importar**. As tarefas são incluídas no plano de implementação. Se o processo de importação não for bem-sucedido, clique em **Visualizar relatório** para exibir o log de erro.

Quando você importa um plano de implementação do IBM UrbanCode Release, os segmentos são convertidos em grupos com o mesmo padrão de execução que os segmentos originais. As tarefas do segmento são agrupadas por tarefas Segmento Inicial e Segmento Final do tipo nota. Dependências da Tarefa são preservados durante a importação. As dependências do segmento são representadas por dependências para tarefas de Segmento Final.

A tabela a seguir contém os campos que definem uma tarefa em um plano de implementação do IBM UrbanCode Release. A primeira linha no arquivo CSV contém os cabeçalhos da coluna, que correspondem à coluna **Campo** da tabela. As linhas após a primeira linha contêm dados da tarefa, uma tarefa por linha. A ordem das colunas não importa.

Para aprender sobre os planos de implementação exportados do IBM UrbanCode Release, faça download do arquivo `SamplePlan.csv` no diálogo Importar tarefas.

Se você está criando tarefas em um arquivo CSV, deve-se incluir os campos obrigatórios que são identificados pelo caractere asterisco (*) na tabela a seguir.

| Campo  | Descrição  |
| ------------------ |------------------|
|SegmentName *                 |O segmento do nome. Campo Obrigatório.|                                                    
|Nome *                        |O nome da tarefa de implementação. Campo Obrigatório.|                                                                
|type*                        |Tipo de tarefa. Os valores possíveis são `note`, `waitfortimetask`, `ucdtask` ou `manual`. Durante a importação, se o campo contiver um valor não reconhecido, a tarefa será designada ao tipo manual.|
|descrição                 |Descrição do plano de implementação.|                                                                                                    
|Property:processId           |O ID do processo no IBM UrbanCode Deploy que corresponde à tarefa.|
|Ambientes-property:task   |Ambientes de Aplicativos disponíveis para a tarefa.|
|Property:mailRecipients|Os endereços de e-mail de usuários que recebem mensagens de e-mail quando as notificações são enviadas.|
|TaskTagNames                 |Os nomes das tags que estão associadas à tarefa.|
|TaskPrequisiteIds         |Uma lista separada por vírgula de IDs para tarefas que devem ser concluídas antes que essa tarefa possa ser iniciada.|
|SegmentPrerequisitelds       |Uma lista separada por vírgula de IDs para segmentos com os quais o segmento atual possui dependências.|
|TaskPrequisiteNames         |Uma lista separada por vírgula de nomes para tarefas que devem ser concluídas antes que essa tarefa possa ser iniciada.|
|segmentPrerequisiteNames       |Uma lista separada por vírgula de nomes para segmentos com os quais o segmento atual possui dependências.|
|AssignedUserEmail                |Endereço de e-mail do usuário que está designado à tarefa atual.|
|ExecutorGroup                |Grupo de usuários designado à tarefa atual.|
|SegmentPattern                |Padrão de Execução do segmento selecionado.|

{: caption="Tabela 1. Campos de plano de implementação do IBM UrbanCode Release" caption-side="top"}

## Copiando e promover planos de implementação
{: #plan_copyPromote}

É possível duplicar planos de implementação promovendo e copiando-os. O status de um plano copiado ou promovido será `draft` mesmo se o plano original tiver um status de `done` ou `in progress`.

Para copiar um plano, use a ação **Copiar este plano** na página Plano de implementação. Ao copiar um plano, um novo plano com o nome "Cópia de `plan_name`" é inserido na página Plano de implementação. O plano copiado contém todas as tarefas que estão definidas no plano original. Se as tarefas do UrbanCode Deploy estiverem no plano, os aplicativos, versões e ambientes que forem selecionados no original também serão selecionados no plano copiado. Os aplicativos, versões e ambientes são exibidos na guia **Versões** na página Detalhes do plano de implementação.

Para promover um plano, use a ação **Promover este plano** na página Plano de implementação. Quando você promove um plano, um novo plano com o nome "Promoção de `plan_name`" é inserido na página Plano de implementação. O plano promovido contém todas as tarefas que estão definidas no plano original. Se as tarefas do UrbanCode Deploy estiverem no plano, os aplicativos e versões que forem selecionados no original também serão selecionados no plano promovido. A diferença entre os planos copiado e promovido é que as versões dos aplicativos não são configuradas em planos promovidos.

## Gerenciando modelos de plano
{: #plan_templates}

É possível converter planos de implementação para criar modelos de plano de implementação.

Para criar um modelo, use a ação **Criar modelo deste plano** na página Plano de implementação. Ao criar um modelo, um novo plano com o nome "Cópia de plan_name' é inserido na página Plano de implementação. O status de um modelo será `template` mesmo se o plano original tiver um status de `done` ou `in progress`. O modelo contém todas as tarefas que estão definidas no plano original. Se as tarefas do UrbanCode Deploy estiverem no plano, os aplicativos selecionados no original também serão selecionados no modelo.

Não é possível executar implementações com modelos. Para usar um modelo para uma implementação, primeiro copie ou promova-o e, em seguida, use o plano copiado ou promovido.

## Arquivando planos de implementação
{: #plan_arch}

Ao colocar um plano de implementação no archive, o plano tem um status de `Archived` e não é exibido na página Plano de implementação, a menos que você use o filtro **Archive**.

Os planos de implementação que estão no archive podem ser restaurados para o status `draft`. Não é possível excluir permanentemente um plano de implementação.

## Revertendo e restaurando
{: #plan_history}

Um histórico de mudanças e revisões é mantido para cada plano de implementação. É possível exibir as revisões na guia **Histórico de mudanças** na página Detalhes do plano de implementação.

Para reverter para uma versão do plano anterior, use a ação **Restaurar** <img class="inline" src="images/restore-icon.png"  alt="ação restaurar"> para a versão que você deseja restaurar. O plano é restaurado para a versão selecionada.  

## Estimando os tempos de implementação
{: #plan_durationEst}

Antes de iniciar uma implementação, é possível estimar sua duração esperada. Para estimar os tempos de duração, use a ação **Estimar tempos de espera** na página Detalhes do plano de implementação. O tempo exibido representa o tempo que a implementação terminará se você iniciar a implementação agora.
