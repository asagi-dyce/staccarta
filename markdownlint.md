# markdownlintの設定
Staccarta向けの`.md`原稿でmarkdownlintを使う場合は、空行や見出しに関する検査を調整します。markdownlintを使っていない場合、この設定は不要です。

## 設定する
1. Staccarta原稿を置くフォルダーをVS Codeで開きます。
2. そのフォルダーに`.markdownlint.json`を作り、次を保存します。既存の設定がある場合は、以下の項目を追加・変更してください。

```json
{
  "MD001": false,
  "MD003": false,
  "MD012": false,
  "MD013": false,
  "MD022": false,
  "MD025": false,
  "MD031": false,
  "MD032": false,
  "MD041": false
}
```

この設定は、そのフォルダーと配下の通常のMarkdown文書にも適用されます。Staccarta向けの原稿を別フォルダーへまとめ、そこに設定を置くと範囲を絞れます。配下に別の設定ファイルがある場合は、そちらの設定が優先されることがあります。

## 調整する理由
| ルール | 無効にする理由 |
| --- | --- |
| MD001 | 見出しの中間レベルを省略できるため |
| MD003 | `=`下線のタイトルと`#`の見出しを併用するため |
| MD012 | 空行2個以上に意味があるため |
| MD013 | 行の長さを揃えるための改行が、出力の改行も変えるため |
| MD022 | 見出し前後の空行を必須にしないため |
| MD025 | 文書タイトルとは別にレベル1の節を複数置けるため |
| MD031 | コードブロック前後にも空行なしで本文を置けるため |
| MD032 | リスト前後に空行なしで本文を置けるため |
| MD041 | タイトルやレベル1見出しで始める必要がないため |

ほかの検査は残ります。markdownlintの解析は通常のMarkdownを前提としており、この設定でStaccarta専用の検査に切り替わるわけではありません。既定では、言語モードがStaccartaの`.stca`はmarkdownlintの対象外です。

別のフォーマッターを使っている場合、その設定は別途確認してください。この設定が調整するのはmarkdownlintの警告と自動修正だけです。

参考：[markdownlintの設定方法](https://github.com/DavidAnson/vscode-markdownlint#configure)、[ルール一覧](https://github.com/DavidAnson/markdownlint/blob/main/doc/Rules.md)
