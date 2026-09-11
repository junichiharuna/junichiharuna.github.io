# junichiharuna.github.io

春名純一の個人ホームページ（https://junichiharuna.github.io/）。素のHTMLとCSSだけで作っていて、ビルド工程はない。GitHub Pagesがmainブランチのルートをそのまま公開する（`.nojekyll`でJekyllの処理を止めている）。

## ページ

| ファイル | 内容 |
|---|---|
| `index.html` | Home（名前の下に業績プロフィールへのリンク、Interest、Keywords、What's new、Contact） |
| `research.html` | 研究概要（3テーマ）とセミナー主催者向けのShort bio |
| `publications.html` | 論文、学位論文、講義ノート、ソフトウェアとデータ |
| `talks.html` | 直近の予定（Upcoming）、講演、セミナー、ポスター。2026年の4講演はスライドPDFへリンク |
| `cv.html` | 経歴。英語CVのPDF（`cv.pdf`）へのリンク |
| `links.html` | 便利なリンク集 |
| `hobby.html` | 趣味 |
| `style.css` | 全ページ共通のスタイル（ライトとダークの両対応） |
| `cv.pdf` | 英語CV。マスターはJHLaboの`Applications/CV/cv_en.tex`で、そこで`latexmk -pdf`したPDFをコピーする |
| `slides/` | 講演スライドのPDF。マスターはJHLaboの`slides/<日付_名前>/`で、ビルドした`out/*.pdf`をコピーする |
| `favicon.svg`、`og.png` | タブのアイコンと、SNSやSlackにURLを貼ったときのプレビュー画像（1200×630） |
| `sitemap.xml`、`robots.txt` | 検索エンジン向け。ページを増やしたら`sitemap.xml`にも足す |

ナビゲーションは各ページに直接書いてある。ページを増やすときは全ページのnavを揃える（`<head>`のフォント読み込み、`description`とOGPのmeta、`favicon`、名前の下の`site-kana`も同じ）。`index.html`の`<head>`にはJSON-LDのPerson情報があり、外部プロフィール（ORCID、Google Scholar、INSPIRE-HEP、arXiv、researchmap、GitHub）を`sameAs`に列挙している。名前の下の`profiles`行と同じ集合に保つ。

## デザイン

論文誌風。書体はセリフ体で、英文がNewsreader、和文がShippori Mincho（どちらもGoogle Fontsから読み込む。読めない環境ではGeorgiaや游明朝に落ちる）。配色はMonokai由来で、OSがダークテーマなら背景`#272822`、本文`#f8f8f2`、リンクは水色`#66d9ef`、現在ページの印とWhat's newの罫線はピンク`#f92672`。ライトはそれを薄めた白地に、少し暗い水色と赤みのピンク。色は`style.css`冒頭の`:root`の変数（`--accent`がリンク、`--mark`が印）にまとめてある。広い画面では左に名前とナビを固定したサイドバーを置き、右の本文は画面幅いっぱいに使う。48remより狭い画面ではサイドバーを上にたたむ。見出し`h2`は小さな大文字のラベルと右へ伸びる罫線。すべて`style.css`一本で、JavaScriptは使っていない。

## 更新の原則

- 論文と講演のマスターはJHLaboの`Applications/CV/publication_list.tex`。先にマスターを直し、このサイトはそこから写す。
- 論文を足したら、`publications.html`に加えて`index.html`のWhat's newにも1行足す（日付は`DD/M/YYYY`）。
- 論文にはDOIとarXivの両方をリンクする。
- `talks.html`のUpcomingには開催前の講演だけを置く。終わったら該当の節（English talks、Japanese talks、Seminar）へ移し、スライドがあれば`slides/`にPDFを置いて`[slides]`のリンクを足す。
- `cv.pdf`は事実が変わったらJHLabo側の`cv_en.tex`を直してビルドし直し、PDFを差し替える（「Last updated」の月も更新）。
- What's newには論文、講義ノート、サイトの大きな変更だけを書く（「Interest updated」のような更新記録は書かない）。

## 手元での確認

```
python -m http.server
```

を実行して http://localhost:8000/ を開く。

## 経緯

2020年2月14日にGoogle Sites（https://sites.google.com/view/jharuna）で開設し、2026年9月11日にこのリポジトリへ移した。
