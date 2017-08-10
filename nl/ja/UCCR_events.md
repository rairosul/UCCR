---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# イベントおよびタグの管理
{: #events_overview}

イベントは、カレンダーを使用してユーザーが管理する、リリースに関連するアクティビティーを表します。

タグは、リリースまたはイベントに追加できるラベルです。タグを使用して、「リリース」ページのアクティビティー・リストをフィルタリングできます。イベントとは異なり、タグはカレンダーに表示されることはありません。

{:shortdesc}

イベントは、リリース、休日、保守期間などの汎用カテゴリーに編成されます。[カレンダー・イベントおよびタグは、リリースに割り当てられます](UCCR_releases.html#releases_overview)。イベントはリリースに追加することも、リリースとは無関係に使用することもできます。  

イベントが割り当てられると、そのイベントは、カレンダー上でイベント・カテゴリーに適したアイコンで表されます。それらのアイコンを使用して、「リリース」ページでフィルタリングを行い、影響を受ける日付 (または日付範囲) のリリースを選択できます。

タグはリリースに割り当てられ、「リリース」ページのフィルタリングに使用できます。割り当てられたタグは「リリース」ページに表示されますが、カレンダーに表示されることはありません。タグを使用して、カレンダーが乱雑になるのを回避できます。

## リリース・イベントおよびデプロイメント計画のフィルタリング
{: #events_findFilter}

「リリース」ページには、自分およびチームが作成した、リリース、イベント、およびデプロイメント計画が表示されます。「リリース」ページでは、リリースの作成やデプロイメント計画の作成など、リリースに関連するほとんどのアクティビティーを実行できます。

デフォルトでは、「リリース」ページには、今後 7 日間にスケジュールされているアクティビティーが表示されます。時刻、イベント、タグ、および状況で、表示内容をフィルタリングできます。例えば、明日にスケジュールされているリリースのみを表示するよう制限できます。現在選択されている日付範囲がアクション・バーに表示されます。

「リリース」ページをイベントまたはタグでフィルタリングするには、検索バーでイベントまたはタグを選択し、Enter を押します。

スケジュールされたアクティビティーを日付でフィルタリングするには、以下のいずれかの操作を実行します。
<ul>
<li>アクション・バーの**「日付」**リストから値を選択します。例えば、今後 1 週間にスケジュールされている項目を表示するには、**「次の 7 日間」**を選択します。</li>
<li>カレンダーで日付または日付範囲を選択します。カレンダーで日付を選択すると、アクション・バーの**「日付」**値は**「カスタム」**に設定されます。</li>
</ul>

選択した日付にスケジュールされているアクティビティーが表示されます。

項目を状況でフィルタリングするには、以下のいずれかのフィルターを選択します。
<ul>
<li>すべてのアクティビティーを表示するには、**「すべて」**を選択します。アーカイブされたものを除いて、すべてのリリース、イベント、およびデプロイメント計画が表示されます。スケジュールされていないデプロイメント計画を表示するには、このオプションを使用してください。
</li>
<li>状況が「進行中」、「完了」、または「失敗」のどれでもないデプロイメント計画を表示するには、**「ドラフト (Draft)」**を選択します。
</li>
<li>選択した日付範囲にスケジュールされているリリース、イベント、および計画を表示するには、**「スケジュールされた」**を選択します。
</li>
<li>進行中であるが、状況が「完了」または「失敗」ではないデプロイメント計画を表示するには、**「進行中」**を選択します。
</li>
<li>状況が「失敗」のデプロイメント計画を表示するには、**「失敗」**を選択します。</li>
<li>状況が「完了」のデプロイメント計画を表示するには、**「完了」**を選択します。
</li>
</li>
<li>アーカイブに保存されたリリース、イベント、およびデプロイメント計画を表示するには、**「アーカイブ」**を選択します。アーカイブされた項目はリストアすることができます。
</li>
<li>テンプレートとして保存されたデプロイメント計画を表示するには、**「テンプレート」**を選択します。計画を作成するためにテンプレートを使用できます。テンプレートをデプロイメント計画に戻すことができます。  
</li>
</ul>

## カレンダーの使用
{: #events_calendarManage}

カレンダー上のイベント・アイコンを選択することによって、**「アクティビティー」**リストをフィルタリングできます。イベント・アイコンのスタイルはカテゴリーごとに異なっていて、表されているイベントのカテゴリーを簡単に判別できるようになっています。イベントのカテゴリーについて、以下のリストで説明します。

<ul>
<li>リリース・イベントは、塗りつぶした円で表されます <img class="inline" src="images/event-icon-release.png"  alt="リリース・イベントのアイコン">。</li>
<li>特定除外日イベントおよび保守イベントは、白抜きの円で表されます <img class="inline" src="images/event-icon-window.png"  alt="カレンダー設定">。</li></li>
<li>休日イベントは、日付の上の塗りつぶした傘のような記号で表されます <img class="inline" src="images/event-icon-holiday.png"  alt="カレンダー設定">。</li>
</ul>

以下の図では、緑色のリリース・イベントが日曜日から火曜日までスケジュールされています。青色のリリース・イベントが水曜日にスケジュールされています。保守イベントが火曜日から土曜日までスケジュールされています。休日イベントが第 2 日曜日にスケジュールされています。

![](images/event-icon-styles2.png "イベント・アイコンのデフォルトのスタイル")

図 1. イベント・アイコンのデフォルトのスタイル

**「アクティビティー」**リストをフィルタリングするには、以下のいずれかの操作を実行します。

<ul>
<li>1 つの日付をクリックします。</li>
<li>日付の範囲を選択します。日付の範囲を選択するには、日付を 1 つクリックした後、Shift を押しながら別の日付をクリックします。</li>
</ul>

選択した日付または日付範囲にスケジュールされている、リリース、イベント、およびデプロイメントが表示されます。1 つの日付に複数のカレンダー・イベントがスケジュールされている場合、その日付には下線が付けられます <img class="inline" src="images/event-icon-twoIcons.png"  alt="カレンダー設定">。

## イベント・タイプの作成
{: #events_eventTypeCreate}

デフォルトのイベント・タイプに加えて、任意のイベント・カテゴリーのイベント・タイプを作成することができます。

イベント・タイプを作成すると、関連付けられたアイコンにグラフィカル・スタイルが自動的に適用されます。イベントを作成した後でアイコンのスタイルを変更できます。

イベントを作成するには、以下の手順に従ってください。

1. 「リリース」ページで**「カレンダー設定」** <img class="inline" src="images/cal-set.png"  alt="カレンダー設定"> をクリックします。

1. 「カレンダーの構成」ページで、作成するイベント・カテゴリーの**「イベント・タイプの追加」** <img class="inline" src="images/event-add.png"  alt="イベント・タイプの追加"> をクリックします。

3. テキスト・ボックスにイベントの名前を入力します。

3. **「保存」**をクリックします。イベント・タグを編集および削除することができます。

## イベント・タイプの管理
{: #events_eventEdit}

デフォルトでは、イベント・アイコンのスタイルは、カテゴリーに従って自動的かつランダムに適用されます。

次の図では、上 2 行のスタイルはリリース・イベント・カテゴリーのイベントに、3 行目のスタイルは保守イベントおよび特定除外日イベントに、4 行目のスタイルは休日に適用されます。

![](images/event-styles.png "標準的なデプロイメント計画")

図 2. イベント・アイコンのスタイル

イベント・タイプのスタイルを編集するには、以下の手順に従ってください。

1. 「リリース」ページで**「カレンダー設定」**をクリックします。

2. 「カレンダーの構成」ページで、変更するイベント・アイコンの横にある**「編集」**アイコンをクリックし、**「詳細表示」**をクリックします。

3. スタイルを選択します。カテゴリーにかかわらず任意のスタイルを選択できます。

イベント・タイプの名前を編集するには、イベント・タイプの名前の横にある**「編集」**アイコンをクリックし、名前を編集します。

イベント・タイプを削除するには、名前の横にある**「削除」**アイコンをクリックします。

## リリースおよびイベントのインポート
{: #events_importing}

ユーザー独自のリリースおよびイベントをインポートできます。インポートするには、インポートする項目をコンマ区切り値 (CSV) ファイル内に定義します。CSV ファイル・フォーマットは、アプリケーション間でデータを交換するために使用される標準フォーマットです。CSV ファイルでは、レコード内の各フィールドはコンマで区切られ、各レコードは別々の行にあります。イベントおよびリリースを定義するには、以下のフォーマットを使用します。  

`name*,description,start*,end,team*,tag`

以下のフィールドは必須です。

`name、start、team`

例: `Holiday,New Years Day,1/1/18,1/1/18,my_team,National Holiday` 

イベントおよびリリースをインポートするには、以下の手順に従ってください。

1. 「リリース」ページで**「インポート」** <img class="inline" src="images/import-events.png"  alt="イベントのインポート"> をクリックします。

2. 「CSV からのインポート」ダイアログ・ボックスで、リリースおよびイベントを含んでいる CSV ファイルを選択し、**「イベントのインポート」**をクリックします。ダイアログ・ボックスには、サンプル CSV イベント・ファイルをダウンロードできる場所へのリンクがあります。

インポートが成功すると、リリースおよびイベントが「リリース」ページに表示されます。**「タグ」**フィールドの値に、前に定義済みのイベント・タイプが含まれている場合、イベントはカレンダーに表示されます。その他の場合、**「タグ」**フィールドの値はタグとして扱われます。

## タグの作成
{: #events_tagManage}

[リリースを作成または変更するときに、「リリースの作成」ページでタグを作成します。](UCCR_releases.html#releases_create) タグは、「リリース」ページに、タグを所有するリリースとともに表示されます。タグはカレンダーに表示されませんが、タグを使用して、「リリース」ページに表示される項目をフィルタリングできます。