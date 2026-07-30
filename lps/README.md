# lps/ ディレクトリの使い方

このフォルダの直下に、LP1本＝フォルダ1つで格納する。

```
lps/
├── <lp-slug>/
│   ├── <lp-slug>-lp.html
│   └── images/
```

## 命名規則

- フォルダ名・HTMLファイル名は英小文字・ハイフン区切り（kebab-case）。
  例: `pest-control-tokyo/pest-control-tokyo-lp.html`
- 商材名や地域名など、他のLPと混同しない具体的な名前にする。
- 既存LPのファイルは上書きしない。方向性違いを比較したい場合は
  `<lp-slug>-v2-lp.html` のように別ファイルとして残す。

## 新しいLPを作る

Claude Code（ローカル / claude.ai/code）でこのリポジトリを開き、
「新しいLPを作りたい、商材は◯◯」とチャットで伝えると `lp-create` スキルが
自動起動し、競合リサーチ→構成提案→Q&A→完成HTMLまで一気通貫で作成される。
詳細は [`.claude/skills/lp-create/SKILL.md`](../.claude/skills/lp-create/SKILL.md) を参照。
