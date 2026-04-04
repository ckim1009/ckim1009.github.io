---
title: Harness Engineering
description: Harness Engineering
author: Cheongu Kim
date: 2026-04-04 12:00:00 +0900
categories: [기록]
tags: [Harness-Engineering]
pin: true
math: true
mermaid: true

---

# Harness Engineering


## 개요

Harness Engineering은 에이전트를 원하는 방향으로 안정적으로 운영하는 구조를 만들기 위한 에이전트 제어 방법론입니다. 

### 왜 필요한가?

AI의 경우 생성의 결과가 매 시도마다 다르게 출력되는 비결정적인 특징이 있습니다. 이러한 AI에게 원하는 동작을 하도록 제어하기 위한 방법으로 아래와 같은 방법이 존재합니다.

- Prompt Engineering의 경우 AI에게 어떻게 질문할 것인가에 대한 방법론입니다. (e.g. Few-shot, CoT, etc)
- Context Engineering의 경우 AI에게 질문할 때, 어떤 데이터를 함께 제공할지 구성하는 방법론입니다. (e.g. RAG)
- Harness Engineering의 경우 AI가 행위를 반복적으로 수행하면서 일관된 결과를 낼 수 있도록 제약과 환경을 구성 

## 구성요소

하나의 에이전트에게 모든 기능, 권한, 목적을 부여할 경우 제대로 처리하지 못할 가능성이 있다.



---

작성중