# SIMSA-FIX-BRIEF

이 파일은 Simsa 시각 검수가 생성한 수리 지시서입니다.
이 브랜치에서 아래 지시서를 그대로 실행한 뒤, 이 파일은 삭제해도 됩니다.

---

당신은 이 프로젝트의 코드를 수정하는 개발 에이전트입니다.
아래는 Simsa가 실제 브라우저로 이 앱을 열어 관찰한 사실입니다. 여기 적힌 증거만 근거로 진단하고 수정하세요.
증거에 없는 문제를 추측으로 만들어내지 마세요.

[대상]
- URL: https://applywalmart-v2.vercel.app/
- 검수한 사용자 플로우: 지원자가 월마트 지원 절차를 시작하고 진행할 수 있어야 한다
- 판정: Needs Clarification (무엇을 확인해야 할지 애매해요)

[브라우저 관찰 사실]
- 첫 화면 HTTP 상태: 200
- 핵심 동작 요소(버튼/입력) 발견: 예
- 실제 상호작용(클릭/입력) 수행: 아니오
- 상호작용 후 주소: 없음 (주소 변경: 아니오)
- 네트워크 실패: 없음
- 콘솔 오류: 없음
- 플로우 단계 결과:
  - 핵심 버튼 'Get Free Eligibility Check · 3 minutes' 누르기: 실패 — 동작 실패: TimeoutError: locator.click: Timeout 8000ms exceeded.
Call log:
  - waiting for getByText('Get Free 
  - 버튼을 누른 뒤 화면 확인: 성공

[고칠 문제 — 우선순위순]
1. [중간] '핵심 버튼 'Get Free Eligibility Check · 3 minutes' 누르기' 단계가 끝까지 되지 않았어요.
   - 원인 설명: 이유: 동작 실패: TimeoutError: locator.click: Timeout 8000ms exceeded.
Call log:
  - waiting for getByText('Get Free 
   - 수정 방향: 그 단계에서 무엇이 나와야 하는지 정하고, 눌렀을 때 그 결과가 실제로 뜨는지 확인하세요.
   - 증거: 동작 실패: TimeoutError: locator.click: Timeout 8000ms exceeded.
Call log:
  - waiting for getByText('Get Free 

[작업 규칙]
- 재현 먼저: 앱을 로컬에서 실행해 위 플로우를 그대로 밟아 같은 실패를 확인한 뒤 수정하세요.
- 최소 수정: 증거가 가리키는 원인만 고치고, 무관한 리팩터링은 하지 마세요.
- 비밀값 금지: API 키·백엔드 주소 같은 환경값을 코드에 하드코딩하지 마세요.
- 검증: 수정 후 같은 플로우에서 네트워크 실패 0건, 콘솔 오류 0건인지 확인하세요.
- 보고: 무엇을/왜/어떻게 바꿨는지와 검증 결과를 5줄 이내로 보고하세요.
