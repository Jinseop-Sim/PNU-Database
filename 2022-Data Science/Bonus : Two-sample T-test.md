# Two Sample T-test
---
> 앞서 통계적 추론을 배울 때는 One Sample T-test를 진행해서 가설을 검정했었다.  
> 모집단의 Mean과 추출한 Sample의 Mean이 얼마나 다른 지를 검사하는 Test였다.  
> 이번에는 2개의 Sample을 통해서 T-test를 진행해본다.  
> 두 개의 Sample이 같은 모집단에서 온 것인지를 알 수 있다.  

## A/B Test
> 두 Sample A와 B는 같은 모집단에서 왔는가?
- Numerical Data : T-test
- Categorical Data : X^2-test(카이제곱)

### Terminology
- Treatment(처치) : 검증이 필요한 새로 만들어낸 무언가. (ex) 신약)
- Treatment Group(실험군, 처리군) : 신약 개발을 했다고 치면, 약을 먹은 집단.
- Control group(대조군) : 약을 먹지 않은 집단.
- Randomization : 피실험자들을 Random하게 실험군 / 대조군에 Assign하는 일
- Subjects : 피실험자 혹은 피실험대상들.
- Test Statistic(검정 통계량) : Treatment의 효과를 측정하는 지표.
  - 1 Sample T-test였다면, T-statistic과 P-value가 될 것이다.
- Examples
  - 두 개의 Web Headlines 중 어느게 더 클릭을 많이 유도하는가?
  - 두 개의 Therapies 중 어느게 더 암을 효과적으로 억제할 수 있는가?

### T-test for 2 Population Means
- 모집단의 표준편차를 아는 경우 : Z-test
- 모집단의 표준편차를 알 수 없는 경우 : T-test

- Assumption
  - 두 Sample이 정규분포를 따른다고 가정한다.
  - 두 독립된 Sample은 두 개별적인 모집단에서 온 Simple Random한 Sample이다.
- Independent Two-sample T-test
  - 같은 Sample size와 Variance ==> T-test
  - 다른 Sample size이거나, 다른 Variance를 가질 때 ==> Welch's T-test
