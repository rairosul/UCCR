---

Copyright: years: 2017 lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gerenciando eventos e tags
{: #events_overview}

Um evento representa uma atividade relacionada à liberação que você gerencia com o calendário.

Uma tag é um rótulo que pode ser incluído em uma liberação ou um evento. É possível usar tags para filtrar a lista Atividades na página Liberações. Diferentemente de eventos, as tags não aparecem no calendário.

{:shortdesc}

Os eventos são organizados em categorias gerais que incluem liberações, feriados e janelas de manutenção. [Os eventos e tags de calendário são designados a liberações](UCCR_releases.html#releases_overview). É possível incluir eventos em liberações ou usá-los independentemente de liberações.  

Quando um evento é designado, ele é representado no calendário por um ícone apropriado para a categoria de evento. É possível usar os ícones para filtrar a página Liberações e selecionar liberações para qualquer data afetada ou intervalo de datas.

As tags são designadas a liberações e podem ser usadas para filtrar a página Liberações. As tags designadas aparecem na página Liberações, mas elas não aparecem no calendário. É possível usar tags para evitar confusões no calendário.

## Filtrando eventos de liberação e planos de implementação
{: #events_findFilter}

A página Liberações exibe as liberações, os eventos e os planos de implementação que são criados por você e suas equipes. Na página Liberações, é possível executar mais atividades relacionadas à liberação, como criar liberações e planos de implementação.

Por padrão, a página Liberações exibe as atividades que estão planejadas para os próximos sete dias. É possível filtrar a exibição por tempo, evento, tag e status. Por exemplo, você pode restringir a exibição a liberações que estão planejadas para amanhã. O intervalo de data selecionado atualmente é exibido na barra de ação.

Para filtrar a página Liberações por evento ou tag, selecione o evento ou tag na barra de procura e, em seguida, pressione Enter.

Para filtrar as atividades planejadas por data, conclua uma das tarefas a seguir:
<ul>
<li>Selecione um valor na lista **Datas** na barra de ação. Por exemplo, para exibir itens que estão planejados para a próxima semana, selecione **Próximos 7 dias**.</li>
<li>No calendário, selecione uma data ou um intervalo de datas. Quando você seleciona datas no calendário, o valor **Datas** na barra de ação é configurado como **Customizada**.</li>
</ul>

As atividades que estão ou foram planejados para as datas selecionadas são exibidas.

Para filtrar itens por status, selecione um dos filtros a seguir:
<ul>
<li>Selecione **Todos** para exibir todas as atividades. Exibe todas as liberações, eventos e planos de implementação, exceto aqueles que estão arquivados. Use essa opção para exibir planos de implementação não planejada.
</li>
<li>Selecione **Rascunho** para exibir planos de implementação que não possuem um status Em andamento, Concluído ou Com falha.
</li>
<li>Selecione **Planejado** para exibir liberações, eventos e planos que estão planejados para o intervalo de data selecionado.
</li>
<li>Selecione **Em andamento** para exibir as implementações que estão em andamento, mas não possuem o status Concluído ou Com falha.
</li>
<li>Selecione **Com falha** para exibir implementações que possuem o status de Com falha.</li>
<li>Selecione **Concluído** para exibir implementações que possuem o status de Concluído.
</li>
</li>
<li>Selecione **Archive** para exibir liberações, eventos e planos de implementação salvos no archive. Os itens arquivados podem ser restaurados.
</li>
<li>Selecione **Modelos** para exibir planos de implementação que são salvos como modelos. É possível usar modelos para criar planos. É possível reverter modelos para planos de implementação.  
</li>
</ul>

## Usando o calendário
{: #events_calendarManage}

É possível filtrar a lista **Atividades** selecionando ícones de eventos no calendário. Os ícones de eventos são estilizados por categoria, o que facilita identificar a categoria de evento representada. As categorias de eventos são descritas na lista a seguir:

<ul>
<li>Os eventos de Liberação são representados por círculos sólidos coloridos <img class="inline" src="images/event-icon-release.png"  alt="Ícone de evento de liberação">.</li>
<li>Os eventos de blecaute e manutenção são representados por círculos com esboços coloridos <img class="inline" src="images/event-icon-window.png"  alt="Configurações de calendário">.</li></li>
<li>Os eventos de feriado são representados por símbolos coloridos semelhantes a um guarda-chuva acima da data <img class="inline" src="images/event-icon-holiday.png"  alt="Configurações de calendário">.</li>
</ul>

Na figura a seguir, o evento de liberação de cor verde está planejado de domingo a terça-feira. O evento de liberação de cor azul está planejado para quarta-feira. O evento de manutenção está planejado de quinta-feira a sábado. O evento de feriado está planejado para o segundo domingo.

![](images/event-icon-styles2.png "Estilos de ícone de evento padrão")

Figura 1.  Estilos de ícone de evento padrão

Para filtrar a lista **Atividades**, conclua uma das ações a seguir:

<ul>
<li>Clique em uma data.</li>
<li>Selecione um intervalo de datas. É possível selecionar um intervalo de datas clicando em uma data e, em seguida, clicando com shift em outra data.</li>
</ul>

Liberações, eventos e implementações que estão planejados para as datas selecionadas são exibidos. Se uma data tiver mais de um evento de calendário planejado, a data será sublinhada <img class="inline" src="images/event-icon-twoIcons.png"  alt="Configurações de calendário">.

## Criando tipos de eventos
{: #events_eventTypeCreate}

Além dos tipos de eventos padrão, é possível criar tipos de eventos para qualquer uma das categorias de eventos.

Ao criar um tipo de evento, estilos gráficos são aplicados automaticamente ao ícone associado. É possível mudar o estilo de ícone depois de criar um evento.

Para criar um evento, complete as seguintes etapas:

1. Na página Liberações, clique em **Configurações de calendário** <img class="inline" src="images/cal-set.png"  alt="Configurações de calendário">.

1. Na página de calendário Configurar, clique em **Incluir tipo de evento** <img class="inline" src="images/event-add.png"  alt="Incluir tipo de evento"> para a categoria de evento que você deseja criar.

3. Na caixa de texto, insira um nome para o evento.

3. Clique em **Salvar**. É possível editar e excluir tags de evento.

## Gerenciando tipos de eventos
{: #events_eventEdit}

Por padrão, estilos de ícone de evento são aplicados automaticamente e de forma aleatória de acordo com a categoria.

Na ilustração a seguir, os estilos nas duas linhas superiores são aplicados a eventos na categoria de eventos de liberação; os estilos na terceira linha são aplicados a eventos de manutenção e blecaute; os estilos na quarta linha são aplicados a feriados.

![](images/event-styles.png "Typical deployment plan")

Figura 2.  Estilos de Ícone de Evento

Para editar um estilo do tipo de evento, conclua as etapas a seguir:

1. Na página Liberações, clique em **Configurações de calendário**.

2. Na página de calendário Configurar, clique no ícone **Editar** próximo ao ícone de evento que você deseja mudar, em seguida, clique em **Mais**.

3. Selecione um estilo. É possível selecionar qualquer estilo, independentemente da categoria.

Para editar um nome do tipo de evento, clique no ícone **Editar** próximo ao nome do tipo de evento e, em seguida, edite o nome.

Para excluir um tipo de evento, clique no ícone **Excluir** próximo ao nome.

## Importando liberações e eventos
{: #events_importing}

É possível importar suas próprias liberações e eventos. Para importar itens, defina-os em um arquivo de valores separados por vírgula (CSV). O formato de arquivo CSV é um formato padrão usado para trocar dados entre aplicativos. Em arquivos CSV, cada campo em um registro é separado por vírgulas e cada registro está em uma linha separada. Use o formato a seguir para definir eventos e liberações:  

`name*,description,start*,end,team*,tag`

Os campos a seguir são necessários:

`nome, início, equipe`

Por exemplo, `Holiday,New Years Day,1/1/18,1/1/18,my_team,National Holiday` 

Para importar eventos e liberações, conclua estas etapas:

1. Na página Liberações, clique em **Importar** <img class="inline" src="images/import-events.png"  alt="Importar eventos">.

2. Na caixa de diálogo Importar do CSV, selecione o arquivo CSV que contém suas liberações e eventos e, em seguida, clique em **Importar eventos**. A caixa de diálogo fornece um link no qual é possível fazer download de um arquivo de evento CSV de amostra.

Se a importação for bem-sucedida, as liberações e os eventos serão exibidos na página Liberações. Se o valor no campo **tag** contiver um tipo de evento definido anteriormente, o evento será exibido no calendário. Caso contrário, o valor no campo **tag** será tratado como uma tag.

## Criando marcações
{: #events_tagManage}

[Você cria tags na página Criar liberação ao criar ou modificar uma liberação.](UCCR_releases.html#releases_create) As tags são exibidas na página Liberações juntamente com a liberação que as possui. Embora as tags não apareçam no calendário, é possível usá-las para filtrar os itens exibidos na página Liberações.
