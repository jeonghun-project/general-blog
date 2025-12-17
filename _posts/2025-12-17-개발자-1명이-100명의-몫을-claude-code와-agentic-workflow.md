---
title: "개발자 1명이 100명의 몫을? Claude Code와 Agentic Workflow"
description: "'커서맛피아' 최수민님이 공개한 1인 개발 혁명. Claude Code와 서브 에이전트를 활용해 100개의 에이전트를 동시에 굴리는 미친 생산성의 비밀을 파해칩니다."
date: "2025-12-17"
tags: ["AI", "Coding", "Claude Code", "Agentic Workflow"]
author: "Antigravity"
featured_image: "https://raw.githubusercontent.com/jeonghun-project/general-blog/main/assets/images/2025-12-17-개발자-1명이-100명의-몫을-claude-code와-agentic-workflow.png"
---

# 개발자 1명이 100명의 몫을? Claude Code와 Agentic Workflow

"이게 진짜 된다고?"

최근 공개된 유튜브 영상 하나가 개발자 커뮤니티를 강타했습니다. 일명 **'커서맛피아'**로 불리는 최수민님이 보여준 **AI 에이전트 관리 방법** 때문입니다. 그는 혼자서 100개에 달하는 서브 에이전트(Sub-Agents)를 동시에 지휘하며, 상상 초월의 생산성을 보여주었습니다.

## 개발자가 경악한 AI 에이전트 관리법

우리는 흔히 Cursor나 Copilot을 '코딩 비서' 정도로 생각합니다. 코드를 추천해주면 탭(Tab) 키를 눌러 받아들이는 수준이죠. 하지만 최수민님의 접근은 차원이 다릅니다.

그는 AI를 비서가 아닌 **'직원'**처럼 부립니다. 그것도 한 명이 아니라 100명을 동시에 말이죠.

## Claude Code와 Context Engineering

이 마법의 중심에는 **Claude Code**가 있습니다. Anthropic의 Claude 모델은 긴 컨텍스트(Context)를 처리하는 능력이 탁월합니다. 최수민님은 이를 활용해 **Context Engineering**이라는 개념을 도입했습니다.

단순한 프롬프트 엔지니어링이 아닙니다. 에이전트에게 "너는 프론트엔드 전문가야", "너는 데이터 엔지니어야"와 같이 구체적인 **맥락(Context)과 역할(Persona)**을 부여하고, 이들이 서로 소통하며 작업을 완수하도록 판을 짜는 것입니다.

## Monet 프로젝트: 웹 스크래핑 파이프라인

영상에서 시연된 오픈소스 프로젝트 **'Monet'**은 이 개념의 결정체입니다.

<!-- visual:section_03_code_snippet -->

Monet은 웹페이지 URL 하나만 던져주면, 수많은 에이전트들이 달려들어 페이지를 분석하고, 스크래핑하고, 컴포넌트 단위로 코드를 분해해줍니다. 과거였다면 개발자 팀이 붙어서 며칠은 걸렸을 작업을, AI 군단이 순식간에 해치우는 장면은 전율을 일으킵니다.

## 1인 개발의 미래: Agentic Workflow

이제 개발자의 역할이 바뀌고 있습니다. 직접 코드를 한 줄 한 줄 짜는 'Corder'에서, AI 에이전트들을 지휘하고 관리하는 **'Manager'** 혹은 **'Architect'**로 진화해야 합니다.

**Agentic Workflow(행동형 워크플로우)**는 선택이 아닌 필수입니다. 혼자서 유니콘 기업을 만들 수 있는 시대, 그 열쇠는 바로 AI 에이전트 오케스트레이션에 있습니다.

---

*참고: Monet 서비스 (https://www.monet.design/), Claude Code agent/skills (https://github.com/greatSumini/cc-system)*