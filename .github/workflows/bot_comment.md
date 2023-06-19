このPull Requestではtextlintが走ります．各lintのルールはサブモジュールの[paper-lintrules](https://github.com/dbgroup-nagoya-u/paper-lintrules)で管理されているため，適宜以下のコマンドでルールを更新してください．

```bash
git submodule update --remote .linter
```

### 執筆手順

必ず上から順番に行いましょう．各手順が終わったらチェックをつけてください．

- [ ] **下に表示される論文チェックリストをもとに添削を行う：**
  - 1つ下のコメントに表示されているチェックリストは，論文執筆の際の一般的な注意事項をまとめたものです．
  - 論文の内容とは関係がない（i.e.,本質的でない）部分はなるべく自力で修正しましょう．
- [ ] **textlintを参考に，可能な限り執筆・修正：**
  - 最初はReviewerを追加せず，このDraft Pull Requestで執筆・修正を続けてください．可能な限りtextlintが指摘します．
  - 漢字や送り仮名に対する微妙な指摘については[電子情報通信学会の資料（1ページ）](https://www.ieice.org/jpn/shiori/pdf/furoku_d.pdf)や[常用漢字一覧表 - 文化庁](https://www.bunka.go.jp/kokugo_nihongo/sisaku/joho/joho/kakuki/14/pdf/jyouyou_kanjihyou.pdf)を参考にしてください．
  - 修正した指摘や無視した指摘についてはResolve conversationボタンを押しておくと良いです．
  - Review commentの数が100に近づくとページの表示が重くなります．適宜Draft Pull RequestをCloseし，別のDraft Pull Requestで作業を続けてください．
- [ ] **参考文献のタイトルに含まれる固有名詞を`{}`で囲う：**
  - Bibtexではタイトルの文字が自動的に大文字や小文字に変換されます．固有名詞をそのままの文字で残すため，それらを波括弧で囲んでください．textlintからの指摘は行われないので注意してください．
    - （例）`title={... {MySQL}}`
- [ ] **このDraft Pull RequestをClose**
- [ ] **Pull Requestを作成：**
  - 元のDraft Pull RequestをCloseし，新たに（通常の）Pull Requestを作成してください．Reviewerに共著者を追加し，共著者からの指摘や議論を基に執筆・修正を続けてください．
  - 共著者の追加方法は[ここ](https://github.com/dbgroup-nagoya-u/template-latex/tree/main#%E5%9F%B7%E7%AD%86%E3%81%AE%E6%B5%81%E3%82%8C)を見てください．

### バグ報告

おかしな指摘・指摘されていないが今後プログラムで指摘可能なルールを発見した場合は，今後のために[こちら](https://github.com/dbgroup-nagoya-u/paper-lintrules/issues/new?assignees=&labels=&template=bug-report.md&title=)から指摘をお願いします．

執筆頑張ってください！
