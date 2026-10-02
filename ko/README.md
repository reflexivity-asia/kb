# Reflexivity 지식 베이스

**언어:** [English](../en/README.md) · [日本語](../ja/README.md) · **한국어** · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

자료가 많기 때문에 처음부터 모든 페이지를 읽을 필요는 없습니다. **이 Knowledge Base 문서를 이용하는 방법**은 크게 세 가지입니다.

1. AI에게 이 문서에 대해 질문하기
2. 페이지를 직접 찾아보기
3. 없는 자료를 지원팀에 문의하기

> **중요:** 이 Knowledge Base를 AI에게 읽혀 질문하는 것과, **Reflexivity 서비스 자체**를 MCP로 AI 애플리케이션에 연결하는 것은 서로 다른 기능입니다. MCP 연결은 아래의 별도 섹션에서 설명합니다.

## 1. AI에게 이 Knowledge Base에 대해 질문하기

GitHub에 있는 문서를 AI가 참고하게 하면 관련 페이지를 찾거나, 요약·비교하거나, 필요한 링크를 바로 받을 수 있습니다.

- **GitHub Copilot** — [reflexivity-kb/docs](https://github.com/reflexivity-kb/docs)를 열고 현재 저장소에 대해 Copilot에게 질문하거나, 저장소를 Copilot context로 추가합니다. [GitHub 안내](https://docs.github.com/en/copilot/tutorials/explore-a-codebase)
- **ChatGPT** — ChatGPT에서 GitHub를 연결하고 **reflexivity-kb/docs**, 그리고 접근 권한이 있다면 **reflexivity-kb/client-resources**를 허용한 뒤 해당 저장소의 문서에 대해 질문합니다. [OpenAI 안내](https://help.openai.com/ko-kr/articles/11145903-connecting-github-to-chatgpt)
- **Claude** — 채팅의 **Add from GitHub** 또는 Project knowledge의 GitHub 연결에서 필요한 파일이나 폴더를 추가합니다. [Claude 안내](https://support.claude.com/en/articles/10167454-use-the-github-integration)

질문 언어는 사용하는 AI 어시스턴트가 지원하는 언어라면 제한이 없습니다. 문서 원문은 현재 6개 locale로 제공됩니다.

AI에는 다음처럼 지시하면 편리합니다.

> Reflexivity GitHub 문서를 기준 자료로 사용해 주세요. 가장 관련 있는 페이지에서 답하고, 사용한 페이지의 직접 링크를 포함해 주세요. 문서 안에 답이 없다면 추측하지 말고 없다고 알려 주세요.

### 이렇게 물어볼 수 있습니다

아래는 현재 저장소에 실제로 존재하는 자료로 답할 수 있는 **문서 질문** 예시입니다.

1. “에퀴티 관련 Reflexivity 유스케이스를 직접 링크와 함께 알려줘.”
2. “채권 관련 유스케이스는 어떤 게 있어? 각 페이지 링크도 줘.”
3. “Long-only Asset Manager용 유스케이스를 리서치 유형별로 정리해줘.”
4. “NVIDIA, Micron, AI, 반도체, 데이터센터와 관련된 QUICK 제공 유스케이스를 알려줘.”
5. “Scenario Insight 유스케이스가 어떤 게 있는지 원문 링크와 함께 알려줘.”
6. “Reflexivity AI Connections / MCP가 무엇이고 어떤 리서치를 할 수 있다고 문서에 나와 있어?”
7. “Reflexivity 연결 가이드가 있는 AI 애플리케이션은 어떤 것들이야?”
8. “문서에 나온 Reflexivity MCP의 7개 도구와 각각의 역할을 설명해줘.”
9. “ChatGPT 연결 가이드에서는 연결 후 무엇을 확인하라고 되어 있어?”
10. “Reflexivity AI 연결에서 실시간 시세나 과거 가격 시계열을 제공해? 별도로 어떤 Price History 문서가 있어?”

### 별도 기능: AI에서 Reflexivity 서비스 자체 사용하기

ChatGPT, Claude 등 지원되는 AI 애플리케이션에서 **Reflexivity를 직접 호출해 사용**하려면 **Reflexivity MCP**를 연결합니다. 이것은 GitHub 매뉴얼을 AI가 읽게 하는 것과는 별개의 제품 연결입니다.

승인된 사용자는 [Client Resources](https://github.com/reflexivity-kb/client-resources)의 애플리케이션별 연결 가이드를 이용할 수 있습니다.

- [ChatGPT](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/03-ChatGPT/README.md)
- [Claude](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/01-Claude/README.md)
- [GitHub Copilot in VS Code](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/07-GitHub-Copilot-in-VS-Code/README.md)

MCP 연결을 통해 AI 애플리케이션에서 문서화된 Reflexivity Insights와 Knowledge Graph 기능을 사용할 수 있습니다. 일반적인 실시간 시세나 과거 가격 시계열을 조회하는 연결은 아닙니다.

## 2. 페이지를 직접 찾아보기

직접 둘러보고 싶다면 공개 KB는 여섯 개 컬렉션으로 구성되어 있습니다.

1. **Reflexivity란?** — [Reflexivity가 왜 존재하고 리서치 방식을 어떻게 바꾸는지](01-Reflexivity란/README.md)
2. **이용 가이드** — [사용 방법·온보딩·FAQ](02-이용가이드/README.md)
3. **제품** — [제품 자료](03-제품/README.md)
4. **릴리스** — [릴리스 노트](04-릴리스/README.md)
5. **유스케이스** — [리서치 워크플로와 사례](05-유스케이스/README.md)
6. **아티클** — [아티클 및 과거 공개 자료](06-아티클/README.md)

유스케이스는 **투자자/운용자 유형, 인사이트 유형, 자산군** 기준으로 찾아볼 수 있습니다. 예를 들어 [주식 유스케이스](05-유스케이스/03-운용자산별/04-주식/README.md)로 바로 들어갈 수 있습니다.

승인된 사용자는 [Client Resources](https://github.com/reflexivity-kb/client-resources)도 이용할 수 있으며, REST API와 AI/MCP 연결을 다루는 접근 제한형 **기술 레퍼런스**가 포함되어 있습니다.

## 3. 없는 자료는 바로 문의하기

필요한 자료를 찾을 수 없다면 **jim@reflexivity.com**으로 문의해 주세요.

Client Resources 접근 권한이 있는 사용자는 [GitHub Discussions](https://github.com/reflexivity-kb/client-resources/discussions)에서도 문서 질문, 내용 확인, 피드백, 누락 자료 요청을 남길 수 있습니다.

문의할 때는 가능하면 **해당 페이지의 하드 링크 또는 페이지 제목**과 함께, 무엇을 찾고 있었는지 짧게 적어 주세요. 어떤 자료가 빠졌는지 훨씬 빠르게 확인할 수 있습니다.

Discussions에는 계정 인증정보, 토큰, 고객 기밀정보, 특정 고객의 상업정보를 올리지 마세요.

### GitHub 알림을 조용하게 유지하기

저장소의 모든 업데이트를 Watch할 필요는 없습니다. 저장소 화면에서 **Watch → Participating and @mentions**를 선택하는 것을 권장합니다. 알림이 전혀 필요 없으면 **Ignore**를 선택할 수 있습니다. Discussions 등 특정 이벤트만 받고 싶을 때만 **Custom**을 사용하세요.

GitHub 공식 안내: [Configuring notifications](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications)
