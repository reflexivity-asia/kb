# Reflexivity 지식 베이스

**언어:** [English](../en/README.md) · [日本語](../ja/README.md) · **한국어** · [简体中文](../zh-cn/README.md) · [繁體中文（台灣）](../zh-tw/README.md) · [繁體中文（香港）](../zh-hk/README.md)

자료가 많기 때문에 처음부터 모든 페이지를 읽을 필요는 없습니다. 목적에 맞게 아래 세 가지 방식 중 하나로 이용하면 됩니다.

## 1. Reflexivity를 AI에 연결하기

Reflexivity는 **MCP**를 통해 지원되는 AI 애플리케이션에 직접 연결할 수 있습니다. 연결하면 대화 안에서 Reflexivity의 **Insights**와 **Knowledge Graph** 기능을 사용할 수 있습니다.

이 기능은 AI에게 이 GitHub 문서 저장소를 읽게 하는 것과는 별개입니다.

[Reflexivity Client Resources](https://github.com/reflexivity-kb/client-resources) 접근 권한이 있다면 애플리케이션별 연결 가이드를 이용해 주세요.

- **ChatGPT** — [Reflexivity를 ChatGPT에 연결하기](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/03-ChatGPT/README.md)
- **Claude** — [Reflexivity를 Claude에 연결하기](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/01-Claude/README.md)
- **GitHub Copilot** — [Reflexivity를 GitHub Copilot in VS Code에 연결하기](https://github.com/reflexivity-kb/client-resources/blob/main/ko/01-기술-레퍼런스/11-AI-연결/02-애플리케이션-가이드/07-GitHub-Copilot-in-VS-Code/README.md)

사용 가능 여부와 검증 상태는 애플리케이션이나 워크스페이스에 따라 다를 수 있습니다. 설정 후에는 로그인 성공 여부만 보지 말고 실제로 Reflexivity 도구 호출이 되는지 확인해 주세요.

**질문 언어에는 제한이 없습니다.** 사용 중인 AI 어시스턴트가 지원하는 언어로 질문하면 됩니다. Reflexivity 도구의 언어 지정은 지원되는 도구에서 best-effort로 적용되며, 번역본이 없는 콘텐츠는 영어로 반환될 수 있습니다.

### Reflexivity에 이렇게 물어볼 수 있습니다

아래 예시는 현재 Reflexivity MCP 문서에 기재된 기능으로 수행할 수 있는 질문입니다.

1. “NVIDIA의 최근 Earnings Recap과 Earnings Preview를 찾아줘.”
2. “NVIDIA 관련 최근 Company Catalyst 리서치를 보여줘.”
3. “NVIDIA와 가장 관련성이 높은 테마를 알려주고 상위 3개의 근거도 설명해줘.”
4. “Artificial Intelligence 테마와 관련된 기업들을 찾아줘.”
5. “Knowledge Graph에서 NVIDIA의 주요 경쟁사를 찾고 관계의 근거도 보여줘.”
6. “이 기업과 관련된 macro/financial theme을 보여주고, 가능한 경우 exposure direction도 알려줘.”
7. “내가 사용할 수 있는 Reflexivity watchlist와 basket을 보여줘.”
8. “이 watchlist 또는 basket 전체에서 최근 리서치를 찾아줘.”
9. “이 기업의 Scenario Insight를 찾아서 가능한 forecast 날짜와 값을 보여줘.”
10. “이 테마와 관련된 기업을 찾은 뒤, 각 기업의 최근 earnings research를 비교해줘.”

MCP 연결은 Reflexivity 리서치와 Knowledge Graph를 사용하기 위한 것입니다. 일반적인 실시간 시세나 과거 가격 시계열을 조회하는 연결은 아닙니다.

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
