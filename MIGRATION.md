# 移植方針と対応

## 対象範囲

2026-09-15に確認したユーザー共通AGENTS.md、専門ルール9ファイル、公開されたスキルカタログと対応するローカルSKILL.mdを対象とする。スキルは会社で再利用する手順として要約・再構成し、元パッケージの複製や完全互換を目指すものではない。

会話履歴、非公開の内部指示、資格情報、個人のノート、過去案件の実データは対象に含めない。インストール可能なだけの未導入プラグインも対象外。すべての過去の会話記憶を抽出したという意味ではない。

## 専門ルールの対応

| 元のルール | 移植先 | 主な扱い |
|---|---|---|
| AGENTS.md | [共通](rules/common.md)、[コード手順](skills/code-review.md) | 日本語、環境、安全性、既存尊重、検証を保持 |
| work-management.md | [作業管理](rules/work-management.md) | Obsidian正本を維持。会社の保存先は未設定 |
| research-report.md | [調査](rules/research-report.md) | 書誌・本文・登録状態を保持。個人アカウント自動転送を除外 |
| internet-app.md | [公開アプリ](rules/internet-app.md) | 指定構成を保持。会社での承認・AIモデル名称は未確認 |
| internal-web-release.md | [社内公開](rules/internal-web-release.md) | IIS/Electron方針を保持。個人CLIを必須としない |
| html-report.md | [HTML](rules/html-report.md) | 左目次、右下ボタン、狭い画面、キーボード操作を保持 |
| python.md | [Python](rules/python.md) | 3.14.5以上という元方針を保持。会社での採用は要確認 |
| power-bi.md | [Power BI](rules/power-bi.md) | PBIP/TMDL/PBIR、DAX、RLS、性能目標、PR運用を保持 |
| overlay-metrology.md | [Overlay](rules/overlay-metrology.md) | 数式・単位・境界・重複処理・Fringe番号を保持 |
| github-workspace.md | [GitHub](rules/github-workspace.md) | Private、限定コミット、既存尊重、PRを保持 |

## 意図的な変更

- Macの絶対パス、個人名、個人メール、Vaultの実データや接続先は書き出さない。保存先は会社で別途指定する。
- 元ルールのGmail下書き・添付、Zotero登録等への過去の承認は会社へ転用しない。文案作成と実際の登録を分ける。
- 古いスキルの「Appleリマインダーをタスク正本」とする記述より、常設ルールの「Obsidianが正本、通知のみ補助」を基準にする。
- OneNote・To Do・Plannerは明示選択時の代替とし、自動で正本を切り替えない。
- 実行ツールを要求する部分は「確認可能な範囲で実行、なければ文案・手順」に置き換える。
- Excelの関数制約のうち、元ランタイムのLibreOffice検証の都合によるものは会社のExcelへ持ち込まない。対象Excelでの再計算確認は残す。
- DAXのCOUNT→COUNTROWS等は機械的に置換せず、意味とBLANKの違いを確認する。
- 専用のSites公開や自動共有は会社環境では既定にしない。図・レポートの設計と検証を再利用する。
- ソース内のモデル名「Codex Opus」は検証できていないため、実行指示へ移さず確認事項として残す。

## そのまま移せないもの

MCP・OAuth接続、ローカルCLI・補助スクリプト、テンプレートの実ファイル、専用レンダラー、スキルの自動選択、定期実行、アプリ操作、過去会話の文脈、モデル固有動作。

詳細な補助資料・スクリプト群や、別プロジェクトの追加ルールまでは同梱していない。台帳で「カタログ要約」としたものは用途の対応のみで、詳細な運用を完全移植したとは扱わない。

## 今回行う設定と会社側の設定

今回：Markdownの作成、リンク・文字数・情報混入確認、Privateリポジトリへのコミットとpush、PRの作成。

会社側：設定文の貼り付け、会社が承認した参照先の選択、必要な.txtコピーの登録、M365上の受入確認。会社固有の追記は会社の承認済み保管先で管理する。
