# Good To Talk v2 — Examples / 사용 예시

These are fictional examples for testing the behavior described in [SKILL.md](../SKILL.md).

**Mental protection is not denial:** actionable criticism must still be preserved. This skill filters needless insults but must not fabricate reassurance, prove an unverified accusation, or remove real technical risks. Possible inner thoughts are **hypotheses, not mind-reading**.

## 1. Mockery with no actionable feedback / 근거 없는 조롱

**Input**

> 이딴 것도 오픈소스라고 만듦? ㅋㅋ

**🧼 말랑말랑 번역**

> 이번 메시지에는 구체적인 수정 사항이나 개선 요청이 없어요. 지금 바로 처리할 작업은 없습니다. 📭

**🔎 유효한 비판**

> 구체적인 근거 또는 개선 요청이 없어, 현재 반영할 피드백은 없습니다.

**🧠 유쾌한 의역 (가설)**

> “버그 리포트는 도착했는데 재현 방법이 비어 있네요. 🐛”

**Anti-pattern:** Do **not** reply “오픈소스로 공개하기에는 부족하다” or “완성도가 낮다.” Neither claim is established.

## 2. Vague usability complaint / 사용하기 어렵다는 막연한 불만

**Input**

> 하... 이 코드 못 쓰겠네.

**🧼 말랑말랑 번역**

> 사용 중 막힌 부분이 있었나 봐요. 어떤 환경에서 무엇이 작동하지 않았는지 확인되면 다음 단계를 정할 수 있어요. 🧩

**🔎 유효한 비판**

- **확인된 정보:** 문제 발생 상황이나 원인은 아직 제공되지 않았습니다.
- **제기된 문제:** 사용하기 어렵다는 보고가 있습니다.
- **다음 행동:** 실행 환경, 오류 메시지, 재현 절차 요청.

**Anti-pattern:** Do **not** call the code “unusable” as verified fact.

## 3. Concrete performance issue / 실제 문제 단서가 있는 기술 지적

**Input**

> 인덱스도 안 걸어놓고 운영 올렸어요? 조회 4초씩 걸리는데 기본도 안 되어 있네요.

**🧼 말랑말랑 번역**

> 조회 시간이 4초라는 보고가 있어요. 인덱스 설정과 쿼리 실행 계획을 확인하면 원인을 좁힐 수 있겠습니다.

**🔎 유효한 비판**

- **확인된 정보:** 메시지에 4초 조회 시간 보고가 포함됩니다. 아직 독립적으로 검증되지는 않았습니다.
- **제기된 문제:** 조회 지연 및 인덱스 누락 가능성.
- **다음 행동:** 느린 쿼리 재현, 실행 계획 및 인덱스 점검, 측정 조건 확인.

**Anti-pattern:** Do **not** erase the 4-second metric or assume missing indexes are the confirmed cause.

## 4. Design criticism + legitimate question / 단정적 설계 비판과 확인 요청

**Input**

> 확장성이 전혀 고려되지 않은 상태로 보입니다. 설계 단계에서 어떻게 고려되었는지 확인 부탁드립니다.

**🧼 말랑말랑 번역**

> 향후 확장 시 변경 범위를 확인하고 싶다는 요청이에요. 설계 당시 고려된 요구사항이나 제약조건을 공유해 주시면 검토에 도움이 되겠습니다.

**🔎 유효한 비판**

- **확인된 정보:** 설계 의사결정에 대한 문의가 있습니다.
- **제기된 문제:** 확장 시 수정 범위에 대한 우려가 표현됐지만, 구체적인 실패 시나리오나 근거는 없습니다.
- **다음 행동:** 관련 설계 기록 확인 및 우려되는 확장 시나리오 요청.

**🧠 본심 추측 (가설)**

> “나중에 고칠 곳이 많아질지 걱정될 수 있겠어요. 설계 의도를 먼저 알고 싶은 걸지도요.”

## 5. Urgent production issue / 심각한 장애는 축소하지 않기

**Input**

> 지금 결제 API 500 터지고 주문 실패 중인데 대체 뭐 하셨어요? 당장 롤백하세요.

**🧼 말랑말랑 번역**

> 결제 API에서 HTTP 500 오류와 주문 실패가 발생 중이라는 긴급 보고예요. 즉시 장애 상황을 확인하고 롤백 필요 여부를 판단해야 합니다.

**🔎 유효한 비판**

- **확인된 정보:** 발신자가 결제 API 500 오류와 주문 실패를 보고했습니다. 장애 범위는 검증이 필요합니다.
- **제기된 문제/요청:** 결제 오류, 주문 실패, 즉시 롤백 요청.
- **다음 행동:** 장애 현황 및 배포 변경점 확인, 롤백의 위험과 효과 검토, 온콜/사고 대응 착수.

**Anti-pattern:** Do not use cheerful emojis or say there is nothing to do. Keep the urgency and the sender's rollback request visible, while not presuming rollback is always safe.

## 6. Angry outgoing reply / 발신 메일 순화

**Input**

> [보낼 글] 아니 요구사항을 매번 바꾸면 우리가 무슨 수로 맞춰요? 말이 되는 소리를 하세요.

**✉️ 보내기 좋은 답장**

> 요청사항 변경으로 인해 개발 범위와 일정에 영향이 발생하고 있습니다. 변경된 요구사항과 우선순위를 확정해 주시면 영향도를 검토하고 가능한 일정을 안내드리겠습니다.

**🔎 유지한 핵심:** 잦은 요구사항 변경이 일정에 영향을 주므로 변경 범위와 우선순위 확정이 필요함.

## 7. Neutral message / 이미 충분히 업무적인 문장

**Input**

> 기존 DB 스키마 변경 시 주문 조회 API에 영향이 있을 수 있습니다. 테스트가 필요합니다.

**🧼 말랑말랑 번역**

> DB 스키마 변경이 주문 조회 API에 영향을 줄 수 있어요. 변경 전후 테스트가 필요합니다.

**🔎 유효한 비판**

- **제기된 문제/요청:** 주문 조회 API 영향 가능성, 테스트 필요.
- **다음 행동:** 관련 API 회귀 테스트 수행.

No added criticism or invented toxic intent.

## 8. English PR insult / English code review

**Input**

> Did you even test this? Nobody writes production code like this.

**🧼 Gentle translation**

> A question was raised about whether this change was tested. It would help to share the test coverage and expected production behavior.

**🔎 Valid criticism**

- **Known:** The reviewer asks about testing; no failed test or production bug is demonstrated.
- **Claim:** Possible concern about test coverage.
- **Next step:** Share the test cases or ask which production scenario is concerning.

**Anti-pattern:** Do not assert that this code is not production-ready.

## Try it

```text
Good To Talk로 번역해줘.
1) 상처 주는 표현을 반복하지 않는 말랑말랑 번역
2) 확인된 사실 / 제기된 문제 / 다음 행동을 구분한 유효한 비판
3) 가능하면 유쾌한 본심 추측 (단정하지 말 것)

[여기에 업무 메일 또는 PR 코멘트 붙여넣기]
```
