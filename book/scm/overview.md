# SCM
관찰 데이터를 활용해 ground truth 수준의 인과 메커니즘을 추론하기 위해 SCM(Structural Causal Model)을 사용할 수 있습니다.

SCM을 통한 인과추론 과정은 다음과 같이 요약됩니다:

1. **Model**: 변수들 사이의 인과적 관계를 DAG로 정의하고, 혼란변수(confounder), 매개변수(mediator), 충돌변수(collider) 등을 구분합니다.
2. **Identify**: 관심 있는 인과효과가 그래프에서 식별 가능한지 검토하고, Back-door, Front-door, 도구변수(IV)와 같은 식별 전략을 탐색합니다.
3. **Estimate**: 식별 전략에 적합한 통계적 방법으로 인과효과를 추정합니다.
4. **Refute**: 위약(placebo) 분석, 무작위 교란(Randomization Test) 등을 통해 추정된 인과효과의 강건성을 검증합니다.