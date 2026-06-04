# concept field

既存語を組み合わせて、新しい概念を立てる遊び。

- **concept card** … 概念を一枚に封じたもの。
- **concept deck** … カードを集めて並べたもの。

公開サイト: `https://<user>.github.io/concept-field/`

## 思想

- **造語は使わない。** 既存語の意外な隣接で、見慣れた言葉がぐらっと再発見される。
  新語を発明した人ではなく、既存語の隠れた隣接を発見した人が勝つ。
- **言語のみ、イラストなし。** 概念は言葉のまま差し出すからこそ美しい。
  足し算（リッチ）ではなく引き算（端正）。

## カードの型

Markdown の見出しに写像する。

```markdown
---
---
# 概念名（English Name）
## What ── 一行のつかみ
### 展開
```

- **h1** = 概念名（和名 + 英名）
- **h2** = What（定義というほど格式張らない一行）
- **h3** = 展開。型は固定しない（`→` のシーケンス／要素の列挙／現象の言い換え）。
  枚数も自由。

## カードを増やす

`docs/_cards/_template.md.txt` をコピーして `docs/_cards/your-concept.md` として保存する。
1 card = 1 markdown file。それ以外の作業は不要（一覧も個別ページも自動生成される）。

## 構成

```
docs/
  _config.yml        Jekyll 設定（baseurl はここ）
  index.html         deck（一覧 = 密）
  _layouts/
    default.html     共通の枠
    card.html        card（個別 = 疎）
  _cards/            1 card = 1 md
  assets/style.css   最小 CSS（色も装飾もほぼ使わない）
```

## ローカルで見る

```
cd docs
jekyll serve
```

## 公開（GitHub Pages）

リポジトリの **Settings → Pages** で、Source を `Deploy from a branch`、
Branch を `master` / フォルダ `/docs` に設定する。
独自ドメインやユーザーページで公開する場合は `docs/_config.yml` の
`baseurl` を `""` にする。
