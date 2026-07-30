# ms_lptest — LP管理リポジトリ

複数のランディングページ（LP）をこのリポジトリ1つで管理する。
チームメンバーはGitHub Desktop（GUI）とClaude Code（claude.ai/code）だけで
作業でき、`git` コマンドを直接叩く必要はない想定。

## フォルダ構成

```
.
├── .claude/
│   └── skills/
│       └── lp-create/        # 全LP共通のLP作成ワークフロー（スキル）
├── lps/
│   └── <lp-slug>/
│       ├── <lp-slug>-lp.html
│       └── images/
└── CLAUDE.md                 # このファイル
```

- 新しいLPは必ず `lps/<lp-slug>/` の下に作る。ルート直下やlps外に置かない。
- `<lp-slug>` は英小文字・ハイフン区切り（kebab-case）。例: `pest-control-tokyo`
- 既存LPのHTMLは直接上書きせず、方向性違いは別ファイル（`-v2` 等）で残す。

## LP作成の標準フロー

「新しいLPを作りたい、商材は◯◯」とチャットで伝えると、
[`lp-create` スキル](.claude/skills/lp-create/SKILL.md) が自動起動し、
競合リサーチ → 構成・配色の提案 → 短いQ&A → 完成HTMLまでを一気通貫で行う。
詳細な手順・注意点はスキル本体を参照（このファイルには重複記載しない）。

## チームメンバー向けの運用

- 閲覧のみ: GitHub Desktopでclone → `lps/<lp-slug>/*.html` をブラウザで開く。
- 新規LP作成: claude.ai/codeでこのリポジトリを開いてチャットするだけ。
  完了後は自動でブランチにpush・PR作成される。
- 既存ファイルの直接編集: GitHub Desktopでclone→エディタで編集→
  コミットメッセージを書いて「Commit to main」→「Push origin」。
- 他人の変更を取り込む: GitHub Desktopで「Fetch origin」→「Pull origin」。

いずれの操作も `git clone` / `git push` 等のコマンド入力は不要。
