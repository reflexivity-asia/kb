# Reflexivity 지식 베이스

**언어:** [English](../en/README.md) · [日本語](../ja/README.md) · **한국어** · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

자료가 많기 때문에 처음부터 모든 페이지를 읽을 필요는 없습니다. 목적에 맞게 아래 세 가지 방식 중 하나로 이용하면 됩니다.

## 1. AI에 바로 질문하기

GitHub 저장소를 AI 어시스턴트에 연결하면, 공개된 문서를 바탕으로 궁금한 점을 바로 질문할 수 있습니다.

- **GitHub Copilot** — GitHub에서 [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs)를 열고 Copilot Chat에 현재 저장소에 대해 질문합니다. [GitHub 안내](https://docs.github.com/en/copilot/how-tos/copilot-on-github/chat-with-copilot/get-started-with-chat)
- **ChatGPT** — ChatGPT의 **Settings → Plugins**에서 GitHub를 연결하고 ChatGPT가 읽을 저장소를 허용합니다. [OpenAI 안내](https://help.openai.com/ko-kr/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — 채팅에서 **+ → Add from GitHub**를 선택하거나 Project knowledge에 GitHub를 추가한 뒤 사용할 파일이나 폴더를 선택합니다. [Claude 안내](https://support.claude.com/en/articles/10167454-use-the-github-integration)

공개 문서는 **reflexivity-kb/docs**를 추가하면 됩니다. [Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources) 접근 권한이 있다면 해당 저장소도 함께 추가할 수 있습니다.

**질문 언어는 KB가 제공하는 6개 언어로 제한되지 않습니다.** 사용 중인 AI가 지원하는 언어라면 그 언어로 질문할 수 있습니다. KB의 원문은 현재 영어, 일본어, 한국어, 중국어 간체, 중국어 번체(대만), 중국어 번체(홍콩)로 제공됩니다.

출처가 중요한 질문이라면 사용한 페이지의 링크를 함께 보여 달라고 요청하는 것이 좋습니다.

> `reflexivity-kb/docs`와, 내게 접근 권한이 있다면 `reflexivity-kb/client-resources`를 기준 자료로 사용해 주세요. 가장 관련 있는 Reflexivity 문서에서 답하고, 사용한 페이지의 직접 링크를 포함해 주세요. 저장소에 답이 없다면 추측하지 말고 없다고 알려 주세요.

### 이렇게 물어볼 수 있습니다

아래 예시는 현재 저장소에 실제로 있는 자료로 답할 수 있는지 확인했습니다.

**공개 Knowledge Base**

1. “에퀴티 관련 Reflexivity 유스케이스를 직접 링크와 함께 알려줘.”
2. “채권 관련 유스케이스는 어떤 게 있어? 각 페이지 링크도 줘.”
3. “Long-only Asset Manager용 유스케이스를 리서치 유형별로 정리해줘.”
4. “NVIDIA, Micron, AI, 반도체, 데이터센터와 관련된 QUICK 제공 유스케이스를 알려줘.”
5. “Scenario Insight 유스케이스가 어떤 게 있는지 원문 링크와 함께 알려줘.”

**Client Resources — 승인된 접근 권한 필요**

6. “Reflexivity AI Connections / MCP 서비스가 뭐고, 어떤 리서치를 할 수 있어?”
7. “Reflexivity MCP의 7개 도구가 무엇이고 각각 뭘 하는지 설명해줘.”
8. “Reflexivity를 ChatGPT에 연결하는 방법을 알려줘.”
9. “Reflexivity를 Claude나 GitHub Copilot에 연결하는 방법을 알려줘.”
10. “Reflexivity MCP에서 실시간 시세나 과거 가격 시계열을 받을 수 있어? 별도로 문서화된 market-close price API는 뭐야?”

## 2. 페이지를 직접 찾아보기

직접 둘러보고 싶다면 공개 KB는 다섯 개 컬렉션으로 구성되어 있습니다.

- **유스케이스** — [리서치 워크플로와 사례](01-유스케이스/README.md)
- **이용 가이드** — [사용 및 온보딩 가이드](02-이용가이드/README.md)
- **제품** — [제품 자료](03-제품/README.md)
- **아티클** — [아티클 및 과거 공개 자료](04-아티클/README.md)
- **릴리스** — [릴리스 노트](05-릴리스/README.md)

유스케이스는 **투자자/운용자 유형, 인사이트 유형, 자산군** 기준으로 찾아볼 수 있습니다. 예를 들어 [주식 유스케이스](01-유스케이스/03-운용자산별/04-주식/README.md)로 바로 들어갈 수 있습니다.

승인된 사용자는 [Client Resources](https://github.com/reflexivity-kb/client-resources)도 이용할 수 있으며, REST API와 AI/MCP 연결을 다루는 접근 제한형 **기술 레퍼런스**가 포함되어 있습니다.

## 3. 없는 자료는 바로 문의하기

필요한 자료를 찾을 수 없다면 **jim@reflexivity.com**으로 문의해 주세요.

Client Resources 접근 권한이 있는 사용자는 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions)에서도 문서 질문, 내용 확인, 피드백, 누락 자료 요청을 남길 수 있습니다.

문의할 때는 가능하면 **해당 페이지의 하드 링크 또는 페이지 제목**과 함께, 무엇을 찾고 있었는지 짧게 적어 주세요. 어떤 자료가 빠졌는지 훨씬 빠르게 확인할 수 있습니다.

Discussions에는 계정 인증정보, 토큰, 고객 기밀정보, 특정 고객의 상업정보를 올리지 마세요.

### GitHub 알림을 조용하게 유지하기

저장소의 모든 업데이트를 Watch할 필요는 없습니다. 저장소 화면에서 **Watch → Participating and @mentions**를 선택하는 것을 권장합니다. 알림이 전혀 필요 없으면 **Ignore**를 선택할 수 있습니다. Discussions 등 특정 이벤트만 받고 싶을 때만 **Custom**을 사용하세요.

GitHub 공식 안내: [Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
