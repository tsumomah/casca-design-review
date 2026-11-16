# CASCA Design Review

UI/UX のレビューと、画面設計の判断の進め方を Claude に渡すプラグインです。東京の UI デザインスタジオ CASCA が、実務で使っている基準を誰でも使える形にまとめました。

## 入っているスキル

| スキル | 使うとき | 返すもの |
|---|---|---|
| `ui-review` | 画面・コンポーネント・プロトタイプ・スクリーンショット・URL・フロントエンドのコードを、出す前に見てほしいとき | 欠陥を「致命・改善・好み」に分け、どこが・誰がどう困るか・どう直すかを書いた一覧 |
| `ui-design-process` | 画面や機能を新しく設計する、作り直す、見せ方を決めるとき | 狙い → 文脈 → 構造 → 画面 → 細部 → 検証の順に、段ごとに決めることと、決めたと言える形 |

## 見るところ

- 12の状態（読み込み中・結果が0件・エラー・無効・最初の空・フォーカス・hover など）の抜け
- アクセシビリティを数値で判定（コントラスト比、当たり判定 44×44px、フォーカスの表示、320px 幅、200% の拡大）
- 言葉（ボタンと見出しの一致、エラーの書き方、placeholder だけの入力欄）
- 一貫性、視覚の優先順位、幅を変えたときの崩れ
- AI が結果を作る画面の、出所・確かさ・生成中・一部だけの直し

## 入れ方

claude.ai・デスクトップ・Cowork では、カスタマイズの画面のプラグインの一覧から追加します。Claude Code では次の1行で入ります。

```
/plugin install casca-design-review --marketplace tsumomah/casca-design-review
```

## 使い方

入れたあと、Claude に次のように頼みます。

- 「この画面をレビューして」（スクリーンショット、URL、コードを添える）
- 「この機能の画面を設計して」

## 動作について

このプラグインは手順と基準を書いた文書（スキル）だけで、プログラム・MCP サーバー・フックは含みません。外部へのデータ送信や取得は行いません。レビューで画面を描画するときは、使っている環境にあるブラウザやプレビューの機能を使います。

## English

CASCA Design Review gives Claude two skills from CASCA, a UI design studio in Tokyo. `ui-review` audits screens, components, prototypes, screenshots, URLs or front-end code before release, and returns every defect sorted into critical, improvement and preference, each with where it is, who it hurts and how to fix it. It checks twelve interaction states, accessibility by measured numbers (contrast ratios, 44×44px touch targets, focus indicators, 320px width, 200% zoom), interface copy, consistency, visual priority, responsive behavior, and the specific needs of AI-generated results. `ui-design-process` guides the design of new screens through intent, context, structure, screen, detail and verification, and states what must be decided at each step. The plugin contains only instruction documents: no programs, MCP servers or hooks, and it sends or fetches no data. The skills are written in Japanese; Claude can apply them in any language.

## ライセンス

MIT License。詳しくは [LICENSE](LICENSE) を見てください。
