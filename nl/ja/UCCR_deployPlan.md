---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---


<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# デプロイメント計画の管理
{: #plan_overview}

デプロイメント計画は、タスクのコンテナーです。タスクは、チームがソフトウェア・デプロイメントを完了するために実行するアクティビティーを定義したものです。

{:shortdesc}

デプロイメント計画を作成するには、管理するチームを割り当てた後、計画にタスクを追加します。チーム・メンバーは、デプロイメント中に、計画へのタスクの追加およびタスクの実行を行います。管理チームは、使用可能な IBM UrbanCode Deploy アプリケーションの判別も行います。DevOps Connect を使用して統合が構成された後は、IBM UrbanCode Deploy でチームが管理するすべてのアプリケーションが {{site.data.keyword.uccr_short}} で使用可能です。  

タスクは、チームがデプロイメントを完了するために実行するアクティビティーを定義したものです。新規タスクの作成、他のデプロイメント計画からのタスクのコピー、または CSV ファイルからのタスクのインポートを行うことができます。計画が完成したら、デプロイメントをスケジュールできます。計画のタスクの 1 つを開始することによって、デプロイメントをいつでも実行することもできます。

タスクは、デプロイメント計画内で個々の行に表示されます。各行には、タスクを識別する情報と、タスクの状況を提供する情報が含まれます。さらに、各行には、デプロイメント中に使用されるアクション・アイコン (タスクの**開始**やタスクの**スキップ**など) も含まれています。

デフォルトでは、タスクは計画内の先頭タスク (最上位タスク) から順次実行されます。先頭タスクが終了したら 2 番目のタスクが実行に適格になり、以後同様に続きます。タスクが実行に適格になる順序を実行順序と呼びます。

タスクをグループ化することによって、実行順序を変更できます。[グループを作成する](/docs/services/UCCR/UCCR_tasks.html#tasks_groups)ときに、グループの実行パターン (順次または並列) を設定します。グループの実行パターンが順次の場合、そのグループのタスクは、先頭タスクから順に実行されます。デプロイメント計画のデフォルトの実行パターンは順次です。グループの実行パターンが並列の場合、そのグループ内のタスクは、任意の順序で開始でき、同時に実行できます。計画内のすべてのタスクが並列の場合、リスト中の位置に関係なく、どのタスクでも開始できます。

タスク依存関係もタスクが適格かどうかに影響することがあります。[タスクに前提条件がある場合](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies)、すべての前提条件タスクが解決されるまでは、それ以外の点では開始に適格であってもそのタスクは開始できません。

実行に適格になったらすぐに自動的に開始されるタスクと、手動で開始されるタスクがあります。タスクが自動的に開始されるかどうかは、タスクのタイプによって決まります。手動タスクは、名前が意味するように、手動で開始されます。UrbanCode Deploy タスクおよび遅延実行タイプのタスクは、適格になると即座に自動的に開始されます。

適格タスクには**「タスクの開始」**ボタンが表示されます。デプロイメントを開始するには、計画の適格タスクの 1 つを開始します。スケジュールされたデプロイメントは、自動開始が可能なタイプ (UrbanCode Deploy など) の適格なタスクがあれば、スケジュールされた時刻に自動的に開始されます。

## デプロイメント計画の作成
{: #plan_create}
タスクが何も定義されていない空の計画から始めるか、または、既存の計画をコピーすることができます。計画テンプレートから始めることもできます。計画をコピーするか、テンプレートを使用する場合は、多くのタスクが既に定義済みです。

デプロイメント計画を作成するには、以下の手順に従ってください。

1. 「リリース」ページまたは「リリースの詳細」ページで、**「デプロイメント計画の作成」**をクリックします。

2. 「デプロイメント計画の作成」ウィンドウの**「テンプレート」**リスト内で、計画のベースとして使用するテンプレートを指定します。デフォルト値は **None** です。

2. **「計画名」**フィールドに計画の名前を入力します。

3. **「チーム」**リストから、この計画を管理するチームを選択します。メンバーとして所属しているすべてのチームが選択可能です。チーム・メンバーは、計画の変更およびタスクの管理を行うことができます。UrbanCode Deploy でチームによって管理されている UrbanCode Deploy アプリケーションは、UrbanCode Deploy タイプのタスクへの割り当てに選択可能です。

4. 計画のデプロイメントをスケジュールするには、**「開始時刻」**をクリックし、次に、デプロイメントの日時を選択します。スケジュールされたデプロイメントは、適格な自動タスクが計画に含まれていれば、スケジュールされた時刻に自動的に開始されます。将来の任意の時刻にデプロイメントをスケジュールできます。

5. **「リリース」**リストで、計画を追加するリリースを選択します。チームのいずれかに属しているリリースが選択可能です。リリースを選択すると、デプロイメント計画が「リリースの詳細」ページに表示されます。

6. **「保存」**をクリックします。「リリースの詳細」ページで計画を作成した場合、その計画は選択されたリリースの一部になります。

計画を保存した後、計画の詳細を編集するには、**「編集」**をクリックします。

## デプロイメント計画へのタスクのインポート
{: #plan_importTasks}

コンマ区切り値 (CSV) ファイル内に定義されたタスクをデプロイメント計画にインポートできます。IBM UrbanCode Release から、または、CSV ファイルを作成する機能のある別のアプリケーションからエクスポートされた CSV ファイルを使用できます。

**重要:** タスクをインポートすると、デプロイメント計画内に既に定義されているタスクは上書きされ、CSV ファイル内のタスクで置き換えられます。

デプロイメント計画にタスクをインポートするには、以下の手順に従ってください。

1. 「デプロイメント計画の詳細」ページで、**「タスクのインポート」**をクリックします。

3. 「タスクのインポート」ダイアログで、**「ファイルの選択」**をクリックし、CSV ファイルを選択します。**「ファイルの選択」**フィールドにファイルをドラッグすることもできます。

6. **「インポート」**をクリックします。タスクがデプロイメント計画に追加されます。インポート処理が失敗する場合、**「レポートの表示」**をクリックしてエラー・ログを表示してください。

IBM UrbanCode Release からデプロイメント計画をインポートすると、セグメントは変換されて、元のセグメントと同じ実行パターンのグループになります。セグメント・タスクは、note タイプの Start Segment タスクおよび End Segment タスクで囲まれています。インポート中、タスク依存関係は保持されます。セグメントの依存関係は、End Segment タスクへの依存関係によって表されます。

以下の表に、IBM UrbanCode Release デプロイメント計画内のタスクを定義するフィールドを示します。CSV ファイル内の第 1 行には列ヘッダーが含まれていて、それが以下の表の**「フィールド」**欄に対応しています。2 行目以降には、タスクのデータが含まれます (1 行に 1 つのタスク)。列の順序は関係ありません。

IBM UrbanCode Release からエクスポートされたデプロイメント計画について学習するには、「タスクのインポート」ダイアログから `SamplePlan.csv` ファイルをダウンロードしてください。

CSV ファイル内にタスクを作成する場合、次の表でアスタリスク文字 (*) で示されている必須フィールドを含める必要があります。

| フィールド| 説明|
| ------------------ |------------------|
|segmentName*                 |セグメントの名前。必須フィールド。|                                                    
|name*                        |デプロイメント・タスクの名前。必須フィールド。|                                                                
|type*                        |タスク・タイプ。可能な値は、`note`、`waitfortimetask`、`ucdtask`、または `manual` です。インポート中に、このフィールドに認識できない値が含まれている場合、タスクには manual タイプが割り当てられます。|
|description                 |デプロイメント計画の説明。|                                                                                                    
|property:processId           |タスクに対応する IBM UrbanCode Deploy のプロセス ID。|
|property:task-environments   |タスクに使用可能なアプリケーション環境。|
|property:mailRecipients|通知が送信された場合に E メール・メッセージを受信するユーザーの E メール・アドレス。|
|taskTagNames                 |タスクに関連付けられているタグの名前。|
|taskPrequisiteIds         |このタスクを開始する前に完了している必要のあるタスクの ID のコンマ区切りリスト。|
|segmentPrerequisitelds       |現行セグメントとの依存関係のあるセグメントの ID のコンマ区切りリスト。|
|taskPrequisiteNames         |このタスクを開始する前に完了している必要のあるタスクの名前のコンマ区切りリスト。|
|segmentPrerequisiteNames       |現行セグメントとの依存関係のあるセグメントの名前のコンマ区切りリスト。|
|assignedUserEmail                |現行タスクに割り当てられたユーザーの E メール・アドレス。|
|executorGroup                |現行タスクに割り当てられたユーザー・グループ。|
|segmentPattern                |選択されたセグメントの実行パターン。|

{: caption="表 1. IBM UrbanCode Release デプロイメント計画フィールド" caption-side="top"}

## デプロイメント計画のコピーおよびプロモート
{: #plan_copyPromote}

デプロイメント計画のプロモートおよびコピーによって、デプロイメント計画を複製できます。元の計画の状況が`「完了」`または`「進行中」`であっても、コピーまたはプロモートされた計画の状況は`「ドラフト (draft)」`です。

計画をコピーするには、「デプロイメント計画」ページで**「この計画のコピー (Copy this plan)」**アクションを使用します。計画をコピーすると、「Copy of `plan_name`」という名前の新規計画が「デプロイメント計画」ページに挿入されます。コピーされた計画には、元の計画内に定義されているすべてのタスクが含まれます。計画内に UrbanCode Deploy タスクがある場合、元の計画で選択されたアプリケーション、バージョン、および環境は、コピーされた計画でも選択されます。アプリケーション、バージョン、および環境は、「デプロイメント計画の詳細」ページの**「バージョン」**タブに表示されます。

計画をプロモートするには、「デプロイメント計画」ページで**「この計画のプロモート」**アクションを使用します。計画をプロモートすると、「Promotion of `plan_name`」という名前の新規計画が「デプロイメント計画」ページに挿入されます。プロモートされた計画には、元の計画内に定義されているすべてのタスクが含まれます。計画内に UrbanCode Deploy タスクがある場合、元の計画で選択されたアプリケーションおよびバージョンは、プロモートされた計画でも選択されます。コピーされた計画とプロモートされた計画の相違点は、プロモートされた計画内にはアプリケーション・バージョンが設定されないことです。

## 計画テンプレートの管理
{: #plan_templates}

デプロイメント計画を変換してデプロイメント計画テンプレートを作成することができます。

テンプレートを作成するには、「デプロイメント計画」ページで**「この計画のテンプレート」**アクションを使用します。テンプレートを作成すると、「Copy of plan_name」という名前の新規計画が「デプロイメント計画」ページに挿入されます。元の計画の状況が`「完了」`または`「進行中」`であっても、テンプレートの状況は`「テンプレート」`です。テンプレートには、元の計画内に定義されているすべてのタスクが含まれます。計画内に UrbanCode Deploy タスクがある場合、元の計画で選択されたアプリケーションは、テンプレートでも選択されます。

テンプレートを使用してデプロイメントを実行することはできません。デプロイメントにテンプレートを使用するには、まずテンプレートをコピーまたはプロモートし、その後で、コピーまたはプロモートされた計画を使用します。

## デプロイメント計画の保存
{: #plan_arch}

デプロイメント計画をアーカイブに入れると、その計画の状況は `「アーカイブ済み」`になり、**「アーカイブ」**フィルターを使用しない限り、その計画は「デプロイメント計画」ページには表示されません。

アーカイブ内のデプロイメント計画を `draft` (ドラフト) 状況に復元することができます。デプロイメント計画を永久に削除することはできません。

## 復帰および復元
{: #plan_history}

すべてのデプロイメント計画について、変更およびリビジョンの履歴が維持されます。「デプロイメント計画の詳細」ページの**「変更履歴」**タブで、リビジョンを表示できます。

前のバージョンの計画に復帰するには、復元したいバージョンに対して**「復元」**アクション <img class="inline" src="images/restore-icon.png"  alt="復元アクション"> を使用します。選択したバージョンに計画が復元されます。  

## デプロイメント時間の見積もり
{: #plan_durationEst}

デプロイメントを開始する前に、予期される所要時間を見積もることができます。所要時間を見積もるには、「デプロイメント計画の詳細」ページで**「タスク時間の見積もり」**アクションを使用します。表示される時刻は、デプロイメントを今すぐ開始した場合にデプロイメントが終了する時刻です。
