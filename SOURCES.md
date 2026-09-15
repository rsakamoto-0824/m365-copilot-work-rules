# 参照資料

確認日：2026-09-15。製品仕様や画面は変更されるため、導入時は会社アカウントの画面でも確認する。

## Microsoft公式資料

| 資料 | 確認した事項 |
|---|---|
| [Copilotの応答をカスタマイズ](https://support.microsoft.com/en-us/microsoft-365-copilot/customize-how-microsoft-365-copilot-responds-to-you) | Chat settings、Personalization、Custom instructions |
| [Agent Builderでエージェントを作成](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents) | Configure、Instructionsの8,000文字上限、Try it、ライセンス依存 |
| [エージェントのKnowledge](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-add-knowledge) | .txt対応、.mdは対応形式一覧に未掲載、資料とエージェントの共有 |
| [ノートブックの指示](https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook) | ノートブック単位のInstructionsと保存 |
| [ノートブックの参照資料](https://support.microsoft.com/en-us/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook) | 参照資料の追加操作 |
| [Markdown・TXT・RTF参照への対応](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/copilot-notebooks-now-works-with-markdown-plain-text-and-rich-text-files/4545652) | ノートブックのMarkdown対応。検索で案内内容を確認、本文抽出は不可だったため、導入先での確認を前提とする |

Agent BuilderのKnowledge件数は公式ページ間でも記載差があるため、本資料では上限値を断定しない。必要な資料だけを選び、実際の画面の制限に従う。

## Codex側の仕組み

[Build skills](https://learn.chatgpt.com/docs/build-skills)を確認した。スキルには指示以外の実行資源も含まれ得るため、Markdownの移植とツールの移植を区別する。

## ローカルの移植元

ユーザーの共通ルール、専門ルール、個人スキルと導入済みスキルのカタログを確認した。[移植台帳](SOURCE-INVENTORY.md)には個人の絶対パスを含めず、識別用の相対名とSHA-256を記録する。

本文を再構成した手順はこのリポジトリの移植版であり、元スキルの完全な再配布ではない。参照元のスクリプトや第三者ライブラリを同梱せず、元ソフトウェアのライセンスを付け替えない。
