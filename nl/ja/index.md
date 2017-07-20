---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Continuous Release (ベータ) 入門

{: #gettingstartedtemplate}

IBM {{site.data.keyword.Bluemix_short}} の {{site.data.keyword.uccr_full}} サービスは、包括的なリリース管理ソリューションです。{{site.data.keyword.uccr_short}} を使用すると、開発ライフサイクルにおいてすべてのソフトウェア・アプリケーションのリリースおよびデプロイメントを実行できます。
{:shortdesc}

{{site.data.keyword.uccr_short}} の[インスタンスを作成した後](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")、最初に行う作業を選択してください。

* すぐに取り掛かってデプロイメント計画の作成を開始したい場合は、**[リリースの作成とデプロイメントの実行](#gs_create_plan)**から始めます。

* {{site.data.keyword.uccr_short}} をオンプレミス IBM UrbanCode&trade; Deploy インスタンスと統合したい場合は、**[DevOps Connect のインストールと構成](#gs_install_dc)**から始めます。統合を構成した後、Continuous Release タスクを使用して UrbanCode Deploy アプリケーションを管理できます。


## リリースの作成とデプロイメントの実行
{: #gs_create_plan}

1. [リリースを作成](/docs/services/UCCR/UCCR_releases.html##releases_create)し、それをいずれかのチームに割り当てます。すべてのチーム・メンバーが、そのリリースのデプロイメント計画を作成し、デプロイメントを実行することができます。

1. リリースにデプロイメント計画を追加します。

  * [計画を作成](/docs/services/UCCR/UCCR_releases.html#releases_planAdd)し、それをリリースに割り当てます。 

  * [デプロイメント計画にタスクを追加](/docs/services/UCCR/UCCR_tasks.html#tasks_create)します。各タスクは、デプロイメント計画内の別々の行にリストされます。さまざまなタイプ (手動、UrbanCode Deploy、継続的デリバリー・パイプライン、遅延実行、E メール、Slack) のタスクを追加してみてください。

  * 計画内のタスクのリストにさまざまな変更を加えることができます。タスクの位置を変更したり、タスクをコピーしたり、タスクを削除したりできます。 

4. デプロイメント計画の準備ができたら、前のステップで作成したデプロイメント計画を使用してデプロイメントを実行します。

  * [デプロイメント計画内のタスクを解決することによって、デプロイメントを実行します](/docs/services/UCCR/UCCR_deployRun.html)。タスクを解決するには、タスクを開始し、状況を`「完了」`、`「失敗」`、または`「スキップ (Skipped)」`に変更します。デプロイメント計画内のすべてのタスクが解決されると、デプロイメントの状況は「完了」になります。

  * タスクは、開始に適格である場合に開始可能です。適格かどうかは、計画の実行パターンによって決まります。デフォルトでは、計画の実行パターンは順次です。最初に、先頭 (最上位) タスクが開始に適格になります。タスクをグループ化することによって、実行パターンを変更することができます。タスク・グループでは実行パターンが並列であることが可能です。これは、グループのタスクが任意の順序で開始でき、同時に実行できることを意味します。1 つのデプロイメント計画が複数のグループを含むことができ、グループを他のグループ内にネストできます。

  * 自動タスクと呼ばれるタスクは、実行に適格になると即座に自動的に開始されます。タイプが UrbanCode Deploy および継続的デリバリー・パイプラインのタスクは、実行に適格になると、手操作による介入なしですぐに開始されます。また、自動タスクの状況は手操作による介入なしで更新されます。  

## DevOps Connect のインストールと構成
{: #gs_install_dc}

IBM Bluemix DevOps Connect は、オンプレミスの IBM UrbanCode Deploy インストール済み環境と {{site.data.keyword.uccr_short}} との間の通信を調整します。DevOps Connect をインストールした後、統合を作成できます。統合によって、{{site.data.keyword.uccr_short}} タスクを使用して UrbanCode Deploy アプリケーションを管理することが可能になります。

**前提条件**

* DevOps Connect を登録するには、IBM ID を持っている必要があります。

* ホスト・システムに [Java™ Runtime Environment バージョン 7 以降](https://java.com/en/download/){:new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") があり、そのロケーションがシステム PATH 変数に設定されている必要があります。

* UrbanCode Deploy からの管理許可トークンが必要です。   


1. DevOps Connect をインストールし、それを使用して {{site.data.keyword.uccr_short}} を UrbanCode Deploy と統合します。

  1.  {{site.data.keyword.uccr_short}} の「開始」ページで**「セットアップ」**をクリックします。

  1.  「UrbanCode Deploy 統合セットアップ」ダイアログ・ボックスで、**「ダウンロード」**をクリックして DevOps Connect をダウンロードします。UrbanCode Deploy にアクセスできるコンピューター上に JAR ファイルを置いてください。

  1.  ダイアログ・ボックスを使用して、DevOps Connect インストール・スクリプトをコピーします。このスクリプトには、DevOps Connect を開始するためのコマンドと、{{site.data.keyword.uccr_short}} Bluemix サービスを識別するために必要な資格情報が含まれています。

  1.  DevOps Connect を置いたコンピューターで、コマンド・シェルを開き、コピーしたスクリプトを貼り付けます。

  1.  スクリプトを実行します。DevOps Connect が始動メッセージを表示します。

2. DevOps Connect を登録します。

  1.  Web ブラウザーを使用して、DevOps Connect ダッシュボードを開きます。デフォルトの URL は `https://localhost:8443` です。URL を変更する場合や、他の始動オプションの詳細を知りたい場合は、[DevOps Connect 資料](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

  1.  登録ページで、DevOps Connect インストール済み環境の名前を指定します。

  1.  **「登録」**をクリックします。DevOps Connect に初めてアクセスすると、IBM ID を使用して登録するようにプロンプトが出されます。

  1.  **「IBM へのサインイン」**ページで、IBM ID とパスワードを入力し、**「サインイン」**をクリックします。サインインは、DevOps Connect を開始するたびに行います。

3. DevOps Connect で、IBM UrbanCode Deploy for Cloud Reporting プラグインを使用して、{{site.data.keyword.uccr_short}} と UrbanCode Deploy との間の統合を作成します。

    1.  DevOps Connect ダッシュボードで、**「統合」**をクリックし、**「新規追加」**をクリックします。

    1.  **「名前」**フィールドに統合の名前を入力します。

    1.  **「統合タイプ」**リストから、 **「IBM UrbanCode Deploy for Cloud Reporting」**を選択します。IBM UrbanCode Deploy for Cloud Reporting プラグインは DevOps Connect に組み込まれています。

    1.  **「サーバー URI」**フィールドに、UrbanCode Deploy サーバーのパブリック URL を入力します。例えば、`https://my_UCD.example.com:8447` です。

    1.  **「認証トークン」**フィールドに、UrbanCode Deploy によって生成された認証トークンを入力するか貼り付けます。

    1.  **「管理ユーザーの E メール」**フィールドに、E メール・アドレスを入力します。

    1.  **「保存」**をクリックします。

4.  統合を実行して、機能することを確認します。

    1.  統合ページで**「実行」**をクリックします。DevOps Connect は、**「サーバー URI」**フィールドに指定された UrbanCode Deploy インスタンスに接続します。**「認証トークン」**フィールドに貼り付けられたトークンによって DevOps Connect が認可されます。

    1.  {{site.data.keyword.uccr_short}} で、UrbanCode Deploy タイプのタスクを作成することによって、統合が成功したことを確認します。UrbanCode Deploy アプリケーションを選択できれば、統合は成功です。{{site.data.keyword.uccr_short}} インスタンスは、DevOps Connect のログインおよび始動パラメーターを使用して、UrbanCode Deploy アプリケーションを識別します。  
