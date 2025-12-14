# SCM

Structural Causal Model(SCM) 관점에서 인과 추론을 model → identify → estimate → (refute) 파이프라인 구조로 공식화하여 접근합니다.
이를 바탕으로 주요 식별 전략과 데이터 기반 causal discovery를 다룹니다.


- **Backdoor Criterion**:

  원인($X$)과 결과($Y$) 모두에 영향을 미치는 backdoor path를 차단하여 인과효과를 식별합니다.

$$
P(Y \mid do(X)) = \sum_Z P(Y \mid X, Z) P(Z)
$$


- **Frontdoor Criterion**:

  원인($X$)이 결과($Y$)에 미치는 효과가 매개변수($M$)을 통해서만 전달될 때, 다음 식을 통해 인과효과를 간접적으로 식별합니다.

$$
P(Y \mid do(X)) = \sum_M P(M \mid X) \sum_{X'} P(Y \mid M, X') P(X')
$$


- **Instrument Variable (IV)**:
  
  원인($X$)과 결과($Y$) 간의 내생성 문제를 해결하기 위해,
  ($X$)에는 영향을 주지만 ($Y$) 에는 직접 영향을 미치지 않는 도구변수($Z$)를 사용합니다.  


- **Causal Discovery**:
  
  score-based, constraint-based, function-based 등 탐색 알고리즘과 도메인 지식을 활용해 데이터로부터 인과 구조(DAG)를 도출합니다.
