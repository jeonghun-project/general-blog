---
title: "NVIDIA의 새로운 무기, Skip Softmax: LLM 추론 속도 1.4배 향상"
description: "NVIDIA가 텐서RT-LLM에 'Skip Softmax' 기술을 탑재했습니다. 불필요한 어텐션 연산을 건너뛰어 정확도 저하 없이 속도를 1.4배 높이는 원리를 분석합니다."
date: "2025-12-17"
tags: ["AI", "NVIDIA", "TensorRT", "Inference"]
author: "Antigravity"
featured_image: "https://raw.githubusercontent.com/jeonghun-project/general-blog/main/assets/images/2025-12-17-nvidia의-새로운-무기-skip-softmax-llm-추론-속도-14배-향상.png"
---

# NVIDIA의 새로운 무기, Skip Softmax: LLM 추론 속도 1.4배 향상

거대언어모델(LLM)을 서비스하는 기업들의 최대 고민은 바로 '추론 비용'입니다. NVIDIA가 이 고민을 덜어줄 새로운 기술, **Skip Softmax**를 TensorRT-LLM에 탑재했습니다. 

핵심은 간단합니다. "중요하지 않은 정보는 계산하지 않고 건너뛴다(Skip)"는 것입니다.

## LLM 비용 절감의 핵심, 추론 효율성

LLM이 긴 텍스트(Long Context)를 처리할 때, 연산량은 기하급수적으로 늘어납니다. 특히 Softmax 연산은 메모리 대역폭을 많이 잡아먹는 주범 중 하나죠. 

NVIDIA는 이를 최적화하기 위해 하드웨어, 특히 **Hopper(H100)**와 차세대 **Blackwell** 아키텍처에 특화된 기법을 내놓았습니다.

## Skip Softmax란 무엇인가?

**Skip Softmax**는 **Sparse Attention(희소 어텐션)**의 일종입니다. 
LLM이 다음에 올 단어를 예측할 때, 문맥 전체를 다 볼 필요는 없습니다. Softmax 함수의 수학적 특성을 이용하면, 결과값에 거의 영향을 주지 않는(즉, 확률이 매우 낮은) 블록들은 미리 파악해서 계산을 아예 생략(Pruning)할 수 있습니다.

<!-- visual:section_02_infographic -->

재학습(Retraining) 없이 기존 모델에 바로 적용할 수 있는 **Drop-in** 방식이라는 점이 가장 큰 매력입니다.

## Llama 3.3 70B 모델 성능 테스트 결과

실제 성능은 어떨까요? NVIDIA의 테스트 결과 놀라운 수치가 나왔습니다.

*   **모델**: Llama 3.3 70B
*   **컨텍스트 길이**: 128K
*   **성능 향상**:
    *   Prefill 단계: **1.4배** 속도 향상
    *   Decoding 단계: **1.36배** 속도 향상

<!-- visual:section_03_chart -->

가장 중요한 '정확도' 문제도 잡았습니다. 벤치마크 결과, 연산의 **50%를 생략(Sparsity 50%)**하더라도 정확도 손실은 거의 없었습니다(Near-lossless). 단, 60%를 넘어가면 성능 저하가 발생하므로 적절한 튜닝이 필요합니다.

## Hopper와 Blackwell 아키텍처 최적화

이 기술은 NVIDIA의 최신 GPU 아키텍처인 Hopper와 Blackwell에서 최고의 성능을 냅니다. TensorRT-LLM을 사용하고 있다면, API 설정을 통해 이 기능을 활성화하는 것만으로 추론 서버의 처리량(Throughput)을 크게 높일 수 있을 것으로 기대됩니다.

---

*출처: NVIDIA Developer Blog, Blockchain.News*