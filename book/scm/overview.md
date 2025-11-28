# SCM

SCM(Structural Causal Model)은 변수 간의 causal mechanism을 구조방정식과 DAG로 표현하는 접근입니다.  
이 섹션에서는 주요 식별 전략을 중심으로, 실제 데이터를 활용한 인과효과 분석을 다룹니다.


- **Backdoor Criterion**:

  원인과 결과 모두에 영향을 미치는 교란변수(confounder) 를 통제하여, 인과효과를 다음과 같이 식별합니다.

$$
P(Y \mid do(X)) = \sum_Z P(Y \mid X, Z) P(Z)
$$


- **Frontdoor Criterion**:

  원인($X$)이 결과($Y$)에 미치는 효과가 매개변수($M$)을 통해서만 전달될 때, 다음 식을 통해 인과효과를 간접적으로 식별합니다.

$$
P(Y \mid do(X)) = \sum_M P(M \mid X) \sum_{X'} P(Y \mid M, X') P(X')
$$


- **Instrument Variable (IV)**:
  
  ($X$)와 ($Y$) 간의 내생성(endogeneity) 문제를 해결하기 위해,
  ($X$)에는 영향을 주지만 ($Y$) 에는 직접 영향을 미치지 않는 도구변수($Z$)를 사용합니다.  
  인과효과는 다음과 같이 식별됩니다.

$$
\hat{\beta}_{IV} = \frac{Cov(Z, Y)}{Cov(Z, X)}
$$

- **Causal Discovery**:
  
  score-based, constraint-based, function-based 등 탐색 알고리즘과 도메인 지식을 활용해 데이터로부터 인과 구조(DAG)를 도출합니다.
