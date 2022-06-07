# Chi Square Test
---
> 이전 T-Test는 T Distribution을 가정으로 통계량을 계산했었다.  
> Chi Square Test는, 역시 Chi Square Distribution을 가정으로 통계량을 계산하는 방식이다.  

## Chi Square Distribution
- DF = 자유도 일 때
  - Mean = DF 이고, STD(표준편차) = sqrt(2(DF)) 인 분포를 의미한다.
  - DF = k의 Chi^2 Distribution은, K개의 독립 Normal Variables들의 제곱의 합을 의미한다.
- 분포가 Nonsymmetrical하고, 오른쪽으로 약간 Skewed 된다.
- DF에 따라서 분포의 형태가 바뀐다.
  - DF > 90 의 경우에는, 거의 정규분포에 근사한다.
- Chi^2 통계량은 항상 0보다 크거나 같다.
- Mean은 항상 Peak 지점의 약간 오른쪽에 위치한다.

### 3 Major Application with Chi^2
1. Goodness of Fit Test (적합성 검정)
  - Data가 어떤 특정한 Distribution을 따르는 지 검사한다.
2. Test of Independence
  - 두 사건들이 서로 독립인지 검사한다.
3. Test of a Homogeneity (동질성 검정)
  - 두 모집단이 같은 Distribution을 따르는지 검사한다.

### Goodness of Fit Test
- 어떤 Data가 특정 Distribution에 Fit(적합) 한지 아닌지 검사한다!
- Example : Employees' Absent
  - 모든 고용인들이 주에 같은 날만큼 결근을 한다는 가설이 맞는지 검정해보자.  
  ![image](https://user-images.githubusercontent.com/71700079/172381082-123c04a1-89f6-4e9f-9baa-00f4fe0048ad.png)  
  - 과연 두 분포는 같은 분포인가? 0.05의 유의수준으로 Test를 진행해보자.  
  ![image](https://user-images.githubusercontent.com/71700079/172381358-e14857de-c6c0-4aef-bcc4-b7aca6fc43b6.png)  
  
  - 계산의 결과는 3.0 이라는 통계랑을 보인다.
  - 그럼 DF = 4인 Chi^2 Distribution에 대해서, p-Value는 어떻게 되는가?   
  ![image](https://user-images.githubusercontent.com/71700079/172382519-88af1a7e-ef24-4876-87ed-eb8bcb853eb0.png)  
    - 위 표에 의하면, p-Value가 유의수준보다 훨씬 크다. 따라서 우리는 귀무 가설을 Reject 할 수 없다! (증거 불충분)  

- 위 Test에는 몇가지 Condition이 필요하다.
  1. Data는 Random하게 모집단에서 뽑아온 Data이거나, Randomized Experiment에서 추출된 Data여야 한다.
  2. 비복원 추출의 경우엔, Sample size가 전체 모집단의 10% 미만이어야 Sample의 독립성을 보장할 수 있다.
  3. Expected Value의 갯수는 최소 5개보다는 많아야 한다.
