# Good To Talk 🛡️🧼

**An open-source AI Agent Skill for anyone who wants to filter hurtful messages into useful information — without turning insults into "constructive criticism."**

**상처 주는 말은 걸러내고, 유효한 피드백과 다음 행동만 건지는 멘탈 보호형 AI Agent Skill.**

[English](#what-it-does) · [한국어](#한국어) · [Examples / 사용 예시](./examples/demo.md) · [Agent install prompt](./AGENT_INSTALL.md) · [SKILL.md](./SKILL.md)

> No email integration. No account access. No automatic sending. Copy, paste, and get a calmer version of what actually matters.

## What it does

| Feature | What you get |
| --- | --- |
| 🛡️ **Emotional safety first** | Filters out mockery and unsupported value judgments instead of rephrasing them as milder insults. |
| 🧼 **Safe message translation** | Delivers concrete situations, requests and next steps in calm, readable language. |
| 🔎 **Valid criticism extractor** | Separates specific issues, **reported but unverified claims**, missing evidence and actions. Says when there is no actionable feedback. |
| 🧠 **Playful possible concerns** | Optional, clearly speculative interpretations for a lighter perspective — not mind-reading. |
| ✉️ **Firm reply rewriting** | Turns your own frustrated draft into a professional message without surrendering your position. |

**Korean-first, English-supported.** Useful across professions: customer support, sales, operations, product management, engineering, design, HR, education, and everyday workplace communication.

### The key change in v2

A polite-looking sentence can still hurt. The skill now **does not echo negative judgments if they carry no useful evidence**. It gives you the useful signal instead.

- **Concrete bug, risk, metric or request?** Preserve it, mark what is not verified, and extract the next step.
- **Vague complaint?** Acknowledge there was a report, but don't promote it to a proven defect. Ask for reproduction details.
- **Mockery without substance?** No invented criticism. Say there is nothing actionable to address.
- **Urgent production/security issue?** Keep it urgent; do not soften away real risk.

## Demo 1 — Insult without useful feedback

**Original**

> 이딴 것도 오픈소스라고 만듦? ㅋㅋ

**🧼 말랑말랑 번역 / Gentle translation**

> 이번 메시지에는 구체적인 수정 사항이나 개선 요청이 없어요. 지금 바로 처리할 작업은 없습니다. 📭

**🔎 유효한 비판 / Valid criticism**

> 구체적인 근거 또는 개선 요청이 없어, 현재 반영할 피드백은 없습니다.

The skill **does not** invent "your project is not ready to be open source" as a factual criticism.

## Demo 2 — Technical concern with a useful question

**Original**

> 확장성이 전혀 고려되지 않은 상태로 보입니다. 설계 단계에서 어떻게 고려되었는지 확인 부탁드립니다.

**🧼 말랑말랑 번역 / Gentle translation**

> 향후 확장 시 변경 범위를 확인하고 싶다는 요청이에요. 설계 당시 고려된 요구사항이나 제약조건을 공유해 주시면 검토에 도움이 되겠습니다.

**🔎 유효한 비판 / Valid criticism**

- **Known:** Someone requested the original design rationale.
- **Unverified concern:** The architecture may be costly to extend; no supporting scenario was included.
- **Next step:** Review design decisions and ask for the concrete expansion scenario.

**🧠 본심 추측 / Possible inner thoughts** *(speculation only)*

> “혹시 이거 수정 범위가 커지는 작업일까요? 먼저 지도를 좀 보고 싶어요… 🗺️”

See [additional cases](./examples/demo.md), including vague complaints, real performance feedback, outgoing replies and neutral messages.

## Install

### A. Ask your AI agent to install it

Share this URL with an agent that can open GitHub repositories:

`https://github.com/roseline124/good-to-talk`

Then paste:

```text
Install the Good To Talk Agent Skill from https://github.com/roseline124/good-to-talk.
Read SKILL.md and use the skill-installation method supported by your environment.
If persistent installation isn't possible, read and apply SKILL.md in this conversation.
Tell me whether installation succeeded or the instructions are active only for this chat.
Do not request email access or send any messages.
```

An assistant that cannot access repository contents or persist skills cannot guarantee installation. See the [Korean/English copy-paste prompts](./AGENT_INSTALL.md).

### B. Agent Skills CLI (compatible environments)

```bash
npx skills add roseline124/good-to-talk
```

Select your agent when prompted. Compatibility and global options depend on the [skills CLI](https://github.com/vercel-labs/skills) and your agent.

### C. Manual / chat-only

Load [SKILL.md](./SKILL.md) from a supported `good-to-talk/` skill directory, or paste its content into an AI chat / project instructions. No extra server, API key, Python runtime or mailbox permissions are needed for this prompt-based skill.

## Try it

```text
Good To Talk로 번역해줘. 상처 주는 평가는 걸러내고, 유효한 비판과 다음 행동만 알려줘:
"하... 이 코드 못쓰겠네."
```

```text
이 메일을 1) 말랑말랑 번역 2) 유효한 비판 3) 유쾌한 본심 추측으로 분석해줘:
"확장성이 전혀 고려되지 않은 상태로 보입니다. 설계 당시 고려사항을 공유해 주세요."
```

```text
내가 보낼 답장인데 비꼼은 지우고 정중하지만 단호하게 고쳐줘:
"아니 설계도 안 보고 왜 단정하시는데요? 근거부터 보내세요."
```

```text
Filter the insults from this PR review and extract actionable criticism:
"Did you even test this? Nobody writes production code like this."
```

## Principles

1. **Protect the reader without lying.** No manufactured reassurance or fake positivity.
2. **Don't launder insults.** Unsupported mockery never becomes an authoritative negative assessment.
3. **Preserve valid technical signals.** Keep precise facts, requests, numbers, deadlines and risks, distinguishing verified from reported.
4. **Separate comments from evidence.** “Someone disliked this” ≠ “This is defective.”
5. **No mind-reading.** Inner thoughts are explicitly speculative, humorous interpretations, not facts.
6. **No automatic email access or sending.** Users own their data and decide whether to use a rewrite.
7. **Respect privacy.** Redact secrets, personal data and confidential company/customer details before pasting text into an AI model.

## 한국어

**Good To Talk**은 **직군과 무관하게** 업무 메일, 고객 응대, 협업 채팅, 피드백, 리뷰 등에서 마주치는 공격적인 표현을 필요한 정보만 남기고 받아들이도록 돕는 **독성 말투 정화 / 유효한 비판 추출 / 정중한 답장 작성 AI 에이전트 스킬**입니다.

기존에는 "이딴 것도 오픈소스라고 만듦?"이라는 조롱을 "공개하기에는 아쉬운 점이 있네요"처럼 바꾸면서, **근거 없는 공격을 실제 품질 평가처럼 전달하는 문제**가 있었습니다.

v2에서는 이를 바꿨습니다.

- **🧼 말랑말랑 번역:** 상처 주는 평가를 되풀이하지 않고, 실제 상황·요청·확인 사항만 편안하게 전달
- **🔎 유효한 비판:** 객관적 정보, 아직 검증되지 않은 주장, 필요한 추가 정보와 다음 행동을 구분. 구체적인 근거가 없으면 **"현재 반영할 피드백 없음"**
- **🧠 본심 추측:** 실제 마음을 안다고 주장하지 않는, 선택적인 유쾌한 해석
- **✉️ 답장 순화:** 내가 화가 나서 쓴 메일도 입장을 유지하면서 업무적으로 작성

메일, 사내 메신저, 고객 문의, 커뮤니티 댓글, 코드 리뷰 등 **어떤 채널의 글이든 복사해 붙여넣는 방식**으로 사용합니다. 외부 서비스와 자동 연동되지는 않습니다.

### 에이전트에게 설치 부탁하기

```text
https://github.com/roseline124/good-to-talk 의 Good To Talk 스킬을 설치해줘.
SKILL.md를 읽고 가능한 정식 설치 방법으로 등록해줘.
설치를 지원하지 않으면 이 대화에만 적용하고 실제 설치 여부를 정확히 말해줘.
메일 계정 연결이나 자동 전송은 하지 마.
```

설치 후: **"Good To Talk로 이 메일 번역해줘. 유효한 비판도 알려줘."**

## Compatibility & limitations

- Format: [Agent Skills](https://agentskills.io/) with YAML-frontmatter `SKILL.md`.
- The model may make mistakes when assessing whether feedback is substantiated; review technically important material and the original when needed.
- Mental protection is a design goal, not a guarantee that no result will ever feel hurtful.
- This is not a psychological diagnosis, automated email filter, email proxy, or background monitoring service.
- License: [MIT](./LICENSE). Issues and pull requests are welcome.

---

**Keywords:** AI agent skill, emotional safety, toxic message filter, professional communication, workplace communication, customer service, business email, actionable feedback, valid criticism, tone rewriter, passive-aggressive messages, constructive feedback, Korean AI skill, 독성 말투 번역, 멘탈 보호, 업무 메일 순화, 유효한 비판, 본심 추측, 말투 변환.
