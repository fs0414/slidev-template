# Slidev Common Template

## 🎨 デザインの特徴

- **oklch color space**: モダンなカラーパレット（Purple to Blue gradient）
- **レスポンシブタイポグラフィ**: clamp()を使用した自動調整
- **グラデーション見出し**: アニメーション付き
- **曲線アンダーライン**: 視覚的なアクセント
- **View Transition対応**: モダンブラウザの新機能サポート
- **Emoji統合**: Twemoji対応
- **ダークモード**: 自動切り替え対応

## 🚀 セットアップ

### 1. 依存関係のインストール

```bash
bun install
```

### 2. 開発サーバーの起動

```bash
bun run dev
```

ブラウザで http://localhost:3030 が自動的に開きます。

### 3. ビルド

```bash
bun run build
```

静的ファイルが `dist/` ディレクトリに生成されます。

### 4. PDF/PPTX/PNG エクスポート

```bash
bun run export
```

初回実行時に playwright-chromium が自動インストールされます。

## 📝 カスタマイズ方法

### frontmatter設定（slides.mdの先頭）

```yaml
---
theme: seriph              # テーマ (seriph, default, geist)
title: タイトル             # プレゼンテーションタイトル
transition: slide-left     # トランジション効果
highlighter: shiki         # シンタックスハイライター
lineNumbers: false         # 行番号表示
download: true             # ダウンロード機能
mdc: true                  # MDC構文
---
```

### スタイルのカスタマイズ

`style.css`で以下の変数を変更できます:

```css
:root {
  --color-primary: oklch(0.6 0.2 270);     /* メインカラー */
  --color-secondary: oklch(0.65 0.2 240);  /* セカンダリカラー */
  --color-accent: oklch(0.7 0.18 210);     /* アクセントカラー */
}
```

## 🎯 よく使うスタイルクラス

### グラデーション見出し

```html
<h1 class="gradient-heading">美しいグラデーション</h1>
```

アニメーション付きのグラデーション効果を適用します。

### 曲線アンダーライン

```html
<span class="curved-underline">強調したいテキスト</span>
```

テキストに曲線のアンダーラインを追加します。

### アニメーション付きテキストシャドウ

```html
<h1 class="animated-shadow">輝くテキスト</h1>
```

テキストにパルスアニメーションのシャドウを追加します。

### スライド背景グラデーション

```yaml
---
class: slide-gradient-bg
---
```

スライド全体に微妙なグラデーション背景を適用します。

### Emoji

```html
<span class="emoji">👋</span>
```

絵文字を適切なサイズと配置で表示します。

## 📐 レイアウトパターン

### 2カラムレイアウト

```markdown
---
layout: two-cols
---

# 左側のコンテンツ

テキストやリストなど

::right::

# 右側のコンテンツ

コードやイメージなど
```

### センターレイアウト

```markdown
---
layout: center
class: text-center
---

# 中央に表示されるコンテンツ
```

### カスタムグリッド

```html
<div class="grid grid-cols-2 gap-8">
  <div>左側</div>
  <div>右側</div>
</div>
```

## 🎬 アニメーション

### v-click（クリックで表示）

```html
<v-click>

クリックで表示される内容

</v-click>
```

### v-clicks（複数要素を順次表示）

```html
<v-clicks>

- 項目1
- 項目2
- 項目3

</v-clicks>
```

### コードハイライト

```markdown
\`\`\`ts {2-4|6-8|all}
// 行2-4をハイライト → 行6-8 → 全体
const code = 'example'
\`\`\`
```

## 🎨 カラーパレット

テンプレートで使用している oklch カラー:

- **Primary**: Purple (270度)
- **Secondary**: Blue-Purple (240度)
- **Accent**: Blue (210度)

色相（hue）を変更することで、簡単にカラースキームをカスタマイズできます。

## 📚 参考資料

- [Slidev公式ドキュメント](https://ja.sli.dev/)
- [Slidevテーマギャラリー](https://sli.dev/themes/gallery.html)
- [MDC構文](https://sli.dev/features/mdc)
- [oklch color space](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch)

## 🛠️ トラブルシューティング

### ポートが既に使用されている

```bash
# ポートを変更して起動
bun run dev -- --port 3031
```

### PDFエクスポートが失敗する

```bash
# playwright-chromiumを手動インストール
bunx playwright install chromium
```

### スタイルが反映されない

- ブラウザのキャッシュをクリア
- 開発サーバーを再起動

## 📄 ライセンス

このテンプレートはMITライセンスで提供されています。

---

Made with ❤️ using [Slidev](https://sli.dev/)
