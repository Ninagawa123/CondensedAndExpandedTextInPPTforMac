# 長体・平体 PPT for Mac

PowerPoint for Mac には Illustrator/InDesign のような**文字の水平比率/垂直比率**プロパティが存在せず、日本語DTPで多用される **長体 / 平体** をそのままかけることができません。

このツールは、**源ノ角ゴシック / 源ノ明朝** のテキストをブラウザ上で **SVG アウトラインパス**に変換し、PowerPoint に貼付 → 「シェイプに変換」 → 縦横を非比例スケール、というワークフローで擬似的に長体・平体を実現します。

## ライブデモ

**[https://ninagawa123.github.io/CondensedAndExpandedTextInPPTforMac/](https://ninagawa123.github.io/CondensedAndExpandedTextInPPTforMac/)**

Chrome 推奨（Clipboard API の SVG 対応差のため）

## 使い方

1. ページを開く
2. **ファミリー**（源ノ角ゴシック / 源ノ明朝）と**ウェイト**を選択
3. **テキスト**を入力（改行可）
4. **「SVGをダウンロード」** をクリック
5. ダウンロードした `.svg` を PowerPoint のスライドに**ドラッグ&ドロップ**（または「挿入 &gt; 画像 &gt; このデバイス」から選択）
6. 挿入されたSVGを**右クリック → 「シェイプに変換」**
7. シェイプを縦横に**非比例スケール** → 長体・平体完成

> **PowerPoint for Mac はクリップボード経由の SVG 貼付に対応していない**ため、上記のダウンロード方式を推奨します。Windows 版 PowerPoint 365 なら「SVGをコピー」→ <kbd>Ctrl</kbd>+<kbd>V</kbd> でも貼付可能です。

## フォントの扱い

- **Regular / Bold** はサイトに同梱（両ファミリー合計 4 ファイル、約 80MB）
- 他のウェイト（ExtraLight / Light / Normal / Medium / SemiBold / Heavy）は初回選択時に [jsDelivr CDN](https://www.jsdelivr.com/) から [Adobe 公式リポジトリ](https://github.com/adobe-fonts) 経由で自動取得
- 取得済みフォントはブラウザの **IndexedDB** にキャッシュされ、次回以降オフラインでも即座に利用可能
- 「詳細オプション」から**全ウェイトの一括プリフェッチ**も可能

## 対応環境

- macOS + Chrome / Edge（Chromium系ブラウザ）
- Safari は Clipboard API の SVG 対応が限定的なため、コピーが機能しない場合があります（その場合は「SVGをダウンロード」を使用）

## ローカルで使う

このリポジトリを clone / ダウンロードし、`index.html` をブラウザで開くだけです（ビルド不要）。

```bash
git clone https://github.com/Ninagawa123/CondensedAndExpandedTextInPPTforMac.git
cd CondensedAndExpandedTextInPPTforMac
open index.html
```

## 依存

- [opentype.js](https://opentype.js.org/) v1.3.4 — フォント解析とパス化（CDN 読込）

## ライセンス

- **コード**: [MIT License](./LICENSE)
- **同梱フォント（源ノ角ゴシック / 源ノ明朝 Regular・Bold）**: [SIL Open Font License 1.1](./fonts/LICENSE.txt) — © Adobe

## 参考

- [Source Han Sans (Adobe)](https://github.com/adobe-fonts/source-han-sans)
- [Source Han Serif (Adobe)](https://github.com/adobe-fonts/source-han-serif)
