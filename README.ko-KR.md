# Harness Interview Workflow

> 비싼 실행 전에 속도를 늦춥니다. 모호한 요청을 블라인드스팟 스캔, 인터뷰, 경로 선택, 승인 후 실행으로 바꾸는 Codex workflow입니다.

[🇺🇸 English](README.md) · [🇨🇳 简体中文](README.zh-CN.md) · [🇯🇵 日本語](README.ja-JP.md) · [🇰🇷 한국어](README.ko-KR.md) · [다국어 쇼케이스](https://2023anita.github.io/harness-interview-workflow/)

![Harness Interview Workflow cover](assets/illustrations/00-cover-blindspot-ai.png)

## 왜 필요한가

모델이 강해질수록 모호한 지시의 비용은 더 커집니다.

Harness Interview Workflow는 실행 직전에 사용하는 Codex skill입니다. 복잡하거나 위험하거나, GitHub, 게시, 연구, 로컬 파일, 승인 게이트가 포함된 작업에서 Codex가 바로 실행하기 전에 먼저 중요한 질문을 하도록 만듭니다.

먼저 확인하는 것:

- 이미 알고 있는 것은 무엇인가?
- 모른다는 것을 알고 있는 것은 무엇인가?
- 너무 당연해서 말하지 않은 전제는 무엇인가?
- 아직 보이지 않는 블라인드스팟은 무엇인가?
- 어떤 답이 구조, 위험, 산출물, 검증 방식을 바꾸는가?

![Map versus territory](assets/illustrations/02-map-territory.png)

## Core Loop

1. 목표와 산출물을 다시 말합니다.
2. 블라인드스팟 스캔을 합니다.
3. 한 번에 가장 중요한 질문 1-3개만 묻습니다.
4. 참고 자료를 먼저 분류합니다.
5. 2-3개의 경로를 제안합니다.
6. 명확한 승인을 기다립니다.
7. 실행 중 계획에서 벗어나면 구현 노트를 남깁니다.
8. 증거, 검증 결과, 간단한 이해 확인 퀴즈를 제공합니다.

![Eight-step toolbox](assets/illustrations/05-eight-step-toolbox.png)

## Install

```bash
cp -R skills/harness-interview-workflow ~/.codex/skills/
```

Codex에서 사용하는 예:

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

GitHub README는 언어 링크를 제공하고, GitHub Pages 쇼케이스에서는 영어, 중국어, 일본어, 한국어를 한 번의 클릭으로 전환할 수 있습니다.

[다국어 쇼케이스 열기](https://2023anita.github.io/harness-interview-workflow/)

## License

MIT
