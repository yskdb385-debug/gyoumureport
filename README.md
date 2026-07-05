# 発掘調査日報アプリ（GitHub Pages 公開手順）

## フォルダの中身
```
index.html        … アプリ本体
manifest.json      … ホーム画面追加用の設定
sw.js               … オフラインでも開けるようにするための設定（現場の電波が弱い時用）
icons/              … アプリアイコン
```
この4点セット（フォルダごと）をそのままGitHubにアップロードしてください。

## 1. GitHubにリポジトリを作る
1. https://github.com にログイン → 右上の「+」→「New repository」
2. Repository name を決める（例：`field-report`）
3. Public のまま「Create repository」

## 2. ファイルをアップロードする
1. 作成したリポジトリの画面で「Add file」→「Upload files」
2. このフォルダの中身（`index.html`, `manifest.json`, `sw.js`, `icons/` フォルダ）をすべてドラッグ＆ドロップ
   - `icons` フォルダごとドロップすれば中の画像も一緒にアップロードされます
3. 「Commit changes」

## 3. GitHub Pages を有効にする
1. リポジトリの「Settings」タブ →左メニューの「Pages」
2. 「Build and deployment」の「Source」を **Deploy from a branch** にする
3. 「Branch」を `main`（または `master`）、フォルダは `/ (root)` を選択して「Save」
4. 1〜2分待つと、ページ上部に
   `https://（あなたのユーザー名）.github.io/（リポジトリ名）/`
   というURLが表示されます。これが公開URLです。

## 4. iPadのSafariで開く
1. 上記URLをSafariで開く（**Chrome/Edgeではなく必ずSafari**。iOSではホーム画面追加とオフライン保存の相性がSafariが一番良いです）
2. 共有ボタン（□に↑の矢印のアイコン）→「ホーム画面に追加」
3. ホーム画面のアイコンから起動すると、アドレスバーのないアプリらしい見た目で動きます

## 5. データの保存について
- データはこの**ブラウザ（この端末）の中だけ**に保存されます（IndexedDBという仕組み）。他の端末や、Safari以外のブラウザで開いても見えません。
- 端末の「設定」アプリで「Safariの詳細データを消去」のような操作をすると、保存した日報データも消えてしまいます。**大事な記録は保存後にExcel出力して、こまめにファイルアプリやクラウド（iCloud Drive等）にも保存しておくことを強くおすすめします。**
- 設定画面（アプリ内）に、今どの保存先を使っているかが表示されます。

## 6. 更新のしかた
アプリの内容（`index.html`）を後から直したい場合は、GitHubの当該ファイルを開いて「Edit」→保存すれば、数分でPagesにも反映されます。
