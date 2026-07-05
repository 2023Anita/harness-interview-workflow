# Harness Interview Workflow

> 高コストな実行の前に、いったん減速する。曖昧な依頼を、盲点スキャン、インタビュー、ルート選択、承認後の実行へ変える Codex workflow。

[🇺🇸 English](README.md) · [🇨🇳 简体中文](README.zh-CN.md) · [🇯🇵 日本語](README.ja-JP.md) · [🇰🇷 한국어](README.ko-KR.md) · [多言語ショーケース](https://2023anita.github.io/harness-interview-workflow/)

![Harness Interview Workflow cover](assets/illustrations/00-cover-blindspot-ai.png)

## なぜ必要か

モデルが強くなるほど、曖昧な指示のコストは高くなります。

Harness Interview Workflow は、実行の直前に使う Codex skill です。複雑な作業、リスクのある作業、公開や GitHub、研究、ローカルファイル、承認ゲートを含む作業で、Codex がすぐに走り出す前に、まず高レバレッジな質問をします。

最初に確認すること：

- すでに分かっていることは何か。
- 分かっていないと自覚していることは何か。
- 当たり前すぎて言語化していない前提は何か。
- 完全に見えていない盲点は何か。
- どの答えが設計、リスク、成果物、検証を変えるか。

![Map versus territory](assets/illustrations/02-map-territory.png)

## Animated Architecture

この workflow は、Lanshu スタイルの動的アーキテクチャ図として可視化されています。タスクのシグナルが harness core に入り、盲点スキャンとインタビュー packets を通り、承認ゲートで止まり、承認後に再利用可能な成果物へ進みます。

![Animated Harness Interview Workflow](assets/architecture/harness-interview-workflow/harness-interview-workflow.gif)

## Core Loop

1. 目標と成果物を言い換える。
2. 盲点スキャンを行う。
3. 1 回につき 1-3 個だけ重要な質問をする。
4. 参照資料を分類してから使う。
5. 2-3 個のルートを提示する。
6. 明確な承認を待つ。
7. 実行中の逸脱を実装メモに残す。
8. 証拠、検証結果、簡単な理解チェックを渡す。

![Eight-step toolbox](assets/illustrations/05-eight-step-toolbox.png)

## Install

```bash
cp -R skills/harness-interview-workflow ~/.codex/skills/
```

Codex で呼び出す例：

```text
Use harness-interview-workflow. Start with a blindspot scan and ask only the highest-leverage questions.
```

## Quick Start Prompt

```text
Use harness-interview-workflow.
Do not execute yet.
First restate my goal, run the blindspot scan, ask only 1-3 key questions, propose routes, and wait for approval.
```

## Blindspot Scan

```text
Known knowns:
Known unknowns:
Unknown knowns:
Unknown unknowns:
Highest-risk misunderstanding:
Smallest next move:
```

![Four unknowns](assets/illustrations/03-four-unknowns.png)

## GitHub Pages

GitHub README では言語リンクを提供し、GitHub Pages では英語・中国語・日本語・韓国語をワンクリックで切り替えられます。

[多言語ショーケースを開く](https://2023anita.github.io/harness-interview-workflow/)

## License

MIT
