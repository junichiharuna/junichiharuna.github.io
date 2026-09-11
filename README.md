# junichiharuna.github.io

春名純一の個人ホームページ（https://junichiharuna.github.io/）。素のHTMLとCSSだけで作っていて、ビルド工程はない。GitHub Pagesがmainブランチのルートをそのまま公開する（`.nojekyll`でJekyllの処理を止めている）。

## ページ

| ファイル | 内容 |
|---|---|
| `index.html` | Home（Interest、Keywords、What's new、Contact） |
| `publications.html` | 論文、学位論文、講義ノート |
| `talks.html` | 講演、セミナー、ポスター |
| `cv.html` | 経歴 |
| `links.html` | 便利なリンク集 |
| `hobby.html` | 趣味 |
| `style.css` | 全ページ共通のスタイル（ライトとダークの両対応） |

ナビゲーションは各ページに直接書いてある。ページを増やすときは全ページのnavを揃える（`<head>`のフォント読み込みと、名前の下の`site-kana`も同じ）。

## デザイン

論文誌風。書体はセリフ体で、英文がNewsreader、和文がShippori Mincho（どちらもGoogle Fontsから読み込む。読めない環境ではGeorgiaや游明朝に落ちる）。背景は生成りの紙色で、OSがダークテーマなら暗い配色に切り替わる。広い画面では左に名前とナビを固定したサイドバーを置き、右の本文は画面幅いっぱいに使う。48remより狭い画面ではサイドバーを上にたたむ。見出し`h2`は小さな大文字のラベルと右へ伸びる罫線。すべて`style.css`一本で、JavaScriptは使っていない。

## 更新の原則

- 論文と講演のマスターはJHLaboの`Applications/CV/publication_list.tex`。先にマスターを直し、このサイトはそこから写す。
- 論文を足したら、`publications.html`に加えて`index.html`のWhat's newにも1行足す（日付は`DD/M/YYYY`）。
- 論文にはDOIとarXivの両方をリンクする。

## 手元での確認

```
python -m http.server
```

を実行して http://localhost:8000/ を開く。

## 経緯

2020年2月14日にGoogle Sites（https://sites.google.com/view/jharuna）で開設し、2026年9月11日にこのリポジトリへ移した。
