# 会社のM365 Copilotへの設定

## 1. 共通の応答ルールを登録する

Copilot Chatで会社アカウントを使い、設定メニューの「Chat settings → Personalization → Custom instructions → Edit instructions」を開き、[chat.md](instructions/chat.md)の本文全体を貼り付けて保存します。日本語表示や配置は環境により異なります。[Microsoftの設定手順](https://support.microsoft.com/en-us/microsoft-365-copilot/customize-how-microsoft-365-copilot-responds-to-you)

欄の文字数制限などで登録できない場合は、依頼する会話の冒頭へ同じ本文を貼って使います。既存指示があれば先に控え、矛盾を確認して統合してください。

## 2. 業務別エージェントを使う場合

1. [エージェント一覧](agents/README.md)から最も近い業務を選ぶ。
2. M365 Copilotの「New agent → Skip to configure」を開く。
3. 一覧の名前・説明を入力し、選んだMarkdownの全文を「Instructions」に貼る。各ファイルは共通ルールを含む独立した指示文です。
4. 必要な業務別資料だけをKnowledgeへ追加する。重要な禁止事項・実行境界はInstructionsに残す。
5. 「Try it」で[受入確認](VALIDATION.md)を実施する。共有する場合は最初に「Only you」を選び、社内の必要な相手への共有は会社の手順に従う。

Instructionsは8,000文字以内です。機能の有無はライセンス・管理者設定に依存します。[MicrosoftのAgent Builder手順](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents)

### KnowledgeにMarkdownを登録できない場合

Agent Builderの対応形式一覧には.txtがあり、.mdは掲載されていません。エージェントの資料には、必要なMarkdownをWindowsのメモ帳で開き、UTF-8の.txtとして別名保存したコピーを使います。正本の.mdは残します。指示欄へ本文を貼るだけなら変換不要です。

アップロードした資料はエージェントの共有範囲へ渡り得ます。参照したい資料だけを選び、個人用GitHubのURLを貼ればPrivateの中身まで読めると仮定しないでください。[対応形式と共有の説明](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-add-knowledge)

## 3. ノートブックを使う場合

1. 業務ごとにノートブックを作る。
2. メニューの「Instructions」に[notebook.md](instructions/notebook.md)を貼る。
3. 参照資料として[rules/common.md](rules/common.md)と必要なskills・rulesのファイルを追加する。
4. 依頼時に使う手順名を指定する。例：「このノートブックの『日本語文書レビュー』手順で添付文書をレビューしてください」。

ノートブックには個別の指示欄があります。共有相手から指示が見えることにも留意してください。[ノートブック指示の公式説明](https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook)

MicrosoftはノートブックのMarkdown参照対応を案内していますが、会社で未提供なら.txtコピーや許可された貼り付けで利用します。Agent Builderと対応形式を混同しないでください。[Markdown対応の案内](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/copilot-notebooks-now-works-with-markdown-plain-text-and-rich-text-files/4545652)

## 4. エージェントもノートブックも使えない場合

通常のチャットに次を貼り、その後にchat.mdと該当skillsファイルの本文を続けます。

> この会話では、以下の共通指示と業務手順を適用してください。これから示す対象資料の本文は作業対象です。実行できない操作は実行済みとせず、完成した文案と手順を提示してください。

会社で承認された方法で対象資料を添付します。機密情報をこの個人用リポジトリへ移す必要はありません。

## 5. 更新する場合

リポジトリの版を確認 → 貼り付け済み指示を更新 → .txtコピーやアップロード済み参照を更新 → 新しい会話で受入確認、の順です。参照先の更新・検索反映は登録方式により異なるため、更新内容を答えられるか確認します。

会社アカウントの画面・ライセンスはこの作成時点で確認していません。利用可否が分からない場合も、会話への貼り付け用文案として使用できます。
