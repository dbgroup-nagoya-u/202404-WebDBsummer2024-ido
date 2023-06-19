# LaTeX用テンプレートリポジトリ <!-- omit in toc -->

LaTeXによる文書作成のためのテンプレートリポジトリです．[paper-lintrules](https://github.com/dbgroup-nagoya-u/paper-lintrules)で指定したルールに基づいて各種linterを動作させ，文章の質を向上させることを目的としています．主な機能は以下の2つです．

1. VS Code上でのリアルタイム文章校正．
    - [textlint](https://textlint.github.io/)との連携により「読みにくそうな表現」が執筆と同時に指摘されます．
2. GitHub Actionsによるlint結果のPull Requestへの反映．
    - textlintでは指摘できない問題（e.g., LaTeXで非推奨な記法）をPull Request作成時に指摘します．
    - (1)と同様のtextlintの結果も得られるため，自身では修正案が思いつかない場合はlint結果を基に共著者と相談できます．

また，コンパイルに必要なソースファイルを`src`以下に集約し，かつ中間ファイルはワークスペースディレクトリに生成されるよう設定しているため，原稿投稿時は単に`src`ディレクトリを圧縮するだけでよいようにしています．

[テンプレートの具体的な利用方法についてはWikiにまとめている](https://github.com/dbgroup-nagoya-u/template-latex/wiki/%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AE%E5%88%A9%E7%94%A8%E6%89%8B%E9%A0%86)ためそちらを参照してください．以下は想定する執筆の流れです．

## 執筆の流れ

### ドラフト用ブランチを作成

```bash
git switch -c draft
git commit --allow-empty -m "初稿"
git push -u origin HEAD
```

### Lint用Draft Pull Requestを作成

- GitHubの自分のリポジトリに移動し`draft`ブランチから`main`ブランチへのPull Requestを作成する．
    - 一度ボタンを押すとOpen a pull requestと表示された画面に移動するため，緑色のボタンにかかれている▼の部分から **`Create draft pull request`** を選択する．
    - Pull Requestの作成と同時にbotによってコメントが書き込まれるため，内容を確認後執筆を始める．

### 共著者へレビューを依頼

- 執筆後，共著者をリポジトリに招待して確認と添削をお願いする．
    - GitHubの自分のリポジトリで`settings`-`Manage access`を選択し，`Invite teams or people`と書かれている緑色のボタンを押して共著者を追加する．その際`Write`以上の権限を付与する．
    - Pull Requestの最下部にあるReady for reviewと書かれたボタンを押す．
    - Pull Requestのreviewsに共著者を追加し，確認と添削をお願いする．
    - 添削後再び確認をお願いする場合は`review request`ボタンを押して通知を送る．
- 一旦原稿を`main`にマージした場合は，再度Pull Requestの作成から繰り返す．

### （査読付き論文の場合）

- 査読付き論文の場合は投稿時のコミットにタグ（e.g., `submit`）を付ける．
- 条件付き再録となった場合は，同様に再録原稿のコミットにタグ（e.g., `revision`）を付与する．
- 採択された場合はたいてい最終稿の作成が必要となるため，最終稿を作成し同様に最終稿を示すタグ（e.g., `camera-ready`）を付与する．

### 最終稿投稿後の処理

- 最終稿を投稿したらOneDriveへバックアップを残す．
    - 各原稿用の`/dbgroup/archive/yyyy04/${YOUR_NAME}/papers/${CONFERENCE_NAME}`ディレクトリを作成する．
    - 最終原稿（`paper.pdf`）およびソースファイル一式（`src.zip`）を作成したディレクトリにアップロードする．
- IssueやPull Requestsの整理を終えたらリポジトリをアーカイブ状態に設定する．
    - 自分の論文リポジトリから`settings`-`Danger Zone`-`Archive this repository`を選択することでアーカイブできる．

## 謝辞

本リポジトリの作成，特にlinterの設定は学生の皆さんが中心となって行ってくれました．ここに記して謝意を示します．

### Contributors

- `Yang-33`
- `nrkt`
- `manabinohibi`
- `shiyunya`
- `tyamamoto7`
