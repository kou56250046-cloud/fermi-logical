# 思考力トレーニング（Think Daily）

フェルミ推定・論理・推理・水平思考・三段論法・確率・規則性・クリティカル思考を、**毎日1問**じっくり鍛えるトレーニングサイトです。

- **完全無料・静的サイト**（サーバー／DB／APIキー不要）
- **PWA対応**：ホーム画面に追加してアプリのように使え、オフラインでも動作
- **完全ローカル保存**：記録はこの端末内のみ（外部送信なし）
- **PC／スマホ レスポンシブ**・緑系の落ち着いたデザイン＋アニメーション

## ファイル構成
```
thinking-training/
├─ index.html              本体（HTML/CSS/JS・問題データ内蔵）
├─ manifest.webmanifest    PWA設定
├─ sw.js                   Service Worker（オフラインキャッシュ）
└─ icons/
   ├─ icon-192.png
   ├─ icon-512.png
   └─ icon-maskable-512.png
```

## GitHub Pages で公開してリンク化する手順

1. GitHub で新しいリポジトリを作成（例：`thinking-training`）。
2. このフォルダ内の全ファイルを、フォルダ構成を保ったままアップロード（`index.html` がリポジトリ直下に来るようにする）。
   - Web上でやる場合：「Add file → Upload files」でドラッグ＆ドロップ。`icons` フォルダごと入れる。
3. リポジトリの **Settings → Pages** を開く。
4. **Build and deployment** の Source を「Deploy from a branch」にし、Branch を `main` ／フォルダ `/(root)` を選んで Save。
5. 数十秒〜数分待つと、ページ上部に公開URLが表示されます。
   - 例：`https://<ユーザー名>.github.io/thinking-training/`
6. そのURLがあなたの公開リンクです。スマホで開き、ブラウザの「ホーム画面に追加」でアプリとして使えます。

> パス指定はすべて相対パスのため、リポジトリのサブフォルダURL（`/thinking-training/`）でもそのまま動作します。

## 更新・カスタマイズ

- **問題を追加**：`index.html` 内の `const POOL = [ ... ]` に、同じ形式で1件追記すれば、その日から日替わり出題の対象になります。
- 日替わりの問題は「日付」をもとに自動選出され、同じ日は誰が見ても同じ問題、日が変われば別問題、プールを一巡したら循環します。
- **称号・レベル**は `const RANKS` で、配色は CSS 冒頭の `:root` 変数で調整できます。
- ファイルを更新したら、`sw.js` の `const CACHE = 'think-train-v1'` の番号（`v2` など）を上げると、利用者側のキャッシュが新しい内容に更新されます。

## 動作環境

- モダンブラウザ（Chrome / Safari / Edge / Firefox 等）
- PWA・Service Worker は **https**（GitHub Pages は標準でhttps）で有効になります。ローカルのファイルを直接ダブルクリックして開くと一部機能（インストール等）は制限される場合がありますが、問題演習・記録は動作します。
